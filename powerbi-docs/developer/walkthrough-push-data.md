---
title: "Принудительная отправка данных в набор данных"
description: "Принудительная отправка данных набор данных Power BI"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: e62b08614a38502fb79f48f369013d32fd538659
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="push-data-into-a-power-bi-dataset"></a>Принудительная отправка данных набор данных Power BI
API Power BI позволяет принудительно отправлять данные в набор данных Power BI. Например, вам нужно расширить существующий бизнес-процесс для отправки ключевых данных в набор данных. В этом случае необходимо отправить набор данных "Продажи и маркетинг", содержащий таблицу "Продукт".

Для принудительной передачи данных в набор данных требуется Azure Active Directory (Azure AD) и [учетная запись Power BI](create-an-azure-active-directory-tenant.md).

## <a name="steps-to-push-data-into-a-dataset"></a>Принудительная отправка данных в набор данных
* Шаг 1. [Регистрация приложения в Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)
* Шаг 2. [Получение токена доступа для проверки подлинности](walkthrough-push-data-get-token.md)
* Шаг 3. [Создание набора данных в Power BI](walkthrough-push-data-create-dataset.md)
* Шаг 4. [Получение набора данных для добавления строк в таблицу Power BI](walkthrough-push-data-get-datasets.md)
* Шаг 5. [Добавление строк в таблицу Power BI](walkthrough-push-data-add-rows.md)

В следующем разделе приводятся общие сведения об операциях API Power BI для отправки данных.

## <a name="power-bi-api-operations-to-push-data"></a>Операции API Power BI для отправки данных
REST API Power BI позволяет принудительно отправлять источники данных в панель мониторинга Power BI. Когда приложение добавляет строки в набор данных, плитки на панели мониторинга обновляются автоматически обновленными данными. Для отправки данных используйте операцию [Создание набора данных](https://msdn.microsoft.com/library/mt203562.aspx) вместе с операцией [Добавление строк](https://msdn.microsoft.com/library/mt203561.aspx). Чтобы найти набор данных, используйте операцию [Получение наборов данных](https://msdn.microsoft.com/library/mt203567.aspx). С помощью каждой из этих операций можно передать идентификатор группы для работы с группой. Чтобы получить список идентификаторов групп, используйте операцию [Получение групп](https://msdn.microsoft.com/library/mt243842.aspx). Примеры использования REST API Power BI см. в документации [Power BI REST API on APIARY](http://docs.powerbi.apiary.io/) (Справочник по REST API Power BI на APIARY).

Ниже перечислены операции по отправке данных в набор данных.

* [Создание набора данных](https://msdn.microsoft.com/library/mt203562.aspx)
* [Получение наборов данных](https://msdn.microsoft.com/library/mt203567.aspx)
* [Добавление строк](https://msdn.microsoft.com/library/mt203561.aspx)
* [Получение групп](https://msdn.microsoft.com/library/mt243842.aspx)

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

Таким образом, в нашем примере с набором данных "Продажи и маркетинг" нужно передать строку JSON, аналогичную показанной ниже. В этом примере **SalesMarketing** — это имя набора данных, а **Product** — имя таблицы. После определения таблицы следует определить схему таблицы. В случае набора данных **SalesMarketing** схема таблицы содержит следующие столбцы: ProductID, Manufacturer, Category, Segment, Product и IsCompete.

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
| Boolean |Нет |
| DateTime |Во время загрузки данных мы квантуем значения с частями суток на целые значения, кратные 1/300 секунды (3,33 мс). |
| String |В настоящее время вмещает до 128 000 знаков. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Дополнительные сведения о принудительной отправке данных в Power BI
Чтобы приступить к отправке данных в набор данных, см. сведения в левой области навигации — [Шаг 1. Регистрация приложения в Azure AD](walkthrough-push-data-register-app-with-azure-ad.md).

[Дальнейшие действия >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Дальнейшие действия
[Регистрация бесплатной учетной записи Power BI с пользовательским клиентом каталога Azure Active Directory](create-an-azure-active-directory-tenant.md)  
[Создание набора данных](https://msdn.microsoft.com/library/mt203562.aspx)  
[Получение наборов данных](https://msdn.microsoft.com/library/mt203567.aspx)  
[Добавление строк](https://msdn.microsoft.com/library/mt203561.aspx)  
[Получение групп](https://msdn.microsoft.com/library/mt243842.aspx)  
[Общие сведения о JSON](http://json.org/)  
[Обзор интерфейса REST API Power BI](overview-of-power-bi-rest-api.md)  
[Power BI REST API on APIARY](http://docs.powerbi.apiary.io/) (Справочник по REST API Power BI на APIARY)  
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

