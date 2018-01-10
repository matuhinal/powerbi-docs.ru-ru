---
title: "Интеграция отчета Power BI в приложение для организации"
description: "Узнайте, как интегрировать (внедрить) отчет в веб-приложение с помощью API-интерфейсов Power BI."
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
ms.openlocfilehash: 8285cbbc2d8dee653863cad50036da58362c32d1
ms.sourcegitcommit: 7517c068db806f12bb0b953e9a1bd4249ca12da5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="integrate-a-report-into-an-app-for-your-organization"></a>Интеграция отчета в приложение для организации
Узнайте, как интегрировать (внедрить) отчет в веб-приложение с помощью вызовов REST API и API JavaScript для Power BI для вашей организации.

![Пример внедренного отчета](media/integrate-report/powerbi-embedded-report.png)

Для работы с руководством вам потребуется учетная запись **Power BI**. Если у вас нет учетной записи, вы можете [зарегистрироваться для получения бесплатной учетной записи Power BI](../service-self-service-signup-for-power-bi.md) или создать собственный [клиент Azure Active Directory](create-an-azure-active-directory-tenant.md) для тестирования.

> [!NOTE]
> Требуется внедрить отчет для клиентов с помощью embedtoken? См. статью [Интеграция в приложение панели мониторинга, плитки или отчета (данные принадлежат приложению)](embed-sample-for-customers.md).
> 
> 

Для интеграции отчета в веб-приложение используется REST API **Power BI** или пакет SDK для C# в Power BI и **маркер доступа** проверки подлинности Azure Active Directory (AD) для получения отчета. Затем вы загружаете отчет, используя тот же маркер доступа. API **Power BI** обеспечивает программный доступ к определенным ресурсам **Power BI**. Дополнительные сведения см. в [обзоре интерфейса REST API Power BI](https://msdn.microsoft.com/library/dn877544.aspx) и документации по [API JavaScript для Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Скачивание примера
В этой статье показан код, используемый при [интеграции отчета в веб-приложение ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) на сайте GitHub. Для работы с этим пошаговым руководством можно загрузить пример кода.

## <a name="step-1---register-an-app-in-azure-ad"></a>Шаг 1. Регистрация приложения в Azure AD
Необходимо зарегистрировать приложение в Azure AD, чтобы осуществлять вызовы REST API. Дополнительные сведения см. в статье [Регистрация приложения Azure AD для внедрения содержимого Power BI](register-app.md).

Если вы скачали код [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), можно использовать **идентификатор** и **секрет клиента**, полученные после регистрации, чтобы настроить этот пример для аутентификации в Azure AD. Для настройки примера измените **идентификатор** и **секрет клиента** в файле *cloud.config*.

![](media/integrate-report/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>Шаг 2. Получение маркера доступа из Azure AD
Перед выполнением вызовов в REST API Power BI в приложении потребуется получить **маркер доступа** из Azure AD. Дополнительные сведения см. в статье [Authenticate users and get an Azure AD access token for your Power BI app](get-azuread-access-token.md) (Проверка подлинности для пользователей и получение маркера доступа Azure AD для приложения Power BI).

## <a name="step-3---get-a-report"></a>Шаг 3. Получение отчета
Для получения отчета **Power BI** используется операция [Получение отчетов](https://msdn.microsoft.com/library/mt634543.aspx), возвращающая список отчетов **Power BI**. В списке отчетов можно получить идентификатор отчета.

### <a name="get-reports-using-an-access-token"></a>Получение отчетов с помощью маркера доступа
После получения **маркера доступа** на [шаге 2](#step-2-get-an-access-token-from-azure-ad) можно вызвать операцию [Получение отчетов](https://msdn.microsoft.com/library/mt634543.aspx). Операция [Получение отчетов](https://msdn.microsoft.com/library/mt634543.aspx) возвращает список отчетов. Можно получить один отчет в списке отчетов. Ниже приведен полный метод C# для получения отчета. 

Для вызова REST API необходимо включить заголовок *авторизации* в формате *Носитель {маркер доступа}*.

#### <a name="get-reports-with-the-rest-api"></a>Получение отчетов с помощью REST API
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-reports-using-the-net-sdk"></a>Получение отчетов с помощью пакета SDK для .NET
Вы можете использовать пакет SDK для .NET, чтобы получить список отчетов, не вызывая REST API напрямую.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

## <a name="step-4---load-a-report-using-javascript"></a>Шаг 4. Загрузка отчета с помощью JavaScript
Чтобы загрузить отчет в элемент div веб-страницы, вы можете использовать JavaScript.

**Default.aspx**

```
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

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
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

Если вы скачали и запустили код [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), он будет выглядеть аналогично приведенному ниже примеру.

![Пример внедренного отчета](media/integrate-report/powerbi-embedded-report.png)

## <a name="working-with-groups-app-workspaces"></a>Работа с группами (рабочими областями приложений)
Чтобы внедрить отчет из группы (рабочей области приложения), необходимо получить список всех доступных отчетов в группе, используя следующий вызов интерфейса REST API. Дополнительные сведения о вызове интерфейса REST API см. в статье [Get Reports](https://msdn.microsoft.com/library/mt634543.aspx) (Получение отчетов). Для получения результатов запроса требуются разрешения в группе.

```
https://api.powerbi.com/v1.0/myorg/groups/{group_id}/reports
```

Приведенный выше API возвращает список доступных отчетов. У каждого отчета есть свойство EmbedUrl, которое поддерживает внедрение группы по умолчанию.

```
https://app.powerbi.com/reportEmbed?reportId={report_id}&groupId={group_id}
```

## <a name="next-steps"></a>Дальнейшие действия
Пример приложения для проверки можно найти на сайте GitHub. Дополнительные сведения см. на странице [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app).

Чтобы больше узнать об API JavaScript, ознакомьтесь с документацией по [API JavaScript для Power BI](https://github.com/Microsoft/PowerBI-JavaScript).

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

