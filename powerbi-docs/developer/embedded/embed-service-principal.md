---
title: Внедрение содержимого Power BI с помощью субъект-службы и секрета приложения
description: Сведения о том, как выполнять проверку подлинности внедренной аналитики с помощью субъекта-службы приложения Azure Active Directory и секрета приложения.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: how-to
ms.custom: ''
ms.date: 10/15/2020
ms.openlocfilehash: 6f6a13f239d1bcfa7731361f4efcd129da7e2031
ms.sourcegitcommit: 1428acb6334649fc2d3d8ae4c42cfbc17e8f7476
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2020
ms.locfileid: "92197750"
---
# <a name="embed-power-bi-content-with-service-principal-and-an-application-secret"></a>Внедрение содержимого Power BI с помощью субъект-службы и секрета приложения

[!INCLUDE[service principal overview](../../includes/service-principal-overview.md)]

В этой статье описывается проверка подлинности субъекта-службы с помощью *идентификатора приложения* и *секрета приложения* .

>[!NOTE]
>Рекомендуем защищать серверные службы с помощью сертификатов, а не секретных ключей.
>* [Дополнительные сведения о получении маркеров доступа из Azure AD с помощью секретных ключей или сертификатов](/azure/architecture/multitenant-identity/client-assertion).
>* [Внедрение содержимого Power BI с помощью субъекта-службы и сертификата](embed-service-principal-certificate.md)

## <a name="method"></a>Метод

Чтобы использовать субъект-службу и идентификатор приложения со встроенной аналитикой, выполните следующие действия.

1. Создайте [приложение Azure AD](/azure/active-directory/manage-apps/what-is-application-management).

    1. Создайте секрет приложения Azure AD.
    
    2. Получите *Идентификатор приложения* и *Секрет приложения* .

    >[!NOTE]
    >Эти действия описаны в **шаге 1** . Дополнительные сведения о создании приложения Azure AD см. в статье [Создание приложения Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal).

2. Создайте группу безопасности Azure AD.

3. Включите параметры администрирования службы Power BI.

4. Добавьте субъект-службу в рабочую область.

5. Внедрите свое содержимое.

> [!IMPORTANT]
> После активации субъекта-службы для использования с Power BI разрешения приложения в Active Directory перестают действовать. В дальнейшем управление разрешениями приложения осуществляется на портале администрирования Power BI.

## <a name="step-1---create-an-azure-ad-app"></a>Шаг 1. Создание приложения Azure AD

Создайте приложение Azure AD одним из методов, перечисленных ниже.

* Создать приложение на [портале Microsoft Azure](https://portal.azure.com/#allservices)

* Создать приложение с помощью [PowerShell](/powershell/azure/create-azure-service-principal-azureps).

### <a name="creating-an-azure-ad-app-in-the-microsoft-azure-portal"></a>Создание приложения Azure AD на портале Microsoft Azure

[!INCLUDE[service create app](../../includes/service-principal-create-app.md)]

7. Перейдите на вкладку **Сертификаты и секреты** .

     ![Снимок экрана: панель "Сертификаты и секреты" для приложения на портале Azure.](media/embed-service-principal/certificates-and-secrets.png)


8. Щелкните **Создать секрет клиента** .

    ![Снимок экрана: кнопка "Создать секрет клиента" на панели "Сертификаты и секреты".](media/embed-service-principal/new-client-secret.png)

9. В окне *Добавление секрета клиента* введите описание, укажите, когда должен истечь срок действия секрета клиента, и нажмите кнопку **Добавить** .

10. Скопируйте и сохраните значение *Секрет клиента* .

    ![Снимок экрана: размытое значение секрета на панели "Сертификаты и секреты".](media/embed-service-principal/client-secret-value.png)

    >[!NOTE]
    >После закрытия этого окна значение секрета клиента будет скрыто, и вы не сможете снова просмотреть или скопировать его.

### <a name="creating-an-azure-ad-app-using-powershell"></a>Создание приложения Azure AD с помощью PowerShell

В этом разделе содержится пример скрипта для создания нового приложения Azure AD с помощью [PowerShell](/powershell/azure/create-azure-service-principal-azureps).

```powershell
# The app ID - $app.appid
# The service principal object ID - $sp.objectId
# The app key - $key.value

# Sign in as a user that's allowed to create an app
Connect-AzureAD

# Create a new Azure AD web application
$app = New-AzureADApplication -DisplayName "testApp1" -Homepage "https://localhost:44322" -ReplyUrls "https://localhost:44322"

# Creates a service principal
$sp = New-AzureADServicePrincipal -AppId $app.AppId

# Get the service principal key
$key = New-AzureADServicePrincipalPasswordCredential -ObjectId $sp.ObjectId
```
[!INCLUDE[service create steps two, three and four](../../includes/service-principal-create-steps.md)]

## <a name="step-5---embed-your-content"></a>Шаг 5. Внедрение содержимого

Вы можете внедрить содержимое в пример приложения или в собственное приложение.

* [Внедрение содержимого с помощью примера приложения](embed-sample-for-customers.md#embed-content-using-the-sample-application)
* [Внедрение содержимого в приложении](embed-sample-for-customers.md#embed-content-within-your-application)

После того, как содержимое будет внедрено, вы можете [переносить его в производственную среду](embed-sample-for-customers.md#move-to-production).

[!INCLUDE[service principal limitations](../../includes/service-principal-limitations.md)]

## <a name="next-steps"></a>Дальнейшие действия

>[!div class="nextstepaction"]
>[Регистрация приложения](register-app.md)

> [!div class="nextstepaction"]
>[Power BI Embedded для клиентов](embed-sample-for-customers.md)

>[!div class="nextstepaction"]
>[Объекты приложения и субъекта-службы в Azure Active Directory](/azure/active-directory/develop/app-objects-and-service-principals)

>[!div class="nextstepaction"]
>[Безопасность на уровне строк с использованием локального шлюза данных с субъектом-службой](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal)

>[!div class="nextstepaction"]
>[Внедрение содержимого Power BI с помощью субъект-службы и сертификата](embed-service-principal-certificate.md)