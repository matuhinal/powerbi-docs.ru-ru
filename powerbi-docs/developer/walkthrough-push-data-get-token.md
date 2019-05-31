---
title: Получение токена доступа для проверки подлинности
description: Пошаговое руководство по отправке данных — получение токена доступа для проверки подлинности
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: 4a0b0f5e7d697c137da343576d05fbcc91b4a4f7
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710355"
---
# <a name="step-2-get-an-authentication-access-token"></a>Шаг 2. Получение токена доступа для проверки подлинности

Эта статья является частью пошагового руководства по [принудительной отправке данных в набор данных](walkthrough-push-data.md).

На **шаге 1** ([Регистрация приложения в Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)) руководства по принудительной отправке данных в набор данных вы зарегистрировали клиентское приложение в Azure AD. На этом шаге вы получите токен доступа для проверки подлинности. Приложения Power BI интегрированы с **Azure AD** для обеспечения безопасного входа и авторизации в приложении. Токен используется для проверки подлинности в **Azure AD** и получения доступа к ресурсам Power BI.

Далее приведены действия по получению токена.

## <a name="get-an-authentication-access-token"></a>Получение токена доступа для проверки подлинности

> **ПРИМЕЧАНИЕ**. Перед началом работы убедитесь, что выполнены предыдущие шаги из пошагового руководства по [принудительной отправке данных в набор данных](walkthrough-push-data.md).

1. Создайте в Visual Studio (2015 или более поздней версии), **консольное приложение** проекта.
2. Установите [библиотеку проверки подлинности Azure AD для пакета NuGet .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/2.22.302111727). Этот пакет используется при получении токена безопасности для проверки подлинности в приложении .NET. Ниже приведены действия по установке пакета.

     а. В Visual Studio (2015 или более поздней версии) выберите **средства** > **диспетчер пакетов NuGet** > **консоль диспетчера пакетов**.

     б. В **консоли диспетчера пакетов**введите команду Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612.
3. Добавьте приведенный ниже код в класс Program {...}.
4. Замените "{ClientID}" на **идентификатор клиента**, который вы получили при регистрации приложения. См. статью [Регистрация приложения в Azure AD](walkthrough-push-data-register-app-with-azure-ad.md).
5. После установки пакета Microsoft.IdentityModel.Clients.ActiveDirectory добавьте **using Microsoft.IdentityModel.Clients.ActiveDirectory;** в файл Program.cs.
6. Запустите консольное приложение и войдите в свою учетную запись Power BI. В окне консоли вы должны увидеть строку токена.

**Пример кода получения маркера безопасности для проверки подлинности**

Добавьте этот код в Program {...}.

* Переменная токена для вызова операций:
  
  ```csharp
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* В методе static void Main(string[] args):
  
  ```csharp
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* Добавьте метод GetToken():

```csharp
       #region Get an authentication access token
       private static string GetToken()
       {
           // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
           // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

           //The client id that Azure AD created when you registered your client app.
           string clientID = "{Client_ID}";

           //RedirectUri you used when you register your app.
           //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
           // You can use this redirect uri for your client app
           string redirectUri = "https://login.live.com/oauth20_desktop.srf";

           //Resource Uri for Power BI API
           string resourceUri = "https://analysis.windows.net/powerbi/api";

           //OAuth2 authority Uri
           string authorityUri = "https://login.microsoftonline.net/common/";

           //Get access token:
           // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
           // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
           // To install the Active Directory Authentication Library NuGet package in Visual Studio,
           //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

           // AcquireToken will acquire an Azure access token
           // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
           AuthenticationContext authContext = new AuthenticationContext(authorityUri);
           string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

           Console.WriteLine(token);
           Console.ReadLine();

           return token;
       }

       #endregion
```

Получив токен проверки подлинности, вы можете вызывать любые операции Power BI. Далее показано, как вызвать операцию [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets) для создания набора данных, отправляемого в панель мониторинга.

На следующем шаге выполняются действия по [созданию набора данных в Power BI](walkthrough-push-data-create-dataset.md).

Ниже приведен [полный листинг кода](#code).

<a name="code"/>

## <a name="complete-code-listing"></a>Полный листинг кода

```csharp
using System;
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace walkthrough_push_data
{
    class Program
    {
        private static string token = string.Empty;

        static void Main(string[] args)
        {

            //Get an authentication access token
            token = GetToken();

        }

        #region Get an authentication access token
        private static string GetToken()
        {
            // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
            // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

            //The client id that Azure AD created when you registered your client app.
            string clientID = "{Client_ID}";

            //RedirectUri you used when you register your app.
            //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
            // You can use this redirect uri for your client app
            string redirectUri = "https://login.live.com/oauth20_desktop.srf";

            //Resource Uri for Power BI API
            string resourceUri = "https://analysis.windows.net/powerbi/api";

            //OAuth2 authority Uri
            string authorityUri = "https://login.microsoftonline.com/common/";

            //Get access token:
            // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
            // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
            // To install the Active Directory Authentication Library NuGet package in Visual Studio,
            //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

            // AcquireToken will acquire an Azure access token
            // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
            AuthenticationContext authContext = new AuthenticationContext(authorityUri);
            string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

            Console.WriteLine(token);
            Console.ReadLine();

            return token;
        }

        #endregion

    }
}
```

[Дальнейшие действия >](walkthrough-push-data-create-dataset.md)

## <a name="next-steps"></a>Дальнейшие действия

[Создание набора данных в панели мониторинга Power BI](walkthrough-push-data-create-dataset.md)  
[Регистрация приложения в Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)  
[Библиотека проверки подлинности Azure AD для пакета NuGet для .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Принудительная отправка данных в панель мониторинга Power BI](walkthrough-push-data.md)  
[Обзор интерфейса REST API Power BI](overview-of-power-bi-rest-api.md)  
[Справочник по REST API Power BI](https://docs.microsoft.com/rest/api/power-bi/)  
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)