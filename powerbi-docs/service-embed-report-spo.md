---
title: Внедрение с помощью веб-части отчетов в SharePoint Online
description: С помощью новой веб-части отчетов Power BI для SharePoint Online вы можете легко внедрять интерактивные отчеты Power BI в страницы SharePoint Online.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 05/16/2019
ms.openlocfilehash: c8789d47ed1b67f9fd6808865514120457a29dfe
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051269"
---
# <a name="embed-with-report-web-part-in-sharepoint-online"></a>Внедрение с помощью веб-части отчетов в SharePoint Online

С помощью новой веб-части отчетов Power BI для SharePoint Online вы можете легко внедрять интерактивные отчеты Power BI в страницы SharePoint Online.

Если вы используете новый **внедрить в SharePoint Online** параметр, внедренные отчеты являются полностью защищенными, поэтому можно легко создавать безопасные внутренние порталы.

## <a name="requirements"></a>Требования

Для **внедрить в SharePoint Online** работы отчетов необходимо:

* Лицензия Power BI Pro или [емкости Power BI Premium (EM или P SKU)](service-premium-what-is.md) с лицензией Power BI.
* Для веб-части Power BI для SharePoint Online требуются [современные страницы](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b).

## <a name="embed-your-report"></a>Внедрение отчета
Чтобы внедрить отчет в SharePoint Online, необходимо получить URL-адрес отчета и использовать его в SharePoint Online новой веб-части Power BI.

### <a name="get-a-report-url"></a>Получить URL-адрес отчета

1. В Power BI просмотрите отчет.

2. Выберите **файл** в раскрывающемся меню выберите **внедрить в SharePoint Online**.

    ![Меню "Файл"](media/service-embed-report-spo/powerbi-file-menu.png)

3. Скопируйте URL-адрес отчета в диалоговом окне.

    ![Ссылка для внедрения](media/service-embed-report-spo/powerbi-embed-link-sharepoint.png)

### <a name="add-the-power-bi-report-to-a-sharepoint-online-page"></a>Добавление отчета Power BI на страницу SharePoint Online

1. Откройте целевой страницы в SharePoint Online и выберите **изменить**.

    ![Изменение страницы в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-edit-page.png)

    Или, в Sharepoint Online выберите **+ создать** создать новую современную страницу сайта.

    ![Новая страница в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-new-page.png)

2. Выберите **+** раскрывающийся список и выберите **Power BI**.

    ![Новая веб-часть в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-new-web-part.png)

3. Нажмите кнопку **Добавить отчет**.

    ![Новый отчет в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-new-report.png)  

4. Вставьте URL-адрес отчета, ранее были скопированы в **ссылка на отчет Power BI** области. Отчет загружается автоматически.

    ![Свойства новой веб-части в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-new-web-part-properties.png)

5. Нажмите кнопку **Опубликовать**, чтобы отчет стал видимым для пользователей SharePoint Online.

    ![Загруженный отчет в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-report-loaded.png)

## <a name="grant-access-to-reports"></a>Предоставление доступа к отчетам

При внедрении отчета в SharePoint Online не предоставляется пользователям автоматически разрешение на просмотр отчета — вам нужно задать разрешения на просмотр в Power BI.

> [!IMPORTANT]
> Обязательно проверьте, кто может просматривать отчет в службе Power BI, и предоставьте доступ пользователям, которых нет в списке.

Существует два способа для предоставления доступа к отчетов в Power BI. Первый способ, если вы используете группу Office 365 для создания сайта группы SharePoint Online, — в списке пользователь является членом **рабочей области приложения в службе Power BI** и **страницы SharePoint**. Дополнительные сведения см. в статье об [управлении рабочей областью приложения](service-manage-app-workspace-in-power-bi-and-office-365.md).

Второй способ — для внедрения отчета в приложение и поделиться им напрямую с пользователями:  

1. (Должен быть пользователем уровня Pro) автор создает отчет в рабочей области приложения. Для совместного использования с **пользователи с бесплатной лицензией Power BI**, рабочую область приложения необходимо задать как **рабочей области "премиум"** .

2. Автор публикует приложение и устанавливает его. Автор должен не забудьте установить приложение должно иметь доступ к URL-адрес отчета, который используется для внедрения в SharePoint Online.

3. Теперь все пользователи также должны установить приложение. Можно также использовать **автоматическая установка приложения** функции, которые можно включить в [портал администрирования Power BI](service-admin-portal.md), чтобы у вас есть приложение, предварительно установленным для конечных пользователей.

   ![Автоматическая установка приложения](media/service-embed-report-spo/install-app-automatically.png)

4. Автор открывает приложение и переходит к отчету.

5. Автор копирует URL-адрес внедрения отчета в отчете установленное приложение. **Не используйте исходный URL-адрес отчета из рабочей области приложения.**

6. Создайте сайт группы в SharePoint Online.

7. Добавьте URL-адрес отчета, ранее были скопированы в веб-часть Power BI.

