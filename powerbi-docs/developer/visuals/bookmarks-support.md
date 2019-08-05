---
title: Закладки
description: Визуальный элемент Power BI может обрабатывать переключение закладок
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 90e3fc73cd49a5c84a5c2acc68a8cf5e0e4aa42b
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425512"
---
# <a name="add-bookmarks-support-for-power-bi-visuals"></a>Добавление поддержки закладок для визуальных элементов Power BI

Закладки отчета Power BI позволяют зафиксировать настроенное представление страницы отчета, состояние выбора, состояние фильтрации визуального элемента. Однако для поддержки закладок и правильного реагирования на изменения пользовательские визуальные элементы требуют некоторой доработки.

Дополнительные сведения о закладках см. в [документации](https://docs.microsoft.com/power-bi/desktop-bookmarks)

## <a name="report-bookmarks-support-in-your-visual"></a>Поддержка закладок отчетов в визуальном элементе

Если визуальный элемент взаимодействует с другими визуальными элементами, выбирает точки данных или фильтрует другие визуальные элементы, нужно восстановить состояние из свойств.

## <a name="how-to-add-report-bookmarks-support"></a>Добавление поддержки закладок отчета

1. Установите (или обновите) требуемую служебную программу: `powerbi-visuals-utils-interactivityutils`(https://github.com/Microsoft/PowerBI-visuals-utils-interactivityutils/) версии 3.0.0 или более поздней. Она содержит дополнительные классы для работы с фильтрацией или выбором состояния. Она необходима для визуальных элементов с фильтром и всех визуальных элементов, использующих `InteractivityService`.

2. Обновите API визуальных элементов до версии 1.11.0, чтобы использовать `registerOnSelectCallback` в экземпляре `SelectionManager`. Это необходимо для визуальных элементов без фильтра, использующих обычный `SelectionManager`, а не `InteractivityService`.

### <a name="how-custom-visuals-interact-with-power-bi-in-the-report-bookmarks-scenario"></a>Взаимодействие пользовательских визуальных элементов с Power BI в сценарии закладок отчета

Рассмотрим следующий пример: пользователь создает несколько закладок на странице отчета, задав разные состояния выбора на каждой из них.

Сначала пользователь выбирает точку данных в визуальном элементе. Визуальный элемент взаимодействует с Power BI и другими визуальными элементами, передавая выбранные фрагменты на узел. Затем пользователь выбирает "Добавить" в `Bookmark panel`, и Power BI сохраняет текущие выбранные фрагменты для новой закладки.

Это происходит многократно по мере того, как пользователь изменяет выбор и добавляет новые закладки.
После создания пользователь может переключаться между закладками.

Когда пользователь выбирает закладку, Power BI восстанавливает сохраненный фильтр или сохраненное состояние выбора и передает их визуальным элементам. Другие визуальные элементы будут выделены или отфильтрованы в соответствии с состоянием, хранящимся в закладке. Узел Power BI отвечает за выполнение действий. Ваш визуальный элемент отвечает за правильное отражение нового состояния выбора (например, изменение цвета отрисованных точек данных).

Новое состояние выбора передается визуальному элементу через метод `update`. Аргумент `options` будет содержать специальное свойство: `options.jsonFilters`. Это свойство JSONFilter может содержать `Advanced Filter` и `Tuple Filter`.

Визуальный элемент должен восстановить значения фильтра, чтобы отобразить соответствующее состояние визуального элемента для выбранной закладки.

Либо используйте специальный метод `registerOnSelectCallback`объекта ISelectionManager, зарегистрированный в вызове функции обратного вызова, если визуальный элемент использует только выбранные фрагменты.

### <a name="visuals-with-selections"></a>Визуальные элементы с выбранными фрагментами

Если визуальные элементы взаимодействуют с другими визуальными элементами помощью [выбранных фрагментов](https://github.com/Microsoft/PowerBI-visuals/blob/master/Tutorial/Selection.md), добавить закладки можно двумя способами:

* Вы можете использовать метод `FilterManager.restoreSelectionIds`, если раньше **не использовали[ `InteractivityService`](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)** в визуальном элементе.

* Если ваш визуальный элемент уже использует **[`InteractivityService`](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)** для управления выбранными фрагментами, следует использовать метод `applySelectionFromFilter` в экземпляре `InteractivityService`.

#### <a name="using-iselectionmanagerregisteronselectcallback"></a>Использование `ISelectionManager.registerOnSelectCallback`

Когда пользователь щелкает закладки, Power BI вызывает метод `callback` визуального элемента с соответствующими выбранными фрагментами. 

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        //called when a selection was set by Power BI
    });
);
```

Предположим, что у вас есть точка данных в визуальном элементе, созданном в методе [`'visualTransform'`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts#L74).

При этом `datapoints` выглядит следующим образом:

```typescript
visualDataPoints.push({
    category: categorical.categories[0].values[i],
    color: getCategoricalObjectValue<Fill>(categorical.categories[0], i, 'colorSelector', 'fill', defaultColor).solid.color,
    selectionId: host.createSelectionIdBuilder()
        .withCategory(categorical.categories[0], i)
        .createSelectionId(),
    selected: false
});
```

У вас есть `visualDataPoints` в качестве точек данных и массив `ids`, переданный в функцию `callback`.

На этом этапе визуальный элемент должен сравнить массив `ISelectionId[]` с выбранными фрагментами в массиве `visualDataPoints` и отметить соответствующие точки данных как выбранные.

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        visualDataPoints.forEach(dataPoint => {
            ids.forEach(bookmarkSelection => {
                if (bookmarkSelection.equals(dataPoint.selectionId)) {
                    dataPoint.selected = true;
                }
            });
        });
    });
);
```

