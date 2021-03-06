---
title: Источники данных отчетов Power BI в решении "Сервер отчетов Power BI"
description: Отчеты Power BI можно подключать к разным источникам данных. В зависимости от способа использования данных доступны различные источники данных.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 08/04/2020
ms.author: maggies
ms.openlocfilehash: cedabd613e177aa9a3645e80db38b74d799b8799
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90861206"
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Источники данных отчетов Power BI в решении "Сервер отчетов Power BI"
Отчеты Power BI можно подключать к разным источникам данных. В зависимости от способа использования данных доступны различные источники данных. Данные можно импортировать или запрашивать напрямую с помощью DirectQuery или активного подключения к службам SQL Server Analysis Services. Некоторые источники данных, доступные в Power BI Desktop, оптимизированы для сервера отчетов Power BI, но не поддерживаются для публикации на сервере отчетов Power BI.

Эти источники данных относятся к отчетам Power BI, которые используются в решении "Сервер отчетов Power BI" Сведения об источниках данных, которые поддерживаются для отчетов с разбивкой на страницы (RDL), см. в разделе [Источники данных, поддерживаемые службами Reporting Services (SSRS)](/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

> [!IMPORTANT]
> Для настройки запланированного обновления в отчете Power BI Desktop должны поддерживаться все источники данных.
>  

## <a name="list-of-supported-data-sources"></a>Список поддерживаемых источников данных

| **Источник данных** | **Кэшированные данные** | **Запланированное обновление** | **Активное подключение или подключение DirectQuery** |
| --- | --- | --- | --- |
| База данных SQL Server |Да |Да |Да |
| службы SQL Server Analysis Services |Да |Да |Да |
| База данных SQL Azure |Да |Да |Да |
| Хранилище данных SQL Azure |Да |Да |Да |
| Excel |Да |Да |Нет |
| База данных Access |Да |Да |Нет |
| Active Directory |Да |Да |Нет |
| Amazon Redshift |Да |Нет |Нет |
| хранилище BLOB-объектов Azure |Да |Да |Нет |
| Хранилище озера данных Azure |Да |Нет |Нет |
| Azure HDInsight (HDFS) |Да |Нет |Нет |
| Azure HDInsight (Spark) |Да |Нет |Нет |
| Хранилище таблиц Azure |Да |Да |Нет |
| Dynamics 365 (в сети) |Да |Нет |Нет |
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
| OLE DB |Да |Да |Нет |
| Oracle Database |Да |Да |Да |
| База данных PostgreSQL |Да |Да |Нет |
| Служба Power BI |Нет |Нет |Нет |
| Сценарий R |Да |Нет |Нет |
| Объекты Salesforce |Да |Нет |Нет |
| Отчеты SalesForce |Да |Нет |Нет |
| Сервер SAP Business Warehouse |Да |Да |Да |
| База данных SAP HANA |Да |Да |Да |
| Папка SharePoint (локальная) |Да |Да |Нет |
| Список SharePoint (локальный) |Да |Да |Нет |
| Список SharePoint Online |Да |Нет |Нет |
| Snowflake |Да |Нет |Нет |
| База данных Sybase |Да |Да |Нет |
| Teradata |Да |Да |Да |
| Text/CSV |Да |Да |Нет |
| Интернет |Да |Да |Нет |
| XML |Да |Да |Нет |
| appFigures (бета-версия) |Да |Нет |Нет |
| База данных Azure Analysis Services |Да |Нет |Да |
| Azure Cosmos DB (бета-версия) |Да |Нет |Нет |
| Azure HDInsight Spark (бета-версия) |Да |Нет |Нет |
| Common Data Service (бета-версия) |Да |Нет |Нет |
| comScore Digital Analytix (бета-версия) |Да |Нет |Нет |
| Dynamics 365 для Customer Insights (бета-версия) |Да |Нет |Нет |
| Dynamics 365 for Financials (бета-версия) |Да |Нет |Нет |
| GitHub (бета-версия) |Да |Нет |Нет |
| Google BigQuery (бета-версия) |Да |Нет |Нет |
| База данных IBM Informix (бета-версия) |Да |Нет |Нет |
| IBM Netezza (бета-версия) |Да |Нет |Нет |
| Kusto (бета-версия) |Да |Нет |Нет |
| MailChimp (бета-версия) |Да |Нет |Нет |
| Microsoft Azure Consumption Insights (бета-версия) |Да |Нет |Нет |
| Mixpanel (бета-версия) |Да |Нет |Нет |
| Planview Enterprise (бета-версия) |Да |Нет |Нет |
| Projectplace (бета-версия) |Да |Нет |Нет |
| QuickBooks Online (бета-версия) |Да |Нет |Нет |
| Smartsheet |Да |Нет |Нет |
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

## <a name="list-of-supported-authentication-methods-for-model-refresh"></a>Список поддерживаемых методов проверки подлинности для обновления модели

Сервер отчетов Power BI не поддерживает проверку подлинности на основе OAuth для обновления модели. Некоторые источники данных, такие как Excel или базы данных Access, для подключения к данным используют дополнительный шаг, например файл или веб-приложение.

| **Источник данных** | **Анонимная аутентификация** | **Проверка подлинности с использованием ключа** | **Имя пользователя и пароль** | **Проверка подлинности Windows** |
| --- | --- | --- | --- | --- |
| База данных SQL Server |Нет |Нет |Да |Да |
| службы SQL Server Analysis Services |Нет |Нет |Да |Да |
| Интернет |Да |Нет |Да |Да |
| База данных SQL Azure |Нет |Нет |Да |Нет |
| Хранилище данных SQL Azure |Нет |Нет |Да |Нет |
| Active Directory |нет |нет |Да |Да |
| Amazon Redshift |Нет |Нет |Нет |Нет |
| хранилище BLOB-объектов Azure |Да |Да |Нет |Нет |
| Хранилище озера данных Azure |Нет |Нет |Нет |Нет |
| Azure HDInsight (HDFS) |Нет |Нет |Нет |Нет |
| Azure HDInsight (Spark) |Нет |Нет |Нет |Нет |
| Хранилище таблиц Azure |Нет |Да |Нет |Нет |
| Dynamics 365 (в сети) |Нет |Нет |Нет |Нет |
| Facebook |Нет |Нет |Нет |Нет |
| Папка |Нет |Нет |Нет |Да |
| Google Analytics |Нет |Нет |Нет |Нет |
| Файл Hadoop (HDFS) |Нет |Нет |Нет |Нет |
| База данных IBM DB2 |Нет |Нет |Да |Да |
| Impala |Нет |Нет |Нет |Нет |
| Microsoft Exchange |Нет |Нет |Нет |Нет |
| Microsoft Exchange Online |Нет |Нет |Нет |Нет |
| База данных MySQL |Нет |Нет |Да |Да |
| Веб-канал OData |Да |Да |Да |Да |
| ODBC |Да |Нет |Да |Да |
| OLE DB |Да |Нет |Да |Да |
| Oracle Database |Нет |Нет |Да |Да |
| База данных PostgreSQL |Нет |Нет |Да |Нет |
| Служба Power BI |Нет |Нет |Нет |Нет |
| Сценарий R |Нет |Нет |Нет |Нет |
| Объекты Salesforce |Нет |Нет |Нет |Нет |
| Отчеты SalesForce |Нет |Нет |Нет |Нет |
| Сервер SAP Business Warehouse |Нет |Нет |Да |Нет |
| База данных SAP HANA |Нет |Нет |Да |Да |
| Папка SharePoint (локальная) |Да |Нет |Нет |Да |
| Список SharePoint (локальный) |Да |Нет |Нет |Да |
| Список SharePoint Online |Нет |Нет |Нет |Нет |
| Snowflake |Нет |Нет |Нет |Нет |
| База данных Sybase |Нет |Нет |Да |Да |
| Teradata |Нет |Нет |Да |Да** |
| appFigures (бета-версия) |Нет |Нет |Нет |Нет |
| База данных служб Analysis Services Azure (бета-версия) |Нет |Нет |Нет |Нет |
| Azure Cosmos DB (бета-версия) |Нет |Нет |Нет |Нет |
| Azure HDInsight Spark (бета-версия) |Нет |Нет |Нет |Нет |
| Common Data Service (бета-версия) |Нет |Нет |Нет |Нет |
| comScore Digital Analytix (бета-версия) |Нет |Нет |Нет |Нет |
| Dynamics 365 для Customer Insights (бета-версия) |Нет |Нет |Нет |Нет |
| Dynamics 365 for Financials (бета-версия) |Нет |Нет |Нет |Нет |
| GitHub (бета-версия) |Нет |Нет |Нет |Нет |
| Google BigQuery (бета-версия) |Нет |Нет |Нет |Нет |
| База данных IBM Informix (бета-версия) |Нет |Нет |Нет |Нет |
| IBM Netezza (бета-версия) |Нет |Нет |Нет |Нет |
| Kusto (бета-версия) |Нет |Нет |Нет |Нет |
| MailChimp (бета-версия) |Нет |Нет |Нет |Нет |
| Microsoft Azure Consumption Insights (бета-версия) |Нет |Нет |Нет |Нет |
| Mixpanel (бета-версия) |Нет |Нет |Нет |Нет |
| Planview Enterprise (бета-версия) |Нет |Нет |Нет |Нет |
| Projectplace (бета-версия) |Нет |Нет |Нет |Нет |
| QuickBooks Online (бета-версия) |Нет |Нет |Нет |Нет |
| Smartsheet |Нет |Нет |Нет |Нет |
| Spark (бета-версия) |Нет |Нет |Нет |Нет |
| SparkPost (бета-версия) |Нет |Нет |Нет |Нет |
| SQL Sentry (бета-версия) |Нет |Нет |Нет |Нет |
| Stripe (бета-версия) |Нет |Нет |Нет |Нет |
| SweetIQ (бета-версия) |Нет |Нет |Нет |Нет |
| Troux (бета-версия) |Нет |Нет |Нет |Нет |
| Twilio (бета-версия) |Нет |Нет |Нет |Нет |
| tyGraph (бета-версия) |Нет |Нет |Нет |Нет |
| Vertica (бета-версия); |Нет |Нет |Нет |Нет |
| Visual Studio Team Services (бета-версия) |Нет |Нет |Нет |Нет |
| Webtrends (бета-версия) |Нет |Нет |Нет |Нет |
| ZenDesk (бета-версия) |Нет |Нет |Нет |Нет |

** Проверка подлинности LDAP с помощью Teradata (включается в Power BI Desktop с помощью команды командной строки "setx PBI_EnableTeradataLdap true") не поддерживается для обновления модели.

## <a name="list-of-supported-authentication-methods-for-directquery"></a>Список поддерживаемых методов проверки подлинности для DirectQuery

Сервер отчетов Power BI не поддерживает проверку подлинности на основе OAuth для DirectQuery.

| **Источник данных** | **Анонимная аутентификация** | **Проверка подлинности с использованием ключа** | **Имя пользователя и пароль** | **Проверка подлинности Windows** | **Встроенная аутентификация Windows** |
| --- | --- | --- | --- | --- | --- |
| База данных SQL Server |Нет |Нет |Да |Да |Да |
| службы SQL Server Analysis Services |Нет |Нет |Да |Да |Да |
| База данных SQL Azure |Нет |Нет |Да |Нет |Нет |
| Хранилище данных SQL Azure |Нет |Нет |Да |Нет |Нет |
| Oracle Database |Нет |Нет |Да |Да |Да |
| Сервер SAP Business Warehouse |Нет |Нет |Да |Нет |Нет |
| База данных SAP HANA |Нет |Нет |Да |Да |Да** |
| Teradata |Нет |Нет |Да |Да |Да |

** SAP HANA поддерживает DirectQuery со встроенной проверкой подлинности Windows только при использовании в качестве реляционной базы данных в опубликованном файле Power BI Desktop (PBIX).

## <a name="next-steps"></a>Дальнейшие действия

[Источники данных для отчетов Power BI](../connect-data/power-bi-data-sources.md) в службе Power BI

Подключившись к источнику данных, воспользуйтесь содержащимися в нем данными, чтобы [создать отчет Power BI](quickstart-create-powerbi-report.md).

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)