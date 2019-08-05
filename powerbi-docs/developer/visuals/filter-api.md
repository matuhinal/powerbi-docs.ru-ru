---
title: API фильтров визуальных элементов
description: Фильтрация визуальными элементами Power BI других визуальных элементов
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 50e9601faf497675ebc3f24609a856a600e3bcb1
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425052"
---
# <a name="power-bi-visual-filters-api"></a>API фильтров визуальных элементов Power BI

Фильтрация визуальных элементов позволяет фильтровать данные. Основное отличие от выбора заключается в том, что другие визуальные элементы будут фильтроваться всегда, независимо от поддержки выделения другими визуальными элементами.

Чтобы включить фильтрацию для визуального элемента, он должен содержать объект `filter` в разделе `general` файла capabilities.json.

```json
"objects": {
        "general": {
            "displayName": "General",
            "displayNameKey": "formattingGeneral",
            "properties": {
                "filter": {
                    "type": {
                        "filter": true
                    }
                }
            }
        }
    }
```

API фильтра доступны в пакете [`powerbi-models`](https://www.npmjs.com/package/powerbi-models). Этот пакет также содержит классы для создания экземпляров фильтра.

```cmd
npm install powerbi-models --save
```

Если используется старая версия средств (ниже 3.x.x), следует включить `powerbi-models` в пакет визуальных элементов. [Краткое руководство по включению пакета](https://github.com/Microsoft/powerbi-visuals-sampleslicer/blob/master/doc/AddingAdvancedFilterAPI.md)

Все фильтры расширяют интерфейс `IFilter`.

```typescript
export interface IFilter {
    $schema: string;
    target: IFilterTarget;
}
```

`target` — столбец таблицы в источнике данных.

## <a name="basic-filter-api"></a>API базового фильтра

Интерфейс базового фильтра:

```typescript
export interface IBasicFilter extends IFilter {
    operator: BasicFilterOperators;
    values: (string | number | boolean)[];
}
```

`operator` — перечисление со значениями "In", "NotIn", "All".

`values` — значения для условия.

Пример базового фильтра:

```typescript
let basicFilter = {
    target: {
        column: "Col1"
    },
    operator: "In",
    values: [1,2,3]
}
```

Фильтр имеет следующее значение: "вывести все строки, где `col1` равняется 1, 2 или 3".

Эквивалент SQL:

```sql
SELECT * FROM table WHERE col1 IN ( 1 , 2 , 3 )
```

Чтобы создать фильтр, можно использовать класс BasicFilter в `powerbi-models`.

При использовании старой версии средств нужно получить экземпляр моделей в объекте window, используя `window['powerbi-models']`:

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')),
    column: categories.source.displayName
};

let values = [ 1, 2, 3 ];

let filter: IBasicFilter = new window['powerbi-models'].BasicFilter(target, "In", values);
```

Визуальный элемент вызывает фильтр, используя метод applyJsonFilter() в интерфейсе узла IVisualHost, предоставляемом визуальному элементу в конструкторе.

```typescript
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

## <a name="advanced-filter-api"></a>API расширенного фильтра

[API расширенного фильтра](https://github.com/Microsoft/powerbi-models) позволяет выполнять сложные запросы выборки и фильтрации точек данных на основе нескольких визуальных элементов (например, "LessThan", "Contains", "Is", "IsBlank" и т. п.).

Этот фильтр появился в API визуальных элементов 1.7.0.

API расширенного фильтра также требует `target` с `table` и именем `column`. Однако операторами API расширенного фильтра являются `"And" | "Or"`. 

Кроме того, фильтр использует условия вместо значений с интерфейсом:

```typescript
interface IAdvancedFilterCondition {
    value: (string | number | boolean);
    operator: AdvancedFilterConditionOperators;
}
```

Операторами условий для параметра `operator` являются `"None" | "LessThan" | "LessThanOrEqual" | "GreaterThan" | "GreaterThanOrEqual" | "Contains" | "DoesNotContain" | "StartsWith" | "DoesNotStartWith" | "Is" | "IsNot" | "IsBlank" | "IsNotBlank"`.

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')), // table
    column: categories.source.displayName // col1
};

let conditions: IAdvancedFilterCondition[] = [];

conditions.push({
    operator: "LessThan",
    value: 0
});

let filter: IAdvancedFilter = new window['powerbi-models'].AdvancedFilter(target, "And", conditions);

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

Эквивалент SQL:

```sql
SELECT * FROM table WHERE col1 < 0;
```

Полный пример кода с использованием API расширенного фильтра можно найти в [репозитории `Sampleslicer visual`](https://github.com/Microsoft/powerbi-visuals-sampleslicer).

## <a name="tuple-filter-api-multi-column-filter"></a>API фильтра кортежей (фильтр для нескольких столбцов)

API фильтра кортежей появился в API визуальных элементов 2.3.0.

API фильтра кортежей аналогичен базовому фильтру, но позволяет определять условия для нескольких столбцов и таблиц.

Фильтр имеет интерфейс: 

```typescript
interface ITupleFilter extends IFilter {
    $schema: string;
    filterType: FilterType;
    operator: TupleFilterOperators;
    target: ITupleFilterTarget;
    values: TupleValueType[];
}
```

`target` — это массив столбцов с именами таблиц:

```typescript
declare type ITupleFilterTarget = IFilterTarget[];
```

  Фильтр может обращаться к столбцам из разных таблиц.

`$schema` имеет значение "http://powerbi.com/product/schema#tuple".

`filterType` имеет значение `FilterType.Tuple`.

`operator` допускается только использование оператора `"In"`.

`values` — это массив кортежей значений, где каждый кортеж представляет одно разрешенное сочетание значений целевого столбца. 

```typescript
declare type TupleValueType = ITupleElementValue[];

interface ITupleElementValue {
    value: PrimitiveValueType
}
```

Полный пример:

```typescript
let target: ITupleFilterTarget = [
    {
        table: "DataTable",
        column: "Team"
    },
    {
        table: "DataTable",
        column: "Value"
    }
];

let values = [
    [
        // the 1st column combination value (aka column tuple/vector value) that the filter will pass through
        {
            value: "Team1" // the value for `Team` column of `DataTable` table
        },
        {
            value: 5 // the value for `Value` column of `DataTable` table
        }
    ],
    [
        // the 2nd column combination value (aka column tuple/vector value) that the filter will pass through
        {
            value: "Team2" // the value for `Team` column of `DataTable` table
        },
        {
            value: 6 // the value for `Value` column of `DataTable` table
        }
    ]
];

let filter: ITupleFilter = {
    $schema: "http://powerbi.com/product/schema#tuple",
    filterType: FilterType.Tuple,
    operator: "In",
    target: target,
    values: values
}

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

**Порядок имен столбцов и значений условия имеет значение.**

Эквивалент SQL:

```sql
SELECT * FROM DataTable WHERE ( Team = "Team1" AND Value = 5 ) OR ( Team = "Team2" AND Value = 6 );
```  

## <a name="restoring-json-filter-from-dataview"></a>Восстановление фильтра JSON из DataView

Начиная с API 2.2 **фильтры JSON** можно восстановить из **VisualUpdateOptions**.

```typescript
export interface VisualUpdateOptions extends extensibility.VisualUpdateOptions {
    viewport: IViewport;
    dataViews: DataView[];
    type: VisualUpdateType;
    viewMode?: ViewMode;
    editMode?: EditMode;
    operationKind?: VisualDataChangeOperationKind;
    jsonFilters?: IFilter[];
}
```

Power BI вызывает метод `update` визуального элемента, когда использует переключение между закладками и визуальный элемент получает соответствующий объект `filter`.
[Дополнительные сведения о поддержке закладок](bookmarks-support.md)

### <a name="sample-json-filter"></a>Пример фильтра JSON

![Снимок экрана с фильтром JSON](./media/json-filter.png)

### <a name="clear-json-filter"></a>Очистка фильтра JSON

API фильтра принимает значение `null` фильтра в качестве сброса или очистки.

```typescript
// invoke the filter
visualHost.applyJsonFilter(null, "general", "filter", FilterAction.merge);
```
