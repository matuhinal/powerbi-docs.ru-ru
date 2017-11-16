---
title: "Интеграция панели мониторинга в приложение для организации"
description: "Узнайте, как интегрировать (внедрить) панель мониторинга в веб-приложение с помощью API-интерфейсов Power BI."
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
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/05/2017
ms.author: asaxton
ms.openlocfilehash: f3968fd9fb89e868754bb6025a23fdbd028a3965
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="integrate-a-dashboard-into-an-app-for-your-organization"></a>Интеграция панели мониторинга в приложение для организации
Узнайте, как интегрировать (внедрить) панель мониторинга в веб-приложение с помощью вызовов REST API и API JavaScript для Power BI для вашей организации.

![Внедренная панель мониторинга](media/integrate-dashboard/powerbi-embed-dashboard.png)

Для работы с руководством вам потребуется учетная запись **Power BI**. Если у вас нет учетной записи, вы можете [зарегистрироваться для получения бесплатной учетной записи Power BI](../service-self-service-signup-for-power-bi.md) или создать собственный [клиент Azure Active Directory](create-an-azure-active-directory-tenant.md) для тестирования.

> [!NOTE]
> Требуется внедрить панель мониторинга для клиентов с помощью embedtoken? См. статью [Интеграция в приложение панели мониторинга, плитки или отчета (данные принадлежат приложению)](embed-sample-for-customers.md).
> 
> 

Для интеграции панели мониторинга в веб-приложение используется REST API **Power BI** или пакет SDK для C# в Power BI и **маркер доступа** проверки подлинности Azure Active Directory (AD) для получения панели мониторинга. Затем вы загружаете панель мониторинга, используя тот же маркер доступа. API **Power BI** обеспечивает программный доступ к определенным ресурсам **Power BI**. Дополнительные сведения см. в [обзоре интерфейса REST API Power BI](https://msdn.microsoft.com/library/dn877544.aspx) и документации по [API JavaScript для Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Скачивание примера
В этой статье показан код, используемый при [интеграции панели мониторинга в веб-приложение ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) на сайте GitHub. Для работы с этим пошаговым руководством можно загрузить пример кода.

## <a name="step-1---register-an-app-in-azure-ad"></a>Шаг 1. Регистрация приложения в Azure AD
Необходимо зарегистрировать приложение в Azure AD, чтобы осуществлять вызовы REST API. Дополнительные сведения см. в статье [Регистрация приложения Azure AD для внедрения содержимого Power BI](register-app.md).

Если вы скачали [пример интеграции панели мониторинга](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app), можно использовать **идентификатор клиента** и **секрет клиента**, полученные после регистрации, чтобы настроить этот пример для проверки подлинности в Azure AD. Для настройки примера измените **идентификатор** и **секрет клиента** в файле *cloud.config*.

