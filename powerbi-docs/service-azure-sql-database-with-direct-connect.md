---
title: База данных SQL Azure с DirectQuery
description: База данных SQL Azure с DirectQuery
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/20/2018
LocalizationGroup: Data from databases
ms.openlocfilehash: f03f4933566a8c18510ef0ce07b71db61ecfa8fd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770598"
---
# <a name="azure-sql-database-with-directquery"></a>База данных SQL Azure с DirectQuery

Узнайте, как можно подключиться непосредственно к базе данных SQL Azure и создавать отчеты, в которых используются реальные данные. Можно хранить данные в источнике, а не в Power BI.

При использовании DirectQuery запросы отправляются обратно в Базу данных SQL Azure при просмотре данных в представлении отчетов. Этот процесс рекомендуется пользователям, знакомым с базами данных и сущностями, к которым они подключаются.

**Примечания**

* Укажите полное имя сервера при подключении (см. дополнительные сведения ниже).
* Убедитесь, что в правилах брандмауэра [разрешен доступ к службам Azure](https://msdn.microsoft.com/library/azure/ee621782.aspx).
* Каждое действие, например выбор столбца или добавление фильтра, отправляет запрос в базу данных.
* Плитки обновляются каждый час (обновление не требуется планировать). его можно настроить в разделе дополнительных параметров при подключении;
* Функция вопросов и ответов для наборов данных DirectQuery недоступна.
* Изменения схемы не извлекаются автоматически.

Эти ограничения и примечания могут быть изменены по мере улучшения службы. Ниже описаны инструкции по подключению.

> [!Important]
> Мы улучшили параметры подключения к базе данных SQL Azure.  Для наиболее эффективного подключения к источнику данных базы данных SQL Azure используйте Power BI Desktop.  После создания модели и отчета их можно опубликовать в службе Power BI.  Прямое подключение к базе данных SQL Azure в службе Power BI теперь признано нерекомендуемым.

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop и DirectQuery

Чтобы подключиться к базе данных SQL Azure с помощью DirectQuery, необходимо использовать Power BI Desktop. Такой подход обеспечивает дополнительные возможности и гибкость работы. Отчеты, созданные с помощью Power BI Desktop, затем можно опубликовать в службе Power BI. См. дополнительные сведения о подключении к [базе данных SQL Azure с помощью DirectQuery](desktop-use-directquery.md) в Power BI Desktop.

## <a name="single-sign-on"></a>Единый вход

Когда вы опубликуете набор данных Azure SQL DirectQuery в службе, вы сможете включить для пользователей единый вход через OAuth2 Azure Active Directory (Azure AD).

Чтобы включить единый вход, перейдите к параметрам набора данных, откройте вкладку **Источники данных** и установите флажок единого входа.

![Настройка диалогового окна DQ для Azure SQL](media/service-azure-sql-database-with-direct-connect/sso-dialog.png)

Если включен параметр единого входа и пользователям предоставлен доступ к отчетам на основе источника данных, Power BI отправляет их учетные данные для аутентификации Azure AD в запросах к базе данных Azure SQL. Это позволяет Power BI использовать параметры безопасности, настроенные на уровне источника данных.

Параметр единого входа применяется ко всем наборам данных, в которых используется этот источник. Это не влияет на метод аутентификации, который применяется для сценариев импорта.

> [!Note]
> Многофакторная идентификация Azure (MFA) не поддерживается. Чтобы пользователи могли применять единый вход с Azure SQL DirectQuery, исключите их из MFA.

## <a name="finding-parameter-values"></a>Поиск значений параметров

Полное имя сервера и имя базы данных можно найти на портале Azure.

![Новое обновление порта Azure](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![Обновление портала Azure](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

## <a name="next-steps"></a>Дальнейшие действия

* [Использование DirectQuery в Power BI Desktop](desktop-use-directquery.md)  
* [Что такое Power BI?](power-bi-overview.md)  
* [Получение данных для Power BI](service-get-data.md)  

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)
