---
title: Получение токена доступа для проверки подлинности
description: Пошаговое руководство по отправке данных — получение токена доступа для проверки подлинности
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: maghan
ms.openlocfilehash: 238d068e5083c8f46ac3299faddd4e0872f0654d
ms.sourcegitcommit: 8ee0ebd4d47a41108387d13a3bc3e7e2770cbeb8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2018
ms.locfileid: "34812636"
---
# <a name="step-2-get-an-authentication-access-token"></a>Шаг 2. Получение токена доступа для проверки подлинности
Эта статья является частью пошагового руководства по [принудительной отправке данных в набор данных](walkthrough-push-data.md).

На **шаге 1** ([Регистрация приложения в Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)) руководства по принудительной отправке данных в набор данных вы зарегистрировали клиентское приложение в Azure AD. На этом шаге вы получите токен доступа для проверки подлинности. Приложения Power BI интегрированы с **Azure AD** для обеспечения безопасного входа и авторизации в приложении. Токен используется для проверки подлинности в **Azure AD** и получения доступа к ресурсам Power BI.

Далее приведены действия по получению токена.

## <a name="get-an-authentication-access-token"></a>Получение токена доступа для проверки подлинности
> **ПРИМЕЧАНИЕ.** Перед началом работы убедитесь, что выполнены предыдущие шаги из пошагового руководства по [принудительной отправке данных в набор данных](walkthrough-push-data.md).
> 
> 

1. В Visual Studio 2015 создайте проект **консольного приложения** .
2. Установите [библиотеку проверки подлинности Azure AD для пакета NuGet .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/). Этот пакет используется при получении токена безопасности для проверки подлинности в приложении .NET. Ниже приведены действия по установке пакета.
   
     а. В Visual Studio 2015 выберите пункты **Сервис** > **Диспетчер пакетов NuGet** > **Консоль диспетчера пакетов**.
   
     б. В **консоли диспетчера пакетов**введите команду Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612.
3. Добавьте приведенный ниже код в класс Program {...}.
4. Замените "{ClientID}" на **идентификатор клиента**, который вы получили при регистрации приложения. См. статью [Регистрация приложения в Azure AD](walkthrough-push-data-register-app-with-azure-ad.md).
5. После установки пакета Microsoft.IdentityModel.Clients.ActiveDirectory добавьте **using Microsoft.IdentityModel.Clients.ActiveDirectory;** в файл Program.cs.
6. Запустите консольное приложение и войдите в свою учетную запись Power BI. В окне консоли вы должны увидеть строку токена.

**Пример кода получения маркера безопасности для проверки подлинности**

Добавьте этот код в Program {...}.

* Переменная токена для вызова операций:
  
  ```
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* В методе static void Main(string[] args):
  
  ```
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* Добавьте метод GetToken():

```
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
           string authorityUri = "https://login.windows.net/common/oauth2/authorize";

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
                string authorityUri = "https://login.windows.net/common/oauth2/authorize";

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


[Дальнейшие действия >](walkthrough-push-data-create-dataset.md)

## <a name="next-steps"></a>Дальнейшие действия
[Создание набора данных в панели мониторинга Power BI](walkthrough-push-data-create-dataset.md)  
[Регистрация приложения в Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)  
[Библиотека проверки подлинности Azure AD для пакета NuGet для .NET](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Принудительная отправка данных в панель мониторинга Power BI](walkthrough-push-data.md)  
[Обзор интерфейса REST API Power BI](overview-of-power-bi-rest-api.md)  
[Справочник по REST API Power BI](https://docs.microsoft.com/rest/api/power-bi/)  
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

