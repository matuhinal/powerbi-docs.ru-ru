---
title: Возможности и свойства визуальных элементов Power BI
description: В этой статье описываются возможности и свойства визуальных элементов Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 7d24ea77fd73ca6a83176d1b8560c88fa98a8d6b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "79380762"
---
# <a name="add-context-menu-to-power-bi-visual"></a>Добавление контекстного меню к визуальному элементу Power BI

Вы можете использовать `selectionManager.showContextMenu()` с параметрами `selectionId` и положением (в качестве объекта `{x:, y:}`), чтобы Power BI отображал контекстное меню для визуального элемента.

> [!IMPORTANT]
> `selectionManager.showContextMenu()` появился в API визуальных элементов 2.2.0.

Обычно он добавляется как событие щелчка правой кнопкой мыши (или длительное нажатие для сенсорных устройств). Контекстное меню было добавлено в образец BarChart для справки:

```typescript
    public update(options: VisualUpdateOptions) {
        //...
        //handle context menu
        this.svg.on('contextmenu', () => {
            const mouseEvent: MouseEvent = d3.event as MouseEvent;
            const eventTarget: EventTarget = mouseEvent.target;
            let dataPoint = d3.select(eventTarget).datum();
            this.selectionManager.showContextMenu(dataPoint? dataPoint.selectionId : {}, {
                x: mouseEvent.clientX,
                y: mouseEvent.clientY
            });
            mouseEvent.preventDefault();
        });
```
