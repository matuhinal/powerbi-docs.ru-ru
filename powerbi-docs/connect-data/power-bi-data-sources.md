---
title: Источники данных Power BI
description: В этой статье перечислены источники данных, поддерживаемые Power BI, включая сведения о DirectQuery и локальном шлюзе данных.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/01/2020
ms.author: kfollis
ms.openlocfilehash: 7fcd5b5f7a6365aac597186618ce2b18fcc44d7f
ms.sourcegitcommit: 49daa8964c6e30347e29e7bfc015762e2cf494b3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84273398"
---
# <a name="power-bi-data-sources"></a>Источники данных Power BI

В следующей таблице указаны источники данных, поддерживаемые Power BI для наборов данных, включая сведения о DirectQuery и локальном шлюзе данных. См. сведения о [подключении к источникам данных для потоков данных Power BI](../transform-model/service-dataflows-data-sources.md).

> [!NOTE]
> Существует много соединителей данных для Power BI Desktop, для проверки подлинности которых требуется Internet Explorer 10 (или более поздняя версия). 


| Источник данных | Подключение из версии Desktop | Подключение и обновление из службы | Подключение DirectQuery и активное подключение | Шлюз (поддерживается) | Шлюз (обязательно) |
|---|---|---|---|---|---|---|---|
| База данных Access | Yes | Yes | Нет | Да <sup>1</sup> | Yes |
| ActiveDirectory | Yes | Yes | Нет | Yes | Yes |
| Adobe Analytics | Yes | Yes | Нет | Нет | Нет |
| Amazon Redshift | Yes | Yes | Yes | Yes | Нет |
| Рисунки приложений | Yes | Yes | Нет | Нет | Нет |
| Кубы AtScale | Yes | Yes | Yes | Yes | Нет |
| Azure Analysis Services | Yes | Yes | Yes | Нет | Нет |
| Хранилище BLOB-объектов Azure | Yes | Yes | Нет | Yes | Нет |
| Azure Cosmos DB | Yes | Yes | Нет | Нет | Нет |
| Управление затратами Azure | Yes | Yes | Нет | Нет | Нет |
| Azure Data Explorer (Kusto) | Yes | Yes | Yes | Нет | Нет |
| Azure Data Lake Storage 1-го поколения | Yes | Yes | Нет | Нет | Нет |
| Azure Data Lake Storage 2-го поколения | Yes | Yes | Нет | Yes | Нет |
| Azure DevOps | Yes | Yes | Нет | Нет | Нет |
| Azure DevOps Server | Yes | Yes | Нет | Yes | Yes |
| Azure HDInsight (HDFS) | Yes | Yes | Нет | Нет | Нет |
| Azure HDInsight Spark | Yes | Yes | Yes | Нет | Нет |
| База данных SQL Azure | Yes | Yes | Yes | Да <sup>2</sup> | Нет |
| Хранилище данных SQL Azure | Yes | Yes | Yes | Да <sup>2</sup> | Нет |
| Хранилище таблиц Azure | Yes | Yes | Нет | Yes | Нет |
| Соединитель BI | Yes | Yes | Yes | Yes | Yes |
| BI360 — отчеты по бюджетам и финансам | Yes | Yes | Нет | Нет | Нет |
| Common Data Service | Yes | Yes | Нет | Нет | Нет |
| Data.World — получение набора данных | Yes | Yes | Нет | Нет | Нет |
| Denodo | Yes | Yes | Yes | Yes | Yes |
| Dremio | Yes | Yes | Yes | Yes | Yes |
| Dynamics 365 (Online) | Yes | Yes | Нет | Нет | Нет |
| Dynamics 365 Business Central | Yes | Yes | Нет | Нет | Нет |
| Dynamics 365 Business Central (локальный) | Yes | Yes | Нет | Нет | Нет |
| Dynamics 365 Customer Insights | Yes | Yes | Нет | Нет | Нет |
| Dynamics NAV | Yes | Yes | Нет | Нет | Нет |
| Источник данных Emigo | Yes | Yes | Нет | Нет | Нет |
| Entersoft Business Suite | Yes | Yes | Нет | Нет | Нет |
| Essbase | Yes | Yes | Yes | Yes | Yes |
| Exasol | Yes | Yes | Yes | Yes | Yes |
| Excel | Да <sup>3</sup> | Да <sup>3</sup> | Нет | Да <sup>3</sup> | Нет <sup>4</sup> |
| Facebook | Yes | Yes | Нет | Нет | Нет |
| Файл | Yes | Yes | Нет | Yes | Yes |
| Папка | Yes | Yes | Нет | Yes | Yes |
| GitHub | Yes | Yes | Нет | Нет | Нет |
| Google Analytics | Yes | Yes | Нет | Нет | Нет |
| Google BigQuery | Yes | Yes | Да | Нет | Нет |
| Файл Hadoop (HDFS) | Yes | Нет | Нет | Нет | Нет |
| HDInsight Interactive Query | Yes | Yes | Yes | Нет | Нет |
| IBM DB2 | Yes | Yes | Yes | Yes | Нет |
| База данных IBM Informix | Yes | Yes | Нет | Yes | Нет |
| IBM Netezza | Yes | Yes | Yes | Yes | Yes |
| Impala | Yes | Yes | Yes | Yes | Yes |
| Indexima | Yes | Yes | Yes | Yes | Yes |
| Industrial App Store | Yes | Yes | Нет | Нет | Нет |
| Information Grid | Yes | Yes | Нет | Нет | Нет |
| Intersystems IRIS | Yes | Yes | Yes | Yes | Yes |
| Хранилище данных Intune | Yes | Yes | Нет | Нет | Нет |
| Jethro ODBC | Yes | Yes | Yes | Yes | Yes |
| JSON | Yes | Yes | Нет | Да** | Нет <sup>4</sup> |
| Kyligence Enterprise | Yes | Yes | Yes | Yes | Yes |
| MailChimp | Yes | Yes | Нет | Нет | Нет |
| Marketo | Yes | Yes | Нет | Нет | Нет |
| MarkLogic ODBC | Yes | Yes | Yes | Yes | Yes |
| Microsoft Azure Consumption Insights | Yes | Yes | Нет | Нет | Нет |
| Microsoft Exchange | Yes | Yes | Нет | Yes | Нет |
| Microsoft Exchange Online | Yes | Yes | Нет | Нет | Нет |
| Безопасность Microsoft Graph | Yes | Yes | Нет | Yes | Нет |
| Mixpanel | Yes | Yes | Нет | Нет | Нет |
| MySQL | Yes | Yes | Нет | Yes | Yes |
| OData | Yes | Yes | Нет | Yes | Нет |
| ODBC | Yes | Yes | Нет | Yes | Yes |
| OleDb | Yes | Yes | Нет | Yes | Yes |
| Oracle | Yes | Yes | Yes | Yes | Yes |
| Paxata | Yes | Yes | Нет | Yes | Нет |
| PDF; | Yes | Yes | Нет | Yes | Нет <sup>4</sup> |
| Planview Enterprise One — CTM | Yes | Yes | Нет | Нет | Нет |
| Planview Enterprise One — PRM | Yes | Yes | Нет | Нет | Нет |
| Planview Projectplace | Yes | Yes | Нет | Нет | Нет |
| PostgreSQL | Yes | Yes | Yes | Yes | Нет |
| Потоки данных Power BI | Yes | Yes | Нет | Нет | Нет |
| Наборы данных Power BI | Yes | Yes | Yes | Нет | Нет |
| Потоки данных Power Platform | Yes | Yes | Нет | Нет | Нет |
| Скрипт Python | Yes | Да <sup>5</sup> | Нет | Да <sup>5</sup> | Yes |
| QubolePresto | Yes | Yes | Yes | Yes | Yes |
| Quick Base | Yes | Yes | Нет | Yes | Yes |
| QuickBooks Online | Yes | Yes | Нет | Нет | Нет |
| Сценарий R | Yes | Да <sup>5</sup> | Нет | Да <sup>5</sup> | Нет |
| Roamler | Yes | Yes | Нет | Yes | Нет |
| Объекты SalesForce | Yes | Yes | Нет | Нет | Нет |
| Отчеты Salesforce | Yes | Yes | Нет | Нет | Нет |
| Сервер сообщений SAP Business Warehouse | Yes | Yes | Yes | Yes | Yes |
| Сервер SAP Business Warehouse | Yes | Yes | Yes | Yes | Yes |
| SAP HANA | Yes | Yes | Yes | Yes | Yes |
| Папка SharePoint | Yes | Yes | Нет | Yes | Нет <sup>4</sup> |
| Список SharePoint | Yes | Yes | Нет | Yes | Нет <sup>4</sup> |
| Список SharePoint Online | Yes | Yes | Нет | Да <sup>2</sup> | Нет |
| Smartsheet | Yes | Yes | Нет | Нет | Нет |
| Снежинка | Yes | Yes | Yes | Yes | Нет |
| Spark | Yes | Yes | Yes | Yes | Нет |
| SparkPost. | Yes | Yes | Нет | Нет | Нет |
| SQL Server | Yes | Yes | Yes | Yes | Yes |
| Службы SQL Server Analysis Services | Yes | Yes | Yes | Yes | Yes |
| Stripe | Yes | Yes | Нет | Нет | Нет |
| SurveyMonkey | Yes | Yes | Нет | Yes | Нет |
| SweetIQ | Yes | Yes | Нет | Нет | Нет |
| Sybase | Yes | Yes | Нет | Yes | Yes |
| TeamDesk | Yes | Yes | Нет | Yes | Нет |
| Tenforce | Yes | Yes | Нет | Нет | Нет |
| Teradata | Yes | Yes | Yes | Yes | Yes |
| Text/CSV. | Yes | Yes | Нет | Yes | Нет <sup>4</sup> |
| Twilio | Yes | Yes | Нет | Нет | Нет |
| tyGraph | Yes | Yes | Нет | Нет | Нет |
| Vertica | Yes | Yes | Yes | Yes | Yes |
| Интернет | Yes | Yes | Нет | Yes | Да <sup>6</sup> |
| Webtrends | Yes | Yes | Нет | Нет | Нет |
| Workforce Dimensions | Yes | Yes | Нет | Yes | Нет |
| XML | Yes | Yes | Нет | Yes | Нет <sup>4</sup> |
| Zendesk | Yes | Yes | Нет | Нет | Нет |
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
- Хранилище данных SQL Azure
- Impala
- SAP HANA
- SAP BW
- Сервер сообщений SAP BW
- Снежинка
- Spark
- SQL Server
- Teradata

> [!Note]
> Многофакторная идентификация Azure (MFA) не поддерживается. Чтобы пользователи могли применять единый вход с DirectQuery, исключите их из MFA.

## <a name="next-steps"></a>Дальнейшие действия

[Подключение к данным в Power BI Desktop](desktop-quickstart-connect-to-data.md)  
[Использование DirectQuery в Power BI](desktop-directquery-about.md)  
[Динамические данные служб SQL Server Analysis Services в Power BI](sql-server-analysis-services-tabular-data.md)  
[Что такое локальный шлюз данных?](service-gateway-onprem.md)  
