---
title: Источники данных, поддерживаемые DirectQuery в Power BI
description: Список источников данных, которые можно использовать для DirectQuery.
author: davidiseminger
ms.author: davidi
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/16/2019
LocalizationGroup: Connect to data
ms.openlocfilehash: a9e8d2aaab7c0b3ed1daea32486260d09bc6f6a2
ms.sourcegitcommit: 83e1e162a037f352e542bd5c198a3c98f5db23c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72511640"
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Источники данных, поддерживаемые DirectQuery в Power BI

**Power BI Desktop** и **служба Power BI** имеют много источников данных, к которым можно подключиться и получить доступ. В этой статье описывается, какие источники данных для Power BI поддерживают метод подключения **DirectQuery**. Дополнительные сведения о DirectQuery см. в статье [**Power BI и DirectQuery**](desktop-directquery-about.md).

Следующие источники данных поддерживают DirectQuery в Power BI:

* Amazon Redshift
* AtScale (бета-версия)
* Azure Data Explorer
* Azure HDInsight Spark
* [База данных SQL Azure](service-azure-sql-database-with-direct-connect.md)
* [Хранилище данных SQL Azure](service-azure-sql-data-warehouse-with-direct-connect.md)
* Denodo
* Google BigQuery
* HDInsight Interactive Query
* IBM DB2 (поставщик Майкрософт)
* IBM Netezza
* Impala (версии 2.x)
* MarkLogic
* База данных Oracle (версии 12 и более поздней)
* Oracle Essbase
* PostgreSQL
* Сервер приложений SAP Business Warehouse
* Сервер сообщений SAP Business Warehouse
* SAP HANA
* Снежинка
* Spark (версии 0.9 и более поздней)
* SQL Server
* Teradata
* Vertica

Источники данных, после имени которых указана **(бета-версия)** или **(предварительная версия)** , могут быть изменены и не поддерживаются для использования в рабочей среде. Они также могут не поддерживаться после публикации отчета в **службе Power BI**. Это означает, что открытие опубликованного отчета или просмотр набора данных может привести к ошибке.

Единственное различие между источниками данных в **бета-версии** и **предварительной версии** в том, что для использования источники **предварительной версии** необходимо включить как предварительную версию функции. Для включения соединителя данных **предварительной версии** в **Power BI Desktop** щелкните **Файл > Параметры и настройки > Параметры** и затем выберите **Предварительная версия функций**.

> [!NOTE]
> Запросы DirectQuery к SQL Server требуют проверки подлинности с использованием актуальных учетных данных Windows или учетных данных для доступа к базе данных. Другие учетные данные не поддерживаются.
>

## <a name="on-premises-gateway-requirements"></a>Требования для локального шлюза
В следующей таблице указано, необходим ли **локальный шлюз данных** для подключения к определенному источнику данных после публикации отчета в **службе Power BI**.

| Источник | Требуется шлюз? |
| --- | --- |
| Amazon Redshift |Нет |
| Azure HDInsight Spark (бета-версия) |Нет |
| База данных SQL Azure |Нет |
| Хранилище данных SQL Azure |Нет |
| Google BigQuery |Нет |
| IBM Netezza |Да |
| IBM DB2 (поставщик IBM) |Да |
| IBM DB2 (поставщик Майкрософт) |Нет |
| База данных IBM Informix |Нет |
| Impala (версии 2.x) |Да |
| MySQL |Да |
| ODBC |Да |
| База данных Oracle |Да |
| PostgreSQL |Да |
| Сервер приложений SAP Business Warehouse |Да |
| Сервер сообщений SAP Business Warehouse |Да |
| SAP HANA |Да |
| Снежинка |Да |
| Spark (бета-версия) версии 0.9 и более поздней |Да |
| SQL Server |Да |
| Sybase |Да |
| Teradata |Да |
| Vertica |Да |


## <a name="single-sign-on-sso-for-directquery-sources"></a>Единый вход для источников DirectQuery

Если включен параметр единого входа и пользователям предоставлен доступ к отчетам на основе источника данных, Power BI отправляет их учетные данные для проверки подлинности Azure AD в запросах к базовому источнику данных. Это позволяет Power BI использовать параметры безопасности, настроенные на уровне источника данных.

Параметр единого входа применяется ко всем наборам данных, в которых используется этот источник. Это не влияет на метод аутентификации, который применяется для сценариев импорта. Следующие источники данных поддерживают единый вход для подключений через DirectQuery.

- База данных SQL Azure
- Хранилище данных SQL Azure
- Impala
- SAP HANA
- SAP BW
- Сервер сообщений SAP BW (предварительная версия)
- Spark
- SQL Server
- Teradata

> [!Note]
> Многофакторная идентификация Azure (MFA) не поддерживается. Чтобы пользователи могли применять единый вход с DirectQuery, исключите их из MFA.

## <a name="next-steps"></a>Дальнейшие действия
Дополнительные сведения о DirectQuery см. в следующих статьях:

* [Power BI и DirectQuery](desktop-directquery-about.md)
* [DirectQuery и SAP HANA](desktop-directquery-sap-hana.md)
* [Использование DirectQuery и SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md)
* [Локальный шлюз данных](service-gateway-onprem.md)

