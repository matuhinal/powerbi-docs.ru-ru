---
title: Сортировка
description: Режим сортировки по умолчанию для визуального элемента Power BI.
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f3d913e2bce34850dfae4c9486b2e43c78521a58
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424523"
---
# <a name="sorting-options"></a>Параметры сортировки

`Sorting` указывает режим сортировки по умолчанию для визуального элемента.
Для этой возможности требуется один из параметров, указанных ниже:

## <a name="default-sorting"></a>Сортировка по умолчанию

Параметр `default` является простейшей формой. Он позволяет сортировать данные, представленные в разделе "DataMappings".
Этот параметр обеспечивает сортировку "DataMappings" пользователем и позволяет задать ее направление.

```json
    "sorting": {
        "default": {   }
    }
```

![Параметры сортировки в контекстном меню](./media/sorting.png)

## <a name="implicit-sorting"></a>Неявная сортировка

Параметр `implicit` обозначает сортировку с параметром массива `clauses`, который описывает сортировку для каждой роли данных.
`implicit` означает, что пользователь визуального элемента не может изменить порядок сортировки.
Power BI не будет отображать параметры сортировки в меню визуального элемента. Однако Power BI будет сортировать данные в соответствии с указанными параметрами.

Параметры `clauses` могут содержать несколько объектов с двумя параметрами:

- `role` — определяет `DataMapping` для сортировки.

- `direction` — определяет направление сортировки (1 — по возрастанию, 2 — по убыванию).

```json
    "sorting": {
        "implicit": {
            "clauses": [
                {
                    "role": "category",
                    "direction": 1
                },
                {
                    "role": "measure",
                    "direction": 2
                }
            ]
        }
    }
```

## <a name="custom-sorting"></a>Пользовательская сортировка

`custom` означает, что сортировка управляется разработчиком в коде визуального элемента.