После обновления точек данных они будут отражать текущее состояние выбора, сохраненное в объекте `filter`. Затем при отрисовке точек данных состояние выбора пользовательского визуального элемента будет соответствовать состоянию закладки.

### <a name="using-interactivityservice-for-control-selections-in-the-visual"></a>Использование `InteractivityService` для управления выбранными фрагментами в визуальном элементе

Если визуальный элемент использует `InteractivityService`, дополнительные действия для обеспечения в нем поддержки закладок не требуются.

Служебная программа будет управлять состоянием выбора визуального элемента при выборе закладки пользователем.

### <a name="visuals-with-filter"></a>Визуальные элементы с фильтром

Предположим, что визуальный элемент создает фильтр данных по диапазону дат. Итак, у нас есть `startDate` и `endDate` в качестве начала и конца диапазона.
Визуальный элемент создает расширенный фильтр и вызывает метод узла `applyJsonFilter` для фильтрации данных по соответствующим условиям.
`target` — это таблица для фильтрации.

```typescript
import { AdvancedFilter } from "powerbi-models";

const filter: IAdvancedFilter = new AdvancedFilter(
    target,
    "And",
    {
        operator: "GreaterThanOrEqual",
        value: startDate
            ? startDate.toJSON()
            : null
    },
    {
        operator: "LessThanOrEqual",
        value: endDate
            ? endDate.toJSON()
            : null
    });

this.host.applyJsonFilter(
    filter,
    "general",
    "filter",
    (startDate && endDate)
        ? FilterAction.merge
        : FilterAction.remove
);
```

Каждый раз, когда пользователь щелкает закладку, пользовательский визуальный элемент получает вызов `update`.

Пользовательский визуальный элемент должен проверить фильтр в объекте:

```typescript
const filter: IAdvancedFilter = FilterManager.restoreFilter(
    && options.jsonFilters
    && options.jsonFilters[0] as any
) as IAdvancedFilter;
```

Если объект `filter` не имеет значение NULL, визуальный элемент должен восстановить условия фильтра из объекта:

```typescript
const jsonFilters: AdvancedFilter = this.options.jsonFilters as AdvancedFilter[];

if (jsonFilters
    && jsonFilters[0]
    && jsonFilters[0].conditions
    && jsonFilters[0].conditions[0]
    && jsonFilters[0].conditions[1]
) {
    const startDate: Date = new Date(`${jsonFilters[0].conditions[0].value}`);
    const endDate: Date = new Date(`${jsonFilters[0].conditions[1].value}`);

    // apply restored conditions
} else {
    // apply default settings
}
```

После этого визуальный элемент должен изменить свое внутреннее состояние — точки данных и объекты визуализации (линии, прямоугольники и т. п.), чтобы отразить текущие условия.

> [!IMPORTANT]
> В сценарии с закладками отчета визуальный элемент не должен вызывать `applyJsonFilter` для фильтрации других визуальных элементов — они уже будут фильтроваться Power BI.

Визуальный элемент среза временной шкалы изменяет селектор диапазонов на соответствующие диапазоны данных.

Дополнительные сведения см. в [репозитории среза временной шкалы](https://github.com/Microsoft/powerbi-visuals-timeline/commit/606f1152f59f82b5b5a367ff3b117372d129e597?diff=unified#diff-b6ef9a9ac3a3225f8bd0de84bee0a0df).

### <a name="filter-state-to-save-visual-properties-in-bookmarks"></a>Фильтрация состояния для сохранения свойств визуальных элементов в закладках

Свойство `filterState` включает свойство в фильтрацию. Визуальный элемент может хранить различные значения в закладках.

Чтобы сохранить значение свойства как состояние фильтра, свойство объекта должно быть помечено как `"filterState": true` в `capabilities.json`.

Пример: `Timeline Slicer` сохраняет значения свойства `Granularity` в фильтре. Кроме того, он позволяет изменять текущую степень детализации при изменении закладок пользователем.

Дополнительные сведения см. в [репозитории среза временной шкалы](https://github.com/microsoft/powerbi-visuals-timeline/commit/8b7d82dd23cd2bd71817f1bc5d1e1732347a185e#diff-290828b604cfa62f1cb310f2e90c52fdR334).
