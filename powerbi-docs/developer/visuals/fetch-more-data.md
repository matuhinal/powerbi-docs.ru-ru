---
title: Получение дополнительных данных
description: Включение сегментированного получения больших наборов данных для визуальных элементов Power BI
author: AviSander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: bc8ff673927fd66bf44164e4e9950c279b98c6c1
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425075"
---
# <a name="fetch-more-data-from-power-bi"></a>Получение дополнительных данных из Power BI

API для загрузки дополнительных данных позволяет преодолеть жесткое ограничение в 30 тыс. для точки данных. Он передает данные фрагментами. Размер фрагмента можно настроить для повышения производительности в соответствии с вариантом использования.  

## <a name="enable-segmented-fetch-of-large-datasets"></a>Включение сегментированного получения больших наборов данных

Для сегментного режима `dataview` определите dataReductionAlgorithm "окна" в `capabilities.json` визуального элемента для требуемого dataViewMapping.
`count` определит размер окна, ограничивающий количество новых строк данных, добавляемых к `dataview` при каждом обновлении.

Для добавления в capabilities.json

```typescript
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                },
                "dataReductionAlgorithm": {
                    "window": {
                        "count": 100
                    }
                }
            }
    }
]
```

Новые сегменты добавляются к существующему `dataview` и предоставляются визуальному элементу в виде вызова `update`.

## <a name="usage-in-the-custom-visual"></a>Использование в пользовательском визуальном элементе

Существование данных индикации можно определить с помощью проверки существования `dataView.metadata.segment`:

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

Кроме того, можно установить, является ли это обновление первым или последующим, проверив `options.operationKind`.

`VisualDataChangeOperationKind.Create` обозначает первый сегмент, а `VisualDataChangeOperationKind.Append` — последующие.

Пример реализации см. в следующем фрагменте кода:

```typescript
// CV update implementation
public update(options: VisualUpdateOptions) {
    // indicates this is the first segment of new data.
    if (options.operationKind == VisualDataChangeOperationKind.Create) {

    }

    // on second or subesquent segments:
    if (options.operationKind == VisualDataChangeOperationKind.Append) {

    }

    // complete update implementation
}
```

Метод `fetchMoreData` также можно вызвать из обработчика событий пользовательского интерфейса

```typescript
btn_click(){
{
    // check if more data is expected for the current dataview
    if (dataView.metadata.segment) {
        //request for more data if available, as resopnce Power BI will call update method
        let request_accepted: bool = this.host.fetchMoreData();
        // handle rejection
        if (!request_accepted) {
            // for example when the 100 MB limit has been reached
        }
    }
}
```

Power BI вызовет метод `update` визуального элемента с новым сегментом данных в качестве ответа на вызов метода `this.host.fetchMoreData`.

> [!NOTE]
> Power BI ограничит общий объем получаемых данных значением **100 МБ**, чтобы предотвратить нехватку памяти на клиенте. На достижение этого лимита указывает возвращение fetchMoreData() значения "false".*
