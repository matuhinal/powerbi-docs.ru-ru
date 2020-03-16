---
title: Источники данных Power BI
description: В этой статье перечислены источники данных, поддерживаемые Power BI, включая сведения о DirectQuery и локальном шлюзе данных.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/10/2020
ms.author: kfollis
ms.openlocfilehash: 1853e710958b5bed0dad011594d9e04ccc99842d
ms.sourcegitcommit: 87b7cb4a2e626711b98387edaa5ff72dc26262bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/10/2020
ms.locfileid: "79041684"
---
# <a name="power-bi-data-sources"></a>Источники данных Power BI

В следующей таблице указаны источники данных, поддерживаемые Power BI для наборов данных, включая сведения о DirectQuery и локальном шлюзе данных. См. сведения о [подключении к источникам данных для потоков данных Power BI](service-dataflows-data-sources.md).

> [!NOTE]
> Существует много соединителей данных для Power BI Desktop, для проверки подлинности которых требуется Internet Explorer 10 (или более поздняя версия). 


| Источник данных | Подключение из версии Desktop | Подключение и обновление из службы | Подключение DirectQuery и активное подключение | Шлюз (поддерживается) | Шлюз (обязательно) |
|---|---|---|---|---|---|---|---|
| База данных Access | Да | Да | Нет | Да <sup>1</sup> | Да |
| ActiveDirectory | Да | Да | Нет | Да | Да |
| Adobe Analytics | Да | Да | Нет | Нет | Нет |
| Amazon Redshift | Да | Да | Да | Да | Нет |
| appFigures | Да | Да | Нет | Нет | Нет |
| Кубы AtScale | Да | Да | Да | Да | Нет |
| Azure Analysis Services | Да | Да | Да | Да <sup>2</sup> | Нет |
| Хранилище BLOB-объектов Azure | Да | Да | Нет | Да | Нет |
| Azure Cosmos DB | Да | Да | Нет | Нет | Нет |
| Управление затратами Azure | Да | Да | Нет | Нет | Нет |
| Azure Data Explorer (Kusto) | Да | Да | Да | Нет | Нет |
| Azure Data Lake Storage 1-го поколения | Да | Да | Нет | Нет | Нет |
| Azure Data Lake Storage 2-го поколения | Да | Да | Нет | Да | Нет |
| Azure DevOps | Да | Да | Нет | Нет | Нет |
| Azure DevOps Server | Да | Да | Нет | Да | Да |
| Azure HDInsight (HDFS) | Да | Да | Нет | Нет | Нет |
| Azure HDInsight Spark | Да | Да | Да | Нет | Нет |
| База данных SQL Azure | Да | Да | Да | Да <sup>2</sup> | Нет |
| Хранилище данных SQL Azure | Да | Да | Да | Да <sup>2</sup> | Нет |
| Хранилище таблиц Azure | Да | Да | Нет | Да | Нет |
| Соединитель BI | Да | Да | Да | Да | Да |
| BI360 — отчеты по бюджетам и финансам | Да | Да | Нет | Нет | Нет |
| Common Data Service | Да | Да | Нет | Нет | Нет |
| Data.World — получение набора данных | Да | Да | Нет | Нет | Нет |
| Denodo | Да | Да | Да | Да | Да |
| Dremio | Да | Да | Да | Да | Да |
| Dynamics 365 (в сети) | Да | Да | Нет | Нет | Нет |
| Dynamics 365 Business Central | Да | Да | Нет | Нет | Нет |
| Dynamics 365 Business Central (локальный) | Да | Да | Нет | Нет | Нет |
| Dynamics 365 Customer Insights | Да | Да | Нет | Нет | Нет |
| Dynamics NAV | Да | Да | Нет | Нет | Нет |
| Источник данных Emigo | Да | Да | Нет | Нет | Нет |
| Entersoft Business Suite | Да | Да | Нет | Нет | Нет |
| Essbase | Да | Да | Да | Да | Да |
| Exasol | Да | Да | Да | Да | Да |
| Excel | Да <sup>3</sup> | Да <sup>3</sup> | Нет | Да <sup>3</sup> | Нет <sup>4</sup> |
| Facebook | Да | Да | Нет | Нет | Нет |
| Файл | Да | Да | Нет | Да | Да |
| Папка | Да | Да | Нет | Да | Да |
| GitHub | Да | Да | Нет | Нет | Нет |
| Google Analytics | Да | Да | Нет | Нет | Нет |
| Google BigQuery | Да | Да | Нет | Нет | Нет |
| Файл Hadoop (HDFS) | Да | Нет | Нет | Нет | Нет |
| HDInsight Interactive Query | Да | Да | Да | Нет | Нет |
| IBM DB2 | Да | Да | Да | Да | Нет |
| База данных IBM Informix | Да | Да | Нет | Да | Нет |
| IBM Netezza | Да | Да | Да | Да | Да |
| Impala | Да | Да | Да | Да | Да |
| Indexima | Да | Да | Да | Да | Да |
| Industrial App Store | Да | Да | Нет | Нет | Нет |
| Information Grid | Да | Да | Нет | Нет | Нет |
| Intersystems IRIS | Да | Да | Да | Да | Да |
| Хранилище данных Intune | Да | Да | Нет | Нет | Нет |
| Jethro ODBC | Да | Да | Да | Да | Да |
| JSON | Да | Да | Нет | Да** | Нет <sup>4</sup> |
| Kyligence Enterprise | Да | Да | Да | Да | Да |
| MailChimp | Да | Да | Нет | Нет | Нет |
| Marketo | Да | Да | Нет | Нет | Нет |
| MarkLogic ODBC | Да | Да | Да | Да | Да |
| Microsoft Azure Consumption Insights | Да | Да | Нет | Нет | Нет |
| Microsoft Exchange | Да | Да | Нет | Да | Нет |
| Microsoft Exchange Online | Да | Да | Нет | Нет | Нет |
| Microsoft Graph Security | Да | Да | Нет | Да | Нет |
| Mixpanel | Да | Да | Нет | Нет | Нет |
| MySQL | Да | Да | Нет | Да | Да |
| OData | Да | Да | Нет | Да | Нет |
| ODBC | Да | Да | Нет | Да | Да |
| OleDb | Да | Да | Нет | Да | Да |
| Oracle | Да | Да | Да | Да | Да |
| Paxata | Да | Да | Нет | Да | Нет |
| PDF | Да | Да | Нет | Да | Нет <sup>4</sup> |
| Planview Enterprise One — CTM | Да | Да | Нет | Нет | Нет |
| Planview Enterprise One — PRM | Да | Да | Нет | Нет | Нет |
| Planview Projectplace | Да | Да | Нет | Нет | Нет |
| PostgreSQL | Да | Да | Да | Да | Нет |
| Потоки данных Power BI | Да | Да | Нет | Нет | Нет |
| Наборы данных Power BI | Да | Да | Да | Нет | Нет |
| Потоки данных Power Platform | Да | Да | Нет | Нет | Нет |
| Скрипт Python | Да | Да <sup>5</sup> | Нет | Да <sup>5</sup> | Да |
| QubolePresto | Да | Да | Да | Да | Да |
| Quick Base | Да | Да | Нет | Да | Да |
| QuickBooks Online | Да | Да | Нет | Нет | Нет |
| Скрипт R | Да | Да <sup>5</sup> | Нет | Да <sup>5</sup> | Нет |
| Roamler | Да | Да | Нет | Да | Нет |
| Объекты SalesForce | Да | Да | Нет | Нет | Нет |
| Отчеты Salesforce | Да | Да | Нет | Нет | Нет |
| Сервер сообщений SAP Business Warehouse | Да | Да | Да | Да | Да |
| Сервер SAP Business Warehouse | Да | Да | Да | Да | Да |
| SAP HANA | Да | Да | Да | Да | Да |
| Папка SharePoint | Да | Да | Нет | Да | Нет <sup>4</sup> |
| Список SharePoint | Да | Да | Нет | Да | Нет <sup>4</sup> |
| Список SharePoint Online | Да | Да | Нет | Да <sup>2</sup> | Нет |
| Smartsheet | Да | Да | Нет | Нет | Нет |
| Снежинка | Да | Да | Да | Да | Нет |
| Spark | Да | Да | Да | Да | Нет |
| SparkPost | Да | Да | Нет | Нет | Нет |
| SQL Server | Да | Да | Да | Да | Да |
| Службы SQL Server Analysis Services | Да | Да | Да | Да | Да |
| Stripe | Да | Да | Нет | Нет | Нет |
| SurveyMonkey | Да | Да | Нет | Да | Нет |
| SweetIQ | Да | Да | Нет | Нет | Нет |
| Sybase | Да | Да | Нет | Да | Да |
| TeamDesk | Да | Да | Нет | Да | Нет |
| Tenforce | Да | Да | Нет | Нет | Нет |
| Teradata | Да | Да | Да | Да | Да |
| Текстовый или CSV-файл | Да | Да | Нет | Да | Нет <sup>4</sup> |
| Twilio | Да | Да | Нет | Нет | Нет |
| tyGraph | Да | Да | Нет | Нет | Нет |
| Vertica | Да | Да | Да | Да | Да |
| Интернет | Да | Да | Нет | Да | Да <sup>6</sup> |
| Webtrends | Да | Да | Нет | Нет | Нет |
| Workforce Dimensions | Да | Да | Нет | Да | Нет |
| XML | Да | Да | Нет | Да | Нет <sup>4</sup> |
| Zendesk | Да | Да | Нет | Нет | Нет |
| | | | | | | | |

