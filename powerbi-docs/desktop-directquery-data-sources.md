---
title: "Источники данных, поддерживаемые DirectQuery в Power BI"
description: "Список источников данных, которые можно использовать для DirectQuery."
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 10/26/2017
ms.author: davidi
ms.openlocfilehash: 9817011491f65f84201c4d26ee04aa5cd8704ab1
ms.sourcegitcommit: b3ee37e1587f1269ee7dd9daf1685a06dea3b50c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2017
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Источники данных, поддерживаемые DirectQuery в Power BI
**Power BI Desktop** и **служба Power BI** имеют много источников данных, к которым можно подключиться и получить доступ. В этой статье описывается, какие источники данных для Power BI поддерживают метод подключения **DirectQuery**. Дополнительные сведения о DirectQuery см. в статье [**Power BI и DirectQuery**](desktop-directquery-about.md).

Следующие источники данных поддерживают DirectQuery в Power BI:

* Amazon Redshift
* Azure HDInsight Spark (бета-версия)
* База данных SQL Azure
* Хранилище данных SQL Azure
* Google BigQuery (бета-версия)
* IBM Netezza (бета-версия)
* Impala (версии 2.x)
* База данных Oracle (версии 12 и более поздней)
* SAP Business Warehouse (бета-версия)
* SAP HANA
* Snowflake
* Spark (бета-версия) (версии 0.9 и более поздней)
* SQL Server
* База данных Teradata
* Vertica (бета-версия);

Источники данных, после имени которых указана **(бета-версия)** или **(предварительная версия)**, могут быть изменены и не поддерживаются для использования в рабочей среде. Они также могут не поддерживаться после публикации отчета в **службе Power BI**. Это означает, что открытие опубликованного отчета или просмотр набора данных может привести к ошибке.

Единственное различие между источниками данных в **бета-версии** и **предварительной версии** в том, что для использования источники **предварительной версии** необходимо включить как предварительную версию функции. Для включения соединителя данных **предварительной версии** в **Power BI Desktop** щелкните **Файл > Параметры и настройки**, а затем выберите **Настройки > Параметры > Предварительная версия функций**.

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
| Snowflake (предварительная версия) |Пока не поддерживается в **службе Power BI** |
| Spark (бета-версия) версии 0.9 и более поздней |Пока не поддерживается в **службе Power BI** |
| Azure HDInsight Spark (бета-версия) |Пока не поддерживается в **службе Power BI** |
| IBM Netezza (бета-версия) |Пока не поддерживается в **службе Power BI** |
| SAP Business Warehouse (бета-версия) |Пока не поддерживается в **службе Power BI** |

## <a name="next-steps"></a>Дальнейшие действия
Дополнительные сведения о DirectQuery см. в следующих статьях:

* [Power BI и DirectQuery](desktop-directquery-about.md)
* [DirectQuery и SAP HANA](desktop-directquery-sap-hana.md)
* [Использование DirectQuery и SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md)
* [Локальный шлюз данных](service-gateway-onprem.md)

