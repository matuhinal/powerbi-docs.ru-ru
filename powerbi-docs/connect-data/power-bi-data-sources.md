---
title: Источники данных Power BI
description: В этой статье перечислены источники данных, поддерживаемые Power BI, включая сведения о DirectQuery и локальном шлюзе данных.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/11/2020
ms.author: davidi
ms.openlocfilehash: 926569e783dad7a97b91e2e5c1752401d21d6612
ms.sourcegitcommit: 376ea86f69545444f975378cbf63e54c2f75faa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90084060"
---
# <a name="power-bi-data-sources"></a>Источники данных Power BI

В следующей таблице указаны источники данных, поддерживаемые Power BI для наборов данных, включая сведения о DirectQuery и локальном шлюзе данных. См. сведения о [подключении к источникам данных для потоков данных Power BI](../transform-model/service-dataflows-data-sources.md).

| Источник данных | Подключение из версии Desktop | Подключение и обновление из службы | Подключение DirectQuery и активное подключение | Шлюз (поддерживается) | Шлюз (обязательно) |
|---|---|---|---|---|---|---|---|
| База данных Access | Да | Да | Нет | Да <sup>1</sup> | Да |
| ActiveDirectory | Да | Да | нет | Да | Да |
| Adobe Analytics | Да | Да | нет | Нет | Нет |
| Amazon Redshift | Да | Да | Да | Да | Нет |
| appFigures | Да | Да | нет | Нет | Нет |
| Кубы AtScale | Да | Да | Да | Да | Нет |
| Службы Azure Analysis Services | Да | Да | Да | нет | Нет |
| хранилище BLOB-объектов Azure | Да | Да | нет | Да | Нет |
| Azure Cosmos DB | Да | Да | нет | Нет | Нет |
| Управление затратами Azure | Да | Да | нет | Нет | Нет |
| Azure Data Explorer (Kusto) | Да | Да | Да | Да | Нет |
| Хранилище Azure Data Lake Storage 1-го поколения | Да | Да | нет | Нет | Нет |
| Azure Data Lake Storage 2-го поколения | Да | Да | нет | Да | Нет |
| Azure DevOps | Да | Да | нет | Нет | Нет |
| Azure DevOps Server | Да | Да | нет | Да | Да |
| Azure HDInsight (HDFS) | Да | Да | нет | Нет | Нет |
| Azure HDInsight — Spark | Да | Да | Да | нет | Нет |
| База данных SQL Azure | Да | Да | Да | Да <sup>2</sup> | Нет |
| Хранилище данных SQL Azure | Да | Да | Да | Да <sup>2</sup> | Нет |
| Хранилище таблиц Azure | Да | Да | нет | Да | Нет |
| Соединитель BI | Да | Да | Да | Да | Да |
| BI360 — отчеты по бюджетам и финансам | Да | Да | нет | Нет | Нет |
| Common Data Service | Да | Да | нет | Нет | Нет |
| Data.World — получение набора данных | Да | Да | нет | Нет | Нет |
| Denodo | Да | Да | Да | Да | Да |
| Dremio | Да | Да | Да | Да | Да |
| Dynamics 365 (в сети) | Да | Да | нет | Нет | Нет |
| Dynamics 365 Business Central | Да | Да | нет | Нет | Нет |
| Dynamics 365 Business Central (локальный) | Да | Да | нет | Нет | Нет |
| Dynamics 365 Customer Insights | Да | Да | нет | Нет | Нет |
| Dynamics NAV | Да | Да | нет | Нет | Нет |
| Источник данных Emigo | Да | Да | нет | Нет | Нет |
| Entersoft Business Suite | Да | Да | нет | Нет | Нет |
| Essbase | Да | Да | Да | Да | Да |
| Exasol | Да | Да | Да | Да | Да |
| Excel | Да <sup>3</sup> | Да <sup>3</sup> | Нет | Да <sup>3</sup> | Нет <sup>4</sup> |
| Facebook | Да | Да | нет | Нет | Нет |
| Файл | Да | Да | нет | Да | Да |
| Папка | Да | Да | нет | Да | Да |
| GitHub | Да | Да | нет | Нет | Нет |
| Google Analytics | Да | Да | нет | Нет | Нет |
| Google BigQuery | Да | Да | Да | нет | Нет |
| Файл Hadoop (HDFS) | Да | нет | Нет | Нет | Нет |
| HDInsight Interactive Query | Да | Да | Да | нет | Нет |
| IBM DB2 | Да | Да | Да | Да | Нет |
| База данных IBM Informix | Да | Да | нет | Да | Нет |
| IBM Netezza | Да | Да | Да | Да | Да |
| Impala | Да | Да | Да | Да | Да |
| Indexima | Да | Да | Да | Да | Да |
| Industrial App Store | Да | Да | нет | Нет | Нет |
| Information Grid | Да | Да | нет | Нет | Нет |
| Intersystems IRIS | Да | Да | Да | Да | Да |
| Хранилище данных Intune | Да | Да | нет | Нет | Нет |
| Jethro ODBC | Да | Да | Да | Да | Да |
| JSON | Да | Да | Нет | Да** | Нет <sup>4</sup> |
| Kyligence Enterprise | Да | Да | Да | Да | Да |
| MailChimp | Да | Да | нет | Нет | Нет |
| Marketo | Да | Да | нет | Нет | Нет |
| MarkLogic ODBC | Да | Да | Да | Да | Да |
| Microsoft Azure Consumption Insights | Да | Да | нет | Нет | Нет |
| Microsoft Exchange | Да | Да | нет | Да | Нет |
| Microsoft Exchange Online | Да | Да | нет | Нет | Нет |
| Безопасность Microsoft Graph | Да | Да | нет | Да | Нет |
| Mixpanel | Да | Да | нет | Нет | Нет |
| MySQL | Да | Да | нет | Да | Да |
| OData | Да | Да <sup>7</sup> | Нет | Да | Нет |
| ODBC | Да | Да | нет | Да | Да |
| OleDb | Да | Да | нет | Да | Да |
| Oracle; | Да | Да | Да | Да | Да |
| Paxata <sup>8</sup> | Да | Да | нет | Да | Нет |
| PDF | Да | Да | нет | Да | Нет <sup>4</sup> |
| Planview Enterprise One — CTM | Да | Да | нет | Нет | Нет |
| Planview Enterprise One — PRM | Да | Да | нет | Нет | Нет |
| Planview Projectplace | Да | Да | нет | Нет | Нет |
| PostgreSQL | Да | Да | Да | Да | Нет |
| Потоки данных Power BI | Да | Да | нет | Нет | Нет |
| Наборы данных Power BI | Да | Да | Да | нет | Нет |
| Потоки данных Power Platform | Да | Да | нет | Нет | Нет |
| Сценарий Python | Да | Да <sup>5</sup> | Нет | Да <sup>5</sup> | Да |
| QubolePresto | Да | Да | Да | Да | Да |
| Quick Base | Да | Да | нет | Да | Да |
| QuickBooks Online | Да | Да | нет | Нет | Нет |
| Скрипт R | Да | Да <sup>5</sup> | Нет | Да <sup>5</sup> | Нет |
| Roamler | Да | Да | нет | Да | Нет |
| Объекты Salesforce | Да | Да | нет | Нет | Нет |
| Отчеты SalesForce | Да | Да | нет | Нет | Нет |
| Сервер сообщений SAP Business Warehouse | Да | Да | Да | Да | Да |
| Сервер SAP Business Warehouse | Да | Да | Да | Да | Да |
| SAP HANA | Да | Да | Да | Да | Да |
| Папка SharePoint | Да | Да | нет | Да | Нет <sup>4</sup> |
| SharePoint | Да | Да | нет | Да | Нет <sup>4</sup> |
| Список SharePoint Online | Да | Да | Нет | Да <sup>2</sup> | Нет |
| Smartsheet | Да | Да | нет | Нет | Нет |
| Snowflake | Да | Да | Да | Да | Нет |
| Spark | Да | Да | Да | Да | Нет |
| SparkPost | Да | Да | нет | Нет | Нет |
| SQL Server | Да | Да | Да | Да | Да |
| службы SQL Server Analysis Services | Да | Да | Да | Да | Да |
| Stripe | Да | Да | нет | Нет | Нет |
| SurveyMonkey | Да | Да | нет | Да | Нет |
| SweetIQ | Да | Да | нет | Нет | Нет |
| Sybase | Да | Да | нет | Да | Да |
| TeamDesk | Да | Да | нет | Да | Нет |
| Tenforce | Да | Да | нет | Нет | Нет |
| Teradata | Да | Да | Да | Да | Да |
| Text/CSV | Да | Да | нет | Да | Нет <sup>4</sup> |
| Twilio | Да | Да | нет | Нет | Нет |
| tyGraph | Да | Да | нет | Нет | Нет |
| Vertica | Да | Да | Да | Да | Да |
| Интернет | Да | Да | нет | Да | Да <sup>6</sup> |
| Webtrends | Да | Да | нет | Нет | Нет |
| Workforce Dimensions | Да | Да | нет | Да | Нет |
| XML | Да | Да | нет | Да | Нет <sup>4</sup> |
| Zendesk | Да | Да | нет | Нет | Нет |
| | | | | | | | |

