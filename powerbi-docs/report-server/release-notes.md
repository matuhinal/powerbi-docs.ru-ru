---
title: "Заметки о выпуске сервера отчетов Power BI"
description: "В этом разделе описаны ограничения и проблемы, связанные с использованием сервера отчетов Power BI."
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
ms.date: 11/01/2017
ms.author: asaxton
ms.openlocfilehash: ffd0d1ce38a989121225a666ca4aa924df130216
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi-report-server-release-notes"></a>Заметки о выпуске сервера отчетов Power BI
В этом разделе описаны ограничения и проблемы, связанные с использованием сервера отчетов Power BI.

Чтобы скачать сервер отчетов Power BI и службу Power BI Desktop, оптимизированную для сервера отчетов Power BI, перейдите на страницу [Локальная работа с отчетами с использованием сервера Power BI Report Server](https://powerbi.microsoft.com/report-server/).

## <a name="october-2017"></a>Октябрь 2017 г.
* Поддержка для импортированных данных в отчетах Power BI
* Возможность просмотра книг Excel на веб-портале. Это возможно после настройки Office Online Server.
* Поддержка новых визуальных элементов Power BI "Матрица" и "Таблица".
* Поддержка REST API

## <a name="june-2017"></a>Июнь 2017 г.
* На июнь 2017 г. новые элементы отсутствуют.

## <a name="may-2017"></a>Май 2017 г.
* Для работы с сервером отчетов Power BI отчеты Power BI должны создаваться с использованием приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI. Чтобы скачать Power BI Desktop, перейдите по ссылке в верхней части этой страницы.
* Отчеты Power BI поддерживают только динамические подключения к службам Analysis Services (табличные или многомерные модели).
* Визуальные элементы R не поддерживаются.

**Проблема и ее последствия для клиентов**. Если службы SQL Server Reporting Services и сервер отчетов Power BI установлены на одном компьютере, после удаления одного из этих компонентов вы не сможете больше подключиться к серверу отчетов с помощью диспетчера конфигурации сервера отчетов.

**Решение**. Чтобы решить проблему, после удаления одного из серверов нужно сделать следующее.

1. Запустите командную строку в режиме администратора.
2. Перейдите в каталог, где установлен сервер отчетов.
   
    *Папка сервера отчетов Power BI по умолчанию: C:\Program Files\Сервер отчетов Microsoft Power BI*
   
    *Папка служб SQL Server Reporting Services по умолчанию: C:\Program Files\Microsoft SQL Server Reporting Services*
3. Затем перейдите к следующей папке. Это будет либо *SSRS*, либо *PBIRS* — в зависимости от того, какой компонент остался.
4. Откройте папку WMI.
5. Выполните следующую команду.
   
    ```
    regsvr32 /i ReportingServicesWMIProvider.dll
    ```
   
    Если отобразится следующая ошибка, игнорируйте ее.
   
    ```
    The module "ReportingServicesWMIProvider.dll" was loaded but the entry-point DLLInstall was not found. Make sure that "ReportingServicesWMIProvider.dll" is a valid DLL or OCX file and then try again.
    ```

## <a name="next-steps"></a>Дальнейшие действия
[Новые возможности сервера отчетов Power BI](whats-new.md)  
[Руководство пользователя](user-handbook-overview.md)  
[Руководство администратора](admin-handbook-overview.md)  
[Краткое руководство по установке сервера отчетов Power BI](quickstart-install-report-server.md)  
[Install Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder) (Установка построителя отчетов)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714) (Скачивание SQL Server Data Tools (SSDT))

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

