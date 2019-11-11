---
title: Включение функции синхронизации срезов для визуальных элементов Power BI
description: В этой статье описывается добавление функции синхронизации срезов в визуальные элементы Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 055878988a197b80a8e4842a6567966f75af2ce5
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880149"
---
# <a name="sync-slicers-in-power-bi-visuals"></a>Синхронизация срезов для визуальных элементов Power BI

Чтобы реализовать поддержку функции [Синхронизация срезов](https://docs.microsoft.com/power-bi/desktop-slicers), ваш настраиваемый визуальный элемент среза должен использовать API версии 1.13 или более поздней.

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

![Область "Синхронизация срезов"](./media/sync-slicers-panel.png)

В области **Синхронизация срезов** можно узнать, что параметры видимости и фильтрации срезов могут применяться к нескольким страницам отчета.
