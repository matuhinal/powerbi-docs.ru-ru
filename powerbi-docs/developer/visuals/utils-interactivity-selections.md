---
title: Инструменты для взаимодействия визуальных элементов Power BI
description: В статье описывается добавление выделенных элементов в визуальные элементы Power BI с помощью инструментов для взаимодействия
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: be7a708dfcc6ebc40c62a1a9075e2cbf134363b1
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76818693"
---
# <a name="microsoft-power-bi-visuals-interactivity-utils"></a>Инструменты для взаимодействия визуальных элементов Power BI Microsoft

InteractivityUtils — это набор функций и классов, позволяющий упростить реализацию перекрестного выделения и перекрестной фильтрации пользовательских визуальных элементов для Power BI.

## <a name="installation"></a>Установка

> [!NOTE]
> Если вы продолжаете использовать старую версию powerbi-visuals-tools (номер версии ниже чем 3.x.x), установите новую версию средств (3.x.x).

> [!IMPORTANT]
> Обновления средств для взаимодействия визуальных элементов будут поддерживать только последнюю версию средств. [Подробнее о том, как обновить код визуальных элементов с помощью новейших средств](migrate-to-new-tools.md)

Чтобы установить пакет, выполните следующую команду в каталоге с текущим пользовательским визуальным элементом:

```bash
npm install powerbi-visuals-utils-interactivityutils --save
```

В версии 3.0 или более поздней для разрешения зависимостей также необходимо установить ```powerbi-models```.

```bash
npm install powerbi-models --save
```

Для работы со средствами для взаимодействия визуальных элементов следует импортировать необходимый компонент в исходный код визуального элемента.

```typescript
import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";
```

### <a name="including-css-artifacts-to-the-custom-visual"></a>Включение артефактов CSS в пользовательский визуальный элемент

Чтобы использовать пакет с пользовательскими визуальными элементами, необходимо импортировать файл CSS в файл `your.less`:

`node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css`

В результате у вас будет следующая структура файлов:

```less
@import (less) "node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css";
```

> [!NOTE]
> Файл CSS следует импортировать в файл с расширением LESS, так как средства визуальных элементов Power BI создают оболочку для внешних правил CSS.

## <a name="usage"></a>Использование

### <a name="define-interface-for-data-points"></a>Определение интерфейса для точек данных

Обычно точки данных содержат выделения и значения. Интерфейс расширяет интерфейс `SelectableDataPoint`. `SelectableDataPoint` уже содержит свойства:

```typescript
  /** Flag for identifying that data point was selected */
  selected: boolean;
  /** Identity for identifying the selectable data point for selection purposes */
  identity: powerbi.extensibility.ISelectionId;
  /**
   * A specific identity for when data points exist at a finer granularity than
   * selection is performed.  For example, if your data points should select based
   * only on series even if they exist as category/series intersections.
   */
  specificIdentity?: powerbi.extensibility.ISelectionId;
```

Первым шагом в использовании средств для взаимодействия визуальных элементов является создание экземпляра этих средств и сохранение объекта в качестве свойства визуального элемента.

```typescript
export class Visual implements IVisual {
  // ...
  private interactivity: interactivityBaseService.IInteractivityService<VisualDataPoint>;
  // ...
  constructor(options: VisualConstructorOptions) {
      // ...
      this.interactivity = interactivitySelectionService.createInteractivitySelectionService(this.host);
      // ...
  }
}
```

```typescript
import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";

export interface VisualDataPoint extends interactivitySelectionService.SelectableDataPoint {
    value: powerbi.PrimitiveValue;
}
```

Вторым шагом является расширение поведения базового класса:

