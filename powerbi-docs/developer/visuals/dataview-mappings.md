---
title: Сопоставления представлений данных
description: Преобразование данных в Power BI перед передачей в визуальные элементы
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: ff70b2f12921694617a736164484df1326471eea
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425190"
---
# <a name="data-view-mappings-in-power-bi-visuals"></a>Сопоставления представлений данных в визуальных элементах Power BI

`dataViewMappings` описывает связь между ролями данных и позволяет указать для них условные требования.
Каждому из `dataMappings` посвящен раздел.

Каждое допустимое сопоставление приведет к созданию `DataView`, но сейчас поддерживается выполнение всего одного запроса на визуальный элемент, поэтому в большинстве случаев вы получите только один `DataView`. Однако можно указать несколько сопоставлений данных с разными условиями, что разрешено:

```json
"dataViewMappings": [
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "single": { ... },
        "table": { ... },
        "matrix": { ... }
    }
]
```

> [!NOTE]
> Важно отметить, что Power BI создает сопоставление с DataView только в том случае, если допустимое сопоставление указано в `dataViewMappings`.

Иными словами, если `categorical` определен в `dataViewMappings`, а другие сопоставления, такие как `table`, `single` и т. п., нет, как показано в следующем примере:
```json
"dataViewMappings": [
    {
        "categorical": { ... }
    }
]
```

Power BI создаст `DataView` с одним сопоставлением `categorical` (`table` и другие сопоставления будут `undefined`):
```javascript
{
    "categorical": {
        "categories": [ ... ],
        "values": [ ... ]
    },
    "metadata": { ... }
}
```

## <a name="conditions"></a>Условия

Описывает условия для определенного сопоставления данных. Можно предоставить несколько наборов условий, и если данные совпадают с одним из описанных наборов, визуальный элемент примет данные как допустимые.

Сейчас время для каждого поля можно указать минимальное и максимальное значения. Они представляют количество полей, которые можно привязать к этой роли данных. 

> [!NOTE]
> Если роль данных в условии опущена, она может иметь любое количество полей.

### <a name="example-1"></a>Пример 1

В каждую роль данных можно перетащить несколько полей. В этом примере мы ограничим категорию одним полем данных, а меру — двумя.

```json
"conditions": [
    { "category": { "max": 1 }, "y": { "max": 2 } },
]
```

### <a name="example-2"></a>Пример 2

В этом примере требуется одно из двух условий. Либо ровно одно поле данных категории, либо ровно две меры, либо ровно две категории и ровно одна мера.

```json
"conditions": [
    { "category": { "min": 1, "max": 1 }, "measure": { "min": 2, "max": 2 } },
    { "category": { "min": 2, "max": 2 }, "measure": { "min": 1, "max": 1 } }
]
```

## <a name="single-data-mapping"></a>Одиночное сопоставление данных

Одиночное сопоставление данных — это простейшая форма сопоставления данных. Оно принимает одно поле меры и выдает итог. Если поле является числовым, то будет выдаваться сумма. В противном случае выдается количество уникальных значений.

Чтобы использовать одиночное сопоставление данных, нужно определить имя роли данных, которую требуется сопоставить. Это сопоставление будет работать только с одним полем меры. Если назначено второе поле, представление данных создаваться не будет. Поэтому рекомендуется также включить условие, ограничивающее данные одним полем.

> [!NOTE]
> Это сопоставление данных невозможно использовать совместно с любым другим сопоставлением данных. Оно предназначено для сокращения данных до одного числового значения.

### <a name="example-3"></a>Пример 3

```json
"dataViewMappings": {
    "conditions": [
        { "Y": { "max": 1 } }
    ],
    "single": {
        "role": "Y"
    }
}  
```

Итоговое представление данных по-прежнему будет содержать другие типы (табличные, категориальные и т. д.), но каждое сопоставление будет содержать только одно значение. Рекомендуется просто обращаться к значению по отдельности.

```JSON
{
    "dataView": [
        {
            "metadata": null,
            "categorical": null,
            "matrix": null,
            "table": null,
            "tree": null,
            "single": {
                "value": 94163140.3560001
            }
        }
    ]
}
```

## <a name="categorical-data-mapping"></a>Категориальное сопоставление данных

