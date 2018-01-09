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
ms.date: 12/18/2017
ms.author: asaxton
ms.openlocfilehash: 6ee8ab6d30d84857de9cd415ee58caade4e94a57
ms.sourcegitcommit: ea247cb3cfc1cac076d4b076c1ad8e2fc37e15a1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2017
---
# <a name="azure-sql-database-with-directquery"></a>База данных SQL Azure с DirectQuery
Узнайте, как можно подключиться непосредственно к базе данных SQL Azure и создавать отчеты, в которых используются реальные данные. Можно хранить данные в источнике, а не в Power BI.

При использовании DirectQuery запросы отправляются обратно в Базу данных SQL Azure при просмотре данных в представлении отчетов. Этот процесс рекомендуется пользователям, знакомым с базами данных и сущностями, к которым они подключаются.

**Примечания**

* Укажите полное имя сервера при подключении (см. дополнительные сведения ниже).
* Убедитесь, что в правилах брандмауэра [разрешен доступ к службам Azure](https://msdn.microsoft.com/library/azure/ee621782.aspx).
* Каждое действие, например выбор столбца или добавление фильтра, отправляет запрос в базу данных.
* Плитки обновляются каждый час (обновление не требуется планировать). его можно настроить в разделе дополнительных параметров при подключении;
* функция вопросов и ответов для наборов данных DirectQuery недоступна;
* Изменения схемы не извлекаются автоматически.

Эти ограничения и примечания могут быть изменены по мере улучшения службы. Ниже описаны инструкции по подключению. 

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop и DirectQuery
Чтобы подключиться к базе данных SQL Azure с помощью DirectQuery, необходимо использовать Power BI Desktop. Такой подход обеспечивает дополнительные возможности и гибкость работы. Отчеты, созданные с помощью Power BI Desktop, затем можно опубликовать в службе Power BI. См. дополнительные сведения о подключении к [базе данных SQL Azure с помощью DirectQuery](desktop-use-directquery.md) в Power BI Desktop. 

## <a name="single-sign-on"></a>Единый вход

Когда вы опубликуете набор данных Azure SQL DirectQuery в службе, вы сможете включить для пользователей единый вход через OAuth2 Azure Active Directory (Azure AD). 

Чтобы включить единый вход, перейдите к параметрам набора данных, откройте вкладку **Источники данных** и установите флажок единого входа.

![Настройка диалогового окна DQ для Azure SQL](media/service-azure-sql-database-with-direct-connect/sso-dialog.png)

Если включен параметр единого входа и пользователям предоставлен доступ к отчетам на основе источника данных, Power BI отправляет их учетные данные для аутентификации Azure AD в запросах к базе данных Azure SQL. Это позволяет Power BI использовать параметры безопасности, настроенные на уровне источника данных.

Параметр единого входа применяется ко всем наборам данных, в которых используется этот источник. Это не влияет на метод аутентификации, который применяется для сценариев импорта.

## <a name="finding-parameter-values"></a>Поиск значений параметров
Полное имя сервера и имя базы данных можно найти на портале Azure.

![](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

## <a name="next-steps"></a>Дальнейшие действия
[Использование DirectQuery в Power BI Desktop](desktop-use-directquery.md)  
[Приступая к работе с Power BI](service-get-started.md)  
[Получение данных для Power BI](service-get-data.md)  
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)
