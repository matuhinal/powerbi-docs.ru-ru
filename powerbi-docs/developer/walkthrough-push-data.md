---
title: Принудительная отправка данных в набор данных
description: Принудительная отправка данных набор данных Power BI
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: 9eb81610044f795b6f9dc5c58aeefad13de06542
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222158"
---
# <a name="push-data-into-a-power-bi-dataset"></a>Принудительная отправка данных набор данных Power BI

Power BI API позволяет принудительно отправлять данные в панель мониторинга Power BI. В этой статье мы покажем, как для принудительной отправки продажи и маркетинг набор данных, содержащий таблицу продуктов в существующий набор данных.

Перед началом работы требуется Azure Active Directory (Azure AD) и [учетной записи Power BI](create-an-azure-active-directory-tenant.md).

## <a name="steps-to-push-data-into-a-dataset"></a>Принудительная отправка данных в набор данных

* Шаг 1. [Регистрация приложения в Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)
* Шаг 2. [Получение токена доступа для проверки подлинности](walkthrough-push-data-get-token.md)
* Шаг 3. [Создание набора данных в панели мониторинга Power BI](walkthrough-push-data-create-dataset.md)
* Шаг 4. [Получение набора данных для добавления строк в таблицу Power BI](walkthrough-push-data-get-datasets.md)
* Шаг 5. [Добавление строк в таблицу Power BI](walkthrough-push-data-add-rows.md)

В следующем разделе приводятся общие сведения об операциях API Power BI для отправки данных.

## <a name="power-bi-api-operations-to-push-data"></a>Операции API Power BI для отправки данных

REST API Power BI позволяет принудительно отправлять источники данных в панель мониторинга Power BI. Когда приложение добавляет строки в набор данных, то обновление автоматически с новыми данными плитки панели мониторинга. Чтобы принудительно отправить данные, используйте [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset) и [PostRows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows) операций. Чтобы найти набор данных, используйте [получение наборов данных](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets) операции. Можно передать идентификатор группы для работы с группой для любой из этих операций. Чтобы получить список идентификатор группы, используйте [получения групп](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups) операции.

Ниже перечислены операции по отправке данных в набор данных.

* [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)
* [Получение наборов данных](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)
* [Отправка строк](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows)
* [Получение групп](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups)

Набор данных в Power BI создается путем передачи строки JavaScript Object Notation (JSON) в службу Power BI. Дополнительную информацию о JSON см. в статье [Введение в JSON](http://json.org/).

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

Для примера набора данных продажи и маркетинг следует передавать строку JSON, как показано ниже. В этом примере **SalesMarketing** — имя набора данных, и **продукта** состоит из имени таблицы. После определения таблицы, определить схему таблицы. В случае с набором данных **SalesMarketing** схема таблицы содержит следующие столбцы: ProductID, Manufacturer, Category, Segment, Product и IsCompete.

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
| Double |Значения Double.MaxValue и Double.MinValue не допускается. NaN не поддерживается. + Infinity и - Infinity не поддерживается в некоторых функций (например, Min, Max). |
| Логический |Нет |
| DateTime |Во время загрузки данных мы квантуем значения с частями суток на целые значения, кратные 1/300 секунды (3,33 мс). |
| Строка |В настоящее время позволяет до 128 000 знаков. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Дополнительные сведения о принудительной отправке данных в Power BI

Чтобы приступить к отправке данных в набор данных, см. сведения в левой области навигации — [Шаг 1. Регистрация приложения в Azure AD](walkthrough-push-data-register-app-with-azure-ad.md).

[Дальнейшие действия >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Дальнейшие действия

[Регистрация бесплатной учетной записи Power BI с пользовательским клиентом каталога Azure Active Directory](create-an-azure-active-directory-tenant.md)  
[Общие сведения о JSON](http://json.org/)  
[Обзор интерфейса REST API Power BI](overview-of-power-bi-rest-api.md)  
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)