Категориальное сопоставление данных используется для получения одного или двух независимых группирований данных.

### <a name="example-4"></a>Пример 4

Ниже приведено определение из нашего предыдущего примера для DataRoles.

```json
"dataRole":[
    {
        "displayName": "Category",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Y Axis",
        "name": "measure",
        "kind": "Measure"
    }
]
```

А теперь для сопоставления:

```json
"dataViewMappings": {
    "categorical": {
        "categories": {
            "for": { "in": "category" }
        },
        "values": {
            "select": [
                { "bind": { "to": "measure" } }
            ]
        }
    }
}
```

Это простой пример, который в общем виде означает следующее: "сопоставить мой DataRole `category`, чтобы для каждого поля, которое я перетаскиваю в `category`, его данные сопоставлялись с `categorical.categories`. Кроме того, сопоставить мой DataRole `measure` с `categorical.values`".

* **for...in** — включение всех элементов в этой роли данных в запрос данных.
* **bind...to** — дает тот же результат, что и for...in, но ожидает, что DataRole будет иметь условие, ограничивающее его до одного поля.

### <a name="example-5"></a>Пример 5

В этом примере мы будем использовать два первых DataRoles из предыдущего примера, а также дополнительно определим `grouping` и `measure2`.

```json
"dataRole":[
    {
        "displayName": "Category",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Y Axis",
        "name": "measure",
        "kind": "Measure"
    },
    {
        "displayName": "Grouping with",
        "name": "grouping",
        "kind": "Grouping"
    },
    {
        "displayName": "X Axis",
        "name": "measure2",
        "kind": "Grouping"
    }
]
```

А теперь для сопоставления:

```json
"dataViewMappings":{
    "categorical": {
        "categories": {
            "for": { "in": "category" }
        },
        "values": {
            "group": {
                "by": "grouping",
                "select":[
                    { "bind": { "to": "measure" } },
                    { "bind": { "to": "measure2" } }
                ]
            }
        }
    }
}
```

Разница заключается в том, как мы сопоставляем categorical.values. Мы предписываем: "сопоставить мои роли данных `measure` и `measure2` для группирования по роли данных `grouping`".

### <a name="example-6"></a>Пример 6

Вот dataRoles.

```json
"dataRoles": [
    {
        "displayName": "Categories",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Measures",
        "name": "measure",
        "kind": "Measure"
    },
    {
        "displayName": "Series",
        "name": "series",
        "kind": "Measure"
    }
]
```

Вот dataViewMapping.

```json
"dataViewMappings": [
    {
        "categorical": {
            "categories": {
                "for": {
                    "in": "category"
                }
            },
            "values": {
                "group": {
                    "by": "series",
                    "select": [{
                            "for": {
                                "in": "measure"
                            }
                        }
                    ]
                }
            }
        }
    }
]
```

Категориальный `dataview` можно визуализировать указанным образом.

| Категориальный |  |  | | | |
|-----|-----|------|------|------|------|
| | Год | 2013 | 2014 | 2015 | 2016 |
| Страна | | |
| США | | x | x | 125 | 100 |
| Канада | | x | 80 | 200 | x |
| Мексика | | 300 | x | x | x |
| Соединенное Королевство | | x | x | 75 | x |

Power BI создаст его как категориальное представление данных. Это набор категорий.

```JSON
{
    "categorical": {
        "categories": [
            {
                "source": {...},
                "values": [
                    "Canada",
                    "Mexico",
                    "UK",
                    "USA"
                ],
                "identity": [...],
                "identityFields": [...],
            }
        ]
    }
}
```

Каждая категория также сопоставляется с набором значений. Каждое из этих значений сгруппировано по рядам, то есть годам.

Например, продажи в Канаде в 2013 г. равны нулю, а продажи в Канаде в 2014 г. — 50.

```JSON
{
    "values": [
        {
            "source": {...},
            "values": [
                null,
                300,
                null,
                null
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                50,
                null,
                150,
                null
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                200,
                null,
                null,
                125
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                null,
                null,
                null,
                100
            ],
            "identity": [...],
        }
    ]
}
```

## <a name="table-data-mapping"></a>Сопоставление табличных данных

