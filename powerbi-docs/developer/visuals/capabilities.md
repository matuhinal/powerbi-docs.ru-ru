---
title: Возможности
description: Возможности и свойства визуальных элементов Power BI
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f6bb4293a44f98f2f8098fb197c7b406b618d211
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425466"
---
# <a name="power-bi-visual-capabilities"></a>Возможности визуальных элементов Power BI

Возможности предоставляют узлу сведения о визуальном элементе. Все свойства в модели возможностей являются `optional`

Корневыми объектами возможностей визуального элемента являются `dataRoles`, `dataViewMappings` и т. д.

```json
{
    "dataRoles": [ ... ],
    "dataViewMappings": [ ... ],
    "objects":  { ... },
    "supportsHighlight": true|false,
    "advancedEditModeSupport": 0|1|2,
    "sorting": { ... }
}

```

## <a name="define-the-data-fields-your-visual-expects---dataroles"></a>Определение полей данных, ожидаемых вашими визуальными элементами, — `dataRoles`

Для определения полей, которые можно привязать к данным, мы используем `dataRoles`, который принимает массив объектов `DataViewRole`, определяющий все необходимые свойства.

### <a name="properties"></a>Свойства

* **name** — внутреннее имя этого поля данных (должно быть уникальным).
* **kind** — тип поля:
    * `Grouping` — дискретные значения, используемые для группирования полей мер.
    * `Measure` — числовые значения данных.
    * `GroupingOrMeasure` — может использоваться как группирование или мера.
* **displayName** — имя, отображаемое пользователю на панели свойств.
* **description** — краткое описание поля (необязательно).
* **requiredTypes** — требуемый тип данных для этой роли данных. Всем несовпадающим значениям будет присвоено значение NULL (необязательно).
* **preferredTypes** — предпочтительный тип данных для этой роли данных (необязательно).

### <a name="valid-data-types-in-requiredtypes-and-preferredtypes"></a>Допустимые типы данных в "requiredTypes" и "preferredTypes"

* **bool** — логическое значение.
* **integer** — целочисленное значение (целое число).
* **numeric** — числовое значение.
* **text** — текстовое значение.
* **geography** — географические данные.

### <a name="example"></a>Пример

```json
"dataRoles": [
    {
        "displayName": "My Category Data",
        "name": "myCategory",
        "kind": "Grouping",
        "requiredTypes": [
            {
                "text": true
            },
            {
                "numeric": true
            },
            {
                "integer": true
            }
        ],
        "preferredTypes": [
            {
                "text": true
            }
        ]
    },
    {
        "displayName": "My Measure Data",
        "name": "myMeasure",
        "kind": "Measure",
        "requiredTypes": [
            {
                "integer": true
            },
            {
                "numeric": true
            }
        ],
        "preferredTypes": [
            {
                "integer": true
            }
        ]
    },
    {
        "displayNameKey": "Visual_Location",
        "name": "Locations",
        "kind": "Measure",
        "displayName": "Locations",
        "requiredTypes": [
            {
                "geography": {
                    "address": true
                }
            },
            {
                "geography": {
                    "city": true
                }
            },
            {
                "geography": {
                    "continent": true
                }
            },
            {
                "geography": {
                    "country": true
                }
            },
            {
                "geography": {
                    "county": true
                }
            },
            {
                "geography": {
                    "place": true
                }
            },
            {
                "geography": {
                    "postalCode": true
                }
            },
            {
                "geography": {
                    "region": true
                }
            },
            {
                "geography": {
                    "stateOrProvince": true
                }
            }
        ]
    }
]
```

Приведенные выше роли данных создадут следующие поля:

![Отображаемая роль данных](./media/data-role-display.png)

## <a name="define-how-you-want-the-data-mapped---dataviewmappings"></a>Определение сопоставления данных — `dataViewMappings`

DataViewMapping описывает связь между ролями данных и позволяет указать для них условные требования.

Большинство визуальных элементов предоставляют одиночное сопоставление, но вы можете указать несколько DataViewMappings. Каждое допустимое сопоставление формирует DataView. 

```json
"dataViewMappings": [
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "table": { ... },
        "single": { ... },
        "matrix": { ... }
    }
]
```

[Дополнительные сведения о DataViewMappings](dataview-mappings.md)

## <a name="define-property-pane-options---objects"></a>Определение параметров панели свойств — `objects`

Объекты описывают настраиваемые свойства, связанные с визуальным элементом.
Каждый объект может иметь несколько свойств, и с каждым свойством сопоставлен тип.
Типы указывают, что будет представлять собой свойство. Дополнительные сведения о типах см. ниже.

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

[Дополнительные сведения об объектах](objects-properties.md)

## <a name="handle-partial-highlighting---supportshighlight"></a>Использование частичного выделения — `supportsHighlight`

По умолчанию это значение равно false, то есть ваши "значения" будут автоматически фильтроваться при выборе элемента на странице, что, в свою очередь, приведет к обновлению визуального элемента для отображения только выбранного значения. Если вы хотите отобразить полные данные и просто выделить выбранные элементы, нужно задать значение true для `supportsHighlight` в capabilities.json.

[Дополнительные сведения о выделении](highlight.md)

## <a name="handle-advanced-edit-mode---advancededitmodesupport"></a>Использование режима расширенного редактирования — `advancedEditModeSupport`

Визуальный элемент может объявить поддержку режима расширенного редактирования.
По умолчанию визуальный элемент не поддерживает режим расширенного редактирования, если иное не указано в файле capabilities.json.

[Дополнительные сведения об advancedEditModeSupport](advanced-edit-mode.md)

## <a name="data-sorting-options-for-visual---sorting"></a>Параметры сортировки данных для визуального элемента — `sorting`

Визуальный элемент может определить свое поведение сортировки с помощью возможностей.
По умолчанию визуальный элемент не поддерживает изменение порядка сортировки, если иное не указано в файле capabilities.json.

[Дополнительные сведения о сортировке](sort-options.md)
