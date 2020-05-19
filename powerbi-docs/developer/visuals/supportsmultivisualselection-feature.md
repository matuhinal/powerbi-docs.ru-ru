---
title: Функция supportsMultiVisualSelection
description: В этой статье описывается, как использовать функцию supportsMultiVisualSelection в визуальных элементах Power BI, а также требования к ее использованию.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 04/30/2020
ms.openlocfilehash: 6ad986308fb82f8191829d29654bb96b55d0fbd0
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83272702"
---
# <a name="use-the-supportsmultivisualselection-feature"></a>Использование функции supportsMultiVisualSelection

Функция `supportsMultiVisualSelection` позволяет использовать выбор в нескольких визуальных элементах в отчете.

## <a name="example"></a>Пример

В отчете, состоящем более чем с одного визуального элемента, выберите два значения, чтобы эти значения применялись к другим визуальным элементам. Например, в [примере анализа розничной торговли](../../create-reports/sample-retail-analysis.md) выберите **Fashions Direct** в одном визуальном элементе. Нажмите клавишу "CTRL" и выберите **Jan** в другом визуальном элементе. Параметры выбора в отчете применяются к другим визуальным элементам, поддерживающим использование этой функции. Другие визуальные элементы теперь применяются в **Fashions Direct** и **Jan**.

## <a name="requirements"></a>Требования

Для этой функции требуется API версии 3.2.0 или более поздней версии.

Эту функцию нельзя применить к визуальным элементам изображения. Ее нельзя применить к некоторым расширенным визуальным элементам, таким как ключевые драйверы, дерево декомпозиции, визуальные элементы вопросов и ответов, текстовые поля и диаграммы датчиков.

## <a name="usage"></a>Использование

Чтобы использовать функцию `supportsMultiVisualSelection`, добавьте следующий код в файл `capabilities.json` визуального элемента.

```json
    {   
            ...
        "supportsMultiVisualSelection": true
            ...
    }
```

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения о концепциях Power BI см. в статье [Визуальные элементы в Power BI](power-bi-visuals-concept.md).

Чтобы испытать разработку Power BI, см. статью [Руководство. Разработка визуального элемента Power BI](custom-visual-develop-tutorial.md).
