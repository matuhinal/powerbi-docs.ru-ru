---
title: Подключение к Application Insights с помощью Power BI
description: Application Insights для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/10/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 3f0a23c2bdb97c6fbc75981c40cb92c529550b1b
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008242"
---
# <a name="connect-to-application-insights-with-power-bi"></a>Подключение к Application Insights с помощью Power BI
Используйте Power BI для создания эффективных пользовательских панелей мониторинга на базе телеметрии [Application Insights](/azure/application-insights/app-insights-overview/). Взгляните на данные телеметрии вашего приложения под новым углом. Сочетайте метрики из нескольких приложений или служб компонентов на одной информационной панели. Этот первый выпуск пакета содержимого Power BI для Application Insights включает в себя мини-приложения для распространенных метрик использования, например активных пользователей, просмотра страниц, сеансов, версии браузера и ОС, а также географического распределения пользователей на карте.

Подключите [пакет содержимого Application Insights для Power BI](https://app.powerbi.com/getdata/services/application-insights).

>[!NOTE]
>Сейчас этот метод интеграции является **устаревшим**. Дополнительные сведения о предпочтительном методе подключения Application Insights к Power BI см. в разделе об [экспорте запроса аналитики](https://docs.microsoft.com/azure/application-insights/app-insights-export-power-bi#export-analytics-queries).

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
    ![Кнопка "Получить данные"](media/service-connect-to-application-insights/pbi_getdata.png)
2. В поле **Службы** выберите **Получить**.
   
    ![Кнопка "Получить службы"](media/service-connect-to-application-insights/pbi_getservices.png)
3. Выберите **Application Insights** > **Получить**.
   
    ![Пакет содержимого Application Insights](media/service-connect-to-application-insights/appinsights.png)
4. Укажите сведения о приложении, к которому вы хотите подключиться, включая **имя ресурса Application Insights**, **группу ресурсов** и **идентификатор подписки**. Дополнительные сведения см. в разделе [Поиск параметров Application Insights](#FindingAppInsightsParams) ниже.
   
    ![Диалоговое окно подключения Application Insights](media/service-connect-to-application-insights/pbi_contpkappinsitconnectndialog.png)    
5. Выберите **Вход** и следуйте инструкциям для подключения.
   
    ![Вход для подключения Application Insights](media/service-connect-to-application-insights/pbi_contpkappinsitconnectn2.png)
6. Процесс импорта начинается автоматически. После завершения отображается уведомление, а в области навигации появляется новая информационная панель, отчет и набор данных, отмеченные звездочкой.  Выберите панель мониторинга, чтобы просмотреть импортированные данные.
   
    ![Информационная панель Application Insights](media/service-connect-to-application-insights/pbi_contpkappinsitdash.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="whats-included"></a>Содержимое
Пакет содержимого Application Insights включает следующие таблицы и метрики:  

    ´´´
    - ApplicationDetails  
    - UniqueUsersLast7Days   
    - UniqueUsersLast30Days   
    - UniqueUsersDailyLast30Days  
    - UniqueUsersByCountryLast7Days  
    - UniqueUsersByCountryLast30Days   
    - PageViewsDailyLast30Days   
    - SessionsLast7Days   
    - SessionsLast30Days  
    - PageViewsByBrowserVersionDailyLast30Days   
    - UniqueUsersByOperatingSystemLast7Days   
    - UniqueUsersByOperatingSystemLast30Days    
    - SessionsDailyLast30Days   
    - SessionsByCountryLast7Days   
    - SessionsByCountryLast30Days   
    - PageViewsByCountryDailyLast30Days  
    ´´´ 

<a name="FindingAppInsightsParams"></a>

## <a name="finding-parameters"></a>Поиск параметров
Все нужные значения — имя, группу ресурсов и идентификатор подписки — можно найти на портале Azure. При выборе имени откроется подробное представление, где с помощью раскрывающегося списка основных сведений можно найти все необходимые значения.

![Параметры Application Insights](media/service-connect-to-application-insights/pbi_contpkappinsitparams.png)

Скопируйте эти значения и вставьте их в поля в Power BI:

![Параметры Application Insights](media/service-connect-to-application-insights/pbi_contpkappinsitparam2.png)

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Получение данных в Power BI](service-get-data.md)

