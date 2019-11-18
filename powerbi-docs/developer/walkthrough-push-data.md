---
title: Принудительная отправка данных в набор данных
description: Принудительная отправка данных набор данных Power BI
author: rkarlin
ms.author: rkarlin
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: 5db16bfdc1013668be5103f392d6f298c8faf925
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2019
ms.locfileid: "73875449"
---
# <a name="push-data-into-a-power-bi-dataset"></a>Принудительная отправка данных набор данных Power BI

API Power BI позволяет принудительно отправлять данные в набор данных Power BI. В этой статье показано, как принудительно отправить набор данных по продажам и маркетингу с таблицей продуктов в существующий набор данных.

Для начала вам потребуется учетная запись Azure Active Directory (Azure AD) и [учетная запись Power BI](create-an-azure-active-directory-tenant.md).

## <a name="steps-to-push-data-into-a-dataset"></a>Принудительная отправка данных в набор данных

* Шаг 1. [Регистрация приложения в Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)
* Шаг 2. [Получение токена доступа для проверки подлинности](walkthrough-push-data-get-token.md)
* Шаг 3. [Создание набора данных в панели мониторинга Power BI](walkthrough-push-data-create-dataset.md)
* Шаг 4. [Получение набора данных для добавления строк в таблицу Power BI](walkthrough-push-data-get-datasets.md)
* Шаг 5. [Добавление строк в таблицу Power BI](walkthrough-push-data-add-rows.md)

В следующем разделе приводятся общие сведения об операциях API Power BI для отправки данных.

## <a name="power-bi-api-operations-to-push-data"></a>Операции API Power BI для отправки данных

REST API Power BI позволяет принудительно отправлять источники данных в панель мониторинга Power BI. Когда приложение добавляет строки в набор данных, данные на плитках панели мониторинга обновляются автоматически. Принудительная отправка данных выполняется с помощью операций [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset) и [PostRows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows). Для поиска набора данных используйте операцию [Получить наборы данных](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets). Для всех этих операций можно передать идентификатор группы для работы с группой. Чтобы получить список идентификаторов групп, используйте операцию [Получить группы](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups).

Ниже перечислены операции по отправке данных в набор данных.

* [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)
* [Получение наборов данных](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)
* [Отправка строк](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows)
* [Получение групп](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups)

Набор данных в Power BI создается путем передачи строки JavaScript Object Notation (JSON) в службу Power BI. Дополнительную информацию о JSON см. в статье [Введение в JSON](https://json.org/).

Строка JSON для набора данных имеет следующий формат.

**Объект JSON набора данных Power BI**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

Таким образом, в нашем примере с набором данных по продажам и маркетингу нужно передать строку JSON, как показано ниже. В этом примере **SalesMarketing** — это имя набора данных, а **Product** — имя таблицы. После определения таблицы следует определить схему таблицы. В случае с набором данных **SalesMarketing** схема таблицы содержит следующие столбцы: ProductID, Manufacturer, Category, Segment, Product и IsCompete.

**Пример объекта JSON набора данных**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

Для схемы таблицы Power BI можно использовать следующие типы данных.

## <a name="power-bi-table-data-types"></a>Типы данных таблицы Power BI

| **Тип данных** | **Ограничения** |
| --- | --- |
| Int64 |Int64.MaxValue и Int64.MinValue не допускаются. |
| Double |Значения Double.MaxValue и Double.MinValue не допускается. NaN не поддерживается. В некоторых функциях не поддерживаются +Infinity и -Infinity (например, Min, Max). |
| Логический |Нет |
| DateTime |Во время загрузки данных мы квантуем значения с частями суток на целые значения, кратные 1/300 секунды (3,33 мс). |
| Строка |В настоящее время вмещает до 128 000 знаков. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Дополнительные сведения о принудительной отправке данных в Power BI

Чтобы приступить к отправке данных в набор данных, см. сведения в левой области навигации — [Шаг 1. Регистрация приложения в Azure AD](walkthrough-push-data-register-app-with-azure-ad.md) в области навигации.

[Дальнейшие действия >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Дальнейшие действия

[Регистрация бесплатной учетной записи Power BI с пользовательским клиентом каталога Azure Active Directory](create-an-azure-active-directory-tenant.md)  
[Общие сведения о JSON](https://json.org/)  
[Обзор интерфейса REST API Power BI](overview-of-power-bi-rest-api.md)  
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](https://community.powerbi.com/)