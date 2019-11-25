---
title: Возможности и свойства визуальных элементов Power BI
description: В этой статье описываются возможности и свойства визуальных элементов Power BI.
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 206f1aec7c76b00b6f725d8469eb3e483a01c653
ms.sourcegitcommit: f7b28ecbad3e51f410eff7ee4051de3652e360e8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74061783"
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
