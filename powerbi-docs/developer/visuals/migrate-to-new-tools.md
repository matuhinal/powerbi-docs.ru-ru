---
title: Миграция на powerbi-visuals-tools версии 3.x
description: Начало работы с новой версией powerbi-visuals-tools
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 1b819aeb0f59df9ee0d48d7c41807abe62efed08
ms.sourcegitcommit: 801d2baa944469a5b79cf591eb8afd18ca4e00b1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75885128"
---
# <a name="migrate-to-the-new-powerbi-visuals-tools-version-3x"></a>Миграция на новую версию powerbi-visuals-tools 3.*x*

Начиная с версии 3, для создания пользовательских визуальных элементов в Power BI Visuals Tools (powerbi-visuals-tools или `pbiviz`) используется webpack.
В новой версии разработчикам доступно множество улучшений для создания визуальных элементов.

- По умолчанию используется TypeScript версии 3.*x*. Начиная с TypeScript 1.5, номенклатура изменилась. [Узнать больше о модулях TypeScript](https://www.typescriptlang.org/docs/handbook/modules.html).

- Поддерживаются модули ECMAScript 6 (ES6). Вместо [externalJS](migrate-to-new-tools.md#configure-loading-of-external-libraries) теперь используется импорт ES6.

- Поддерживаются новые версии Data-Driven Documents ([D3v5](https://d3js.org/)) и другие библиотеки на основе модуля ES6.

- Меньший размер пакета. Для удаления неиспользуемого кода в webpack используется [встряхивание дерева](https://webpack.js.org/guides/tree-shaking/). Это позволяет сократить код JavaScript и обеспечивает лучшую производительность при загрузке визуальных элементов.

- Улучшенная производительность API.

- Библиотека Globalize.js [встроена](migrate-to-new-tools.md#remove-the- globalizejs-library) в FormattingUtils.

- Для отображения кода визуального элемента в Power BI Visuals Tools используется [webpack-bundle-analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer).

В данной статье описаны все шаги миграции для новой версии Power BI Visuals Tools.

## <a name="backward-compatibility"></a>Обратная совместимость

Новые средства сохраняют сведения об обратной совместимости для базы кода старых визуальных элементов, но могут потребовать внесения некоторых дополнительных изменений для загрузки внешних библиотек.

Библиотеки, которые поддерживают модульные системы, импортируются как модули webpack. Все остальные библиотеки и исходный код для визуального элемента упаковываются в один модуль.

Глобальные переменные, такие как JQuery и Lodash, которые использовались в предыдущих версиях Power BI Visuals Tools, теперь устарели. Если в старом коде визуального элемента используются глобальные переменные, такой визуальный элемент, вероятно, не будет работать с новыми инструментами.

В предыдущей версии Power BI Visuals Tools требовалось определить визуальный класс в модуле `powerbi.extensibility.visual`. В новой версии средств вместо этого необходимо определить визуальный класс в основном файле TypeScript (.TS). Как правило, это файл `src/visual.ts`.

## <a name="install-powerbi-visuals-tools"></a>Установка powerbi-visuals-tools

Выполните следующую команду, чтобы установить новую версию средств:

```cmd
npm install -g powerbi-visuals-tools
```

Следующий код находится в файле `package.json` в [репозитории визуальных элементов sampleBarChart](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/package.json#L15), после обновления визуального проекта для работы с новыми средствами:

```json
{
    "name": "visual",
    "version": "3.0.0",
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "package": "pbiviz package",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "test": "pbiviz package --resources --no-minify --no-pbiviz"
    },
    "devDependencies": {
        "@types/d3": "5.7.2",
        "d3": "5.12.0",
        "powerbi-visuals-api": "^2.6.1",
        "powerbi-visuals-tools": "^3.1.7",
        "powerbi-visuals-utils-dataviewutils": "^2.2.1",
        "powerbi-visuals-utils-formattingutils": "^4.4.2",
        "powerbi-visuals-utils-interactivityutils": "^5.6.0",
        "powerbi-visuals-utils-tooltiputils": "^2.3.1",
        "tslint": "^5.20.0",
        "tslint-microsoft-contrib": "^6.2.0"
    }
}
```

## <a name="install-the-power-bi-custom-visuals-api"></a>Установка API настраиваемых визуальных элементов Power BI

В новой версии powerbi-visual-tools содержатся не все версии API. Вместо этого необходимо установить определенную версию пакета [powerbi-visuals-api](https://www.npmjs.com/package/powerbi-visuals-api). Выберите версию пакета, соответствующую версии API настраиваемых визуальных элементов Power BI. В пакете представлены все определения типов для API настраиваемых визуальных элементов Power BI.

Добавьте `powerbi-visuals-api` в зависимости проекта, выполнив следующую команду:

```cmd
npm install --save-dev powerbi-visuals-api
```

Кроме того, удалите все ссылки на старые определения типов API, так как webpack автоматически включает типы из `powerbi-visuals-api`. Соответствующие изменения находятся в файлах [package.json](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/package.json#L14) и [tsconfig.json](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/tsconfig.json#L14).

## <a name="update-tsconfigjson"></a>Обновление tsconfig.json

Чтобы использовать внешние модули, измените значение параметра `out` на `outDir`. Например, используйте функцию `"outDir": "./.tmp/build/",` вместо `"out": "./.tmp/build/visual.js",`.

Данное изменение является необходимым, поскольку файлы TypeScript будут компилироваться в файлы JavaScript независимо друг от друга. Поэтому больше не нужно указывать файл visual.js в качестве выходных данных.

Также можно изменить значение параметра `target` на `ES6`, если требуется использовать современный скрипт JavaScript в качестве выходных данных. Это изменение [необязательно](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/tsconfig.json#L7).

## <a name="update-custom-visuals-utilities"></a>Обновление служебных программ настраиваемых визуальных элементов

Если вы используете любой из пакетов [powerbi-visuals-utils](https://www.npmjs.com/search?q=powerbi-visuals-utils), необходимо обновить их до последней версии. Для этого выполните следующую команду:

```cmd
npm install powerbi-visuals-utils-<UTILNAME> --save
```

Например, чтобы получить новую версию с внешними модулями TypeScript, выполните следующую команду: 

```cmd
npm install powerbi-visuals-utils-dataviewutils --save
```

Пример визуального элемента, в котором используются все пакеты `powerbi-visuals-utils`, см. в разделе [Репозиторий MekkoChart](https://github.com/Microsoft/powerbi-visuals-mekkochart).

## <a name="remove-the-globalizejs-library"></a>Удаление библиотеки Globalize.js

В новой версии [powerbi-visuals-utils-formattingutils@4.3](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils) содержится библиотека Globalize.js. Поэтому не нужно вручную включать эту библиотеку в проект. Все необходимые локализации будут автоматически добавлены в окончательный пакет.

## <a name="configure-loading-of-external-libraries"></a>Настройка загрузки внешних библиотек

Добавьте новые файлы JavaScript после библиотек в массив `externalJS` `pbiviz.json`. Например:

```JSON
"externalJS": [
    ...
    "node_modules/lodash/lodash.min.js",
    "externalJS/init.lodash.js",
    ...
]
```

Импортируйте библиотеки в исходный код. Например, для `lodash-es` используйте следующую инструкцию.

```JS
import * as _ from "lodash-es";
```

В предыдущем примере `_` является глобальной переменной для библиотеки `lodash`.

## <a name="make-changes-in-the-sources-of-your-visuals"></a>Внесение изменений в источники визуальных элементов

Основное изменение, которое необходимо сделать, — преобразовать внутренние модули во внешние. Внешние модули нельзя использовать внутри внутренних модулей.

Ниже приведено подробное описание изменений, которые нужно внести. Изменения описаны в контексте примера настраиваемого визуального кода линейчатой диаграммы.

1. Удаление всех определений модулей из каждого файла [исходного кода](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbL1-L3)

    ```typescript
    module powerbi.extensibility.visual {
        ...
    }
    ```

2. [Импорт определений API настраиваемых визуальных элементов Power BI](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR4)

    ```typescript
    import powerbi from "powerbi-visuals-api";
    ```

3. [Импорт необходимых интерфейсов или классов](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR12-R35) из внутреннего модуля `powerbi`

    ```typescript
    import PrimitiveValue = powerbi.PrimitiveValue; 
    import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions; 
    import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions; 
    import IVisualHost = powerbi.extensibility.visual.IVisualHost; 
    import IColorPalette = powerbi.extensibility.IColorPalette; 
    import IVisual = powerbi.extensibility.visual.IVisual; 
    import VisualObjectInstance = powerbi.VisualObjectInstance; 
    import VisualObjectInstanceEnumeration = powerbi.VisualObjectInstanceEnumeration; 
    import EnumerateVisualObjectInstancesOptions = powerbi.EnumerateVisualObjectInstancesOptions; 
    import Fill = powerbi.Fill; 
    import VisualTooltipDataItem = powerbi.extensibility.VisualTooltipDataItem; 
    import ISelectionManager = powerbi.extensibility.ISelectionManager; 
    ```

4. [Импорт библиотеки D3.js](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR2)

    ```typescript
    import * as d3 from "d3";
    ```

    Или импорт только необходимых модулей библиотеки D3

    ```typescript
    import { max, min } from "d3-array";
    ```

5. [Импорт служебных программ, классов, интерфейсов, определенных в визуальном проекте](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR38-R41), в основной файл исходного кода

    ```typescript
    import { getLocalizedString } from "./localization/localizationHelper";
    import { getValue, getCategoricalObjectValue } from "./objectEnumerationUtility";
    import {
        ITooltipServiceWrapper,
        TooltipEventArgs,
        createTooltipServiceWrapper
    } from "./tooltipServiceWrapper";
    ```

### <a name="import-css-styles"></a>Импорт стилей CSS

В новой версии инструментов разработчики могут импортировать стили `CSS` и `Less` непосредственно в код TypeScript. [Раздел Styles](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/pbiviz.json#L21), который использовался ранее, теперь игнорируется компилятором.

Чтобы использовать таблицу стилей, откройте главный файл TypeScript (.TS) и добавьте следующую строку:  

```typescript
import "./../style/visual.less";
```  

Стили `CSS` и `Less` будут скомпилированы автоматически.

### <a name="externaljs-section-in-pbivizjson"></a>Раздел externalJS в pbiviz.json

Средствам [не требуется список библиотек `externalJS` ](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-a1a7bbee7e7d2f9d449f4b534532bcf2R20)для загрузки в визуальный набор, поскольку в состав webpack включены все импортированные библиотеки.

> [!NOTE]
> В `pbiviz.json` оставьте раздел `externalJS` пустым.

Используйте стандартные команды `npm run package`, чтобы создать пакет визуальных элементов или `npm run start` для запуска сервера разработки.

## <a name="update-the-d3js-library-to-version-5"></a>Обновление библиотеки D3.js до версии 5

С помощью новых средств визуализации можно начать использовать новую версию библиотеки D3.js. Выполните следующие команды для обновления D3 в проекте визуального элемента:

- `npm install --save d3@5` для установки новой версии библиотеки D3.js.

- `npm install --save-dev @types/d3@5` для установки новых определений типов для библиотеки D3.js.

> [!IMPORTANT]
> В D3 версии 5 представлено несколько критических изменений.

Измените код для работы с новой версией D3.js:

- Интерфейс `d3.Selection<T>` [был изменен](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR157) на `Selection<GElement extends BaseType, Datum, PElement extends BaseType, PDatum>`.

- Несколько атрибутов нельзя применить с помощью одного вызова метода `attr`. Вместо этого необходимо [передать каждый атрибут в отдельном вызове](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR278) в `attr`. Также необходимо создать [отдельные вызовы метода `style`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR247).

- В D3.js версии 4 появился новый метод `merge`. Этот метод обычно используется для слияния `enter` и `update` после объединения данных. Чтобы правильно использовать D3, [вызовите метод `merge`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/83fe8d52d362dccd0034dd8e32c94080d9376b29#diff-433142f7814fee940a0ffc98dc75bfcbR272).

[Узнайте подробнее](https://github.com/d3/d3/blob/master/CHANGES.md) об изменениях в библиотеке D3.js.

## <a name="install-babel-and-core-js"></a>Установка Babel и core-js

Начиная с версии 3.1, средства визуализации используют Babel для компиляции нового современного кода JavaScript в старый ECMAScript 5 (ES5) для поддержки широкого спектра браузеров.

Эта возможность включена по умолчанию, однако пакет [`core-js`](https://www.npmjs.com/package/core-js) необходимо импортировать вручную. Выполните следующую команду, чтобы установить пакет:

```cmd
npm install --save core-js
```

Затем импортируйте пакет в начальную точку кода визуального элемента. Как правило, это файл "src/visual.ts".

```JS
import "core-js/stable";
```

Дополнительные сведения о Babel см. в [документации](https://babeljs.io/docs/en/).
