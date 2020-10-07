---
title: Включение функции синхронизации срезов для визуальных элементов Power BI
description: В этой статье описывается добавление функции синхронизации срезов в визуальные элементы Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: 4e9989bb7a34a89cb6244a2378d6660a5079fc82
ms.sourcegitcommit: 6bc66f9c0fac132e004d096cfdcc191a04549683
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91748110"
---
# <a name="sync-slicers-in-power-bi-visuals"></a>Синхронизация срезов для визуальных элементов Power BI

Чтобы реализовать поддержку функции [Синхронизация срезов](../../visuals/power-bi-visualization-slicers.md), ваш настраиваемый визуальный элемент среза должен использовать API версии 1.13.0 или более поздней.

Кроме того, необходимо включить соответствующий параметр в файле *capabilities.json*, как показано в следующем коде:

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

После обновления файла *capabilities.json* при выборе настраиваемого визуального элемента среза будет отображаться область параметров **Синхронизация срезов**.

> [!NOTE]
> Функция синхронизации срезов поддерживает не более одного поля. Если срез содержит несколько полей (**Категория** или **Мера**), эта функция будет отключена.

![Область "Синхронизация срезов"](media/enable-sync-slicers/sync-slicers-panel.png)

В области **Синхронизация срезов** можно узнать, что параметры видимости и фильтрации срезов могут применяться к нескольким страницам отчета.