---
title: Подключение к Zendesk с помощью Power BI
description: Zendesk для Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: sarinas
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 1edc4179b000191dfeff87387417009bc28e0ee5
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578872"
---
# <a name="connect-to-zendesk-with-power-bi"></a>Подключение к Zendesk с помощью Power BI

В этой статье рассматривается извлечение данных из учетной записи Zendesk с помощью шаблона приложения Power BI. Приложение Zendesk обеспечивает информационную панель Power BI и набор отчетов Power BI, предоставляющие информацию об объемах заявок и производительности. Данные автоматически обновляются раз в день. 

После установки приложения шаблона, можно настроить информационную панель и отчет, чтобы выделить информацию, которая наиболее важна. Затем можно распространять его как приложение коллегам в организации.

Подключитесь к [пакету содержимого Zendesk](https://app.powerbi.com/getdata/services/zendesk) или прочтите дополнительные сведения об [интеграции Zendesk](https://powerbi.microsoft.com/integrations/zendesk) с Power BI.

После установки шаблона приложения, можно изменить панель мониторинга и отчетов. Затем можно распространять его как приложение коллегам в организации.

>[!NOTE]
>Вам потребуется учетная запись администратора Zendesk для подключения. Дополнительные сведения о [требованиях](#system-requirements) см. ниже.

## <a name="how-to-connect"></a>Способы подключения

[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

3. Выберите **Zendesk** \> **получить сейчас**.
4. В **установить это приложение Power BI?** выберите **установить**.
4. В **приложений** области выберите **Zendesk** плитку.

    ![Плитка приложения Power BI Zendesk](media/service-connect-to-zendesk/power-bi-zendesk-tile.png)

6. В **приступить к работе с нового приложения**выберите **подключайте данные из**.

    ![Начало работы с новым приложением](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

4. Укажите URL-адрес, связанный с вашей учетной записью. URL-адрес имеет вид **https://company.zendesk.com** . Сведения о том, как найти необходимые параметры, см. [ниже](#finding-parameters).
   
   ![Подключение к Zendesk](media/service-connect-to-zendesk/pbi_zendeskconnect.png)

5. При появлении запроса введите учетные данные Zendesk.  Выберите механизм проверки подлинности **oAuth 2** и нажмите **Войти**. Следуйте инструкциям проверки подлинности Zendesk. (Если вы уже вошли в Zendesk в браузере, вам могут не запрашиваться учетные данные.)
   
   > [!NOTE]
   > Этот пакет содержимого требует, что можно подключиться с учетной записью администратора Zendesk. 
   > 
   
   ![Войдите с помощью oAuth2](media/service-connect-to-zendesk/pbi_zendesksignin.png)
6. Нажмите кнопку **Разрешить** , чтобы предоставить Power BI доступ к данным Zendesk.
   
   ![Разрешить](media/service-connect-to-zendesk/zendesk2.jpg)
7. Нажмите кнопку **Подключить** , чтобы начать импорт. 
8. После импорта данных в Power BI вы увидите списке содержимого для приложения Zendesk: Новая панель мониторинга, отчет и набор данных.
9. Выберите панель мониторинга, чтобы начать процесс исследования.

    ![Панель мониторинга Zendesk](media/service-connect-to-zendesk/power-bi-zendesk-dashboard.png)
   
## <a name="modify-and-distribute-your-app"></a>Изменение и распространение приложения

Вы установили шаблона приложения Zendesk. Это означает, что вы также создали рабочую область приложения Zendesk. В рабочей области можно изменить отчет и информационную панель и затем распространить его как *приложения* коллегам в организации. 

1. Чтобы просмотреть все содержимое новой рабочей областью Zendesk, в панели навигации слева, выберите **рабочие области** > **Zendesk**. 

    ![Рабочая область Zendesk в левой области навигации](media/service-connect-to-zendesk/power-bi-zendesk-workspace-left-nav.png)

    Это представление является списке содержимого рабочей области. В правом верхнем углу, вы увидите **обновить приложение**. Когда вы будете готовы для распространения приложения, чтобы ваши коллеги, начнем именно это. 

    ![Список содержимого Zendesk](media/service-connect-to-zendesk/power-bi-zendesk-content-list.png)

2. Выберите **отчеты** и **наборы данных** для отображения элементов в рабочей области.

    Узнайте о [распространение приложений](service-create-distribute-apps.md) своим коллегам.

## <a name="system-requirements"></a>Требования к системе
Для доступа к пакету содержимого Zendesk требуется учетная запись администратора Zendesk. Если вы являетесь агентом или конечным пользователем и хотите просмотреть данные Zendesk, добавьте предложение и проверьте соединитель Zendesk в [Power BI Desktop](desktop-connect-to-data.md).

## <a name="finding-parameters"></a>Поиск параметров
URL-адрес Zendesk будет совпадать с URL-адресом, который используется для входа в учетную запись Zendesk. Если вы не знаете URL-адрес Zendesk, можно использовать [справку по входу](https://www.zendesk.com/login/) Zendesk.

## <a name="troubleshooting"></a>Устранение неполадок
При возникновении проблем с подключением, проверьте URL-адрес Zendesk и убедитесь, что вы используете учетную запись администратора Zendesk.

## <a name="next-steps"></a>Дальнейшие действия

* [Создание новых рабочих областей в Power BI](service-create-the-new-workspaces.md)
* [Установка и использование приложений с информационными панелями и отчетами в Power BI](consumer/end-user-apps.md)
* [Подключение к приложениям Power BI для внешних служб](service-connect-to-services.md)
* У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

