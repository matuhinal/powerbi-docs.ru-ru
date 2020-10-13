---
title: Добавление контекстного меню к визуальному элементу Power BI
description: Узнайте, как добавить контекстное меню в визуальный элемент Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: 9e63a1196ddc7557fcf8b2fceb424415a63d4df9
ms.sourcegitcommit: 6bc66f9c0fac132e004d096cfdcc191a04549683
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91748087"
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
