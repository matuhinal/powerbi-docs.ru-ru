---
title: Создание ссылки на определенное расположение в мобильных приложениях Power BI
description: Сведения о создании прямой ссылки на определенную панель мониторинга, плитку или отчет в мобильном приложении Power BI с помощью универсального кода ресурса (URI).
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 3be6882219e23a2d22ee03e6805ce3a1e8e08b8f
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Создание ссылки на определенное расположение в мобильных приложениях Power BI
Можно создать и использовать универсальный код ресурса (URI), ведущий к определенному расположению (*прямая ссылка*) в мобильных приложениях Power BI на всех мобильных платформах: iOS, Windows 10 и устройствах Android.

Ссылки URI могут указывать непосредственно на панели мониторинга, плитки и отчеты.

Формат URI определяется назначением прямой ссылки. Чтобы создать прямые ссылки на различные расположения, сделайте следующее. 

## <a name="open-the-power-bi-mobile-app"></a>Открытие мобильного приложения Power BI
Используйте этот универсальный код ресурса (URI), чтобы открыть мобильное приложение Power BI на любом устройстве:

    mspbi://app/


## <a name="open-to-a-specific-dashboard"></a>Открытие определенной панели мониторинга
Этот универсальный код ресурса (URI) открывает определенную панель мониторинга в мобильном приложении Power BI:

    mspbi://app/OpenDashboard?DashboardObjectId=<36-character-dashboard-id>

Чтобы найти 36-символьный идентификатор объекта панели мониторинга, перейдите на требуемую панель мониторинга в службе Power BI (https://powerbi.com). Например, см. выделенный отрезок этого URL-адреса:

https://powerbi.com/groups/me/dashboards/**61b7e871-cb98-48ed-bddc-6572c921e270**

Если панель мониторинга находится не в группе "Моя рабочая область", добавьте `&GroupObjectId=<36-character-group-id>` перед идентификатором панели мониторинга или после него. Например: 

mspbi://app/OpenDashboard?DashboardObjectId=e684af3a-9e7f-44ee-b679-b9a1c59b5d60 **&GroupObjectId=8cc900cc-7339-467f-8900-fec82d748248**

Обратите внимание на амперсанд (&) между ними.

## <a name="open-to-a-specific-tile-in-focus"></a>Открытие определенной плитки в режиме фокусировки
Этот универсальный код ресурса (URI) открывает определенную плитку в режиме фокусировки в мобильном приложении Power BI:

    mspbi://app/OpenTile?DashboardObjectId=<36-character-dashboard-id>&TileObjectId=<36-character-tile-id>

Чтобы найти 36-символьные идентификаторы объектов панели мониторинга и плитки, перейдите на требуемую панель мониторинга в службе Power BI (https://powerbi.com) и откройте плитку в режиме фокусировки. Например, см. выделенные отрезки этого URL-адреса:

https://powerbi.com/groups/me/dashboards/**3784f99f-b460-4d5e-b86c-b6d8f7ec54b7**/tiles/**565f9740-5131-4648-87f2-f79c4cf9c5f5**/infocus

Для этой плитки универсальный код ресурса (URI) будет следующим:

    mspbi://app/OpenTile?DashboardObjectId=3784f99f-b460-4d5e-b86c-b6d8f7ec54b7&TileObjectId=565f9740-5131-4648-87f2-f79c4cf9c5f5

Обратите внимание на амперсанд (&) между ними.

Если панель мониторинга находится не в группе "Моя рабочая область", добавьте `&GroupObjectId=<36-character-group-id>`.

## <a name="open-to-a-specific-report"></a>Открытие определенного отчета
Этот универсальный код ресурса (URI) открывает определенный отчет в мобильном приложении Power BI:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>

Чтобы найти 36-символьный идентификатор объекта отчета, перейдите к требуемому отчету в службе Power BI (https://powerbi.com). Например, см. выделенный отрезок этого URL-адреса:

https://powerbi.com/groups/me/reports/**df9f0e94-31df-450b-b97f-4461a7e4d300**

## <a name="open-to-a-specific-report-page"></a>Открытие определенной страницы отчета
Этот универсальный код ресурса (URI) открывает определенную страницу отчета в мобильном приложении Power BI:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>&reportPage=ReportSection<number>

Название страницы отчета состоит из текстового блока ReportSection и определенного номера. Снова откройте отчет в службе Power BI (https://powerbi.com) и перейдите на требуемую страницу отчета. 

Например, см. выделенный отрезок этого URL-адреса:

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**ReportSection11**

## <a name="open-in-full-screen-mode"></a>Открытие плитки в полноэкранном режиме
Добавьте параметр, выделенный полужирным шрифтом, чтобы открыть определенный отчет в полноэкранном режиме:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>**&openFullScreen=true**

Например: 

mspbi://app/OpenReport?ReportObjectId=500217de-50f0-4af1-b345-b81027224033&openFullScreen=true

## <a name="add-context-optional"></a>Добавление контекста (необязательно)
Вы также можете добавить строку контекста. Затем, если вам понадобится связаться с нами, мы используем этот контекст для фильтрации наших данных в вашем приложении. Добавьте `&context=<app-name>` к ссылке.

Например, см. выделенный отрезок этого URL-адреса: 

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**&context=SlackDeepLink**

## <a name="next-steps"></a>Дальнейшие действия
Ваши отзывы помогают нам решить, что следует добавить в следующие выпуски, поэтому не забудьте проголосовать за функции, которые хотели бы увидеть в мобильных приложениях Power BI. 

* [Приложения Power BI для мобильных устройств](mobile-apps-for-mobile-devices.md)
* Подпишитесь на страницу @MSPowerBI в Twitter
* Присоединяйтесь к обсуждению в [сообществе Power BI](http://community.powerbi.com/).
* [Приступая к работе с Power BI](service-get-started.md)