8. Добавьте всех пользователей и (или) группы, которые будут работать с данными на странице SharePoint Online и в приложении Power BI, созданном вами.

    > [!NOTE]
    > **Чтобы пользователи и группы могли видеть отчет на странице SharePoint, им потребуется доступ к странице SharePoint Online и отчету в приложении Power BI.**

Теперь пользователь может перейти на сайт группы SharePoint Online и просматривать отчеты на странице.

## <a name="multi-factor-authentication"></a>Многофакторная проверка подлинности

Если среда Power BI требует входа с помощью многофакторной идентификации, может появиться запрос на вход с помощью устройства безопасности для проверки вашего удостоверения. Это происходит, если была не войти SharePoint Online с помощью многофакторной проверки подлинности, но среда Power BI требует устройства безопасности для проверки учетной записи.

> [!NOTE]
> Azure Active Directory 2.0 не поддерживают многофакторную проверку подлинности — пользователи увидят сообщение об ошибке. Если пользователь повторно войдет в SharePoint Online с помощью своего устройства безопасности, он сможет просматривать отчет.

## <a name="web-part-settings"></a>Настройки веб-части

Ниже приведены параметры, которые можно настроить для веб-части Power BI для SharePoint Online.

![Свойства новой веб-части в SharePoint](media/service-embed-report-spo/powerbi-sharepoint-web-part-properties.png)

| Свойство | Описание |
| --- | --- |
| Имя страницы |Задает страницу по умолчанию веб-части. Выберите значение в раскрывающемся списке. Если ни одна страница не отображается, отчет содержит одну страницу или вставленный URL-адрес содержит имя страницы. Удалите раздел report из URL-адреса, чтобы выбрать определенную страницу. |
| Отображение |Изменяется так, как отчет поместится на странице SharePoint Online. |
| Отображение области навигации |Отображение или скрытие области навигации по страницам. |
| Отображение области фильтров |Отображение или скрытие области фильтров. |

## <a name="reports-that-do-not-load"></a>Отчеты, которые не загружаются

Если отчет не загружается в веб-части Power BI, может появиться следующее сообщение:

![Это содержимое не доступного сообщения](media/service-embed-report-spo/powerbi-sharepoint-report-not-found.png)

Это сообщение может появиться по двум причинам.

1. У вас нет доступа к отчетам.
2. Отчет был удален.

Свяжитесь с владельцем страницы SharePoint Online для устранения проблемы.

## <a name="licensing"></a>Лицензирование

Пользователям, просматривающим отчет в SharePoint, нужна **лицензия Power BI Pro**, если содержимое не размещено в рабочей области **[емкости Power BI Premium (номера SKU: EM или P)](service-admin-premium-purchase.md)** .

## <a name="known-issues-and-limitations"></a>Известные проблемы и ограничения

* Ошибка "Произошла ошибка. Попробуйте выйти из системы и войти снова, а затем вернитесь к этой странице. Идентификатор корреляции: неопределенный, состояние HTTP-ответа: 400, код ошибки сервера 10001, сообщение: Отсутствует маркер обновления".
  
  Если возникает такая ошибка, попробуйте один из описанных ниже шагов по устранению неполадок.
  
  1. Выйдите из SharePoint и войдите снова. Перед повторным входом закройте все окна браузера.

  2. Если для учетной записи пользователя требуется многофакторная проверка подлинности (MFA), затем войдите SharePoint, с помощью многофакторной проверки Подлинности устройства (приложения для телефона, смарт-карт, и т.д.).
  
  3. Гостевые учетные записи B2B Azure не поддерживаются. Пользователи видят логотип Power BI, показывающий, что часть загружается, но отчет не отображается.

* Power BI не поддерживает те же языки с локализацией, что и SharePoint Online. В результате во внедренном отчете требуемая локализация может не отображаться.

* При использовании Internet Explorer 10 могут возникнуть проблемы. См. сведения о [поддерживаемых браузерах для Power BI](consumer/end-user-browsers.md) и [Office 365](https://products.office.com/office-system-requirements#Browsers-section).

* Веб-часть Power BI недоступна в [национальных облаках](https://powerbi.microsoft.com/clouds/).

* Классический сервер SharePoint Server не поддерживается с этой веб-частью.

* [Фильтры URL-адресов](service-url-filters.md) не поддерживаются в веб-части SPO.

## <a name="next-steps"></a>Дальнейшие действия

* [Allow or prevent creation of modern site pages by end users](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b) (Разрешение или запрет создания современных страниц сайта конечными пользователями)  
* [Создание и распространение приложения в Power BI](service-create-distribute-apps.md)  
* [Предоставление общего доступа к панели мониторинга и отчетам коллегам и другим пользователям](service-share-dashboards.md)  
* [Что такое Power BI Premium?](service-premium-what-is.md)
* [Embed a report in a secure portal or website](service-embed-secure.md) (Внедрение отчета в защищенный портал или сайт)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)