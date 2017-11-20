---
title: "Предоставление содержимого Power BI внешним гостевым пользователям с помощью Azure AD B2B"
description: "Power BI интегрируется с Azure Active Directory \"бизнес — бизнес\" (Azure AD B2B), чтобы обеспечить безопасное распространение содержимого Power BI для гостевых пользователей за пределами организации."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/14/2017
ms.author: asaxton
ms.openlocfilehash: 5dabaa09923203c31572b413f8674b76028b7483
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Предоставление содержимого Power BI внешним гостевым пользователям с помощью Azure AD B2B

Power BI интегрируется с Azure Active Directory "бизнес — бизнес" (Azure AD B2B), чтобы обеспечить безопасное распространение содержимого Power BI для гостевых пользователей за пределами организации и сохранить контроль над внутренними данными.

> [!VIDEO https://www.youtube.com/embed/xxQWEQ1NnlY]

## <a name="invite-guest-users"></a>Приглашение гостевых пользователей

Существует два способа приглашения гостевых пользователей в клиент Power BI: плановые или специализированные приглашения. Приглашения нужны только при первом добавлении внешнего пользователя для вашей организации.

### <a name="planned-invites"></a>Плановые приглашения

Плановое приглашение выполняется на портале Microsoft Azure в Azure AD или с помощью PowerShell. Этот вариант следует использовать для известных пользователей. 

**Только администратор клиента может создать гостевых пользователей на портале Azure AD.**

1. Перейдите на [портал Azure](https://portal.azure.com) и выберите **Azure Active Directory**.

2. Выберите **Пользователи и группы** > **Все пользователи** > **Новый гостевой пользователь**.

    ![Новый гостевой пользователь на портале Azure AD](media/service-admin-azure-ad-b2b/azuread-portal-new-guest-user.png)

3. Введите **адрес электронной почты** и **личное сообщение**.

    ![пригласительное сообщение для нового гостевого пользователя на портале Azure AD](media/service-admin-azure-ad-b2b/azuread-portal-invite-message.png)

4. Выберите **Пригласить**.

Чтобы пригласить несколько гостевых пользователей, воспользуйтесь PowerShell. Дополнительные сведения см. в статье [Примеры кода и команд PowerShell для службы совместной работы Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-code-samples).

В полученном электронном письме с приглашением гостевому пользователю нужно выбрать **Get Started** (Приступить к работе). Затем гостевой пользователь добавляется к клиенту.

![Электронное письмо с приглашением для гостевого пользователя](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Специализированные приглашения

Чтобы отправить приглашение в любое время, добавьте внешнего пользователя в список доступа к приложению при его публикации.

![Внешний пользователь добавлен в список доступа приложения](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Гостевой пользователь получит электронное сообщение о предоставлении общего доступа к приложению.

![Электронное сообщение для приложения, к которому предоставлен общим доступ](media/service-admin-azure-ad-b2b/guest-user-invite-email2.png)

Гостевой пользователь должен войти с использованием организационного адреса электронной почты. После входа будет предложено принять приглашение и гостевой пользователь будет перенаправлен к содержимому приложения. Чтобы вернуться в приложение, добавьте ссылку в закладки или сохраните электронное сообщение.

## <a name="licensing"></a>Лицензирование

Для просмотра общедоступного приложения гостевому пользователю понадобится соответствующая лицензия. У вас есть три варианта.

### <a name="use-power-bi-premium"></a>Использование Power BI Premium

Если назначить рабочую область приложения для емкости Power BI Premium, гостевой пользователь сможет работать с приложением без лицензии Power BI Pro. Power BI Premium также позволяет воспользоваться и другими возможностями для приложений, такими как частые обновления, выделенные ресурсы и крупные модели.

![Использование Power BI Premium](media/service-admin-azure-ad-b2b/license-approach1.png)

### <a name="assign-power-bi-pro-license-to-guest-user"></a>Назначение гостевому пользователю лицензии Power BI Pro

Назначенная в клиенте лицензия Power BI Pro позволит гостевому пользователю просматривать содержимое.

> [!NOTE]
> Лицензия Power BI Pro из вашего клиента применяется для гостевых пользователей только при обращении к содержимому в клиенте.

![Назначение лицензии Pro из клиента](media/service-admin-azure-ad-b2b/license-approach2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Применение лицензии Power BI Pro гостевого пользователя

Гостевому пользователю уже назначена лицензия Power BI Pro в клиенте.

![Применение лицензии гостевого пользователя](media/service-admin-azure-ad-b2b/license-approach3.png)

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения, включая сведения о безопасности на уровне строк, см. в [техническом документе](https://aka.ms/powerbi-b2b-whitepaper).

Сведения об Azure Active Directory B2B см. в статье [Что такое служба совместной работы Azure AD B2B](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b)