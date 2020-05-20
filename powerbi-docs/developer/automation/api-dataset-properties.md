---
title: Свойства набора данных Power BI
description: Дополнительные сведения об API-интерфейсах свойств набора данных Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 7dad7071fbf887c36443cacdb9be83d83e0b89be
ms.sourcegitcommit: a72567f26c1653c25f7730fab6210cd011343707
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561508"
---
# <a name="dataset-properties"></a>Свойства набора данных

В текущей версии 1 API набора данных можно создать только набор данных с именем и коллекцией таблиц. У каждой таблицы есть имя и коллекция объектов столбцов. У каждого столбца есть имя и тип данных. Мы существенно расширяем возможности соответствующих свойств главным образом за счет поддержки мер и связей между таблицами. Ниже приведен полный список свойств, поддерживаемых в этом выпуске.

> [!IMPORTANT]
> Он доступен на странице [Группы операций наборов данных](https://docs.microsoft.com/rest/api/power-bi/datasets).

## <a name="dataset"></a>Набор данных

Имя  |Тип  |Описание  |Только для чтения  |Требуется
---------|---------|---------|---------|---------
ид     |  Guid       | Системный идентификатор набора данных.        | Да        | False        
имя     | String        | Определяемое пользователем имя набора данных.        | False        | Да        
tables     | Table[]        | Коллекция таблиц.        |  False       | False        
relationships     | Relationship[]        | Коллекция связей между таблицами.        | False        |  False  
defaultMode     | String        | Определяет действие, выполняемое с набором данных, — отправка или передача в потоковом режиме (или и то и другое). Значения: "Push" и "Streaming".         | False        |  False

## <a name="table"></a>Таблицы

Имя  |Тип  |Описание  |Только для чтения  |Требуется
---------|---------|---------|---------|---------
имя     | String        |  Определяемое пользователем имя таблицы. Также может использоваться в качестве ее идентификатора.       | False        |  Да       
columns     |  column[]       |  Коллекция столбцов.       | False        |  Да       
measures     | measure[]        |  Коллекция мер.       | False        |  False       
isHidden     | Boolean        | Если это свойство имеет значение true, таблица скрыта в клиентских средствах.        | False        | False        

## <a name="column"></a>Столбец

Имя  |Тип  |Описание  |Только для чтения  |Требуется
---------|---------|---------|---------|---------
имя     |  String        | Определяемое пользователем имя столбца.        |  False       | Да       
dataType     |  String       |  Поддерживаемые [типы данных EDM](/dotnet/framework/data/adonet/entity-data-model-primitive-data-types) и ограничения. См. раздел [Ограничения типов данных](#data-type-restrictions).      |  False       | Да        
formatString     | String        | Строка, описывающая формат отображаемого значения. Сведения о форматах строк см. в разделе [Содержимое FORMAT_STRING](/analysis-services/multidimensional-models/mdx/mdx-cell-properties-format-string-contents).      | False        | False        
sortByColumn    | String        |   Строка, представляющая собой название столбца в той же таблице, который нужно использовать для сортировки текущего столбца.     | False        | False       
dataCategory     | String        |  Строковое значение, которое следует использовать в качестве категории данных, описывающей данные в столбце. Вот несколько типичных значений: Address, City, Continent, Country, Image, ImageUrl, Latitude, Longitude, Organization, Place, PostalCode, StateOrProvince, WebUrl       |  False       | False        
isHidden    |  Boolean       |  Свойство, указывающее, является ли столбец скрытым. Значение по умолчанию — False.       | False        | False        
summarizeBy     | String        |  Метод агрегирования по умолчанию для столбца. Доступны следующие значения: default, none, sum, min, max, count, average, distinctCount     |  False       | False

## <a name="measure"></a>Мера

Имя  |Тип  |Описание  |Только для чтения  |Требуется
---------|---------|---------|---------|---------
имя     | String        |  Определяемое пользователем имя меры.       |  False       | Да        
expression     | String        | Допустимое выражение DAX.        | False        |  Да       
formatString     | String        |  Строка, описывающая формат отображаемого значения. Сведения о форматах строк см. в разделе [Содержимое FORMAT_STRING](/analysis-services/multidimensional-models/mdx/mdx-cell-properties-format-string-contents).       | False        | False        
isHidden     | String        |  Если это свойство имеет значение true, таблица скрыта в клиентских средствах.       |  False       | False       

## <a name="relationship"></a>Связь

Имя  |Тип  |Описание  |Только для чтения  |Требуется 
---------|---------|---------|---------|---------
имя     | String        | Определяемое пользователем имя связи. Также может использоваться в качестве ее идентификатора.        | False       | Да        
crossFilteringBehavior     | String        |    Направление фильтрации связи: OneDirection (по умолчанию), BothDirections, Automatic       | False        | False        
fromTable     | String        | Имя таблицы внешнего ключа.        | False        | Да         
fromColumn    | String        | Имя столбца внешнего ключа.        | False        | Да         
toTable    | String        | Имя таблицы первичного ключа.        | False        | Да         
toColumn     | String        | Имя столбца первичного ключа.        | False        | Да        

## <a name="data-type-restrictions"></a>Ограничения типов данных

Эти ограничения относятся только к свойству dataType.

Тип данных  |Ограничения  
---------|---------
Int64     |   Int64.MaxValue и Int64.MinValue не допускаются.      
Double     |  Значения Double.MaxValue и Double.MinValue не допускается. NaN не поддерживается. В некоторых функциях не поддерживаются +Infinity и -Infinity (например, Min, Max).       
Boolean     |   True или False.
DateTime    |   Во время загрузки данных мы квантуем значения с частями суток на целые значения, кратные 1/300 секунды (3,33 мс).      
String     |  Текущее ограничение длины строкового значения: 4000 символов.
Decimal|точность = 28, шкала = 4

## <a name="example"></a>Пример
В приведенном ниже коде продемонстрированы некоторые из этих свойств.

```json
{

  "name": "PushAdvanced",

  "tables": [

    {

      "name": "Date",

      "columns": [

        {

          "name": "Date",

          "dataType": "dateTime",

          "formatString": "dddd\\, mmmm d\\, yyyy",

          "summarizeBy": "none"

        }

      ]

    },

    {

      "name": "sales",

      "columns": [

        {

          "name": "Date",

          "dataType": "dateTime",

          "formatString": "dddd\\, mmmm d\\, yyyy",

          "summarizeBy": "none"

        },

        {

          "name": "Sales",

          "dataType": "int64",

          "formatString": "0",

          "summarizeBy": "sum"

        }

      ],

      "measures": [

        {

          "name": "percent to forecast",

          "expression": "SUM(sales[Sales])/SUM(forecast[forecast])",

          "formatString": "0.00 %;-0.00 %;0.00 %"

        }

      ]

    },

    {

      "name": "forecast",

      "columns": [

        {

          "name": "date",

          "dataType": "dateTime",

          "formatString": "m/d/yyyy",

          "summarizeBy": "none"

        },

        {

          "name": "forecast",

          "dataType": "int64",

          "formatString": "0",

          "summarizeBy": "sum"

        }

      ]

    }

  ],

  "relationships": [

    {

      "name": "2ea345ce-b147-436e-8ac2-9d3c4d82af8d",

      "fromTable": "sales",

      "fromColumn": "Date",

      "toTable": "Date",

      "toColumn": "Date",

      "crossFilteringBehavior": "bothDirections"

    },

    {

      "name": "5d95f419-e589-4345-9581-6e70670b1bba",

      "fromTable": "forecast",

      "fromColumn": "date",

      "toTable": "Date",

      "toColumn": "Date",

      "crossFilteringBehavior": "bothDirections"

    }

  ]

}
```