<sup>1</sup> Поддерживаются [поставщиком ACE OLEDB](https://www.microsoft.com/download/details.aspx?id=54920), установленным на том же компьютере, что и шлюз.

<sup>2</sup> Поддерживается той же функцией M, что и в локальной версии, что приводит к ограничению параметров аутентификации (шлюз не поддерживает OAuth).

<sup>3</sup> Для файлов Файлы Excel 1997–2003 (XLS) требуется [поставщик ACE OLEDB](https://www.microsoft.com/download/details.aspx?id=54920).

<sup>4</sup> Требуется для локальной версии данной технологии.

<sup>5</sup> Поддерживается только в [персональном шлюзе](service-gateway-personal-mode.md).

<sup>6</sup> Требуется для HTML-, XLS-файлов и баз данных Access.

<sup>7</sup> Служба Power BI не поддерживает каналы OData, требующие проверки подлинности.

<sup>8</sup> Paxata поддерживается в версии Power BI Desktop, оптимизированной для сервера отчетов Power BI. Это решение не поддерживается в отчетах Power BI, опубликованных на сервере отчетов Power BI. Список поддерживаемых источников данных см. в статье [Источники данных отчетов Power BI в решении "Сервер отчетов Power BI"](../report-server/data-sources.md).

## <a name="considerations-and-limitations"></a>Рекомендации и ограничения

- Для проверки подлинности во многих соединителях данных для Power BI Desktop требуется Internet Explorer 10 (или более поздняя версия). 
- Некоторые источники данных, доступные в Power BI Desktop, оптимизированы для сервера отчетов Power BI, но не поддерживаются для публикации на сервере отчетов Power BI. Список поддерживаемых источников данных см. в статье [Источники данных отчетов Power BI в решении "Сервер отчетов Power BI"](../report-server/data-sources.md).

## <a name="single-sign-on-sso-for-directquery-sources"></a>Единый вход для источников DirectQuery

Если включен параметр единого входа и пользователям предоставлен доступ к отчетам на основе источника данных, Power BI отправляет их учетные данные для проверки подлинности Azure AD в запросах к базовому источнику данных. Это позволяет Power BI использовать параметры безопасности, настроенные на уровне источника данных.
Параметр единого входа применяется ко всем наборам данных, в которых используется этот источник. Это не влияет на метод аутентификации, который применяется для сценариев импорта. Следующие источники данных поддерживают единый вход для подключений через DirectQuery.

- База данных SQL Azure
- Хранилище данных SQL Azure
- Impala
- SAP HANA
- SAP BW
- Сервер сообщений SAP BW
- Snowflake
- Spark
- SQL Server
- Teradata

> [!Note]
> Многофакторная идентификация Azure (MFA) не поддерживается. Чтобы пользователи могли применять единый вход с DirectQuery, исключите их из MFA.

## <a name="next-steps"></a>Дальнейшие действия

[Подключение к данным в Power BI Desktop](desktop-quickstart-connect-to-data.md)  
[Использование DirectQuery в Power BI](desktop-directquery-about.md)  
[Динамические данные служб SQL Server Analysis Services в Power BI](sql-server-analysis-services-tabular-data.md)  
[Что такое локальный шлюз данных?](service-gateway-onprem.md)  
[Источники данных отчетов Power BI в решении "Сервер отчетов Power BI"](../report-server/data-sources.md)
