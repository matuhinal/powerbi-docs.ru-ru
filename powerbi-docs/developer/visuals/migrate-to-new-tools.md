---
title: Миграция на powerbi-visuals-tools 3.x
description: Начало работы с новой версией powerbi-visuals-tools
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 245475feeb43ee544117aaa54969f2de1e207cd5
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2019
ms.locfileid: "74696289"
---
# <a name="migrate-to-the-new-powerbi-visuals-tools-3xx"></a>Миграция на новую версию powerbi-visuals-tools 3.x.x

Начиная с версии 3, для создания пользовательских визуальных элементов в Power BI Visuals Tools используется Webpack.
Новая версия при создании визуальных элементов предоставляет разработчикам множество новых возможностей:

* TypeScript v3.x.x по умолчанию. Начиная с TypeScript 1.5 номенклатура была изменена. [Узнать больше о модулях TypeScript](https://www.typescriptlang.org/docs/handbook/modules.html).

* Поддерживаются модули ES6. Использовать [externalJS](migrate-to-new-tools.md#fix-loading-external-libraries) больше не нужно, вместо этого используйте импорт из ES6.

* Поддерживаются новые версии [D3v5](https://d3js.org/) и другие библиотеки на основе модуля ES6.

* Меньший размер пакета. Для удаления неиспользуемого кода в пакете используется [встряхивание дерева](https://webpack.js.org/guides/tree-shaking/). Этот метод сокращает объем кода JS и в итоге повышает производительность при загрузке визуальных элементов.

* Улучшенная производительность API.

* Библиотека Globalize.js [интегрирована](migrate-to-new-tools.md#remove-globalizejs-library) в formatting-utils.

* Для отображения кода визуального элемента используется [webpack-bundle-analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer).

Ниже описаны все шаги миграции для новой версии Power BI Visuals Tools.

## <a name="backward-compatibility"></a>Обратная совместимость

Новые средства сохраняют обратную совместимость для базы кода старых визуальных элементов, но могут потребовать внесения некоторых дополнительных изменений для загрузки внешних библиотек.

Библиотеки, которые поддерживают модульные системы, будут импортированы как модули Webpack. Все остальные библиотеки и исходный код визуальных элементов будут перенесены в один модуль.

Глобальные переменные, такие как JQuery и Lodash, которые использовались в предыдущих средствах pbiviz, теперь устарели. Это означает, что если старый код визуальных элементов зависит от глобальных переменных, то этот визуальный элемент может оказаться неработоспособен.

Предыдущая версия Power BI Visuals Tools требовала определить визуальный класс в модуле `powerbi.extensibility.visual`.

## <a name="how-to-install-powerbi-visuals-tools"></a>Установка powerbi-visuals-tools

Новый набор инструментов можно установить, выполнив команду.

```cmd
npm install -g powerbi-visuals-tools
```

Пример визуального элемента sampleBarChart и соответствующие [изменения](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/package.json#L16) в `package.json`:

```json
{
    "name": "visual",
    "version": "1.2.3",
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "test": "pbiviz package --resources --no-minify --no-pbiviz"
    },
    "devDependencies": {
      "@types/d3": "5.0.0",
      "d3": "5.5.0",
      "powerbi-visuals-tools": "^3.1.0",
      "tslint": "^4.4.2",
      "tslint-microsoft-contrib": "^4.0.0"
    }
}
```

## <a name="how-to-install-power-bi-custom-visuals-api"></a>Установка API пользовательских визуальных элементов Power BI

Новая версия powerbi-visual-tools содержит не все версии API. Вместо этого разработчик должен установить определенную версию пакета [`powerbi-visuals-api`](https://www.npmjs.com/package/powerbi-visuals-api). Версия пакета соответствует версии API пользовательских визуальных элементов Power BI и предоставляет все определения типов для API-интерфейса пользовательских визуальных элементов Power BI.

Добавьте `powerbi-visuals-api` в зависимости проекта, выполнив команду `npm install --save-dev powerbi-visuals-api`.
Также следует удалить ссылку на определения типов старых API. Так как сейчас типы из `powerbi-visuals-api` автоматически включаются в состав пакета. Соответствующие изменения находятся в [этой](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/package.json#L14) строке `package.json`.

## <a name="update-tsconfigjson"></a>Обновить `tsconfig.json`

Чтобы использовать внешние модули, следует переключить параметр `out` на `outDir`.
`"outDir": "./.tmp/build/",` вместо `"out": "./.tmp/build/visual.js",`.

Он необходим, так как файлы TypeScript будут компилироваться в файлы JavaScript независимо друг от друга. Поэтому больше не нужно указывать файл visual.js в качестве выходных данных.

Кроме того, можно изменить параметр `target` на `ES6`, если вы хотите использовать современный скрипт JavaScript в качестве выходных данных. [Это необязательно](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/tsconfig.json#L6).

## <a name="update-custom-visuals-utils"></a>Обновление средства пользовательских визуальных элементов

Если вы используете одно из средств powerbi-visuals-utils (https://www.npmjs.com/search?q=powerbi-visuals-utils) ), необходимо обновить их до последней версии.

Выполните команду `npm install powerbi-visuals-utils-<UTILNAME> --save` (например, `npm install powerbi-visuals-utils-dataviewutils --save`), чтобы получить новую версию с внешними модулями TypeScript.

Пример можно найти в [репозитории](https://github.com/Microsoft/powerbi-visuals-mekkochart) MekkoChart.
Этот визуальный элемент использует все служебные программы.

## <a name="remove-globalizejs-library"></a>Удаление библиотеки Globalize.js

Новая версия [powerbi-visuals-utils-formattingutils@4.3](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils) изначально содержит библиотеку globalize.js.
Вам не нужно вручную включать эту библиотеку в проект.
Все необходимые локализации будут автоматически добавлены в окончательный пакет.

## <a name="fix-loading-external-libraries"></a>Исправление загрузки внешних библиотек

Вместо этого добавьте новый файл JS после libs в массиве `externalJS` в `pbiviz.json`. Пример:

```JSON
"externalJS": [
    ...
    "node_modules/lodash/lodash.min.js",
    "externalJS/init.lodash.js",
    ...
]
```

Импорт библиотек в исходном виде. Пример для `lodash-es`:

```JS
import * as _ from "lodash-es";
```

где `_` является глобальной переменной для библиотеки `lodash`.

## <a name="changes-in-the-visuals-sources"></a>Изменения в источниках визуальных элементов

Основное изменение заключается в преобразовании внутренних модулей во внешние модули, так как вы не можете использовать внешние модули во внутренних модулях.

Эти изменения отражают модификации, которые произошли в образце линейчатой диаграммы.

Ниже приведены подробные описания изменений.

1. Удаление всех определений модулей из каждого файла [исходного кода](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L153)

    ```typescript
    module powerbi.extensibility.visual {
        ...
    }
    ```

2. [Импорт определений API пользовательских визуальных элементов Power BI](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L2).

    ```typescript
    import powerbi from "powerbi-visuals-api";
    ```

3. [Импорт](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L12-L23) необходимых интерфейсов или классов из внутреннего модуля `powerbi`.

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

4. [Импорт](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L1) библиотеки D3.js

    ```typescript
    import * as d3 from "d3";
    ```

    или импорт только необходимых модулей библиотеки d3

    ```typescript
    import { max, min } from "d3-array";
    ```

5. [Импорт](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L4-L10) служебных программ, классов, интерфейсов, определенных в визуальном проекте, в основной файл исходного кода

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

Новая версия инструментов позволяет разработчикам импортировать стили LESS CSS непосредственно в код TypeScript.

Таким образом, ранее использовавшийся [раздел стилей](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/pbiviz.json#L22) будет игнорироваться компилятором.

Чтобы использовать таблицу стилей, откройте главный файл ts и добавьте следующую строку:  

```typescript
import "./../style/visual.less";
```  

Стили LESS CSS будут скомпилированы автоматически.  

### <a name="externaljs-section-in-pbivizjson"></a>Раздел externalJS в pbiviz.json

Этим инструментам [не требуется](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/pbiviz.json#L20) список `externalJS` для загрузки в набор визуальных элементов. Это связано с тем, что Webpack содержит все импортированные библиотеки.

**Раздел externalJS в pbivi.json должен быть пустым.**

Вызовите стандартные команды `npm run package`, чтобы создать пакет визуальных элементов или `npm run start` для запуска сервера разработки.

## <a name="updating-d3js-library-to-version-5"></a>Обновление библиотеки D3.js до версии 5

С помощью новых инструментов можно начать использовать новую версию библиотеки D3.js.

Вызовите команды для обновления D3 в проекте визуального элемента

`npm install --save d3@5` для установки новой версии библиотеки D3.js.

`npm install --save-dev @types/d3@5` для установки новых определений типов для библиотеки D3.js.

Существует несколько критических изменений, и вам необходимо изменить код для использования новой версии библиотеки D3.js.

1. Интерфейс `d3.Selection<T>` [был изменен](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR157) на `Selection<GElement extends BaseType, Datum, PElement extends BaseType, PDatum>`

2. Несколько атрибутов нельзя применить с помощью одного вызова метода `attr`. Каждый атрибут [следует передавать](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR278) в отдельном вызове метода `attr`. [Аналогичный](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR247) подход используется также и в методе `style`.

3. В D3.js версии 4 появился новый метод объединения. Этот метод обычно используется для слияния элементов ввода и обновления после объединения данных. [Вызовите метод объединения](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/83fe8d52d362dccd0034dd8e32c94080d9376b29#diff-433142f7814fee940a0ffc98dc75bfcbR272), чтобы правильно использовать d3.

[Дополнительные сведения](https://github.com/d3/d3/blob/master/CHANGES.md) об изменениях в библиотеке D3.js.

## <a name="babel"></a>Babel

Начиная с версии 3.1, это средство использует Babel для компиляции нового современного кода JS в старый ES5 для поддержки широкого спектра браузеров.

Эта возможность включена по умолчанию, но пакет [`@babel/polyfill`](https://babeljs.io/docs/en/babel-polyfill) необходимо импортировать вручную.

Выполните команду для установки пакета

`npm install --save @babel/polyfill`

и импортируйте пакет в начальной точке кода визуального элемента (обычно это файл "src/visual.ts"):

`import "@babel/polyfill";`

Дополнительные сведения о Babel см. в [документации](https://babeljs.io/docs/en/).

Наконец, запустите [webpack-visualizer](https://github.com/chrisbateman/webpack-visualizer), чтобы отобразить базу кода визуального элемента.  

![Статистика кода визуального элемента](./media/webpack-stats.png)
