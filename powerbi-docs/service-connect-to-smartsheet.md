---
title: Подключение к Smartsheet с помощью Power BI
description: Smartsheet для Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 841201aa87139b9630d6fc076d57109fb2b09804
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578905"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Подключение к Smartsheet с помощью Power BI
В этой статье рассматривается извлечение данных из вашей учетной записи Smartsheet с помощью шаблона приложения Power BI. Smartsheet — это удобная платформа для совместной работы и обмена файлами. Шаблон приложения Smartsheet для Power BI предоставляет панель мониторинга, отчеты и набора данных, в которой представлены общие сведения о вашей учетной записи Smartsheet. Можно также использовать [Power BI Desktop](desktop-connect-to-data.md) подключиться напрямую к отдельным листам в учетной записи. 

После установки шаблона приложения, можно изменить панель мониторинга и отчетов. Затем можно распространять его как приложение коллегам в организации.

Подключение к [Smartsheet шаблона приложения](https://app.powerbi.com/groups/me/getdata/services/smartsheet) для Power BI.

>[!NOTE]
>Учетная запись администратора Smartsheet является предпочтительным для подключения и загрузки шаблона приложения Power BI, так как она обеспечивает доступ к дополнительным возможностям.

## <a name="how-to-connect"></a>Способы подключения

[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

3. Выберите **Smartsheet** \> **получить сейчас**.
4. В **установить это приложение Power BI?** выберите **установить**.
4. В **приложений** области выберите **Smartsheet** плитку.

    ![Плитка приложения Power BI Smartsheet](media/service-connect-to-smartsheet/power-bi-smartsheet-tile.png)

6. В **приступить к работе с нового приложения**выберите **подключайте данные из**.

    ![Начало работы с новым приложением](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

4. В качестве метода проверки подлинности выберите **oAuth2 \> Войти**.
   
   При появлении запроса введите учетные данные Smartsheet и пройдите проверку подлинности.
   
   ![Учетные данные Smartsheet](media/service-connect-to-smartsheet/creds.png)
   
   ![Smartsheet входа.](media/service-connect-to-smartsheet/creds2.png)

5. После импорта данных в Power BI открывается панель мониторинга Smartsheet.
   
   ![Панель мониторинга Smartsheet](media/service-connect-to-smartsheet/power-bi-smartsheet-dashboard.png)

## <a name="modify-and-distribute-your-app"></a>Изменение и распространение приложения

Вы установили приложение шаблона Smartsheet. Это означает, что вы также создали рабочую область приложения Smartsheet. В рабочей области можно изменить отчет и информационную панель и затем распространить его как *приложения* коллегам в организации. 

1. Чтобы просмотреть все содержимое новой рабочей областью Smartsheet, в панели навигации слева, выберите **рабочие области** > **Smartsheet**. 

    ![Smartsheet рабочую область в левой области навигации](media/service-connect-to-smartsheet/power-bi-smartsheet-workspace.png)

    Это представление является списке содержимого рабочей области. В правом верхнем углу, вы увидите **обновить приложение**. Когда вы будете готовы для распространения приложения, чтобы ваши коллеги, начнем именно это. 

    ![Список содержимого Smartsheet](media/service-connect-to-smartsheet/power-bi-smartsheet-workspace-content.png)

2. Выберите **отчеты** и **наборы данных** для отображения элементов в рабочей области.

    Узнайте о [распространение приложений](service-create-distribute-apps.md) своим коллегам.

## <a name="whats-included"></a>Содержимое
У Smartsheet шаблона приложения для Power BI содержит общие сведения о вашей учетной записи Smartsheet, например число рабочих областей, отчеты и листы, вы, изменяются и т.д. Пользователи с правами администратора также видеть некоторые сведения о пользователях в системе, например создателей верхних листов.  

Вы можете использовать соединитель Smartsheet в [Power BI Desktop](desktop-connect-to-data.md) для подключения напрямую к отдельным листам в учетной записи.  

## <a name="next-steps"></a>Дальнейшие действия

* [Создание новых рабочих областей в Power BI](service-create-the-new-workspaces.md)
* [Установка и использование приложений с информационными панелями и отчетами в Power BI](consumer/end-user-apps.md)
* [Подключение к приложениям Power BI для внешних служб](service-connect-to-services.md)
* У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)