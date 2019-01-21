---
title: Свойства набора данных Power BI
description: Дополнительные сведения об API-интерфейсах свойств набора данных Power BI
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 4654534d9643b9c5cf5911249a0eda33b5cc32af
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277906"
---
# <a name="dataset-properties"></a>Свойства набора данных

В текущей версии 1 API набора данных можно создать только набор данных с именем и коллекцией таблиц. У каждой таблицы есть имя и коллекция объектов столбцов. У каждого столбца есть имя и тип данных. Мы существенно расширяем возможности соответствующих свойств главным образом за счет поддержки мер и связей между таблицами. Ниже приведен полный список свойств, поддерживаемых в этом выпуске.

> [!IMPORTANT]
> Он доступен на странице [Группы операций наборов данных](https://docs.microsoft.com/rest/api/power-bi/datasets).

## <a name="dataset"></a>Набор данных

Имя  |Тип  |Описание  |Только для чтения  |Требуется
---------|---------|---------|---------|---------
id     |  Guid       | Системный идентификатор набора данных.        | Да        | Нет        
name     | String        | Определяемое пользователем имя набора данных.        | Нет        | Да        
tables     | Table[]        | Коллекция таблиц.        |  Нет       | Нет        
relationships     | Relationship[]        | Коллекция связей между таблицами.        | Нет        |  Нет  
defaultMode     | String        | Определяет действие, выполняемое с набором данных, — отправка или передача в потоковом режиме (или и то и другое). Значения: "Push", "Streaming" и "PushStreaming" соответственно.         | Нет        |  Нет

## <a name="table"></a>Табличные

Имя  |Тип  |Описание  |Только для чтения  |Требуется
---------|---------|---------|---------|---------
name     | String        |  Определяемое пользователем имя таблицы. Также может использоваться в качестве ее идентификатора.       | Нет        |  Да       
columns     |  column[]       |  Коллекция столбцов.       | Нет        |  Да       
measures     | measure[]        |  Коллекция мер.       | Нет        |  Нет       
isHidden     | Boolean        | Если это свойство имеет значение true, таблица скрыта в клиентских средствах.        | Нет        | Нет        

## <a name="column"></a>Column

Имя  |Тип  |Описание  |Только для чтения  |Требуется
---------|---------|---------|---------|---------
name     |  String        | Определяемое пользователем имя столбца.        |  Нет       | Да       
dataType     |  String       |  Поддерживаемые [типы данных EDM](https://msdn.microsoft.com/library/ee382832.aspx) и ограничения. См. раздел [Ограничения типов данных](#DataTypeRestrictions).      |  Нет       | Да        
formatString     | String        | Строка, описывающая формат отображаемого значения. Сведения о форматах строк см. в разделе [Содержимое FORMAT_STRING](https://msdn.microsoft.com/library/ms146084.aspx).      | Нет        | Нет        
sortByColumn    | String        |   Строка, представляющая собой название столбца в той же таблице, который нужно использовать для сортировки текущего столбца.     | Нет        | Нет       
dataCategory     | String        |  Строковое значение, которое следует использовать в качестве категории данных, описывающей данные в столбце. Вот несколько типичных значений: Address, City, Continent, Country, Image, ImageUrl, Latitude, Longitude, Organization, Place, PostalCode, StateOrProvince, WebUrl.       |  Нет       | Нет        
isHidden    |  Boolean       |  Свойство, указывающее, является ли столбец скрытым. По умолчанию принимает значение false.       | Нет        | Нет        
summarizeBy     | String        |  Метод агрегирования по умолчанию для столбца. Доступны следующие значения: default, none, sum, min, max, count, average, distinctCount     |  Нет       | Нет

## <a name="measure"></a>Мера

Имя  |Тип  |Описание  |Только для чтения  |Требуется
---------|---------|---------|---------|---------
name     | String        |  Определяемое пользователем имя меры.       |  Нет       | Да        
expression     | String        | Допустимое выражение DAX.        | Нет        |  Да       
formatString     | String        |  Строка, описывающая формат отображаемого значения. Сведения о форматах строк см. в разделе [Содержимое FORMAT_STRING](https://msdn.microsoft.com/library/ms146084.aspx).       | Нет        | Нет        
isHidden     | String        |  Если это свойство имеет значение true, таблица скрыта в клиентских средствах.       |  Нет       | Нет       

## <a name="relationship"></a>Связь

Имя  |Тип  |Описание  |Только для чтения  |Требуется 
---------|---------|---------|---------|---------
name     | String        | Определяемое пользователем имя связи. Также может использоваться в качестве ее идентификатора.        | Нет       | Да        
crossFilteringBehavior     | Строка        |    Направление фильтра связи: OneDirection (по умолчанию), BothDirections, Automatic       | Нет        | Нет        
fromTable     | String        | Имя таблицы внешнего ключа.        | Нет        | Да         
fromColumn    | String        | Имя столбца внешнего ключа.        | Нет        | Да         
toTable    | String        | Имя таблицы первичного ключа.        | Нет        | Да         
toColumn     | String        | Имя столбца первичного ключа.        | Нет        | Да        

<a name="DataTypeRestrictions"/>

## <a name="data-type-restrictions-applies-to-datatype-property"></a>Ограничения типов данных (для свойства dataType)

Тип данных  |Ограничения  
---------|---------
Int64     |   Int64.MaxValue и Int64.MinValue не допускаются.      
Double     |  Значения Double.MaxValue и Double.MinValue не допускается. NaN не поддерживается. В некоторых функциях не поддерживаются +Infinity и -Infinity (например, Min, Max).       
Boolean     |   True или False.
DateTime    |   Во время загрузки данных мы квантуем значения с частями суток на целые значения, кратные 1/300 секунды (3,33 мс).      
Строка     |  Текущее ограничение длины строкового значения: 4000 символов.
Десятичное|точность = 28, шкала = 4

## <a name="example"></a>Пример
В приведенном ниже коде продемонстрированы некоторые из этих свойств.

```
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