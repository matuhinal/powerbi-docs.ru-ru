---
title: Параметры URL-адресов в отчетах с разбивкой на страницы (построитель отчетов Power BI)
description: В этом разделе описываются распространенные варианты использования для параметров отчета Power BI Report Builder, свойства, которые можно задать, и многое другое.
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: cfinlan
ms.custom: ''
ms.date: 05/01/2020
ms.openlocfilehash: d7e11b40c3a0257e090812ff15f31916cea509f9
ms.sourcegitcommit: f05f7b0112a8ec2dce60839ea5f922eda3cc776c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84336781"
---
# <a name="url-parameters-in-paginated-reports-in-power-bi"></a>Параметры URL-адреса в отчетах с разбивкой на страницы в Power BI

Вы можете отправлять команды в отчеты с разбивкой на страницы в Power BI, добавив параметр в URL-адрес. Например, вы просмотрели отчет, используя конкретный набор значений параметров отчета. Вы инкапсулируете эти сведения в URL-адрес с помощью предопределенных параметров доступа к URL-адресу. Затем вы настраиваете обработку отчета в Power BI путем внедрения параметров для форматов отрисовки или для отображения панели инструментов отчета. После этого вы вставляете этот URL-адрес непосредственно в сообщение электронной почты или на веб-страницу, чтобы другие пользователи могли так же как вы работать с отчетом в браузере. 

Ниже приводятся действия, которые можно выполнять с помощью параметров доступа к URL-адресу. 

- Отправка параметров отчета в отчет. 
- Инициация экспорта содержимого отчета в поддерживаемом формате файла. 
- Скрытие или просмотр панели параметров. 
- Задание параметра DeviceInfo. 

