---
title: Добавление целевой страницы в визуальные элементы Power BI
description: В этой статье описывается добавление целевой страницы в визуальные элементы Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: 6f1590d5635ed6e55833350027c52379e5d7cf51
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "79379974"
---
# <a name="add-a-landing-page-to-your-power-bi-visuals"></a>Добавление целевой страницы в визуальные элементы Power BI

С помощью API версии 2.3.0 вы можете добавить целевую страницу в визуальные элементы Power BI. Для этого необходимо добавить к возможностям элемент `supportsLandingPage` и присвоить ему значение true. В результате этого действия визуальный элемент будет инициализироваться и добавляться до того, как в него будут добавлены данные. Поскольку для визуального элемента более не отображается водяной знак, вы можете разработать собственную целевую страницу, которая будет отображаться в этом визуальном элементе в том случае, если в нем отсутствуют данные.

```typescript
export class BarChart implements IVisual {
    //...
    private element: HTMLElement;
    private isLandingPageOn: boolean;
    private LandingPageRemoved: boolean;
    private LandingPage: d3.Selection<any>;

    constructor(options: VisualConstructorOptions) {
            //...
            this.element = options.element;
            //...
    }

    public update(options: VisualUpdateOptions) {
    //...
        this.HandleLandingPage(options);
    }

    private HandleLandingPage(options: VisualUpdateOptions) {
        if(!options.dataViews || !options.dataViews.length) {
            if(!this.isLandingPageOn) {
                this.isLandingPageOn = true;
                const SampleLandingPage: Element = this.createSampleLandingPage(); //create a landing page
                this.element.appendChild(SampleLandingPage);
                this.LandingPage = d3.select(SampleLandingPage);
            }

        } else {
                if(this.isLandingPageOn && !this.LandingPageRemoved){
                    this.LandingPageRemoved = true;
                    this.LandingPage.remove();
                }
        }
    }
```

На следующем рисунке показан пример целевой страницы:

![Снимок экрана с целевой страницей](media/landing-page/app-landing-page.png)
