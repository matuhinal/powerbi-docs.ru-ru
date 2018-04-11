---
title: Подключение к Planview Enterprise с помощью Power BI
description: Planview Enterprise для Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 2376b639ad6a6ca843f997e52cedcce4c9832a7a
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-planview-enterprise-with-power-bi"></a>Подключение к Planview Enterprise с помощью Power BI
С помощью пакета содержимого Planview Enterprise вы можете визуализировать данные о ресурсах и управлении работой совершенно новыми способами непосредственно в Power BI. Используйте учетные данные Planview Enterprise для интерактивного просмотра инвестиционных расходов на портфель, определить состояние работ и соответствие бюджету, а также узнать, насколько хорошо проекты соответствуют стратегическим целям вашей компании. Также можно расширить готовую информационную панель и отчеты, чтобы получить именно те ценные сведения, которые необходимы вам.

Подключение к [пакету содержимого Planview Enterprise для Power BI](https://app.powerbi.com/getdata/services/planview-enterprise)

>[!NOTE]
>Для импорта данных Planview Enterprise в Power BI вы должны быть пользователем Planview Enterprise, а для вашей роли должна быть включена функция просмотра портала отчетов Reporting Portal Viewer. Дополнительные требования см. в разделе ниже.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
    ![](media/service-connect-to-planview/get.png)
2. В поле **Службы** выберите **Получить**.
   
    ![](media/service-connect-to-planview/services.png)
3. На странице Power BI выберите **Planview Enterprise**, а затем выберите **Получить**.  
    ![](media/service-connect-to-planview/planview.png)
4. В текстовом поле Planview Enterprise URL (URL-адрес Planview Enterprise) введите URL-адрес сервера Planview Enterprise, который вы хотите использовать. В текстовом поле Planview Enterprise Database (База данных Planview Enterprise) введите имя базы данных, Planview Enterprise, а затем нажмите кнопку "Далее".  
    ![](media/service-connect-to-planview/params.png)
5. В списке "Метод проверки подлинности" выберите **Обычная** , если это значение еще не установлено. Введите **Имя пользователя** и **Пароль** для своей учетной записи и выберите **Вход**.  
   ![](media/service-connect-to-planview/creds.png)
6. На левой панели выберите Planview Enterprise в списке информационных панелей.  
     Power BI импортирует данные Planview Enterprise в информационную панель. Обратите внимание, что загрузка данных может занять некоторое время.  
    ![](media/service-connect-to-planview/dashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="system-requirements"></a>Требования к системе
Для импорта данных Planview Enterprise в Power BI вы должны быть пользователем Planview Enterprise, а для вашей роли должна быть включена функция просмотра портала отчетов Reporting Portal Viewer. Дополнительные требования см. в разделе ниже.

Эта процедура предполагает, что вы уже выполнили вход на домашнюю страницу Microsoft Power BI с помощью учетной записи Power BI. Если у вас нет учетной записи Power BI, создайте новую бесплатную учетную запись Power BI на домашней странице Power BI, а затем нажмите кнопку "Получить данные".

## <a name="next-steps"></a>Дальнейшие действия:

[Приступая к работе с Power BI](service-get-started.md)

[Получение данных для Power BI](service-get-data.md)