![](media/integrate-dashboard/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Шаг 2. Получение маркера доступа из Azure AD
Перед выполнением вызовов в REST API Power BI в приложении потребуется получить **маркер доступа** из Azure AD. Дополнительные сведения см. в статье [Authenticate users and get an Azure AD access token for your Power BI app](get-azuread-access-token.md) (Проверка подлинности для пользователей и получение маркера доступа Azure AD для приложения Power BI).

## <a name="step-3---get-a-dashboard"></a>Шаг 3. Получение панели мониторинга
Для получения панели мониторинга **Power BI** используется операция [Получение панелей мониторинга](https://msdn.microsoft.com/library/mt465739.aspx), возвращающая список панелей мониторинга **Power BI**. В списке панелей мониторинга можно получить идентификатор панели мониторинга.

![](media/integrate-dashboard/powerbi-embed-dashboard-get-dashboards.png)

### <a name="get-dashboards-using-an-access-token"></a>Получение панели мониторинга с помощью маркера доступа
После получения **маркера доступа** на [шаге 2](#step-2-get-an-access-token-from-azure-ad) можно вызвать операцию [Получение панелей мониторинга](https://msdn.microsoft.com/library/mt465739.aspx). Операция [Получение панелей мониторинга](https://msdn.microsoft.com/library/mt465739.aspx) возвращает список панелей мониторинга. В списке панелей мониторинга можно получить одну панель мониторинга. Ниже приведен полный метод C# для получения панели мониторинга. Примеры использования REST API Power BI см. в документации [Power BI REST API on APIARY](http://docs.powerbi.apiary.io/) (Справочник по REST API Power BI на APIARY).

Для вызова REST API необходимо включить заголовок *авторизации* в формате *Носитель {маркер доступа}*.

#### <a name="get-dashboards-with-the-rest-api"></a>Получение панелей мониторинга с помощью REST API
**Default.aspx.cs**

```
protected void getDashboardsButton_Click(object sender, EventArgs e)
{
    string responseContent = string.Empty;

    //Configure dashboards request
    System.Net.WebRequest request = System.Net.WebRequest.Create(String.Format("{0}dashboards", baseUri)) as System.Net.HttpWebRequest;
    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            responseContent = reader.ReadToEnd();

            //Deserialize JSON string
            PBIDashboards PBIDashboards = JsonConvert.DeserializeObject<PBIDashboards>(responseContent);

            if (PBIDashboards != null)
            {
                var gridViewDashboards = PBIDashboards.value.Select(dashboard => new {
                    Id = dashboard.id,
                    DisplayName = dashboard.displayName,
                    EmbedUrl = dashboard.embedUrl
                });

                this.GridView1.DataSource = gridViewDashboards;
                this.GridView1.DataBind();
            }
        }
    }
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
    public string embedUrl { get; set; }
    public bool isReadOnly { get; set; }
}
```

#### <a name="get-dashboards-using-the-net-sdk"></a>Получение панелей мониторинга с помощью пакета SDK для .NET
Вы можете использовать пакет SDK для .NET, чтобы получить список панелей мониторинга, не вызывая REST API напрямую.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    var embedUrl = dashboard.EmbedUrl
}
```

## <a name="step-4---load-a-dashboard-using-javascript"></a>Шаг 4. Загрузка панели мониторинга с помощью JavaScript
Чтобы загрузить панель мониторинга в элемент div веб-страницы, вы можете использовать JavaScript.

**Default.aspx**

```
<!-- Embed Dashboard-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a dashboard</div>

            <div>Enter an embed url for a dashboard from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedDashboardAction" value="Embed Dashboard" />
        </div>

        <div id="dashboardContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected dashboard.
    var el = document.getElementById("bEmbedDashboardAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedDashboard, false);
    } else {
        el.attachEvent('onclick', updateEmbedDashboard);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded dashboard if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedDashboard();
    }
};

// update embed dashboard
function updateEmbedDashboard() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the dashboard.
    var dashboardContainer = document.getElementById('dashboardContainer');

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("tileClicked", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Если вы скачали и запустили [пример интеграции информационной панели](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app), он будет выглядеть аналогично приведенному ниже.

![](media/integrate-dashboard/powerbi-embed-dashboard.png)

## <a name="tile-clicked-events"></a>События щелчка плитки
Из приведенного выше примера понятно, что вы можете обрабатывать события, когда кто-то щелкает плитку на панели мониторинга. Дополнительные сведения о событиях см. в статье об [обработке событий в API JavaScript](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events).

```
// dashboard.on will add an event handler which prints to Log window.
dashboard.on("tileClicked", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});

// dashboard.on will add an event handler which prints to Log window.
dashboard.on("error", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Error<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});
```

Если вы скачали и запустили [пример интеграции панели мониторинга](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/PowerBI.com%20Integrate/integrate-dashboard-web-app), щелкните плитку, чтобы вывести текст под панелью мониторинга. Текст будет выглядеть примерно так. Этот код позволит вам регистрировать щелчок плитки и переводить пользователя в соответствующее расположение.

```
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "", "navigationUrl": "https://app.powerbi.com/dashboards/fcff76f9-15ff-4a8e-8242-275ac9c25b90/qna?q=count%20of%20new%20hires%20from%20July%202014%20to%20December%202014", "tileId": "0e99b45c-9b53-4920-b239-cee7d37d2369" }
---------
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "https://app.powerbi.com/reportEmbed?reportId=ab199308-80b1-4626-9823-43a84623bd9c", "navigationUrl": "https://app.powerbi.com/reports/ab199308-80b1-4626-9823-43a84623bd9c/ReportSection1", "tileId": "ffc30447-674a-4511-944f-79e182d719de", "pageName": "ReportSection1" }
---------
```

## <a name="working-with-groups-app-workspaces"></a>Работа с группами (рабочими областями приложений)
Чтобы внедрить панель мониторинга из группы (рабочей области приложения), необходимо получить список всех доступных панелей мониторинга в группе, используя указанный ниже вызов интерфейса REST API. Дополнительные сведения о вызове интерфейса REST API см. в статье [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) (Получение информационных панелей). Для получения результатов запроса требуются разрешения в группе.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards
```

Приведенный выше API возвращает список доступных информационных панелей. У каждой информационной панели имеется свойство EmbedUrl, которое поддерживает внедрения группы по умолчанию.

```
https://app.powerbi.com/dashboardEmbed?dashboardId={dashboardId}&groupId={groupId}
```

## <a name="limitations"></a>Ограничения
* Пользователи, работающие с внедренными панелями мониторинга, должны иметь учетные записи Power BI и доступ к панели мониторинга. Панель мониторинга может принадлежать им или совместно использоваться с ними.
* В настоящее время внедренные информационные панели не поддерживают функцию "Вопросы и ответы".
* При совместном использовании информационной панели с группой безопасности в качестве временного ограничения пользователь сначала должен получить доступ к информационным панелям на сайте PowerBI.com и только потом сможет увидеть ее внедренной.

## <a name="next-steps"></a>Дальнейшие действия
Пример приложения для проверки можно найти на сайте GitHub. Примеры выше основаны на этом образце. Дополнительные сведения см. на странице [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app).

Чтобы больше узнать об API JavaScript, ознакомьтесь с документацией по [API JavaScript для Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

