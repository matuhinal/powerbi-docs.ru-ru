---
title: Просмотр локальных отчетов и ключевых показателей эффективности в мобильных приложениях Power BI
description: Мобильные приложения Power BI обеспечивают динамический мобильный доступ с поддержкой сенсорного ввода к локальным бизнес-данным в службах SQL Server Reporting Services и на сервере отчетов Power BI.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 12/18/2017
ms.author: maggies
ms.openlocfilehash: 4277a8353fa6d9538ff050f0c08b9644d4a218c6
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="view-on-premises-report-server-reports-and-kpis-in-the-power-bi-mobile-apps"></a>Просмотр локальных отчетов на сервере отчетов и ключевых показателей эффективности в мобильных приложениях Power BI
Область применения:

| ![iPhone](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Телефон Android](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Планшет Android](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhone |iPad |Телефоны под управлением Android |Планшеты Android |

Мобильные приложения Power BI обеспечивают динамический мобильный доступ с поддержкой сенсорного ввода к локальным бизнес-данным на сервере отчетов Power BI и в службах SQL Server 2016 Reporting Services (SSRS). 

 ![Домашняя страница сервера отчетов в мобильных приложениях](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-pbi-report-server-home.png)

## <a name="first-things-first"></a>Начните с главного
**Мобильные приложения расположены не там, где создается содержимое Power BI, а там, где вы просматриваете его.**

* Вы и ваши коллеги можете [создавать отчеты Power BI с помощью Power BI Desktop, а затем публиковать их на веб-портале сервера отчетов Power BI](report-server/quickstart-create-powerbi-report.md). 
* Создавайте [ключевые показатели эффективности непосредственно на веб-портале](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services), включайте их в папки и добавляйте в избранное для быстрого поиска. 
* [Создайте мобильные отчеты Reporting Services](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) при помощи издателя мобильных отчетов для SQL Server 2016 Enterprise Edition и опубликуйте их на [веб-портале служб Reporting Services](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).  

Затем в мобильных приложениях Power BI можно подключиться к пяти серверам отчетов, чтобы отобразить в папках или списке избранных элементов отчеты Power BI и ключевые показатели эффективности. 

## <a name="explore-samples-in-the-mobile-apps-without-a-server-connection"></a>Изучение примеров в мобильных приложениях без подключения к серверу
Ознакомиться с ключевыми показателями эффективности и функциями мобильных отчетов Reporting Services можно даже без доступа к веб-порталу служб Reporting Services. 

1. Коснитесь кнопки глобальной навигации ![Кнопка глобальной навигации](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png) в левом верхнем углу экрана, а затем коснитесь значка шестеренки ![Значок шестеренки](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png).
2. Щелкните **Примеры для Reporting Services**, а затем просмотрите и изучите примеры ключевых показателей эффективности и мобильных отчетов.
   
   ![Примеры для Reporting Services](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-ssrs-samples.png)

## <a name="connect-to-an-on-premises-server"></a>Подключение к локальному серверу
Вы можете просматривать локальные отчеты Power BI, мобильные отчеты Reporting Services и ключевые показатели эффективности в мобильных приложениях Power BI. 

1. Откройте приложение Power BI на своем мобильном устройстве.
2. Если вы еще не вошли в Power BI, выберите **Сервер отчетов**.
   
   ![Вход на сервер отчетов](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-connect-to-rs-login.png)
   
   Если вы уже вошли в приложение Power BI, коснитесь кнопки глобальной навигации ![Кнопка глобальной навигации](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png), а затем коснитесь значка шестеренки ![Значок шестеренки](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png) в правом верхнем углу.
3. Выберите **Подключение к серверу**.
   
    ![Подключение к серверу](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-android-server-sign-in.png)

     Мобильному приложению необходимо обеспечить доступ к серверу. Это можно сделать несколькими способами:

    - Проще всего использовать ту же сеть или VPN.
    - Можно использовать прокси веб-приложения для подключения вне организации. См. дополнительные сведения о [подключении к Reporting Services с помощью OAuth](mobile-oauth-ssrs.md). 
    - Откройте подключение (порт) в брандмауэре.

1. Введите адрес сервера, имя пользователя и пароль. Используйте следующий формат для адреса сервера:
   
     `http://<servername>/reports`
   
     OR
   
     `https://<servername>/reports`
   
   В начале строки подключения укажите префикс **http** или **https**.
   
    ![Диалоговое окно "Подключение к серверу"](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-connect-to-server-dialog.png)
5. (Необязательно.) В разделе **Дополнительные параметры** при желании можно присвоить серверу понятное имя.
6. Новый сервер отобразится на навигационной панели слева. В нашем примере ему присвоено имя "power bi report server".
   
   !["Сервер отчетов" на панели навигации слева](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-left-nav-report-server.png)

## <a name="view-power-bi-reports-and-kpis-in-the-power-bi-app"></a>Просмотр отчетов Power BI и ключевых показателей эффективности в приложении Power BI
Отчеты Power BI, мобильные отчеты Reporting Services и ключевые показатели эффективности отображаются в тех же папках, в которых они расположены на веб-портале служб Reporting Services. 

* Коснитесь отчета Power BI ![Значок отчета Power BI](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-report-icon.png). Он открывается в альбомной ориентации и доступен для работы в приложении Power BI.
  
    ![Отчет Power BI](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-report-server-report.png)
* В Power BI Desktop владельцы отчета могут [оптимизировать отчет](desktop-create-phone-report.md) для мобильных приложений Power BI. На мобильных телефонах в оптимизированных отчетах есть специальный значок ![Оптимизированный значок отчета Power BI](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-icon.png) и макет.
  
    ![Отчет Power BI, оптимизированный для мобильных устройств](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-report.png)
* Выберите ключевой показатель эффективности, чтобы просмотреть его в режиме фокуса.
  
    ![Ключевой показатель эффективности в режиме фокусировки](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/pbi_ipad_ssmrp_tile.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Просмотр избранных ключевых показателей эффективности и отчетов
На веб-портале ключевые показатели эффективности и отчеты можно отметить как избранные. Так вы сможете просматривать эти данные на мобильном устройстве в одной папке вместе с избранными панелями мониторинга Power BI.

* Выберите **Избранное**.
  
   !["Избранное" на панели навигации слева](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-faves-pbi-report-server-update.png)
  
   Ваши избранные ключевые показатели эффективности и отчеты находятся на этой странице веб-портала вместе с панелями мониторинга Power BI в службе Power BI:
  
   ![Отчеты и панель мониторинга Power BI на странице "Избранное"](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-favorites.png)

## <a name="remove-a-connection-to-a-report-server"></a>Удаление подключения к серверу отчетов
1. Внизу левой панели навигации выберите **Параметры**.
2. Выберите имя сервера, с которым хотите разорвать соединение.
3. Коснитесь пункта **Удалить сервер**.

## <a name="next-steps"></a>Дальнейшие действия
* [Приступая к работе с Power BI](service-get-started.md)  
* У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

