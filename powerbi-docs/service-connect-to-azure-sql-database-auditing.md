---
title: "Пакет содержимого аудита базы данных SQL"
description: "Пакет содержимого аудита базы данных SQL для Power BI"
services: powerbi
documentationcenter: 
author: SarinaJoan
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
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: eec1af16156e4d4180dd130f4dd285bb78b19903
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2018
---
# <a name="sql-database-auditing-content-pack-for-power-bi"></a>Пакет содержимого аудита базы данных SQL для Power BI
Пакет содержимого [аудита базы данных SQL](http://azure.microsoft.com/documentation/articles/sql-database-auditing-get-started/) Azure для Power BI помогает поддерживать соответствие нормативным требованиям, лучше понимать происходящее в базах данных, а также выявлять расхождения и аномалии, которые могут указывать на проблемы в бизнесе или потенциальные нарушения безопасности. 

Подключитесь к [пакету содержимого аудита базы данных SQL](https://app.powerbi.com/getdata/services/sql-db-auditing) для Power BI.

>[!NOTE]
>Пакет содержимого импортирует данные из всех таблиц, в именах которых есть AuditLogs, и добавляет их в одну таблицу модели данных AuditLogs. В таблицу добавляются последние 250 КБ событий, и данные будут обновляться ежедневно.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getdata.png) 
2. В поле "Службы" выберите "Получить".
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getservices.png) 
3. Выберите **Аудит базы данных SQL** \> **Получить**.
   
   ![](media/service-connect-to-azure-sql-database-auditing/sqldbaudit.png)
4. В окне подключения к аудиту базы данных SQL выполните следующие действия.
   
   - Введите имя учетной записи табличного хранилища Azure или URL-адрес, где хранятся резервные копии журналов.
   
   - Введите имя нужного вам сервера SQL Server. Введите "\*", чтобы загрузить журналы аудита для всех серверов.
   
   - Введите имя нужной вам базы данных SQL. Введите "\*", чтобы загрузить журналы аудита для всех баз данных.
   
   - Введите имя таблицы Azure, которая содержит нужные вам журналы. Введите "\*", чтобы загрузить журналы аудита из всех таблиц, содержащих AuditLogs в имени.
   
   >[!IMPORTANT]
   >Из соображений производительности мы рекомендуем всегда явно указывать имя таблицы, даже если все журналы аудита хранятся в одной таблице.
   
   - Введите дату начала нужных вам журналов аудита. Введите "\*" для загрузки журналов аудита без нижнего предела времени или "1d", чтобы загрузить журналы аудита, начиная с последнего дня.
   
   - Введите дату окончания нужных вам журналов аудита. Введите "\*" для загрузки журналов аудита без верхнего предела времени.
   
   ![](media/service-connect-to-azure-sql-database-auditing/dbauditing_param.png)
5. В качестве метода аутентификации выберите **Ключ**, введите **ключ учетной записи** \> **Войти**.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqlauditing3.png)
6. После импорта данных в Power BI в области навигации слева появятся новая панель мониторинга, отчет и набор данных. Новые элементы отмечены желтой звездочкой \*.
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqldbauditingnewdash.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="next-steps"></a>Дальнейшие действия
[Data sources for the Power BI service](service-get-data.md) (Источники данных для службы PowerBI)
[Приступая к работе с Power BI](service-get-started.md)
