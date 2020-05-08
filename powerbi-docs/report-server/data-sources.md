---
title: Источники данных отчетов Power BI в решении "Сервер отчетов Power BI"
description: Отчеты Power BI можно подключать к разным источникам данных. В зависимости от способа использования данных доступны различные источники данных.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 04/08/2020
ms.author: maggies
ms.openlocfilehash: 166f72a717c99457e1d6b8e9a1f30535a9b4686f
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "80979852"
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Источники данных отчетов Power BI в решении "Сервер отчетов Power BI"
Отчеты Power BI можно подключать к разным источникам данных. В зависимости от способа использования данных доступны различные источники данных. Данные можно импортировать или запрашивать напрямую с помощью DirectQuery или активного подключения к службам SQL Server Analysis Services.

Эти источники данных относятся к отчетам Power BI, которые используются в решении "Сервер отчетов Power BI" Сведения об источниках данных, которые поддерживаются для отчетов с разбивкой на страницы (RDL), см. в разделе [Источники данных, поддерживаемые службами Reporting Services (SSRS)](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

> [!IMPORTANT]
> Для настройки запланированного обновления в отчете Power BI Desktop должны поддерживаться все источники данных.
>  

## <a name="list-of-supported-data-sources"></a>Список поддерживаемых источников данных

Другие источники данных могут работать, даже если они не входят в список поддерживаемых.

| **Источник данных** | **Кэшированные данные** | **Запланированное обновление** | **Активный запрос или запрос DirectQuery** |
| --- | --- | --- | --- |
| База данных SQL Server |Yes |Yes |Yes |
| Службы SQL Server Analysis Services |Yes |Yes |Yes |
| База данных SQL Azure |Yes |Yes |Yes |
| Хранилище данных SQL Azure |Yes |Yes |Yes |
| Excel |Yes |Yes |Нет |
| База данных Access |Yes |Yes |Нет |
| Active Directory |Yes |Yes |Нет |
| Amazon Redshift |Yes |Нет |Нет |
| Хранилище BLOB-объектов Azure |Yes |Yes |Нет |
| Azure Data Lake Store |Yes |Нет |Нет |
| Azure HDInsight (HDFS) |Yes |Нет |Нет |
| Azure HDInsight (Spark) |Yes |Нет |Нет |
| Хранилище таблиц Azure |Yes |Yes |Нет |
| Dynamics 365 (Online) |Yes |Нет |Нет |
| Facebook |Yes |Нет |Нет |
| Папка |Yes |Yes |Нет |
| Google Analytics |Yes |Нет |Нет |
| Файл Hadoop (HDFS) |Yes |Нет |Нет |
| База данных IBM DB2 |Yes |Yes |Нет |
| Impala |Yes |Нет |Нет |
| JSON |Yes |Yes |Нет |
| Microsoft Exchange |Yes |Нет |Нет |
| Microsoft Exchange Online |Yes |Нет |Нет |
| База данных MySQL |Yes |Yes |Нет |
| Веб-канал OData |Yes |Yes |Нет |
| ODBC |Yes |Yes |Нет |
| OLE DB |Yes |Yes |Нет |
| База данных Oracle |Yes |Yes |Yes |
| База данных PostgreSQL |Yes |Yes |Нет |
| Служба Power BI |Нет |Нет |Нет |
| Сценарий R |Yes |Нет |Нет |
| Объекты SalesForce |Yes |Нет |Нет |
| Отчеты Salesforce |Yes |Нет |Нет |
| сервер SAP Business Warehouse; |Yes |Yes |Yes |
| База данных SAP HANA |Yes |Yes |Yes |
| Папка SharePoint (локальная) |Yes |Yes |Нет |
| Список SharePoint (локальный) |Yes |Yes |Нет |
| Список SharePoint Online |Yes |Нет |Нет |
| Снежинка |Yes |Нет |Нет |
| База данных Sybase |Yes |Yes |Нет |
| Teradata |Yes |Yes |Yes |
| Text/CSV. |Yes |Yes |Нет |
| Интернет |Yes |Yes |Нет |
| XML |Yes |Yes |Нет |
| appFigures (бета-версия) |Yes |Нет |Нет |
| База данных Azure Analysis Services |Yes |Нет |Yes |
| Azure Cosmos DB (бета-версия) |Yes |Нет |Нет |
| Azure HDInsight Spark (бета-версия) |Yes |Нет |Нет |
| Common Data Service (бета-версия); |Yes |Нет |Нет |
| comScore Digital Analytix (бета-версия) |Yes |Нет |Нет |
| Dynamics 365 для Customer Insights (бета-версия) |Yes |Нет |Нет |
| Dynamics 365 for Financials (бета-версия) |Yes |Нет |Нет |
| GitHub (бета-версия) |Yes |Нет |Нет |
| Google BigQuery (бета-версия) |Yes |Нет |Нет |
| база данных IBM Informix (бета-версия); |Yes |Нет |Нет |
| IBM Netezza (бета-версия) |Yes |Нет |Нет |
| Kusto (бета-версия) |Yes |Нет |Нет |
| MailChimp (бета-версия) |Yes |Нет |Нет |
| Microsoft Azure Consumption Insights (бета-версия) |Yes |Нет |Нет |
| Mixpanel (бета-версия) |Yes |Нет |Нет |
| Planview Enterprise (бета-версия) |Yes |Нет |Нет |
| Projectplace (бета-версия) |Yes |Нет |Нет |
| QuickBooks Online (бета-версия) |Yes |Нет |Нет |
| Smartsheet |Yes |Нет |Нет |
| Spark (бета-версия) |Yes |Нет |Нет |
| SparkPost (бета-версия) |Yes |Нет |Нет |
| SQL Sentry (бета-версия) |Yes |Нет |Нет |
| Stripe (бета-версия) |Yes |Нет |Нет |
| SweetIQ (бета-версия) |Yes |Нет |Нет |
| Troux (бета-версия) |Yes |Нет |Нет |
| Twilio (бета-версия) |Yes |Нет |Нет |
| tyGraph (бета-версия) |Yes |Нет |Нет |
| Vertica (бета-версия); |Yes |Нет |Нет |
| Visual Studio Team Services (бета-версия) |Yes |Нет |Нет |
| Webtrends (бета-версия) |Yes |Нет |Нет |
| ZenDesk (бета-версия) |Yes |Нет |Нет |

> [!IMPORTANT]
> Предполагается, что безопасность на уровне строк, настроенная в источнике данных, будет работать с определенными функциями DirectQuery (SQL Server, базой данных SQL Azure, Oracle и Teradata) и активными подключениями, если в вашей среде выполнена надлежащая настройка Kerberos.
> 
> 

## <a name="list-of-supported-authentication-methods-for-model-refresh"></a>Список поддерживаемых методов проверки подлинности для обновления модели

Сервер отчетов Power BI не поддерживает проверку подлинности на основе OAuth для обновления модели. Некоторые источники данных, такие как Excel или базы данных Access, для подключения к данным используют дополнительный шаг, например файл или веб-приложение.

| **Источник данных** | **Анонимная проверка подлинности** | **Проверка подлинности с использованием ключа** | **Имя пользователя и пароль** | **Проверка подлинности Windows** |
| --- | --- | --- | --- | --- |
| База данных SQL Server |Нет |Нет |Yes |Yes |
| Службы SQL Server Analysis Services |Нет |Нет |Yes |Yes |
| Интернет |Yes |Нет |Yes |Yes |
| База данных SQL Azure |Нет |Нет |Yes |Нет |
| Хранилище данных SQL Azure |Нет |Нет |Yes |Нет |
| Active Directory |Нет |Нет |Yes |Yes |
| Amazon Redshift |Нет |Нет |Нет |Нет |
| Хранилище BLOB-объектов Azure |Yes |Yes |Нет |Нет |
| Azure Data Lake Store |Нет |Нет |Нет |Нет |
| Azure HDInsight (HDFS) |Нет |Нет |Нет |Нет |
| Azure HDInsight (Spark) |Нет |Нет |Нет |Нет |
| Хранилище таблиц Azure |Нет |Yes |Нет |Нет |
| Dynamics 365 (Online) |Нет |Нет |Нет |Нет |
| Facebook |Нет |Нет |Нет |Нет |
| Папка |Нет |Нет |Нет |Yes |
| Google Analytics |Нет |Нет |Нет |Нет |
| Файл Hadoop (HDFS) |Нет |Нет |Нет |Нет |
| База данных IBM DB2 |Нет |Нет |Yes |Yes |
| Impala |Нет |Нет |Нет |Нет |
| Microsoft Exchange |Нет |Нет |Нет |Нет |
| Microsoft Exchange Online |Нет |Нет |Нет |Нет |
| База данных MySQL |Нет |Нет |Yes |Yes |
| Веб-канал OData |Yes |Yes |Yes |Yes |
| ODBC |Yes |Нет |Yes |Yes |
| OLE DB |Yes |Нет |Yes |Yes |
| База данных Oracle |Нет |Нет |Yes |Yes |
| База данных PostgreSQL |Нет |Нет |Yes |Нет |
| Служба Power BI |Нет |Нет |Нет |Нет |
| Сценарий R |Нет |Нет |Нет |Нет |
| Объекты SalesForce |Нет |Нет |Нет |Нет |
| Отчеты Salesforce |Нет |Нет |Нет |Нет |
| сервер SAP Business Warehouse; |Нет |Нет |Yes |Нет |
| База данных SAP HANA |Нет |Нет |Yes |Yes |
| Папка SharePoint (локальная) |Yes |Нет |Нет |Yes |
| Список SharePoint (локальный) |Yes |Нет |Нет |Yes |
| Список SharePoint Online |Нет |Нет |Нет |Нет |
| Снежинка |Нет |Нет |Нет |Нет |
| База данных Sybase |Нет |Нет |Yes |Yes |
| Teradata |Нет |Нет |Yes |Да** |
| appFigures (бета-версия) |Нет |Нет |Нет |Нет |
| База данных служб Analysis Services Azure (бета-версия) |Нет |Нет |Нет |Нет |
| Azure Cosmos DB (бета-версия) |Нет |Нет |Нет |Нет |
| Azure HDInsight Spark (бета-версия) |Нет |Нет |Нет |Нет |
| Common Data Service (бета-версия); |Нет |Нет |Нет |Нет |
| comScore Digital Analytix (бета-версия) |Нет |Нет |Нет |Нет |
| Dynamics 365 для Customer Insights (бета-версия) |Нет |Нет |Нет |Нет |
| Dynamics 365 for Financials (бета-версия) |Нет |Нет |Нет |Нет |
| GitHub (бета-версия) |Нет |Нет |Нет |Нет |
| Google BigQuery (бета-версия) |Нет |Нет |Нет |Нет |
| база данных IBM Informix (бета-версия); |Нет |Нет |Нет |Нет |
| IBM Netezza (бета-версия) |Нет |Нет |Нет |Нет |
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

| **Источник данных** | **Анонимная проверка подлинности** | **Проверка подлинности с использованием ключа** | **Имя пользователя и пароль** | **Проверка подлинности Windows** | **Интегрированная проверка подлинности Windows** |
| --- | --- | --- | --- | --- | --- |
| База данных SQL Server |Нет |Нет |Yes |Yes |Yes |
| Службы SQL Server Analysis Services |Нет |Нет |Yes |Yes |Yes |
| База данных SQL Azure |Нет |Нет |Yes |Нет |Нет |
| Хранилище данных SQL Azure |Нет |Нет |Yes |Нет |Нет |
| База данных Oracle |Нет |Нет |Yes |Yes |Yes |
| сервер SAP Business Warehouse; |Нет |Нет |Yes |Нет |Нет |
| База данных SAP HANA |Нет |Нет |Yes |Yes |Да** |
| Teradata |Нет |Нет |Yes |Yes |Yes |

** SAP HANA поддерживает DirectQuery со встроенной проверкой подлинности Windows только при использовании в качестве реляционной базы данных в опубликованном файле Power BI Desktop (PBIX).

## <a name="next-steps"></a>Дальнейшие действия
Подключившись к источнику данных, воспользуйтесь содержащимися в нем данными, чтобы [создать отчет Power BI](quickstart-create-powerbi-report.md).

У вас имеются и другие вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
