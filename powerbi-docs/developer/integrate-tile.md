---
title: "Интеграция плитки Power BI в приложение для организации"
description: "Пошаговое руководство по интеграции плитки в приложение, пример кода"
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
ms.date: 12/19/2017
ms.author: asaxton
ms.openlocfilehash: 70ffefa9845f8440205460ee0083f8dc334b7c81
ms.sourcegitcommit: 7517c068db806f12bb0b953e9a1bd4249ca12da5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="integrate-a-tile-into-an-app-user-owns-data"></a>Интеграция плитки в приложение (данные принадлежат пользователю)
Узнайте, как интегрировать (внедрить) плитку в веб-приложение с помощью вызовов REST API и API JavaScript для Power BI для вашей организации.

![Внедренная в веб-приложение плитка](media/integrate-tile/powerbi-embedded-tile.png)

Для работы с руководством вам потребуется учетная запись **Power BI**. Если у вас нет учетной записи, вы можете [зарегистрироваться для получения бесплатной учетной записи Power BI](../service-self-service-signup-for-power-bi.md) или создать собственный [клиент Azure Active Directory](create-an-azure-active-directory-tenant.md) для тестирования.

> [!NOTE]
> Требуется внедрить плитку для клиентов с помощью embedtoken? См. статью [Интеграция в приложение панели мониторинга, плитки или отчета (данные принадлежат приложению)](embed-sample-for-customers.md).
> 
> 

Для интеграции плитки в веб-приложение используется REST API **Power BI** или пакет SDK для C# в Power BI и **маркер доступа** проверки подлинности Azure Active Directory (AD) для получения плитки. Затем вы загружаете плитку, используя тот же маркер доступа. API **Power BI** обеспечивает программный доступ к определенным ресурсам **Power BI**. Дополнительные сведения см. в [обзоре интерфейса REST API Power BI](https://msdn.microsoft.com/library/dn877544.aspx) и документации по [API JavaScript для Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Скачивание примера
В этой статье показан код, используемый при [интеграции плитки в веб-приложение ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) на сайте GitHub. Для работы с этим пошаговым руководством можно загрузить пример кода.

## <a name="step-1---register-an-app-in-azure-ad"></a>Шаг 1. Регистрация приложения в Azure AD
Необходимо зарегистрировать приложение в Azure AD, чтобы осуществлять вызовы REST API. Дополнительные сведения см. в статье [Регистрация приложения Azure AD для внедрения содержимого Power BI](register-app.md).

Если вы скачали код [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app), можно использовать **идентификатор** и **секрет клиента**, полученные после регистрации, чтобы настроить этот пример для аутентификации в Azure AD. Для настройки примера измените **идентификатор** и **секрет клиента** в файле *cloud.config*.

![](media/integrate-tile/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Шаг 2. Получение маркера доступа из Azure AD
Перед выполнением вызовов в REST API Power BI в приложении потребуется получить **маркер доступа** из Azure AD. Дополнительные сведения см. в статье [Authenticate users and get an Azure AD access token for your Power BI app](get-azuread-access-token.md) (Проверка подлинности для пользователей и получение маркера доступа Azure AD для приложения Power BI).

## <a name="step-3---get-a-tile"></a>Шаг 3. Получение плитки
Для получения плитки **Power BI** используется операция [Получение плиток](https://msdn.microsoft.com/library/mt465741.aspx), возвращающая список плиток **Power BI** для определенной панели мониторинга. В списке плиток можно получить идентификатор плитки и внедрить URL-адрес.

Перед получением плитки необходимо получить идентификатор панели мониторинга. Сведения о способах получения панели мониторинга см. в статье [Интеграция информационной панели в приложение](integrate-dashboard.md).

### <a name="get-tiles-using-an-access-token"></a>Получение плиток с помощью маркера доступа
После получения **маркера доступа** на [шаге 2](#step-2-get-an-access-token-from-azure-ad) можно вызвать операцию [Получение плиток](https://msdn.microsoft.com/library/mt465741.aspx). Операция [Получение плиток](https://msdn.microsoft.com/library/mt465741.aspx) возвращает список плиток. Можно получить одну плитку в списке плиток. Ниже приведен полный метод C# для получения плитки. 

Для вызова REST API необходимо включить заголовок *авторизации* в формате *Носитель {маркер доступа}*.

#### <a name="get-tiles-with-the-rest-api"></a>Получение плиток с помощью API REST
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-tiles-using-the-net-sdk"></a>Получение плиток с помощью пакета SDK для .NET
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
    ODataResponseListDashboard tiles = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    // Get the first tile from the above dashbaord
    ODataResponseListTile tiles = client.Dashboards.GetTiles(dashboard.Id);

    Tile tile = tiles.Value.FirstOrDefault();
}
```

## <a name="step-4---load-a-tile-using-javascript"></a>Шаг 4. Загрузка плитки с помощью JavaScript
Чтобы загрузить плитку в элемент div веб-страницы, вы можете использовать JavaScript.

**Default.aspx**

```
<!-- Embed Tile-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a tile</div>

            <div>Enter an embed url for a tile from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedTileAction" value="Embed Tile" />
        </div>

        <div id="tileContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected tile.
    var el = document.getElementById("bEmbedTileAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedTile, false);
    } else {
        el.attachEvent('onclick', updateEmbedTile);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded tile if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedTile();
    }
};

// update embed tile
function updateEmbedTile() {

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
        type: 'tile',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the tile.
    var tileContainer = document.getElementById('tileContainer');

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);

    // tile.on will add an event handler which prints to Log window.
    tile.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Если вы скачали и запустили код [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app), он будет выглядеть аналогично приведенному ниже примеру.

![Внедренная в веб-приложение плитка](media/integrate-tile/powerbi-embedded-tile.png)

## <a name="working-with-groups-app-workspaces"></a>Работа с группами (рабочими областями приложений)
Чтобы внедрить плитку из группы (рабочей области приложения), необходимо получить список всех доступных плиток в группе, используя следующий вызов интерфейса REST API. Дополнительные сведения о вызове интерфейса REST API см. в статье [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) (Получение плиток). Для получения результатов запроса требуются разрешения в группе.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboard_id}/tiles
```

Указанный выше API возвращает список доступных плиток. У каждой плитки есть свойство EmbedUrl, которое поддерживает внедрение группы по умолчанию.

```
https://app.powerbi.com/embed?dashboardId={dashboard_id}&tileId={tile_id}&groupId={group_id}
```

## <a name="next-steps"></a>Дальнейшие действия
[Внедрение плиток](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Tile-Embed). Вики-сайт для Power BI и JavaScript.

[API JavaScript для Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

Пример [интеграции плитки в веб приложение](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) на сайте GitHub.

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

