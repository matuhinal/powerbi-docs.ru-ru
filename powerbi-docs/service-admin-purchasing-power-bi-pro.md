---
title: Приобретение и назначение лицензий Power BI Pro
description: Узнайте, как приобрести и назначить лицензии Power BI Pro для предоставления пользователям доступа ко всему содержимому и возможностям совместной работы службы Power BI.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: quickstart
ms.date: 10/29/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 55cdfad221aef276c790e98de83dd844bc13aafe
ms.sourcegitcommit: 320d83ab392ded71bfda42c5491acab3d9d357b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74958728"
---
# <a name="purchase-and-assign-power-bi-pro-user-licenses"></a>Приобретение и назначение пользовательских лицензий Power BI Pro

Power BI Pro — это отдельная лицензия пользователя, которая позволяет читать отчеты и панели мониторинга, опубликованные в службе Power BI, и взаимодействовать с ними, а также обмениваться содержимым и совместно работать с другими пользователями Power BI Pro. Только пользователи с пользовательской лицензией Power BI Pro могут публиковать содержимое совместно с другими пользователями или использовать содержимое, созданное другими пользователями, если содержимое не размещается в емкости Power BI Premium. Дополнительные сведения см. в разделе _Сравнение функций Power BI_ на странице [Цены на Power BI](https://powerbi.microsoft.com/pricing/).

## <a name="purchase-and-assign-power-bi-pro-user-licenses"></a>Приобретение и назначение пользовательских лицензий Power BI Pro

В этой статье объясняется, как приобрести пользовательские лицензии Power BI Pro в Центре администрирования Microsoft 365, а затем описываются два варианта, которые администраторы могут использовать, чтобы назначить эти лицензии отдельным пользователям: Центр администрирования Microsoft 365 и портал Azure (выберите один вариант).

### <a name="prerequisites"></a>Предварительные требования

Чтобы приобрести и назначить лицензии в Центре администрирования Microsoft 365, необходимо быть членом роли **[глобальный администратор или администратор выставления счетов](https://support.office.com/article/about-office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)** в Microsoft 365.

Для назначения лицензий на портале Azure вы должны быть владельцем подписки Azure, которая используется в Power BI для запросов к Azure Active Directory.

### <a name="purchase-licenses-in-microsoft-365"></a>Приобретение лицензий в Microsoft 365

Выполните следующие действия, чтобы приобрести лицензии Power BI Pro в Центре администрирования Microsoft 365:

1. Откройте [Центр администрирования Microsoft 365](https://portal.office.com/adminportal/home#/homepage).

2. В области навигации выберите **Выставление счетов** > **Подписки**.

    ![Область навигации](media/service-admin-purchasing-power-bi-pro/service-purchasing-power-bi-pro-01.png)

3. В правом верхнем углу страницы **Подписки** щелкните элемент **Добавить подписки**.

    ![Подписка](media/service-admin-purchasing-power-bi-pro/service-purchasing-power-bi-pro-02.png)

4. Найдите требуемое предложение подписки:

    В разделе **Набор корпоративных приложений** выберите **Office 365 корпоративный E5**.

    ![Подписка E5 на Office](media/service-admin-purchasing-power-bi-pro/service-purchasing-power-bi-pro-03.png)

    В области **Другие планы** выберите **Power BI Pro**.

    ![Подписка Power BI](media/service-admin-purchasing-power-bi-pro/service-purchasing-power-bi-pro-04.png)

5. Наведите указатель мыши на многоточие (**. . .**) рядом с нужной подпиской и выберите **Приобрести**.

    ![Приобрести](media/service-admin-purchasing-power-bi-pro/service-purchasing-power-bi-pro-05.png)

6. Выберите предпочитаемый вариант выставления счетов: **Платить ежемесячно** или **Заплатить за весь год**.

7. В области **Сколько пользователей в вашей организации?** введите нужное число лицензий, а затем выберите **Быстрый заказ** и завершите транзакцию.

8. Убедитесь, что приобретенные подписки появились на странице **Подписки**.

   ![Приобретенные подписки](media/service-admin-purchasing-power-bi-pro/service-purchasing-power-bi-pro-06.png)

9. Чтобы добавить дополнительные лицензии после первоначальной покупки, выберите **Power BI Pro** на странице **Подписки**, а затем выберите **Добавить/удалить лицензии**.

### <a name="assign-licenses-in-the-microsoft-365-admin-center"></a>Использование Центра администрирования Microsoft 365 для назначения лицензий

Выполните следующие действия, чтобы назначить лицензии Power BI Pro отдельным учетным записям пользователей:

1. Откройте [Центр администрирования Microsoft 365](https://portal.office.com/adminportal/home#/homepage).

2. В области навигации разверните пункт **Пользователи** и выберите **Активные пользователи**.

    ![Активные пользователи](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-05.png)

3. Выберите пользователя, а затем в разделе **Лицензии на продукты** — **Изменить**.

    ![Изменение лицензий на продукты](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-06.png)

4. В области **Power BI Pro** выберите значение **Включено**, а затем нажмите кнопку **Сохранить**.

    ![Включение лицензий на продукты](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-07.png)

5. В области **Состояние** для выбранных учетных записей убедитесь в назначении лицензии Power BI Pro.

    ![Проверка состояния лицензии](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-08.png)

### <a name="assign-licenses-in-the-azure-portal"></a>Назначение лицензий на портале Azure

Выполните следующие действия, чтобы назначить лицензии Power BI Pro отдельным учетным записям пользователей:

1. Перейдите на [портал Azure](https://ms.portal.azure.com/#@microsoft.onmicrosoft.com/dashboard/private/39bc3cf7-31a4-43f6-954c-f2d69ca2f0).

2. В области навигации выберите **Azure Active Directory**.

    ![Azure Active Directory](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-01.png)

3. В разделе **Azure Active Directory** выберите **Лицензии**.

    ![Лицензии](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-02.png)

4. В разделе **Лицензии** щелкните **Все продукты**, а затем **Power BI Pro**, чтобы отобразить список лицензированных пользователей.

    ![Лицензии — все продукты](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-03.png)

5. Щелкните **Назначить**, чтобы добавить лицензию Power BI Pro для учетной записи пользователя.

    ![Назначение лицензий](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-04.png)

## <a name="next-steps"></a>Дальнейшие действия

Итак, вы назначили лицензии, и теперь можно подробнее изучить Power BI Pro.

[Лицензирование Power BI в организации](service-admin-licensing-organization.md)

[Поиск пользователей Power BI, выполнивших вход](service-admin-access-usage.md)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