<sup>1</sup> Поддерживаются [поставщиком ACE OLEDB](https://www.microsoft.com/download/details.aspx?id=54920), установленным на том же компьютере, что и шлюз.

<sup>2</sup> Поддерживается той же функцией M, что и в локальной версии, что приводит к ограничению параметров аутентификации (шлюз не поддерживает OAuth).

<sup>3</sup> Для файлов Файлы Excel 1997–2003 (XLS) требуется [поставщик ACE OLEDB](https://www.microsoft.com/download/details.aspx?id=54920).

<sup>4</sup> Требуется для локальной версии данной технологии.

<sup>5</sup> Поддерживается только в [персональном шлюзе](service-gateway-personal-mode.md).

<sup>6</sup> Требуется для HTML-, XLS-файлов и баз данных Access.

## <a name="single-sign-on-sso-for-directquery-sources"></a>Единый вход для источников DirectQuery

Если включен параметр единого входа и пользователям предоставлен доступ к отчетам на основе источника данных, Power BI отправляет их учетные данные для проверки подлинности Azure AD в запросах к базовому источнику данных. Это позволяет Power BI использовать параметры безопасности, настроенные на уровне источника данных.
Параметр единого входа применяется ко всем наборам данных, в которых используется этот источник. Это не влияет на метод аутентификации, который применяется для сценариев импорта. Следующие источники данных поддерживают единый вход для подключений через DirectQuery.

- База данных SQL Azure
- Хранилище данных SQL Azure
- Impala
- SAP HANA
- SAP BW
- Сервер сообщений SAP BW
- Снежинка
- Spark
- SQL Server
- Teradata

> [!Note]
> Многофакторная идентификация Azure (MFA) не поддерживается. Чтобы пользователи могли применять единый вход с DirectQuery, исключите их из MFA.

## <a name="next-steps"></a>Дальнейшие действия

[Подключение к данным в Power BI Desktop](desktop-quickstart-connect-to-data.md)  
[Использование DirectQuery в Power BI](desktop-directquery-about.md)  
[Динамические данные служб SQL Server Analysis Services в Power BI](sql-server-analysis-services-tabular-data.md)  
[Что такое локальный шлюз данных?](service-gateway-onprem.md)  
