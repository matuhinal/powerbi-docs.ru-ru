---
title: Подключение к Adobe Analytics с помощью Power BI
description: Подключитесь к Adobe Analytics из Power BI, чтобы получить приложение, в котором отображаются данные вашей учетной записи на панели мониторинга и в отчетах.
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: ef59d5f42ba913e4ecad79116dea635744534198
ms.sourcegitcommit: 52ac456bf2ac025b22ea634c28482f22e1cc19ac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2018
ms.locfileid: "48908585"
---
# <a name="connect-to-adobe-analytics-with-power-bi"></a>Подключение к Adobe Analytics с помощью Power BI
Подключение к Adobe Analytics через Power BI начинается с подключения к учетной записи Adobe Analytics Marketing Cloud. Вы получите приложение с панелью мониторинга и набором отчетов Power BI, с помощью которых можно получить представление о трафике сайта и измерениях пользователей. Данные автоматически обновляются раз в день. Вы можете взаимодействовать с панелью мониторинга и отчетами, но не сохранять изменения.

Подключитесь к [Adobe Analytics](https://app.powerbi.com/getdata/services/adobe-analytics) или прочтите дополнительные сведения об [интеграции Adobe Analytics](https://powerbi.microsoft.com/integrations/adobe-analytics) с Power BI.

## <a name="how-to-connect"></a>Способы подключения
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

3. Выберите **Adobe Analytics** \> **Получить**.
   
   ![](media/service-connect-to-adobe-analytics/adobe.png)
4. При подключении в Power BI указывается имя компании Adobe Analytics и идентификатор набора отчетов (а не имя набора отчетов). Сведения о том, как [найти эти параметры](#FindingParams), см. ниже.
   
   ![](media/service-connect-to-adobe-analytics/parameters.png)
5. В качестве **метода проверки подлинности** выберите **oAuth2** \> **Войти**. При появлении запроса введите учетные данные Adobe Analytics. 
   
    ![](media/service-connect-to-adobe-analytics/creds.png)
   
    ![](media/service-connect-to-adobe-analytics/adobe_signin.png)
6. Нажмите кнопку **Принять** , чтобы предоставить Power BI доступ к данным Adobe Analytics.
   
   ![](media/service-connect-to-adobe-analytics/adobe_authorize.png)
7. После подтверждения процесс импорта начнется автоматически. 

## <a name="view-the-adobe-analytics-dashboard-and-reports"></a>Просмотр панели мониторинга и отчетов Adobe Analytics
[!INCLUDE [powerbi-service-apps-open-app](./includes/powerbi-service-apps-open-app.md)]

   ![Панель мониторинга Adobe Analytics](media/service-connect-to-adobe-analytics/dashboard.png)

[!INCLUDE [powerbi-service-apps-open-app](./includes/powerbi-service-apps-what-now.md)]

## <a name="whats-included"></a>Содержимое
Power BI использует API отчетов Adobe Analytics для определения и запуска отчетов в следующих таблицах.

| **Имя таблицы** | **Сведения о столбце** |
| --- | --- |
| Продукты |elements= "product" (top 25) </br> metrics="cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units" |
| Браузеры |elements= "browser" (top 25)</br>  metrics="bounces", "bouncerate", "visitors", "visits", "uniquevisitors", "totaltimespent", "pageviews" |
| Страницы |elements= "page" (top 25)</br>  metrics="cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units", "visits", "uniquevisitors", "pageviews", "bounces", "bouncerate", "totaltimespent" |
| JavaScript включен |elements= "javascriptenabled", "browser" (top 25) |
| Мобильная ОС |elements= "mobileos"(top 25)</br> metrics="bounces", "bouncerate", "visitors", "visits", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "checkouts", "revenue", "units", "pageviews" |
| Ключевые слова поисковых систем |elements= "searchengine" "searchenginekeyword"</br>  metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units", "pageviews" |
| Поисковая система для продуктов |elements= "searchengine", "product"</br>  metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units", "pageviews" |
| Страницы с исходной ссылкой |elements= "referrer" (top 15), "page" (top 10)</br>  metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units", "pageviews" |
| Страницы по странам |elements= "geocountry" (Top 20), "page"</br>  metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units", "pageviews" |
| Продукты по странам |elements= "geocountry" (Top 20), "product"</br> metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units" |
| Поиск страны и региона |elements= "geocountry" (Top 200)</br>  metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units" |
| Язык |elements= "language", "browser" (Top 25)</br>  metrics="bounces", "bouncerate", "visitors", "visits", "uniquevisitors", "totaltimespent", "pageviews", "cartadditions", "cartremovals", "checkouts", "carts", "cartviews" |
| Поиск в поисковых системах |elements= "searchengine" (top 100)</br>  metrics="bounces", "bouncerate", "visitors", "visits", "entries", "uniquevisitors", "totaltimespent", "cartadditions", "cartremovals", "carts", "cartviews", "checkouts", "revenue", "units" |
| Поиск в Интернете |elements= "browser" (top 25) |

## <a name="system-requirements"></a>Требования к системе
Требуется доступ к [Adobe Analytics](http://www.adobe.com/marketing-cloud/web-analytics.html), включая доступ к нужным параметрам, описанным ниже.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Поиск параметров
**Компания**

Название компании можно найти вверху справа от вашей учетной записи, когда выполнен вход в систему. В значении учитываются пробелы и регистр. Вводите его так же, как оно отображается в вашей учетной записи.

![](media/service-connect-to-adobe-analytics/adobe_companies.png)

**ИД набора отчетов**

Идентификатор набора создается при создании набора отчетов. Чтобы узнать значение идентификатора, можно обратиться к администратору. Это не имя набора отчетов.

Из [документации](https://marketing.adobe.com/resources/help/en_US/reference/new_report_suite.html) Adobe:

![](media/service-connect-to-adobe-analytics/reportsuiteid.png)

## <a name="troubleshooting"></a>Устранение неполадок
Если после предоставления учетных данных отображается ошибка, указывающая, что у вас нет разрешений, обратитесь к своему администратору и проверьте наличие доступа к API Adobe Analytics. Также убедитесь, что предоставленный идентификатор Adobe связан с вашей организацией Marketing Cloud (связанной с компанией Adobe Analytics).

Если вы успешно прошли экран ввода учетных данных до того, как произошла ошибка, завершение обработки отчетов может выполняться слишком долго. Распространенное сообщение об ошибке имеет такой вид: *"Не удалось получить данные из отчета Adobe Analytics. Содержимое включало &quot;referrer, page&quot;, приблизительная продолжительность xx с."* Ознакомьтесь с разделом "Содержимое" и сравните размер с размером экземпляра Adobe. К сожалению, сейчас нет способа обойти это время ожидания. Однако мы рассматриваем возможность выпуска обновлений для улучшения поддержки крупных экземпляров. Оставьте отзыв для группы разработчиков Power BI на сайте https://ideas.powerbi.com

## <a name="next-steps"></a>Дальнейшие действия
* [Что из себя представляют приложения в Power BI?](service-create-distribute-apps.md)
* [Получение данных в Power BI](service-get-data.md)
* Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

