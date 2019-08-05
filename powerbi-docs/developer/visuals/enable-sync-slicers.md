---
title: Активация синхронизации срезов
description: Добавление функции синхронизации срезов для визуальных элементов Power BI
author: EugeneElkin
ms.author: v-evelk
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 9966475e8bcaccad2090451b47ef09ef0a9af125
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425029"
---
# <a name="sync-slicers"></a>Синхронизация срезов

Для поддержки функции [Синхронизация срезов](https://docs.microsoft.com/power-bi/desktop-slicers) ваш настраиваемый визуальный элемент среза должен использовать API 1.13 или более поздней версии.

Вторым необходимым условием является включение параметра в `capabilities.json` (см. пример ниже).

```json
{
    ...
    "supportsHighlight": true,
    "suppressDefaultTitle": true,
    "supportsSynchronizingFilterState": true,
    "sorting": {
        "default": {}
    }
}
```

После внесения изменений в `capabilities.json` вы сможете просмотреть панель параметров "Синхронизация срезов", щелкнув свой настраиваемый визуальный элемент среза.

> [!NOTE]
> Если срез содержит более одного поля (категория или мера), эта функция будет отключена, так как синхронизация срезов не поддерживает несколько полей.

![Панель синхронизации срезов](./media/sync-slicers-panel.png)

На этой панели можно узнать, что видимость среза и его фильтрация могут применяться к нескольким страницам отчета.
