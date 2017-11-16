---
title: "База данных SQL Azure с DirectQuery"
description: "База данных SQL Azure с DirectQuery"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.author: asaxton
ms.openlocfilehash: 83613f0ed915a03b65b90d4bf61e37568b922182
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="azure-sql-database-with-directquery"></a>База данных SQL Azure с DirectQuery
Узнайте, как можно подключиться непосредственно к базе данных SQL Azure и создавать отчеты, в которых используются реальные данные. Можно хранить данные в источнике, а не в Power BI.

При использовании DirectQuery запросы отправляются обратно в Базу данных SQL Azure при просмотре данных в представлении отчетов. Этот процесс рекомендуется пользователям, знакомым с базами данных и сущностями, к которым они подключаются.

**Примечания**

* Укажите полное имя сервера при подключении (см. дополнительные сведения ниже).
* Убедитесь, что настроены правила брандмауэра "[Разрешить доступ к службам Azure](https://msdn.microsoft.com/library/azure/ee621782.aspx)".
* Каждое действие, например выбор столбца или добавление фильтра, отправляет запрос в базу данных.
* Плитки обновляются примерно каждые 15 минут (обновление не требуется планировать). Его можно настроить в разделе дополнительных параметров при подключении.
* Функция вопросов и ответов для наборов данных DirectQuery недоступна.
* Изменения схемы не извлекаются автоматически.

Эти ограничения и примечания могут быть изменены по мере улучшения службы. Ниже описаны инструкции по подключению. 

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop и DirectQuery
Чтобы подключиться к базе данных SQL Azure с помощью DirectQuery, необходимо использовать Power BI Desktop. Такой подход обеспечивает дополнительные возможности и гибкость работы. Отчеты, созданные с помощью Power BI Desktop, затем можно опубликовать в службе Power BI. См. дополнительные сведения о подключении к [базе данных SQL Azure с помощью DirectQuery](desktop-use-directquery.md) в Power BI Desktop. 

## <a name="connecting-through-power-bi"></a>Подключение через Power BI
Возможность подключения к базе данных SQL Azure непосредственно из службы Power BI больше не поддерживается. При выборе [соединителя базы данных SQL Azure](https://app.powerbi.com/getdata/bigdata/azure-sql-database-with-live-connect) вам будет предложено установить подключение в Power BI Desktop. Затем вы сможете публиковать отчеты Power BI Desktop в службе Power BI. 

![](media/service-azure-sql-database-with-direct-connect/azure-sql-database-in-power-bi.png)

### <a name="finding-parameter-values"></a>Поиск значений параметров
Полное имя сервера и имя базы данных можно найти на портале Azure.

![](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

## <a name="next-steps"></a>Дальнейшие действия
[Использование DirectQuery в Power BI Desktop](desktop-use-directquery.md)  
[Приступая к работе с Power BI](service-get-started.md)  
[Получение данных для Power BI](service-get-data.md)  
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

