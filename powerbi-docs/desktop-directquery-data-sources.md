---
title: Источники данных, поддерживаемые DirectQuery в Power BI
description: Список источников данных, которые можно использовать для DirectQuery.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/01/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 098447f4d0c0b1dc9534c91e84827c4cefb8850c
ms.sourcegitcommit: fdb54145f9bc93b312409c15c603749f3a4a876e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "52452552"
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Источники данных, поддерживаемые DirectQuery в Power BI
**Power BI Desktop** и **служба Power BI** имеют много источников данных, к которым можно подключиться и получить доступ. В этой статье описывается, какие источники данных для Power BI поддерживают метод подключения **DirectQuery**. Дополнительные сведения о DirectQuery см. в статье [**Power BI и DirectQuery**](desktop-directquery-about.md).

Следующие источники данных поддерживают DirectQuery в Power BI:

* Amazon Redshift
* Azure HDInsight Spark (бета-версия)
* База данных SQL Azure
* Хранилище данных SQL Azure
* Google BigQuery (бета-версия)
* База данных IBM DB2
* IBM Netezza (бета-версия)
* Impala (версии 2.x)
* База данных Oracle (версии 12 и более поздней)
* Сервер приложений SAP Business Warehouse
* Сервер сообщений SAP Business Warehouse (бета-версия)
* SAP HANA
* Snowflake
* Spark (бета-версия) (версии 0.9 и более поздней)
* SQL Server
* База данных Teradata
* Vertica (бета-версия)

Источники данных, после имени которых указана **(бета-версия)** или **(предварительная версия)**, могут быть изменены и не поддерживаются для использования в рабочей среде. Они также могут не поддерживаться после публикации отчета в **службе Power BI**. Это означает, что открытие опубликованного отчета или просмотр набора данных может привести к ошибке.

Единственное различие между источниками данных в **бета-версии** и **предварительной версии** в том, что для использования источники **предварительной версии** необходимо включить как предварительную версию функции. Для включения соединителя данных **предварительной версии** в **Power BI Desktop** щелкните **Файл > Параметры и настройки > Параметры** и затем выберите **Предварительная версия функций**.

> [!NOTE]
> Запросы DirectQuery к SQL Server требуют проверки подлинности с использованием актуальных учетных данных Windows или учетных данных для доступа к базе данных. Другие учетные данные не поддерживаются.
>

## <a name="on-premises-gateway-requirements"></a>Требования для локального шлюза
В следующей таблице указано, необходим ли **локальный шлюз данных** для подключения к определенному источнику данных после публикации отчета в **службе Power BI**.

| Источник | Требуется шлюз? |
| --- | --- |
| SQL Server |Да |
| База данных SQL Azure |Нет |
| Хранилище данных SQL Azure |Нет |
| SAP HANA |Да |
| База данных Oracle |Да |
| База данных Teradata |Да |
| Amazon Redshift |Нет |
| Impala (версии 2.x) |Да |
| Снежинка |Да |
| Spark (бета-версия) версии 0.9 и более поздней |Да |
| Azure HDInsight Spark (бета-версия) |Нет |
| IBM Netezza |Да |
| Сервер приложений SAP Business Warehouse |Да |
| Сервер сообщений SAP Business Warehouse |Пока не поддерживается в **службе Power BI** |
| Google BigQuery |Нет |


## <a name="next-steps"></a>Дальнейшие действия
Дополнительные сведения о DirectQuery см. в следующих статьях:

* [Power BI и DirectQuery](desktop-directquery-about.md)
* [DirectQuery и SAP HANA](desktop-directquery-sap-hana.md)
* [Использование DirectQuery и SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md)
* [Локальный шлюз данных](service-gateway-onprem.md)

