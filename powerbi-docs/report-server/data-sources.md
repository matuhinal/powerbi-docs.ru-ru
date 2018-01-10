---
title: "Источники данных отчетов Power BI в решении \"Сервер отчетов Power BI\""
description: "Отчеты Power BI можно подключать к различным источникам данных. В зависимости от способа использования данных доступны различные источники данных."
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: dfdb0aebfd86854e756003d188a5b92fd8370fc1
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2018
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Источники данных отчетов Power BI в решении "Сервер отчетов Power BI"
Отчеты Power BI можно подключать к различным источникам данных. В зависимости от способа использования данных доступны различные источники данных. Данные можно импортировать или запрашивать напрямую с помощью DirectQuery или активного подключения к службам SQL Server Analysis Services.

Эти источники данных относятся к отчетам Power BI, которые используются в решении "Сервер отчетов Power BI" Сведения об источниках данных, которые поддерживаются для отчетов с разбивкой на страницы, см. в разделе [Источники данных, поддерживаемые службами Reporting Services (SSRS)](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

> [!IMPORTANT]
> Для настройки запланированного обновления должны поддерживаться все источники данных в отчете Power BI Desktop.
> 
> 

## <a name="list-of-supported-data-sources"></a>Список поддерживаемых источников данных
Другие источники данных могут работать, даже если они не входят в список поддерживаемых.

| **Источник данных** | **Кэшированные данные** | **Запланированное обновление** | **Активный запрос или запрос DirectQuery** |
| --- | --- | --- | --- |
| База данных SQL Server |Да |Да |Да |
| Службы SQL Server Analysis Services |Да |Да |Да |
| База данных SQL Azure |Да |Да |Да |
| Хранилище данных SQL Azure |Да |Да |Да |
| Excel |Да |Да |Нет |
| База данных Access |Да |Да |Нет |
| Active Directory |Да |Да |Нет |
| Amazon Redshift |Да |Нет |Нет |
| Хранилище BLOB-объектов Azure |Да |Да |Нет |
| Azure Data Lake Store |Да |Нет |Нет |
| Azure HDInsight (HDFS) |Да |Да |Нет |
| Azure HDInsight (Spark) |Да |Да |Нет |
| Хранилище таблиц Azure |Да |Да |Нет |
| Dynamics 365 (в сети); |Да |Нет |Нет |
| Facebook |Да |Нет |Нет |
| Папка |Да |Да |Нет |
| Google Analytics |Да |Нет |Нет |
| Файл Hadoop (HDFS) |Да |Нет |Нет |
| База данных IBM DB2 |Да |Да |Нет |
| Impala |Да |Нет |Нет |
| JSON |Да |Да |Нет |
| Microsoft Exchange |Да |Нет |Нет |
| Microsoft Exchange Online |Да |Нет |Нет |
| База данных MySQL |Да |Да |Нет |
| Веб-канал OData |Да |Да |Нет |
| ODBC |Да |Да |Нет |
| OLE DB |Да |Да |Нет |
| База данных Oracle |Да |Да |Да |
| База данных PostgreSQL |Да |Да |Нет |
| Служба Power BI |Нет |Нет |Нет |
| Сценарий R |Да |Нет |Нет |
| Объекты SalesForce |Да |Нет |Нет |
| Отчеты SalesForce |Да |Нет |Нет |
| сервер SAP Business Warehouse; |Да |Да |Да |
| База данных SAP HANA |Да |Да |Да |
| Папка SharePoint (локальная) |Да |Да |Нет |
| Список SharePoint (локальный) |Да |Да |Нет |
| Список SharePoint Online |Да |Нет |Нет |
| Snowflake |Да |Нет |Нет |
| База данных Sybase |Да |Да |Нет |
| База данных Teradata |Да |Да |Да |
| Text/CSV. |Да |Да |Нет |
| Веб-приложение |Да |Да |Нет |
| XML |Да |Да |Нет |
| appFigures (бета-версия) |Да |Нет |Нет |
| База данных служб Analysis Services Azure (бета-версия) |Да |Нет |Нет |
| Azure Cosmos DB (бета-версия) |Да |Нет |Нет |
| Azure HDInsight Spark (бета-версия) |Да |Нет |Нет |
| Common Data Service (бета-версия); |Да |Нет |Нет |
| comScore Digital Analytix (бета-версия) |Да |Нет |Нет |
| Dynamics 365 для Customer Insights (бета-версия) |Да |Нет |Нет |
| Dynamics 365 for Financials (бета-версия) |Да |Нет |Нет |
| GitHub (бета-версия) |Да |Нет |Нет |
| Google BigQuery (бета-версия) |Да |Нет |Нет |
| база данных IBM Informix (бета-версия); |Да |Нет |Нет |
| IBM Netezza (бета-версия) |Да |Нет |Нет |
| Kusto (бета-версия) |Да |Нет |Нет |
| MailChimp (бета-версия) |Да |Нет |Нет |
| Microsoft Azure Consumption Insights (бета-версия); |Да |Нет |Нет |
| Mixpanel (бета-версия) |Да |Нет |Нет |
| Planview Enterprise (бета-версия) |Да |Нет |Нет |
| Projectplace (бета-версия) |Да |Нет |Нет |
| QuickBooks Online (бета-версия) |Да |Нет |Нет |
| Smartsheet (бета-версия) |Да |Нет |Нет |
| Spark (бета-версия) |Да |Нет |Нет |
| SparkPost (бета-версия) |Да |Нет |Нет |
| SQL Sentry (бета-версия) |Да |Нет |Нет |
| Stripe (бета-версия) |Да |Нет |Нет |
| SweetIQ (бета-версия) |Да |Нет |Нет |
| Troux (бета-версия) |Да |Нет |Нет |
| Twilio (бета-версия) |Да |Нет |Нет |
| tyGraph (бета-версия) |Да |Нет |Нет |
| Vertica (бета-версия); |Да |Нет |Нет |
| Visual Studio Team Services (бета-версия) |Да |Нет |Нет |
| Webtrends (бета-версия) |Да |Нет |Нет |
| ZenDesk (бета-версия) |Да |Нет |Нет |

> [!IMPORTANT]
> Предполагается, что безопасность на уровне строк, настроенная в источнике данных, будет работать с определенными функциями DirectQuery (SQL Server, базой данных SQL Azure, Oracle и Teradata) и активными подключениями, если в вашей среде выполнена надлежащая настройка Kerberos.
> 
> 

## <a name="next-steps"></a>Дальнейшие действия
Теперь, когда источник данных выбран, воспользуйтесь содержащимися в нем данными, чтобы [создать отчет](quickstart-create-powerbi-report.md).

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

