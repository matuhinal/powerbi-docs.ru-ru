---
title: Пользовательские макеты с внедренным содержимым Power BI
description: Узнайте о применении пользовательских макетов для внедрения содержимого Power BI в приложение.
author: rkarlin
ms.author: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 12/19/2017
ms.openlocfilehash: cae661641149554a7ecedabda322eb3b181b7f1a
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2019
ms.locfileid: "73875852"
---
# <a name="custom-layouts"></a>Пользовательские макеты

Для внедрения отчета с макетом, отличным от исходного, можно применить пользовательский макет. Определяя новый макет, можно задать только размер страницы, управлять размером визуальных элементов либо же настроить расположение и отображение.

Чтобы определить настраиваемый макет, определите его объект и передайте его в объект параметров в конфигурации внедрения. Кроме того, задайте для параметра LayoutType значение Custom. Дополнительные сведения см. в статье о [конфигурации внедрения](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details).

```javascript
var embedConfig = {
    ...
    settings: {
            layoutType: models.LayoutType.Custom
    customLayout: {...}
    }
};
```

## <a name="object-definition"></a>Определение объекта

```javascript
interface ICustomLayout {
  pageSize?: IPageSize;
  displayOption?: DisplayOption;
  pagesLayout?: PagesLayout;
}

enum PageSizeType {
  Widescreen,
  Standard,
  Cortana,
  Letter,
  Custom
}
interface IPageSize {
  type: PageSizeType;
}
interface ICustomPageSize extends IPageSize {
  width?: number;
  height?: number;
}

enum DisplayOption {
  FitToPage,
  FitToWidth,
  ActualSize
}
```

- `pageSize` — используйте этот параметр, чтобы управлять размером области холста (т. е. незаполненной области отчета).
- `displayOptions` — возможные значения: FitToWidth, FitToPage или ActualSize. Определяет, как масштабировать холст, чтобы он поместился в интернет-кадр.
- `pagesLayout` — определяет макет для каждого визуального элемента. См. дополнительные сведения о PagesLayout.

## <a name="pages-layout"></a>Макет страниц

Определение объекта для макета страниц по сути заключается в определении макета для каждой страницы и для каждого визуального элемента на ней.
PageLayout — необязательный параметр. Если не определить макет для страницы, будет применяться макет по умолчанию (который сохраняется в отчете).

pagesLayout — это сопоставление имени страницы и объекта PageLayout. Определение:

```javascript
type PagesLayout = { [key: string]: IPageLayout; };
```

PageLayout содержит схему макета визуального элемента, которая используется для сопоставления имени каждого визуального элемента с объектом визуального элемента на макете:

```javascript
interface IPageLayout {
  visualsLayout: { [key: string]: IVisualLayout; };
}
```

## <a name="visual-layout"></a>Макет визуального элемента

Чтобы определить макет визуального макета, передайте сведения о его новом расположении, размере и состоянии видимости.

```javascript
interface IVisualLayout {
  x?: number;
  y?: number;
  z?: number;
  width?: number;
  height?: number;
  displayState?: IVisualContainerDisplayState;
}

interface IVisualContainerDisplayState {
  mode: VisualContainerDisplayMode;
}

enum VisualContainerDisplayMode {
  Visible,
  Hidden
}
```

- `x,y,z` — определяет новое расположение визуального элемента.
- `width`, height — определяет новое расположение визуального элемента.
- `displayState` — определяет видимость визуального элемента.

## <a name="update-layout"></a>Обновление макета

Вы можете использовать метод updateSettings, чтобы макет обновлялся при каждой загрузке отчета. См. сведения об [изменении параметров](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Update-Settings).

## <a name="code-example"></a>Пример кода

```javascript
// Get models. models contains enums that can be used.
var models = window['powerbi-client'].models;

var embedConfiguration = {
    type: 'report',
    id: '5dac7a4a-4452-46b3-99f6-a25915e0fe55',
    embedUrl: 'https://app.powerbi.com/reportEmbed',
    tokenType: models.TokenType.Embed,
    accessToken: 'H4...rf',
    settings: {
            layoutType: models.LayoutType.Custom
        customLayout: {
            pageSize: {
                type: models.PageSizeType.Custom,
                width: 1600,
                height: 1200
            },
            displayOption: models.DisplayOption.ActualSize,
            pagesLayout: {
                "ReportSection1" : {
                    visualsLayout: {
                        "VisualContainer1": {
                            x: 1,
                            y: 1,
                            z: 1,
                            width: 400,
                            height: 300,
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Visible
                            }
                        },
                        "VisualContainer2": {
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Hidden
                            }
                        },
                    }
                }
            }
        }
    }
};

// Get a reference to the embedded report HTML element
var embedContainer = document.getElementById('embedContainer');

// Embed the report and display it within the div container.
var report = powerbi.embed(embedContainer, embedConfiguration);
```

## <a name="see-also"></a>См. также:

[Внедрение панелей мониторинга, отчетов и плиток Power BI](embedding-content.md)   
[Спросить в сообществе Power BI](https://community.powerbi.com/)