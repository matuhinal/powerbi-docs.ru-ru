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
ms.date: 06/13/2019
LocalizationGroup: Data from databases
ms.openlocfilehash: 2363b9da3ac46ce9fd49f19a00950a4a3cf23502
ms.sourcegitcommit: 30ee81f8c54fd7e4d47d7e3ffcf0e6c3bb68f6c2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2019
ms.locfileid: "67468095"
---
# <a name="azure-sql-database-with-directquery"></a>База данных SQL Azure с DirectQuery

Узнайте, как можно подключиться непосредственно к базе данных SQL Azure и создавать отчеты, в которых используются реальные данные. Можно хранить данные в источнике, а не в Power BI.

При использовании DirectQuery запросы отправляются обратно в Базу данных SQL Azure при просмотре данных в представлении отчетов. Этот процесс рекомендуется пользователям, знакомым с базами данных и сущностями, к которым они подключаются.

**Примечания**

* Укажите полное имя сервера при подключении (см. дополнительные сведения ниже).
* Убедитесь, что в правилах брандмауэра [разрешен доступ к службам Azure](https://msdn.microsoft.com/library/azure/ee621782.aspx).
* Каждое действие, например выбор столбца или добавление фильтра, отправляет запрос в базу данных.
* Плитки обновляются каждый час (обновление не требуется планировать). Можно указать частоту обновления в разделе дополнительных параметров при подключении.
* Функция вопросов и ответов для наборов данных DirectQuery недоступна.
* Изменения схемы не извлекаются автоматически.

Эти ограничения и примечания могут быть изменены по мере улучшения службы. Ниже описаны инструкции по подключению.

> [!Important]
> Мы улучшили параметры подключения к базе данных SQL Azure.  Для наиболее эффективного подключения к источнику данных базы данных SQL Azure используйте Power BI Desktop.  После создания модели и отчета их можно опубликовать в службе Power BI.  Прямое подключение к базе данных SQL Azure в службе Power BI теперь признано нерекомендуемым.

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop и DirectQuery

Чтобы подключиться к базе данных SQL Azure с помощью DirectQuery, необходимо использовать Power BI Desktop. Такой подход обеспечивает дополнительные возможности и гибкость работы. Отчеты, созданные с помощью Power BI Desktop, затем можно опубликовать в службе Power BI. См. дополнительные сведения о подключении к [базе данных SQL Azure с помощью DirectQuery](desktop-use-directquery.md) в Power BI Desktop.

## <a name="find-parameter-values"></a>Поиск значений параметров

Полное имя сервера и имя базы данных можно найти на портале Azure.

![Очередное обновление портала Azure](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![Обновление портала Azure](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

[!INCLUDE [direct-query-sso](includes/direct-query-sso.md)]

## <a name="next-steps"></a>Дальнейшие действия

* [Использование DirectQuery в Power BI Desktop](desktop-use-directquery.md)  
* [Что такое Power BI?](power-bi-overview.md)  
* [Получение данных для Power BI](service-get-data.md)  

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)
