---
title: Проверка подлинности для пользователей и получение маркера доступа Azure AD для приложения
description: Узнайте, как зарегистрировать приложение в Azure Active Directory для использования внедренного содержимого Power BI.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 08/11/2017
ms.author: maghan
ms.openlocfilehash: 339390bba2e35101bdd42f7f51ab059473231575
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34290897"
---
# <a name="authenticate-users-and-get-an-azure-ad-access-token-for-your-power-bi-app"></a>Проверка подлинности для пользователей и получение маркера доступа Azure AD для приложения Power BI
Узнайте, как выполнять проверку подлинности для пользователей в приложении Power BI и получить маркер доступа для использования с REST API.

Перед вызовом REST API Power BI нужно получить **маркер доступа для проверки подлинности** (маркер доступа) Azure Active Directory (Azure AD). **Маркер доступа** позволяет вашему приложению обратиться к информационным панелям, плиткам и отчетам **Power BI**. Дополнительные сведения об использовании **токена доступа** Azure Active Directory см. в статье [Поток предоставления кода авторизации Azure AD](https://msdn.microsoft.com/library/azure/dn645542.aspx).

Способ получения маркера доступа зависит от того, каким образом внедряется содержимое. В этой статье используются два разных подхода.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Маркер доступа для пользователей Power BI (данные принадлежат пользователю)
В этом примере пользователи входят в Azure AD вручную, используя имя для входа, предоставленное организацией. Этот вариант используется при внедрении для пользователей Power BI, работающих с содержимым, доступ к которому предоставлен в службе Power BI.

### <a name="get-an-authorization-code-from-azure-ad"></a>Получение кода авторизации из Azure AD
Первый шаг при получении **токена доступа** заключается в получении кода авторизации из **Azure AD**. Для этого создайте строку запроса со следующими свойствами и выполните перенаправление в **Azure AD**.

**Строка запроса для кода авторизации**

```
var @params = new NameValueCollection
{
    //Azure AD will return an authorization code. 
    //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
    {"response_type", "code"},

    //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
    //You get the client id when you register your Azure app.
    {"client_id", Properties.Settings.Default.ClientID},

    //Resource uri to the Power BI resource to be authorized
    // https://analysis.windows.net/powerbi/api
    {"resource", Properties.Settings.Default.PowerBiAPI},

    //After user authenticates, Azure AD will redirect back to the web app
    {"redirect_uri", "http://localhost:13526/Redirect"}
};
```

После создания строки запроса выполните перенаправление в **Azure AD** для получения **кода авторизации**.  Ниже приведен полный метод C# для создания строки запроса **кода авторизации** и перенаправления в **Azure AD**. С помощью полученного **кода авторизации** вы получаете **маркер доступа**.

В redirect.aspx.cs выполняется вызов [AuthenticationContext.AcquireTokenByAuthorizationCode](https://msdn.microsoft.com/library/azure/dn479531.aspx) для создания маркера.

**Получение кода авторизации**

```
protected void signInButton_Click(object sender, EventArgs e)
{
    //Create a query string
    //Create a sign-in NameValueCollection for query string
    var @params = new NameValueCollection
    {
        //Azure AD will return an authorization code. 
        //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
        {"response_type", "code"},

        //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
        //You get the client id when you register your Azure app.
        {"client_id", Properties.Settings.Default.ClientID},

        //Resource uri to the Power BI resource to be authorized
        // https://analysis.windows.net/powerbi/api
        {"resource", Properties.Settings.Default.PowerBiAPI},

        //After user authenticates, Azure AD will redirect back to the web app
        {"redirect_uri", "http://localhost:13526/Redirect"}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect authority
    //Authority Uri is an Azure resource that takes a client id to get an Access token
    // AADAuthorityUri = https://login.windows.net/common/oauth2/authorize/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>Получение маркера доступа из кода авторизации
Теперь у вас должен быть код авторизации из Azure AD. Когда **Azure AD** выполняет перенаправление обратно в веб-приложение с использованием **кода авторизации**, можно воспользоваться **кодом авторизации** для получения токена доступа. Ниже приведен пример C#, который вы можете использовать на странице перенаправления и в событии Page_Load для страницы default.aspx.

Пространство имен **Microsoft.IdentityModel.Clients.ActiveDirectory** можно извлечь из пакета NuGet [библиотеки аутентификации Active Directory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/).

```
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

**Redirect.aspx.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{
    //Redirect uri must match the redirect_uri used when requesting Authorization code.
    string redirectUri = String.Format("{0}Redirect", Properties.Settings.Default.RedirectUrl);
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;

    // Get the auth code
    string code = Request.Params.GetValues(0)[0];

    // Get auth token from auth code
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ClientCredential cc = new ClientCredential
        (Properties.Settings.Default.ClientID,
        Properties.Settings.Default.ClientSecret);

    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);

    //Set Session "authResult" index string to the AuthenticationResult
    Session[_Default.authResultString] = AR;

    //Redirect back to Default.aspx
    Response.Redirect("/Default.aspx");
}
```

**Default.aspx**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{

    //Test for AuthenticationResult
    if (Session[authResultString] != null)
    {
        //Get the authentication result from the session
        authResult = (AuthenticationResult)Session[authResultString];

        //Show Power BI Panel
        signInStatus.Visible = true;
        signInButton.Visible = false;

        //Set user and token from authentication result
        userLabel.Text = authResult.UserInfo.DisplayableId;
        accessTokenTextbox.Text = authResult.AccessToken;
    }
}
```

## <a name="access-token-for-non-power-bi-users-app-owns-data"></a>Маркер доступа для пользователей, не работающих с Power BI (данные принадлежат приложению)
Этот подход обычно используется для приложений независимых поставщиков, когда права на доступ к данным принадлежат такому приложению. Пользователи могут и не работать с Power BI, поэтому приложение управляет проверкой подлинности и доступом для конечных пользователей.

Для этого подхода используется одна *главная* учетная запись пользователя Power BI Pro. Учетные данные для этой учетной записи сохраняются приложением. Приложение выполняет проверку подлинности в Azure AD с помощью этих сохраненных учетных данных. Следующий образец кода взят из [примера с данными, принадлежащими приложению](https://github.com/guyinacube/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

**HomeController.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

// Create a user password cradentials.
var credential = new UserPasswordCredential(Username, Password);

// Authenticate using created credentials
var authenticationContext = new AuthenticationContext(AuthorityUrl);
var authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, ClientId, credential);

if (authenticationResult == null)
{
    return View(new EmbedConfig()
    {
        ErrorMessage = "Authentication Failed."
    });
}

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

Дополнительные сведения об использовании оператора **await**, см. в документации [await (Справочник по C#)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)

## <a name="next-steps"></a>Дальнейшие действия
Теперь, когда у вас есть маркер доступа, можно вызвать REST API Power BI, чтобы внедрить содержимое. Дополнительные сведения о внедрении содержимого см. в статье [Как внедрять панели мониторинга, отчеты и плитки Power BI](embedding-content.md#step-2-embed-your-content).

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