Представление табличных данных — это простое сопоставление данных. По сути, это список точек данных, где можно агрегировать точки числовых данных.

### <a name="example-7"></a>Пример 7

Учитывая доступные возможности:

```json
"dataRoles": [
    {
        "displayName": "Values",
        "name": "values",
        "kind": "Measure"
    }
]
```

```json
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                }
            }
        }
    }
]
```

Табличный `dataview` можно визуализировать указанным образом.  

| Страна| Год | Продажи |
|-----|-----|------|
| США | 2016 | 100 |
| США | 2015 | 80 |
| Канада | 2015 | 200 |
| Канада | 2015 | 80 |
| Мексика | 2013 | 300 |
| Соединенное Королевство | 2014 | 150 |
| США | 2015 | 75 |

Power BI создаст его как табличное представление данных. Не следует предполагать наличие порядка.

```JSON
{
    "table" : {
        "columns": [...],
        "rows": [
            [
                "Canada",
                2014,
                50
            ],
            [
                "Canada",
                2015,
                200
            ],
            [
                "Mexico",
                2013,
                300
            ],
            [
                "UK",
                2014,
                150
            ],
            [
                "USA",
                2015,
                100
            ],
            [
                "USA",
                2015,
                75
            ],
            [
                "USA",
                2016,
                100
            ]
        ]
    }
}
```

Эти данные можно агрегировать, выбрав нужное поле и щелкнув сумму.  

![Агрегирование данных](./media/data-aggregation.png)

## <a name="matrix-data-mapping"></a>Сопоставление матричных данных

Сопоставление матричных данных похоже на сопоставление табличных данных, однако строки в нем представляются иерархически. Кроме того, одно из значений `dataRole` можно использовать в качестве заголовка столбца.

```json
{
    "dataRoles": [
        {
            "name": "Category",
            "displayName": "Category",
            "displayNameKey": "Visual_Category",
            "kind": "Grouping"
        },
        {
            "name": "Column",
            "displayName": "Column",
            "displayNameKey": "Visual_Column",
            "kind": "Grouping"
        },
        {
            "name": "Measure",
            "displayName": "Measure",
            "displayNameKey": "Visual_Values",
            "kind": "Measure"
        }
    ],
    "dataViewMappings": [
        {
            "matrix": {
                "rows": {
                    "for": {
                        "in": "Category"
                    }
                },
                "columns": {
                    "for": {
                        "in": "Column"
                    }
                },
                "values": {
                    "select": [
                        {
                            "for": {
                                "in": "Measure"
                            }
                        }
                    ]
                }
            }
        }
    ]
}
```

Power BI создает иерархическую структуру данных. Корень дерева включает данные из первого столбца роли данных `Category` с дочерними элементами из второго ее столбца.

Набор данных:

| Родительские элементы | Дочерние элементы | Внучатые элементы | Столбцы | Значения |
|-----|-----|------|-------|-------|
| Parent1 | Child1 | Grand child1 | Col1 | 5 |
| Parent1 | Child1 | Grand child1 | Col2 | 6 |
| Parent1 | Child1 | Grand child2 | Col1 | 7 |
| Parent1 | Child1 | Grand child2 | Col2 | 8 |
| Parent1 | Child2 | Grand child3 | Col1 | 5 |
| Parent1 | Child2 | Grand child3 | Col2 | 3 |
| Parent1 | Child2 | Grand child4 | Col1 | 4 |
| Parent1 | Child2 | Grand child4 | Col2 | 9 |
| Parent1 | Child2 | Grand child5 | Col1 | 3 |
| Parent1 | Child2 | Grand child5 | Col2 | 5 |
| Parent2 | Child3 | Grand child6 | Col1 | 1 |
| Parent2 | Child3 | Grand child6 | Col2 | 2 |
| Parent2 | Child3 | Grand child7 | Col1 | 7 |
| Parent2 | Child3 | Grand child7 | Col2 | 1 |
| Parent2 | Child3 | Grand child8 | Col1 | 10 |
| Parent2 | Child3 | Grand child8 | Col2 | 13 |

Базовый визуальный элемент матрицы Power BI отрисовывает ее как таблицу.

![Визуальный элемент матрицы](./media/matrix-visual-smaple.png)

