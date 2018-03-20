---
title: "Источники данных в Power BI Desktop"
description: "Источники данных в Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 04/29/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: ff28f5d43b065ae798e2e9f275c8e8b59e9ee1ce
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2018
---
# <a name="data-sources-in-power-bi-desktop"></a>Источники данных в Power BI Desktop
Power BI Desktop позволяет подключаться к данным из многих разных источников. Полный список доступных источников данных представлен в нижней части этой страницы.

Для подключения к данным выберите **Получить данные** на ленте **Главная** . Если щелкнуть стрелку вниз или текст **Получить данные** на кнопке, откроется меню **Наиболее распространенные** с типами данных, как показано на следующем рисунке.

![](media/desktop-data-sources/data-sources_1.png)

Если щелкнуть **Еще...** в меню **Наиболее распространенные**, отобразится окно **Получить данные**. Чтобы открыть окно **Получить данные** (в обход меню **Наиболее распространенные** ), можно сразу щелкнуть **кнопку со значком** **Получить данные** .

![](media/desktop-data-sources/data-sources_2.png)

> [!NOTE]
> Команда разработчиков Power BI постоянно расширяет список источников данных, доступных для приложения **Power BI Desktop** и **службы Power BI**. Поэтому вы часто будете видеть ранние версии источников данных в процессе разработки с пометкой *Бета-версия* или *Предварительная версия*. Все источники данных с пометкой *Бета-версия* или *Предварительная версия* имеют ограниченную поддержку и функциональные возможности и не должны использоваться в рабочих средах.
> 
> 

## <a name="data-sources"></a>Источники данных
Типы данных разделены на следующие категории:

* Все
* Файл
* База данных
* Azure
* Интернет-службы
* Другие

Категория **Все** включает все типы подключений данных из всех категорий.

Категория **Файл** предоставляет следующие подключения к данным:

* Excel
* Text/CSV.
* XML
* JSON
* Папка
* Папка SharePoint.

На следующем рисунке показано окно **Получить данные** для категории **Файл**.

![](media/desktop-data-sources/data-sources_3.png)

> [!NOTE]
> В предыдущих версиях Power BI Desktop **CSV** и **Text** были отдельными типами подключений данных. Эти соединители данных объединены в **CSV/Text**.
> 
> 

Категория **База данных** предоставляет следующие подключения к данным:

* База данных SQL Server
* База данных Access
* База данных SQL Server Analysis Services
* База данных Oracle
* База данных IBM DB2
* база данных IBM Informix (бета-версия);
* IBM Netezza
* База данных MySQL
* База данных PostgreSQL
* База данных Sybase
* База данных Teradata
* База данных SAP HANA
* Сервер приложений SAP Business Warehouse
* Сервер сообщений SAP Business Warehouse (бета-версия)
* Amazon Redshift
* Impala
* Google BigQuery (бета-версия)
* Snowflake

> [!NOTE]
> Некоторые соединители базы данных необходимо включить: выберите **Файл > Параметры и настройки > Параметры**, затем щелкните **Предварительная версия функций** и включите соединитель. Если некоторые из указанных выше соединителей не отображаются, а вы хотите их использовать, проверьте настройки параметра **Предварительная версия функций**. Также обратите внимание, что все источники данных с пометкой *Бета-версия* или *Предварительная версия* имеют ограниченную поддержку и функциональные возможности и не должны использоваться в рабочих средах.
> 
> 

На следующем рисунке показано окно **Получить данные** для категории **База данных**.

![](media/desktop-data-sources/data-sources_4.png)

Категория **Azure** предоставляет следующие подключения к данным:

* База данных SQL Azure
* Хранилище данных SQL Azure
* База данных Azure Analysis Services
* Хранилище BLOB-объектов Azure
* Хранилище таблиц Azure
* Azure Cosmos DB (бета-версия)
* Azure Data Lake Store
* Azure HDInsight (HDFS)
* Azure HDInsight Spark (бета-версия)
* HDInsight Interactive Query (бета-версия)

На следующем рисунке показано окно **Получить данные** для категории **Azure**.

