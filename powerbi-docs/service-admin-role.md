---
title: Основные сведения о роли администратора Power BI
description: Сведения о настройке безопасности на уровне строк для импортированных наборов данных и DirectQuery в службе Power BI.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/30/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: e4cd85e0e5b4f10ead772875434bce3bd0973505
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54287589"
---
# <a name="understanding-the-power-bi-service-administrator-role"></a>Основные сведения о роли администратора службы Power BI

Узнайте, как использовать роль администратора службы Power BI организации. Пользователи с этой ролью могут полностью управлять клиентом Power BI и его административными функциями (кроме лицензирования).

<iframe width="640" height="360" src="https://www.youtube.com/embed/PQRbdJgEm3k?showinfo=0" frameborder="0" allowfullscreen></iframe>

Роль администратора службы Power BI можно назначать пользователям, которым нужен доступ к порталу администрирования Power BI без полного административного доступа к службам Office 365.

Эту роль пользователям назначают администраторы управления пользователями Office 365 в Центре администрирования Office 365 или с помощью скрипта PowerShell. Когда роль будет назначена, пользователь сможет получить доступ к [порталу администрирования Power BI](service-admin-portal.md). Пользователь будет иметь доступ к метрикам использования, а также сможет управлять функциями Power BI на уровне клиента.

## <a name="limitations-and-considerations"></a>Рекомендации и ограничения

Роль администратора службы Power BI не предусматривает следующие возможности:

* изменение пользователей и лицензий в центре администрирования Office 365;

* Доступ к журналам аудита. Дополнительные сведения см. в статье [Применение функции аудита в своей организации](service-admin-auditing.md).

## <a name="assign-users-to-the-admin-role-in-office-365"></a>назначение пользователям роли администратора в Office 365.

Чтобы назначить пользователям роль администратора Power BI в Центре администрирования Office 365, выполните следующие действия:

1. В Центре администрирования Office 365 выберите **Пользователи** > **Активные пользователи**.

    ![Центр администрирования Office 365](media/service-admin-role/powerbi-admin-users.png)

1. Выберите пользователя, которому нужно назначить роль.

1. В разделе **Роли** выберите **Изменить**.

    ![Изменение ролей](media/service-admin-role/powerbi-admin-edit-roles.png)

1. Выберите **Настраиваемый администратор** > **Администратор службы Power BI**.

    ![Администратор служб Power BI](media/service-admin-role/powerbi-admin-role.png)

1. Выберите **Сохранить** и **Закрыть**.

В списке ролей пользователя должна появиться роль **Power BI service administrator** (Администратор службы Power BI).

![Роли](media/service-admin-role/powerbi-admin-role-set.png)

## <a name="assign-users-to-the-admin-role-with-powershell"></a>Назначение пользователям роли администратора с помощью PowerShell

Вы также можете назначать роли пользователям с помощью PowerShell. Управление пользователями осуществляется с помощью Azure Active Directory (Azure AD). Если у вас нет модуля PowerShell для Azure AD, [скачайте и установите последнюю версию](https://www.powershellgallery.com/packages/AzureAD/).

1. Сначала получите **идентификатор объекта** для роли **Администратор службы Power BI**. Чтобы получить **идентификатор объекта**, можно выполнить команду [Get-AzureADDirectoryRole](/powershell/module/azuread/get-azureaddirectoryrole).

    ```
    PS C:\Windows\system32> Get-AzureADDirectoryRole

    ObjectId                             DisplayName                        Description
    --------                             -----------                        -----------
    00f79122-c45d-436d-8d4a-2c0c6ca246bf Power BI Service Administrator     Full access in the Power BI Service.
    250d1222-4bc0-4b4b-8466-5d5765d14af9 Helpdesk Administrator             Helpdesk Administrator has access to perform..
    3ddec257-efdc-423d-9d24-b7cf29e0c86b Directory Synchronization Accounts Directory Synchronization Accounts
    50daa576-896c-4bf3-a84e-1d9d1875c7a7 Company Administrator              Company Administrator role has full access t..
    6a452384-6eb9-4793-8782-f4e7313b4dfd Device Administrators              Device Administrators
    9900b7db-35d9-4e56-a8e3-c5026cac3a11 AdHoc License Administrator        Allows access manage AdHoc license.
    a3631cce-16ce-47a3-bbe1-79b9774a0570 Directory Readers                  Allows access to various read only tasks in ..
    f727e2f3-0829-41a7-8c5c-5af83c37f57b Email Verified User Creator        Allows creation of new email verified users.
    ```

    В этом случае **идентификатором объекта** роли будет 00f79122-c45d-436d-8d4a-2c0c6ca246bf.

1. Затем получите **идентификатор объекта** пользователя. Его можно найти, выполнив команду [Get-AzureADUser](/powershell/module/azuread/get-azureaduser).

    ```
    PS C:\Windows\system32> Get-AzureADUser -SearchString 'tim@contoso.com'

    ObjectId                             DisplayName UserPrincipalName      UserType
    --------                             ----------- -----------------      --------
    6a2bfca2-98ba-413a-be61-6e4bbb8b8a4c Tim         tim@contoso.com        Member
    ```

1. Чтобы добавить участника в роль, выполните команду [Add-AzureADDirectoryRoleMember](/powershell/module/azuread/add-azureaddirectoryrolemember).

    | Параметр | Описание |
    | --- | --- |
    | ObjectId |Идентификатор объекта роли. |
    | RefObjectId |Идентификатор объекта участников. |

    ```powershell
    Add-AzureADDirectoryRoleMember -ObjectId 00f79122-c45d-436d-8d4a-2c0c6ca246bf -RefObjectId 6a2bfca2-98ba-413a-be61-6e4bbb8b8a4c
    ```

## <a name="next-steps"></a>Дальнейшие действия

[Администрирование Power BI в организации](service-admin-administering-power-bi-in-your-organization.md)  
[Портал администрирования Power BI](service-admin-portal.md)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)