Полный список команд и параметров, доступных через доступ к URL-адресу, см. в разделе  [Справочник по параметрам доступа к URL-адресу](#url-access-parameter-reference) далее в этой статье. 

## <a name="url-access-concepts"></a>Основные понятия доступа к URL-адресу 

Запросы URL-адресов к Power BI содержат параметры, обрабатываемые службой. Способ, которым служба обрабатывает запросы URL-адресов, зависит от параметров, префиксов параметров и типов элементов, включенных в URL-адрес. Функции URL-адресов в отчетах с разбивкой на страницы совместимы с большинством браузеров и приложений, поддерживающих стандартную URL-адресацию. 

## <a name="url-access-syntax"></a>Синтаксис доступа к URL-адресу 

Запросы URL-адресов могут содержать несколько параметров, указанных в любом порядке. Параметры разделяются символом амперсанда (&). Пары "имя-значение" разделяются знаком равенства (=). Например:

```
powerbiserviceurl?rp:parametervalueh&rdl:parameter=value  
```

## <a name="syntax-description"></a>Описание синтаксиса 

### <a name="powerbiserviceurl"></a>powerbiserviceurl 

URL-адрес веб-службы клиента Power BI. Например: 

**&** Используется для разделения пар "имя-значение" в параметрах доступа к URL-адресу.

**префикс** — префикс для параметра URL-адреса (например, rp: или rdl:), указывающий действие в службе Power BI. 

> [!NOTE]
> Параметры отчета должны иметь префикс параметра и указываются с учетом регистра. 

**параметр** — имя параметра. 

### <a name="value"></a>Значение 

Текст URL-адреса, соответствующий значению используемого параметра. 

Примеры передачи параметров отчета в URL-адресе см. в статье о  [передаче параметра отчета в URL-адресе](report-builder-url-pass-parameters.md).

## <a name="url-access-parameter-reference"></a>Справочник по параметрам доступа к URL-адресу

Следующие параметры можно использовать как часть URL-адреса для настройки внешнего вида отчетов с разбивкой на страницы в Power BI. В этом разделе перечислены наиболее распространенные параметры. Параметры не учитывают регистр и начинаются с префикса параметра  `rdl:` , если они связаны с выходным форматом.  

### <a name="report-commands-rdl"></a>Команды отчета (`rdl:`) 

**Формат экспорта** — задает формат отображения и экспорта отчета.

Пример: rdl:format=PDF

Доступные значения:
 
- PPTX (PowerPoint)
- MHTML 
- ИЗОБРАЖЕНИЕ 
- EXCELOPENXML (EXCEL) 
- WORDOPENXML (WORD) 
- CSV 
- PDF 
- XML 

**Состояние панели параметров**. Определяет, будет ли панель параметров закрыта, открыта или полностью скрыта при загрузке отчета.

-   rdl:parameterPanelState

    - collapsed — при загрузке отчета панель параметров закрыта. Пользователи могут развернуть панель, нажав кнопку.
    - hidden — при загрузке отчета панель параметров закрыта и кнопка неактивна.
    - expanded (по умолчанию) — при загрузке отчета панель параметров открыта и кнопка активна.

**Сведения об устройстве**. Можно указать дополнительные выходные параметры для следующих форматов экспорта. 

PDF:

- rdl:AccessiblePDF=true/false
- rdl:Columns=целое число
- rdl:ColumnSpacing=десятичное число (дюймы)
- rdl:DpiX=целое число
- rdl:DpiY=целое число
- rdl:EndPage=целое число
- rdl:HumanReadablePDF=true/false
- rdl:MarginBottom=десятичное число (дюймы)
- rdl:MarginLeft=десятичное число (дюймы)
- rdl:MarginRight=десятичное число (дюймы)
- rdl:MarginTop=десятичное число (дюймы)
- rdl:PageHeight=десятичное число (дюймы)
- rdl:PageWidth=десятичное число (дюймы)
    - rdl:StartPage=целое число
    
CSV:

- rdl:Encoding=строка
- rdl:ExcelMode=true/false
- rdl:FieldDelimiter=строка
- rdl:FileExtension=строка
- rdl:NoHeader=true/false
- rdl:Qualifier=строка
- rdl:RecordDelimiter=строка
- rdl:SuppressLineBreaks=true/false
    - rdl:UseFormattedValues=true/false
    
WORDOPENXML (WORD):

- rdl:AutoFit=строка -> True/False/Never/Default
- rdl:ExpandToggles=true/false
- rdl:FixedPageWidth=true/false
- rdl:OmitHyperlinks=true/false
- rdl:OmitDrillthroughs=true/false

EXCELOPENXML (EXCEL):

- rdl:OmitDocumentMap=true/false
- rdl:OmitFormulas=true/false
    - rdl:SimplePageHeaders=true/false
    
PPTX (PowerPoint):
 
- rdl:Columns=целое число
- rdl:ColumnSpacing=десятичное число (дюймы)
- rdl:DpiX=целое число
- rdl:DpiY=целое число
- rdl:EndPage=целое число
- rdl:MarginBottom=десятичное число (дюймы)
- rdl:MarginLeft=десятичное число (дюймы)
- rdl:MarginRight=десятичное число (дюймы)
- rdl:MarginTop=десятичное число (дюймы)
- rdl:PageHeight=десятичное число (дюймы)
- rdl:PageWidth=десятичное число (дюймы)
- rdl:StartPage=целое число
    - rdl:UseReportPageSize=true/false

XML:

- rdl:XSLT=строка
- rdl:MIMEType=строка
- rdl:UseFormattedValues=true/false
- rdl:Indented=true/false
- rdl:OmitNamespace=true/false
- rdl:OmitSchema=true/false
- rdl:Encoding=строка
- rdl:FileExtension=строка
- rdl:Schema=true/false

**Открыть гиперссылку в том же окне браузера** Добавьте "rdl:targetSameWindow=true" в URL-адрес гиперссылки в отчете, чтобы служба Power BI открывала эту гиперссылку в том же окне браузера. Сведения о добавлении гиперссылок в отчет см. в статье [Добавление гиперссылки на URL-адрес](https://docs.microsoft.com/sql/reporting-services/report-design/add-a-hyperlink-to-a-url-report-builder-and-ssrs) в документации по SQL Server Reporting Services.

## <a name="next-steps"></a>Дальнейшие действия

- [Передача параметра отчета в URL-адресе для отчета с разбивкой на страницы в Power BI](report-builder-url-pass-parameters.md)
- [Сведения об отчетах с разбивкой на страницы в Power BI Premium](paginated-reports-report-builder-power-bi.md)