Визуальный элемент получает структуру данных описанным ниже образом (представлены только первые две строки):

```json
{
    "metadata": {...},
    "matrix": {
        "rows": {
            "levels": [...],
            "root": {
                "childIdentityFields": [...],
                "children": [
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Parent1",
                        "identity": {...},
                        "childIdentityFields": [...],
                        "children": [
                            {
                                "level": 1,
                                "levelValues": [...],
                                "value": "Child1",
                                "identity": {...},
                                "childIdentityFields": [...],
                                "children": [
                                    {
                                        "level": 2,
                                        "levelValues": [...],
                                        "value": "Grand child1",
                                        "identity": {...},
                                        "values": {
                                            "0": {
                                                "value": 5 // value for Col1
                                            },
                                            "1": {
                                                "value": 6 // value for Col2
                                            }
                                        }
                                    },
                                    ...
                                ]
                            },
                            ...
                        ]
                    },
                    ...
                ]
            }
        },
        "columns": {
            "levels": [...],
            "root": {
                "childIdentityFields": [...],
                "children": [
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Col1",
                        "identity": {...}
                    },
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Col2",
                        "identity": {...}
                    },
                    ...
                ]
            }
        },
        "valueSources": [...]
    }
}
```

## <a name="data-reduction-algorithm"></a>Алгоритм сокращения данных

`DataReductionAlgorithm` можно применить, если нужно управлять объемом данных, получаемых в DataView.

По умолчанию для всех пользовательских визуальных элементов применяется верхний алгоритм DataReductionAlgorithm, для которого в значении "count" задано 1000 точек данных. Это эквивалентно установке следующих свойств в файле capabilities.json:

```json
"dataReductionAlgorithm": {
    "top": {
        "count": 1000
    }
}
```

Вы можете изменить параметр "count" на любое целое значение не более 30 000. Пользовательские визуальные элементы на основе R могут поддерживать до 150 000 строк.

## <a name="data-reduction-algorithm-types"></a>Типы алгоритмов для сокращения данных

Существует четыре типа параметров `DataReductionAlgorithm`:

* `top` — если требуется ограничить данные значениями, взятыми из верхней части набора данных. Из набора данных будут взяты первые значения "count".
* `bottom` — если требуется ограничить данные значениями, взятыми из нижней части набора данных. Из набора данных будут взяты последние значения "count".
* `sample` — сокращение набора данных с помощью простого алгоритма выборки, ограниченного количеством элементов ("count"). Это означает, что включаются первый и последний элементы, а элементы в количестве "count" располагаются между ними с равными интервалами.
Например, если получен набор данных [0, 1, 2, ... 100] и `count: 9`, то вы получите следующие значения [0, 10, 20 ... 100].
* `window` — загружает одно "окно" точек данных за раз, содержащее определенное число ("count") элементов. Сейчас `top` и `window` эквивалентны. Ведется работа для реализации полной поддержки управления окнами.

## <a name="data-reduction-algorithm-usage"></a>Использование алгоритма для сокращения данных

`DataReductionAlgorithm` может использоваться в категориальном, табличном или матричном сопоставлении `dataview`.

Его можно задать в разделе `categories` и (или) группе объекта `values` для категориального сопоставления данных.

### <a name="example-8"></a>Пример 8

```json
"dataViewMappings": {
    "categorical": {
        "categories": {
            "for": { "in": "category" },
            "dataReductionAlgorithm": {
                "window": {
                    "count": 300
                }
            }  
        },
        "values": {
            "group": {
                "by": "series",
                "select": [{
                        "for": {
                            "in": "measure"
                        }
                    }
                ],
                "dataReductionAlgorithm": {
                    "top": {
                        "count": 100
                    }
                }  
            }
        }
    }
}
```

Алгоритм сокращения данных можно применить к разделу `rows` табличного сопоставления `dataview`.

### <a name="example-9"></a>Пример 9

```json
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                },
                "dataReductionAlgorithm": {
                    "top": {
                        "count": 2000
                    }
                } 
            }
        }
    }
]
```

Алгоритм сокращения данных можно применить к разделу `rows` и (или) `columns` сопоставления `matrix` `dataview`.