> [!NOTE]
> BaseBehavior, появившийся в версии [инструментов для взаимодействия 5.6.x](https://www.npmjs.com/package/powerbi-visuals-utils-interactivityutils/v/5.6.0). Если используется старая версия, создайте класс поведения из примера ниже (класс `BaseBehavior`совпадает):

Определите интерфейс для параметров класса поведения:

```typescript
import { SelectableDataPoint } from "./interactivitySelectionService";

import {
    IBehaviorOptions,
    BaseDataPoint
} from "./interactivityBaseService";

export interface BaseBehaviorOptions<SelectableDataPointType extends BaseDataPoint> extends IBehaviorOptions<SelectableDataPointType> {
    /** D3 selection object of main elements on the chart */
    elementsSelection: Selection<any, SelectableDataPoint, any, any>;
    /** D3 selection object of some element on backgroup to hadle click of reset selection */
    clearCatcherSelection: d3.Selection<any, any, any, any>;
}
```

Определите класс для `visual behavior`. Этот класс отвечает за обработку событий мыши `click`, `contextmenu`.
Когда пользователь щелкает элементы данных, визуальный элемент вызывает обработчик выбора для выбора точек данных. Если пользователь щелкает фоновый элемент визуализации, вызывается обработчик снятия выделения. Класс имеет соответствующие методы: `bindClick`, `bindClearCatcher`, `bindContextMenu`.

```typescript
export class Behavior<SelectableDataPointType extends BaseDataPoint> implements IInteractiveBehavior {
    /** D3 selection object of main elements on the chart */
    protected options: BaseBehaviorOptions<SelectableDataPointType>;
    protected selectionHandler: ISelectionHandler;

    protected bindClick() {
      // ...
    }

    protected bindClearCatcher() {
      // ...
    }

    protected bindContextMenu() {
      // ...
    }

    public bindEvents(
        options: BaseBehaviorOptions<SelectableDataPointType>,
        selectionHandler: ISelectionHandler): void {
      // ...
    }

    public renderSelection(hasSelection: boolean): void {
      // ...
    }
}
```

или можно расширить класс `BaseBehavior`:

```typescript
import powerbi from "powerbi-visuals-api";
import { interactivitySelectionService, baseBehavior } from "powerbi-visuals-utils-interactivityutils";

export interface VisualDataPoint extends interactivitySelectionService.SelectableDataPoint {
    value: powerbi.PrimitiveValue;
}

export class Behavior extends baseBehavior.BaseBehavior<VisualDataPoint> {
  // ...
}
```

Для работы с щелчком по элементам вызовите метод выделения D3 `on` (для elementsSelection и clearCatcherSelection тоже):

```typescript
protected bindClick() {
  const {
      elementsSelection
  } = this.options;

  elementsSelection.on("click", (datum) => {
      const mouseEvent: MouseEvent = getEvent() as MouseEvent || window.event as MouseEvent;
      mouseEvent && this.selectionHandler.handleSelection(
          datum,
          mouseEvent.ctrlKey);
  });
}
```

Добавьте аналогичный обработчик для события `contextmenu`, чтобы вызвать метод диспетчера выбора `showContextMenu`:

```typescript
protected bindContextMenu() {
    const {
        elementsSelection
    } = this.options;

    elementsSelection.on("contextmenu", (datum) => {
        const event: MouseEvent = (getEvent() as MouseEvent) || window.event as MouseEvent;
        if (event) {
            this.selectionHandler.handleContextMenu(
                datum,
                {
                    x: event.clientX,
                    y: event.clientY
                });
            event.preventDefault();
        }
    });
}
```

Средства для взаимодействия вызывают методы `bindEvents` для назначения функций обработчикам и добавления вызовов `bindClick`, `bindClearCatcher` и `bindContextMenu` в метод `bindEvents`:

```typescript
  public bindEvents(
      options: BaseBehaviorOptions<SelectableDataPointType>,
      selectionHandler: ISelectionHandler): void {

      this.options = options;
      this.selectionHandler = selectionHandler;

      this.bindClick();
      this.bindClearCatcher();
      this.bindContextMenu();
  }
```

Метод `renderSelection` отвечает за обновление состояния визуальных элементов на диаграмме.

Пример реализации метода `renderSelection`:

```typescript
public renderSelection(hasSelection: boolean): void {
    this.options.elementsSelection.style("opacity", (category: any) => {
        if (category.selected) {
            return 0.5;
        } else {
            return 1;
        }
    });
}
```

Последним шагом является создание экземпляра `visual behavior` и вызов метода `bind` для экземпляра средств взаимодействия.

```typescript
this.interactivity.bind(<BaseBehaviorOptions<VisualDataPoint>>{
    behavior: this.behavior,
    dataPoints: this.categories,
    clearCatcherSelection: select(this.target),
    elementsSelection: selectionMerge
});
```

* `selectionMerge` является объектом выбора D3, который представляет все выбираемые элементы визуализации.

* `select(this.target)` является объектом выбора D3, который представляет основные элементы модели DOM визуализации.

* `this.categories` — это точки данных с элементами, для которых интерфейсом является `VisualDataPoint` (или `categories: VisualDataPoint[];`).

* `this.behavior` новое имя экземпляра `visual behavior`

  создается в конструкторе визуального элемента:

  ```typescript
  export class Visual implements IVisual {
    // ...
    constructor(options: VisualConstructorOptions) {
        // ...
        this.behavior = new Behavior();
    }
    // ...
  }
  ```

Теперь ваш визуальный элемент готов к обработке выбора.

## <a name="next-steps"></a>Дальнейшие действия

* [Как управлять элементами выбора при переключении закладок](bookmarks-support.md#visuals-with-selection)

* [Сведения о добавлении контекстного меню для точек данных визуальных элементов](context-menu.md)

* [Использование диспетчера выбора для добавления элементов выбора в визуальные элементы Power BI](selection-api.md)
