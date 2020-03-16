---
title: API экспорта отчетов Power BI
description: Узнайте, как экспортировать внедренный отчет из Power BI.
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 03/01/2020
ms.openlocfilehash: 2459982cdce9d2ee2af731ab479a94aefa2a8576
ms.sourcegitcommit: 480bba9c745cb9af2005637e693c5714b3c64a8a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2020
ms.locfileid: "79115002"
---
# <a name="export-report-to-file-preview"></a>Экспорт отчета в файл (предварительная версия)

`exportToFile` API позволяет экспортировать отчет Power BI с помощью вызова REST. Поддерживаются следующие форматы файлов:
* **PPTX** (PowerPoint)
* **PDF**
* **PNG**
    * При экспорте в PNG отчет с несколькими страницами сжимается в ZIP-файл
    * Каждый ZIP-файл в PNG представляет страницу отчета
    * Имена страниц совпадают с возвращаемыми значениями API [Get Pages](https://docs.microsoft.com/rest/api/power-bi/reports/getpages) (Получить страницы)или [Get Pages in Group](https://docs.microsoft.com/rest/api/power-bi/reports/getpagesingroup) (Получить страницы в группе).

## <a name="usage-examples"></a>Примеры использования

Функцию экспорта можно использовать различными способами. Вот несколько примеров.

* **Кнопка Send to print (Отправить на печать)** . В приложении создайте кнопку, которая при нажатии активирует задание экспорта. Задание может экспортировать просматриваемый отчет в формате PDF или PPTX, а после его завершения пользователь может получить его в качестве загружаемого файла. Используя закладки, вы сможете экспортировать отчет в определенном состоянии, включая настроенные фильтры, срезы и дополнительные параметры. Так как API является асинхронным, для доступа к файлу может потребоваться некоторое время.

* **Вложение электронной почты**. Отправка автоматизированного электронного письма через заданные интервалы с вложенным отчетом в формате PDF. Этот сценарий может быть полезен, если вы хотите автоматизировать отправку еженедельного отчета руководителям.

## <a name="using-the-api"></a>Использование API

Перед использованием API убедитесь, что включены следующие [параметры клиента администрирования](../service-admin-portal.md#tenant-settings).
* **Экспорт отчетов в презентации PowerPoint или PDF-документы**. Включено по умолчанию.
* **Экспорт отчетов в файлы изображений** . Требуется только для PNG и отключен по умолчанию.

API является асинхронным. При вызове API [exportToFile](https://docs.microsoft.com/rest/api/power-bi/reports/exporttofile) запускает задание экспорта. После запуска задания экспорта используйте [опрос](https://docs.microsoft.com/rest/api/power-bi/reports/getexporttofilestatus) для отслеживания задания, пока оно не будет завершено.

Во время опроса API возвращает число, представляющее объем выполненной работы. Работа в каждом задании экспорта вычисляется на основе количества страниц отчета. Все страницы имеют одинаковый вес. Если, например, вы экспортируете отчет с 10 страницами, а опрос возвращает 70, это означает, что API обработал семь страниц из 10 в задании экспорта.

После завершения экспорта вызов API опроса возвращает [URL-адрес Power BI](https://docs.microsoft.com/rest/api/power-bi/reports/getfileofexporttofile) для получения файла. URL-адрес будет доступен в течение 24 часов.

## <a name="supported-features"></a>Поддерживаемые функции

### <a name="selecting-which-pages-to-print"></a>Выбор страниц для печати

Укажите страницы, которые нужно напечатать в соответствии с возвращаемым значением [Get Pages](https://docs.microsoft.com/rest/api/power-bi/reports/getpages) (Получить страницы) или [Get Pages in Group](https://docs.microsoft.com/rest/api/power-bi/reports/getpagesingroup) (Получить страницы в группе). Можно также указать порядок экспортируемых страниц.

### <a name="bookmarks"></a>Закладки

 API `exportToFile` можно использовать для программного экспорта отчета в определенном состоянии после применения фильтров к нему. Это можно сделать с помощью возможностей [Закладок](../consumer/end-user-bookmarks.md). Чтобы экспортировать отчет с помощью закладок, используйте [закладки API JavaScript](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Bookmarks).

 Например, метод `capturedBookmark.state` закладки можно использовать для записи изменений, внесенных конкретным пользователем в отчет и его экспорта в текущем состоянии.

[Личные закладки](../consumer/end-user-bookmarks.md#personal-bookmarks) и [Постоянные фильтры](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/) не поддерживаются.

### <a name="authentication"></a>Authentication

Проверку подлинности можно выполнять только с помощью пользователя (или главного пользователя). В настоящее время [субъект-служба](embed-service-principal.md) не поддерживается.

### <a name="row-level-security-rls"></a>Безопасность на уровне строк (RLS)

С помощью [безопасности на уровне строк (RLS)](embedded-row-level-security.md) можно экспортировать отчет, который содержит данные, которые могут просмотреть только определенные пользователи. Например, при экспорте отчета о продажах, определенного с помощью региональных ролей, можно программно фильтровать отчет таким образом, чтобы отображался только определенный регион.

Для экспорта с использованием RLS необходимы следующие разрешения.
* Разрешение на запись и повторное предоставление общего доступа к набору данных, к которому подключен отчет
* Если отчет находится в рабочей области v1, необходимо быть администратором рабочей области.
* Если отчет находится в рабочей области v2, необходимо быть участником или администратором рабочей области.

### <a name="data-protection"></a>Защита данных

Форматы PDF и PPTX поддерживают [метки конфиденциальности](../admin/service-security-data-protection-overview.md#sensitivity-labels-in-power-bi). При экспорте отчета с меткой конфиденциальности в PDF или PPTX экспортируемый файл будет отображать отчет с меткой конфиденциальности.

### <a name="localization"></a>Локализация

При использовании API `exportToFile` можно передать требуемый локальный объект. Параметры локализации влияют на способ отображения отчета, например они могут изменять форматирование в соответствии с выбранным локальным форматом.

## <a name="concurrent-requests"></a>Число одновременных запросов

`exportToFile` поддерживает запросы параллельного экспорта заданий. В таблице ниже показано количество заданий, которые можно выполнять одновременно в зависимости от номера SKU, в котором находится ваш отчет. Число одновременных запросов ссылается на страницы отчета. Например, 20 страниц в одном запросе на экспорт в A6 SKU будут обрабатываться одновременно. Это займет примерно столько же времени, как и отправка 20 запросов экспорта с одной страницей.

Задание, превышающее количество одновременных запросов, не завершается. Например, если вы экспортируете три страницы в A1 SKU, то первое задание запуститься, а два последних будут ждать следующих двух циклов выполнения.

|Номер SKU Azure  |Номер SKU Office  |Максимальное количество страниц отчета  |
|-----------|------------|-----------|
|A1         |EM1         |1          |
|A2         |EM2         |2          |
|A3         |EM3         |3          |
|A4         |P1          |6          |
|A5         |P2          |12         |
|A6         |P3          |24         |

## <a name="limitations"></a>Ограничения

* Экспортируемый отчет должен храниться в емкости Premium или Embedded.
* Набор данных экспортируемого отчета должен храниться в емкости Premium или Embedded.
* Закрытая предварительная версия позволяет экспортировать до 50 страниц отчета Power BI в час.
* Экспортируемые отчеты не могут превышать размер файла 250 МБ.
* При экспорте в PNG метки конфиденциальности не поддерживаются.
* [Субъект-служба](embed-service-principal.md) не поддерживается.
* Количество страниц, которое может быть включено в экспортируемый отчет, равно 30. Если отчет содержит больше страниц, API возвращает ошибку, а задание экспорта отменяется.
* [Личные закладки](../consumer/end-user-bookmarks.md#personal-bookmarks) и [Постоянные фильтры](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/) не поддерживаются
* В настоящее время отчеты с разбивкой по страницам не поддерживаются.
* Перечисленные ниже визуальные элементы Power BI не поддерживаются. При экспорте отчета, содержащего эти визуальные элементы, части отчета с ними не будут отображены, в них будет отображаться символ ошибки.
    * Несертифицированные визуальные элементы Power BI
    * Визуальные элементы R
    * PowerApps
    * Визуализация с помощью инструментов Python
    * Visio

## <a name="code-examples"></a>Примеры кода

При создании задания экспорта необходимо выполнить три шага:

1. отправка запроса на экспорт;
2. опрос;
3. получение файлов.

В этом разделе приводятся примеры для каждого шага.

### <a name="step-1---sending-an-export-request"></a>Шаг 1. Отправка запроса на экспорт

Первый шаг — это отправка запроса на экспорт. В этом примере для определенной страницы отправляется запрос на экспорт.

```csharp
/////// Export sample ///////
private async Task<string> PostExportRequest(
    Guid reportId,
    Guid groupId,
    FileFormat format,
    IList<string> pageNames = null /* Get the page names from the GetPages API */)
        {
            var powerBIReportExportConfiguration = new PowerBIReportExportConfiguration
            {
                Settings = new ExportReportSettings
                {
                    Locale = "en-us",
                },

                // Note that page names differ from the page display names.
                // To get the page names use the GetPages API.
                Pages = pageNames?.Select(pn => new ExportReportPage(Name = pn)).ToList(),
            };

            var exportRequest = new ExportReportRequest
            {
                Format = format,
                PowerBIReportConfiguration = powerBIReportExportConfiguration,
            };

            var export = await Client.Reports.ExportToFileInGroupAsync(groupId, reportId, exportRequest);

            // Save the export ID, you'll need it for polling and getting the exported file
            return export.Id;
        }
```

### <a name="step-2---polling"></a>Шаг 2. Опрос

После отправки запроса на экспорт используйте опрос, чтобы узнать, когда файл экспорта, который вы ожидаете, будет готов.

```csharp
private async Task<Export> PollExportRequest(
    Guid reportId,
    Guid groupId,
    string exportId /* Get from the ExportToAsync response */,
    int timeOutInMinutes,
    CancellationToken token)
    {
        Export exportStatus = null;
        DateTime startTime = DateTime.UtcNow;
        const int c_secToMillisec = 1000;
        do
        {
            if (DateTime.UtcNow.Subtract(startTime).TotalMinutes > timeOutInMinutes || token.IsCancellationRequested)
            {
                // Error handling for timeout and cancellations
                return null;
            }

            var httpMessage = await Client.Reports.GetExportToFileStatusInGroupWithHttpMessagesAsync(groupId, reportId, exportId);
            exportStatus = httpMessage.Body;

            // You can track the export progress using the PercentComplete that's part of the response
            SomeTextBox.Text = string.Format("{0} (Percent Complete : {1}%)", exportStatus.Status.ToString(), exportStatus.PercentComplete);

            if (exportStatus.Status == ExportState.Running || exportStatus.Status == ExportState.NotStarted)
            {
                // The recommended waiting time between polling requests can be found in the RetryAfter header
                // Note that this header is only populated when the status is either Running or NotStarted
                var retryAfter = httpMessage.Response.Headers.RetryAfter;
                var retryAfterInSec = retryAfter.Delta.Value.Seconds;
                await Task.Delay(retryAfterInSec * c_secToMillisec);
            }
        }
        // While not in a terminal state, keep polling
        while (exportStatus.Status != ExportState.Succeeded && exportStatus.Status != ExportState.Failed);

        return exportStatus;
    }
```

### <a name="step-3---getting-the-file"></a>Шаг 3. Получение файлов.

После того, как опрос вернет URL, используйте этот пример для получения файла.

```csharp
private readonly IDictionary<string, string> mediaTypeToSuffix = new Dictionary<string, string>
    {
        { "image/png", "png" },
        { "application/zip", "zip" },
        { "application/pdf", "pdf" },
        { "application/vnd.openxmlformats-officedocument.presentationml.presentation", "pptx" },
    };

private async Task<ExportedFile> GetExportedFile(
    Guid reportId,
    Guid groupId,
    Export export /* Get from the GetExportStatusAsync response */)
    {
        if (export.Status == ExportState.Succeeded)
        {
            var httpMessage = await Client.Reports.GetFileOfExportToFileInGroupWithHttpMessagesAsync(groupId, reportId, export.Id);
            var mediaType = httpMessage.Response.Content.Headers.ContentType.ToString().ToLower();

            if (!mediaTypeToSuffix.TryGetValue(mediaType, out string fileSuffix))
            {
                // Handle unexpected errors
            }
            else
            {
                return new ExportedFile
                {
                    FileStream = httpMessage.Body,
                    FileSuffix = fileSuffix,
                };
            }
        }

        return null;
    }

public class ExportedFile
{
    public Stream FileStream;
    public string FileSuffix;
}
```

### <a name="end-to-end-example"></a>Комплексный пример

Это полный пример для экспорта отчета. Этот пример включает следующие этапы:
1. [Отправка запроса на экспорт](#step-1---sending-an-export-request).
2. [Опрос](#step-2---polling).
3. [Получение файлов](#step-3---getting-the-file).

```csharp
private async Task<ExportedFile> ExportPowerBIReport(
    Guid reportId,
    Guid groupId,
    FileFormat format,
    int pollingtimeOutInMinutes,
    CancellationToken token,
    IList<string> pageNames = null /* Get the page names from the GetPages API */)
        {
            try
            {
                var exportId = await PostExportRequest(reportId, groupId, format, pageNames);

                var export = await PollExportRequest(reportId, groupId, exportId, pollingtimeOutInMinutes, token);
                if (export == null || export.Status != ExportState.Succeeded)
                {
                    // Error, failure in exporting the report
                    return null;
                }

                return await GetExportedFile(reportId, groupId, export);
            }
            catch
            {
                // Error handling
                throw;
            }
        }
```

## <a name="next-steps"></a>Дальнейшие действия

Ознакомьтесь со сведениями о внедрении содержимого для клиентов и вашей организации:

> [!div class="nextstepaction"]
>[Внедрение для клиентов](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Внедрение для организации](embed-sample-for-your-organization.md)