![](media/desktop-data-sources/data-sources_5.png)

Категория **Интернет-службы** предоставляет следующие подключения к данным:

* Служба Power BI
* Список SharePoint Online
* Microsoft Exchange Online
* Dynamics 365 (в сети);
* Dynamics NAV (бета-версия)
* Dynamics 365 for Financials (бета-версия)
* Common Data Service (бета-версия);
* Microsoft Azure Consumption Insights (бета-версия);
* Visual Studio Team Services (бета-версия)
* Объекты SalesForce
* Отчеты SalesForce
* Google Analytics
* Adobe Analytics
* appFigures (бета-версия)
* comScore Digital Analytix (бета-версия)
* Dynamics 365 для Customer Insights (бета-версия)
* Data.World — получение набора данных (бета-версия)
* Facebook
* GitHub (бета-версия)
* MailChimp (бета-версия)
* Merketo (бета-версия)
* Mixpanel (бета-версия)
* Planview Enterprise One — PRM (бета-версия)
* Planview Projectplace (бета-версия)
* QuickBooks Online (бета-версия)
* Smartsheet (бета-версия)
* SparkPost (бета-версия)
* Stripe (бета-версия)
* SweetIQ (бета-версия)
* Planview Enterprise One — CMT (бета-версия)
* Twilio (бета-версия)
* tyGraph (бета-версия)
* Webtrends (бета-версия)
* ZenDesk (бета-версия)

На следующем рисунке показано окно **Получение данных** для категории **Интернет-службы**.

![](media/desktop-data-sources/data-sources_6b.png)

Категория **Другие** предоставляет следующие подключения к данным:

* Vertica (бета-версия);
* Kusto (бета-версия)
* Веб-приложение
* Список SharePoint
* Веб-канал OData
* Active Directory
* Microsoft Exchange
* Файл Hadoop (HDFS)
* Spark (бета-версия)
* Сценарий R
* ODBC
* OLE DB
* Пустой запрос

На следующем рисунке показано окно **Получение данных** для категории **Другие**.

![](media/desktop-data-sources/data-sources_7a.png)

> [!NOTE]
> Подключение к пользовательским источникам данных, полученным с помощью Azure Active Directory, сейчас не работает.
> 
> 

## <a name="connecting-to-a-data-source"></a>Подключение к источнику данных
Чтобы подключиться к источнику данных, выберите его в окне **Получение данных** и нажмите кнопку **Подключить**. На следующем рисунке выбран источник **Интернет** из категории подключения к данным **Другие** .

![](media/desktop-data-sources/data-sources_7b.png)

Отображается окно подключения, зависящее от типа подключения к данным. Если необходимы учетные данные, вам будет предложено ввести их. На следующем рисунке показан ввод URL-адреса для подключения к интернет-источнику данных.

![](media/desktop-data-sources/datasources_fromwebbox.png)

После ввода URL-адреса или сведений о подключении ресурса нажмите кнопку **ОК**. Power BI Desktop устанавливает подключение к источнику данных и представляет доступные источники данных в области **Навигатор**.

![](media/desktop-data-sources/datasources_fromnavigatordialog.png)

Для загрузки данных можно нажать кнопку **Загрузить** внизу области **Навигатор** или редактировать запрос перед загрузкой данных, нажав кнопку **Изменить** .

Это вся информация о подключении к источникам данных в Power BI Desktop. Попробуйте подключиться к данным из нашего растущего списка источников данных и следите за новостями — список постоянно пополняется.

## <a name="next-steps"></a>Дальнейшие действия
Power BI Desktop предоставляет широкие возможности. Дополнительные сведения об этих возможностях см. в следующих ресурсах.

* [Начало работы с Power BI Desktop](desktop-getting-started.md)
* [Общие сведения о запросах в Power BI Desktop](desktop-query-overview.md)
* [Типы данных в Power BI Desktop](desktop-data-types.md)
* [Формирование и объединение данных в Power BI Desktop](desktop-shape-and-combine-data.md)
* [Общие задачи с запросами в Power BI Desktop](desktop-common-query-tasks.md)    
