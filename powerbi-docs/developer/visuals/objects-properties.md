---
title: Объекты и свойства
description: Настраиваемые свойства визуального элемента Power BI
author: MrMeison
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: c22a1cfb281c9902d490e2320b85c2f6bbb63468
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424615"
---
# <a name="object-and-properties"></a>Объекты и свойства

Объекты описывают настраиваемые свойства, связанные с визуальным элементом.
Каждый объект может иметь несколько свойств, и с каждым свойством сопоставлен тип.
Типы указывают, что будет представлять собой свойство. Дополнительные сведения о типах см. ниже.

`myCustomObject` — это внутреннее имя, используемое для ссылки на объект в `dataView` и `enumerateObjectInstances`:

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

## <a name="display-name"></a>Отображаемое имя

`displayName` — это имя, которое будет отображаться на панели свойств.

## <a name="properties"></a>Свойства

`properties` — это карта свойств, определенных разработчиком.

```json
"properties": {
    "myFirstProperty": {
        "displayName": "firstPropertyName",
        "type": ValueTypeDescriptor | StructuralTypeDescriptor
    }
}
```

> [!NOTE]
> `show` — это специальное свойство, позволяющее переключать объект.

Пример:

```json
"properties": {
    "show": {
        "displayName": "My Property Switch",
        "type": {"bool": true}
    }
}
```

### <a name="property-types"></a>Типы свойств

Существует два вида типов свойств: `ValueTypeDescriptor` и `StructuralTypeDescriptor`.

#### <a name="value-type-descriptor"></a>Дескриптор типа значения

`ValueTypeDescriptor` являются главным образом типами-примитивами и обычно используются в качестве статического объекта.
Ниже приведен типичный `ValueTypeDescriptor`:

```typescript
export interface ValueTypeDescriptor {
    text?: boolean;
    numeric?: boolean;
    integer?: boolean;
    bool?: boolean;
}
```

#### <a name="structural-type-descriptor"></a>Дескриптор структурного типа

`StructuralTypeDescriptor` в основном используются для объектов, привязанных к данным.
Заливка является наиболее распространенным `StructuralTypeDescriptor`.

```typescript
export interface StructuralTypeDescriptor {
    fill?: FillTypeDescriptor;
}
```

## <a name="gradient-property"></a>Градиентное свойство

Градиентное свойство — это свойство, которое невозможно задать как стандартное свойство. Вместо этого нужно задать правило для замены свойства палитры (тип заливки).
См. следующий пример:

```json
"properties": {
    "showAllDataPoints": {
        "displayName": "Show all",
        "displayNameKey": "Visual_DataPoint_Show_All",
        "type": {
            "bool": true
        }
    },
    "fill": {
        "displayName": "Fill",
        "displayNameKey": "Visual_Fill",
        "type": {
            "fill": {
                "solid": {
                    "color": true
                }
            }
        }
    },
    "fillRule": {
        "displayName": "Color saturation",
        "displayNameKey": "Visual_ColorSaturation",
        "type": {
            "fillRule": {}
        },
        "rule": {
            "inputRole": "Gradient",
            "output": {
                "property": "fill",
                    "selector": [
                        "Category"
                    ]
            }
        }
    }
}
```

Обратите внимание на свойства `"fill"` и `"fillRule"`. Первое — это палитра, второе — правило подстановки для градиента, которое заменит свойство "fill" `visually` при соблюдении условий правила.

Эта связь между свойством fill и правилом подстановки определяется в разделе `"rule"`->`"output"` свойства `"fillRule"`.

`"Rule"`->`"InputRole"` задает, какая роль данных активирует правило (условие). В этом примере, если роль данных `"Gradient"` содержит данные, правило будет применено к свойству `"fill"`.

Ниже приведен пример роли данных, которая активирует правило заливки (`the last item`).

```json
{
    "dataRoles": [
            {
                "name": "Category",
                "kind": "Grouping",
                "displayName": "Details",
                "displayNameKey": "Role_DisplayName_Details"
            },
            {
                "name": "Series",
                "kind": "Grouping",
                "displayName": "Legend",
                "displayNameKey": "Role_DisplayName_Legend"
            },
            {
                "name": "Gradient",
                "kind": "Measure",
                "displayName": "Color saturation",
                "displayNameKey": "Role_DisplayName_Gradient"
            }
    ]
}
```

## <a name="enumerateobjectinstances-method"></a>Метод `enumerateObjectInstances`

Чтобы эффективно использовать объекты, вам потребуется функция в пользовательском визуальном элементе с именем `enumerateObjectInstances`. Эта функция заполнит панель свойств объектами, а также определит, куда должны быть привязаны объекты внутри dataView.  

Вот как выглядит обычная настройка:

```typescript
public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration {
    let objectName: string = options.objectName;
    let objectEnumeration: VisualObjectInstance[] = [];

    switch( objectName ) {
        case 'myCustomObject':
            objectEnumeration.push({
                objectName: objectName,
                properties: { ... },
                selector: { ... }
            });
            break;
    };

    return objectEnumeration;
}
```

### <a name="properties"></a>Свойства

Свойства в `enumerateObjectInstances` будут отражать свойства, определенные в ваших возможностях. См. пример в нижней части страницы.

### <a name="objects-selector"></a>Селектор объектов

Селектор в `enumerateObjectInstances` определяет, куда будет привязан каждый объект в DataView. Существует четыре отдельных параметра.

#### <a name="static"></a>static

Этот объект будет привязан к метаданным `dataviews[index].metadata.objects`.

```typescript
selector: null
```

#### <a name="columns"></a>columns

Этот объект будет привязан к столбцам с соответствующим `QueryName`.

```typescript
selector: {
    metadata: 'QueryName'
}
```

#### <a name="selector"></a>selector

Этот объект будет привязан к элементу, для которого мы создали `selectionID`. В этом примере предполагается, что мы создали `selectionID` для некоторых точек данные и выполняем их перебор в цикле.

```typescript
for (let dataPoint in dataPoints) {
    ...
    selector: dataPoint.selectionID.getSelector()
}
```

#### <a name="scope-identity"></a>scope identity

Этот объект будет привязан к конкретным значениям на пересечении групп. Например, если у меня есть категории `["Jan", "Feb", "March", ...]` и ряды `["Small", "Medium", "Large"]`, мне может потребоваться объект на пересечении значений, соответствующих `Feb` и `Large`. Для этого я могу получить `DataViewScopeIdentity` обоих столбцов, отправить их в переменную `identities` и использовать этот синтаксис с селектором.

```typescript
selector: {
    data: <DataViewScopeIdentity[]>identities
}
```

##### <a name="example"></a>Пример

В этом примере мы показываем, как будет выглядеть один objectEnumeration для объекта customColor с одним свойством `fill`. Мы хотим, чтобы этот объект был статически привязан к `dataViews[index].metadata.objects`.

```typescript
objectEnumeration.push({
    objectName: "customColor",
    displayName: "Custom Color",
    properties: {
        fill: {
            solid: {
                color: dataPoint.color
            }
        }
    },
    selector: null
});
```
