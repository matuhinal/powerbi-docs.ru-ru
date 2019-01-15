---
title: Внедрение с помощью веб-части отчетов в SharePoint Online
description: С помощью новой веб-части отчетов Power BI для SharePoint Online вы можете легко внедрять интерактивные отчеты Power BI в страницы SharePoint Online.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 11/01/2018
ms.openlocfilehash: 906ecdf8934899f2c16bacc07a271b4549d3c048
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54292836"
---
# <a name="embed-with-report-web-part-in-sharepoint-online"></a>Внедрение с помощью веб-части отчетов в SharePoint Online

С помощью новой веб-части отчетов Power BI для SharePoint Online вы можете легко внедрять интерактивные отчеты Power BI в страницы SharePoint Online.

Если вы используете новый параметр **Внедрить в SharePoint Online**, внедренные отчеты являются полностью защищенными, поэтому вы можете легко создавать безопасные внутренние порталы.

## <a name="requirements"></a>Требования

Чтобы отчеты, **внедренные в SharePoint Online**, работали, необходимо соблюсти несколько требований.

* Требуется лицензия Power BI Pro или [емкость Power BI Premium (номер SKU EM или P)](service-premium.md#premium-capacity-nodes) с лицензией Power BI.
* Для веб-части Power BI для SharePoint Online требуются [современные страницы](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b).

## <a name="embed-your-report"></a>Внедрение отчета

Чтобы внедрить отчет в SharePoint Online, сначала необходимо получить URL-адрес отчета, а затем использовать этот URL-адрес с новой веб-частью Power BI в SharePoint Online.

### <a name="get-a-url-to-your-report"></a>Получение URL-адреса отчета

1. Откройте отчет в службе Power BI.

2. Выберите пункт меню **Файл**.

3. Выберите команду **Внедрить в SharePoint Online**.

    ![Меню "Файл"](media/service-embed-report-spo/powerbi-file-menu.png)

4. Скопируйте URL-адрес из диалогового окна.

    ![Ссылка для внедрения](media/service-embed-report-spo/powerbi-embed-link-sharepoint.png)

### <a name="add-the-power-bi-report-to-a-sharepoint-online-page"></a>Добавление отчета Power BI на страницу SharePoint Online

1. Откройте нужную страницу в SharePoint Online и нажмите кнопку **Изменить**.

    ![Изменение страницы в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-edit-page.png)

    Или создайте новую современную страницу сайта, выбрав **+ Создать** в SharePoint Online.

    ![Новая страница в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-new-page.png)

2. Щелкните значок **+** и выберите веб-часть **Power BI**.

    ![Новая веб-часть в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-new-web-part.png)

3. Нажмите кнопку **Добавить отчет**.

    ![Новый отчет в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-new-report.png)

4. Вставьте URL-адрес отчета в область свойств. В качестве URL-адреса отчета используется URL-адрес, скопированный на предыдущих этапах. Отчет загружается автоматически.

    ![Свойства новой веб-части в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-new-web-part-properties.png)

5. Нажмите кнопку **Опубликовать**, чтобы отчет стал видимым для пользователей SharePoint Online.

    ![Загруженный отчет в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-report-loaded.png)

## <a name="grant-access-to-reports"></a>Предоставление доступа к отчетам

При внедрении отчета в SharePoint Online разрешение на просмотр отчета не предоставляется пользователям автоматически. Разрешения на просмотр отчета настраиваются в службе Power BI.

> [!IMPORTANT]
> Обязательно проверьте, кто может просматривать отчет в службе Power BI, и предоставьте доступ пользователям, которых нет в списке.

Доступ к отчету в службе Power BI можно предоставить двумя способами. Если вы используете группу Office 365 для создания сайта группы SharePoint Online, укажите пользователя как участника **рабочей области приложения в службе Power BI** и на **странице SharePoint**. Дополнительные сведения см. в статье об [управлении рабочей областью приложения](service-manage-app-workspace-in-power-bi-and-office-365.md).

Вы также можете опубликовать отчет напрямую для пользователей, внедрив его в приложение. Чтобы внедрить отчет в приложение, нужно выполнить следующие шаги.  

1. Автор приложения должен быть пользователем версии Pro.

2. Автор создает отчет в рабочей области приложения. *Чтобы предоставить общий доступ **пользователям бесплатной версии Power BI** к рабочей области приложения, нужно настроить ее как **рабочую область "Премиум"**.*

3. Автор публикует приложение и устанавливает его. *Автор должен установить приложение, чтобы получить доступ к URL-адресу отчета, который используется для внедрения в SharePoint Online.*

4. Теперь все пользователи также должны установить приложение. Но можно настроить предварительную установку приложения для пользователей, включив функцию **Автоматическая установка приложения** на [портале администрирования Power BI](service-admin-portal.md).

   ![Автоматическая установка приложения](media/service-embed-report-spo/install-app-automatically.png)

5. Автор открывает приложение и переходит к отчету.

6. Автор копирует URL-адрес для внедрения отчета из отчета, установленного приложением. *Не используйте исходный URL-адрес отчета из рабочей области приложения.*

7. Создайте сайт группы в SharePoint Online.

8. Добавьте URL-адрес отчета, скопированный на шаге 6, в веб-часть Power BI.

9. Добавьте всех пользователей и (или) группы, которые будут работать с данными на странице SharePoint Online и в приложении Power BI, созданном вами.

    > [!NOTE]
    > **Чтобы пользователи и группы могли видеть отчет на странице SharePoint, им потребуется доступ к странице SharePoint Online и отчету в приложении Power BI.**

10. Теперь пользователь может перейти на сайт группы SharePoint Online и просматривать отчеты на странице.

## <a name="multi-factor-authentication"></a>Многофакторная проверка подлинности

Если среда Power BI требует входа с помощью многофакторной идентификации, может появиться запрос на вход с помощью устройства безопасности для проверки вашего удостоверения. Это происходит, если вы не вошли в SharePoint Online с помощью многофакторной идентификации, но среда Power BI требует, чтобы учетная запись была проверена устройством безопасности.

> [!NOTE]
> Многофакторная идентификация еще не поддерживается в Azure Active Directory 2.0. Пользователи получат сообщение об *ошибке*. Если пользователь повторно войдет в SharePoint Online с помощью своего устройства безопасности, он сможет просматривать отчет.

## <a name="web-part-settings"></a>Настройки веб-части

Ниже приведено описание параметров, которые можно изменять в веб-части Power BI для SharePoint Online.

![Свойства новой веб-части в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-web-part-properties.png)

| Свойство | Описание |
| --- | --- |
| Имя страницы |Задает страницу по умолчанию, которую отображает веб-часть. Выберите значение в раскрывающемся списке. Если ни одна страница не отображается, отчет содержит одну страницу или вставленный URL-адрес содержит имя страницы. Удалите раздел report из URL-адреса, чтобы выбрать определенную страницу. |
| Отображение |Параметр настройки размеров отчета на странице SharePoint Online. |
| Отображение области навигации |Отображение или скрытие области навигации по страницам. |
| Отображение области фильтров |Отображение или скрытие области фильтров. |

## <a name="reports-that-do-not-load"></a>Отчеты, которые не загружаются

Отчет может не загружаться в веб-части Power BI. В этом случае отобразится следующее сообщение.

*Это содержимое недоступно.*

![Сообщение "Отчет не найден"](media/service-embed-report-spo/powerbi-sharepoint-report-not-found.png)

Это сообщение может появиться по двум причинам.

1. У вас нет доступа к отчету.
2. Отчет был удален.

Свяжитесь с владельцем страницы SharePoint Online, чтобы он помог устранить проблему.

## <a name="licensing"></a>Лицензирование

Пользователям, просматривающим отчет в SharePoint, нужна **лицензия Power BI Pro**, если содержимое не размещено в рабочей области **[емкости Power BI Premium (номера SKU: EM или P)](service-admin-premium-purchase.md)**.

## <a name="known-issues-and-limitations"></a>Известные проблемы и ограничения

* Ошибка "Произошла ошибка. Попробуйте выйти из системы и войти снова, а затем вернитесь к этой странице. Идентификатор корреляции: неопределенный, состояние HTTP-ответа: 400, код ошибки сервера 10001, сообщение: Отсутствует маркер обновления".
  
  Если возникает такая ошибка, попробуйте один из описанных ниже шагов по устранению неполадок.
  
  1. Выйдите из SharePoint и войдите снова. Перед повторным входом закройте все окна браузера.

  2. Если учетной записи пользователя требуется многофакторная идентификация (MFA), выполните вход в SharePoint с устройства, поддерживающего многофакторную идентификацию (мобильное приложение, смарт-карта и т. д.)
  
  3. Гостевые учетные записи B2B Azure не поддерживаются. Пользователи видят логотип Power BI, показывающий, что часть загружается, но отчет не отображается.

* Power BI не поддерживает те же языки с локализацией, что и SharePoint Online. В результате во внедренном отчете требуемая локализация может не отображаться.

* При использовании Internet Explorer 10 могут возникнуть проблемы. См. сведения о [поддерживаемых браузерах для Power BI](consumer/end-user-browsers.md) и [Office 365](https://products.office.com/office-system-requirements#Browsers-section).

* Веб-часть Power BI недоступна в [национальных облаках](https://powerbi.microsoft.com/en-us/clouds/).

* Классический сервер SharePoint Server не поддерживается с этой веб-частью.

* [Фильтры URL-адресов](service-url-filters.md) не поддерживаются в веб-части SPO.

## <a name="next-steps"></a>Дальнейшие действия

* [Allow or prevent creation of modern site pages by end users](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b) (Разрешение или запрет создания современных страниц сайта конечными пользователями)  
* [Создание и распространение приложения в Power BI](service-create-distribute-apps.md)  
* [Предоставление общего доступа к панели мониторинга и отчетам коллегам и другим пользователям](service-share-dashboards.md)  
* [Что такое Power BI Premium?](service-premium.md)
* [Embed a report in a secure portal or website](service-embed-secure.md) (Внедрение отчета в защищенный портал или сайт)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)