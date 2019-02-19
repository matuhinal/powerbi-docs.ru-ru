---
title: Новые возможности сервера отчетов Power BI
description: Узнайте о новых возможностях сервера отчетов Power BI. Здесь приводятся сведения об основных функциях. Материалы обновляются по мере выпуска новых элементов.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/22/2019
ms.openlocfilehash: ad3025b9649529566972f75e9c447bb7558132b8
ms.sourcegitcommit: 91ac6185f7026ddbaa925dc54057bb742b4fa411
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2019
ms.locfileid: "56325204"
---
# <a name="whats-new-in-power-bi-report-server"></a>Новые возможности сервера отчетов Power BI

Узнайте о новых возможностях сервера отчетов Power BI. В этой статье приводятся сведения об основных функциях. Материалы обновляются по мере выпуска новых элементов.

Чтобы скачать последние версии сервера отчетов Power BI и службы Power BI Desktop, оптимизированной для сервера отчетов Power BI, перейдите на страницу [Локальная работа с отчетами с использованием сервера Power BI Report Server](https://powerbi.microsoft.com/report-server/).

См. дополнительные сведения о новых функциях и возможностях Power BI:

* [Новые возможности службы Power BI](../service-whats-new.md)
* [Новые возможности Power BI Desktop](../desktop-latest-update.md)
* [Новые возможности мобильных приложений для Power BI](../consumer/mobile/mobile-whats-new-in-the-mobile-apps.md)

## <a name="january-2019"></a>Январь 2019 г.

Поддержка следующих возможностей в отчетах Power BI:

[**Безопасность на уровне строк**](row-level-security-report-server.md). Настройка безопасности на уровне строк (RLS) с сервером отчетов Power BI может ограничить доступ к данным для определенных пользователей. Фильтры ограничивают доступ к данным на уровне строк; определить их можно в ролях.

[**Развертывание и свертывание заголовков строк матрицы**](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#expandCollapse). Мы добавили возможность развертывать и свертывать отдельные заголовки строк (одна из наиболее часто запрашиваемых визуальных возможностей).

[**Копирование и вставка между PBIX-файлами**](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#copyPaste). Визуальные элементы можно копировать между PBIX-файлами с помощью контекстного меню визуального элемента или стандартного сочетания клавиш CTRL + C (для вставки в другой отчет используйте клавиши CTRL + V).

[**Интеллектуальные направляющие выравнивания**](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#smartGuides). Эти направляющие отображаются при перемещении объектов на странице отчета, чтобы помочь вам выровнять все объекты на странице (аналогично направляющим в PowerPoint). Интеллектуальные направляющие отображаются при перетаскивании или изменении размера объектов на странице. При перемещении объекта рядом с другим объектом он прикрепляется в положении, учитывающем выравнивание с другим объектом.

**Специальные возможности**. Число специальных возможностей слишком велико, чтобы упомянуть их все. В том числе они включают [поддержку специальных возможностей для панели списка полей](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#fieldList). Для панели списка полей реализован полный диапазон специальных возможностей. Вы можете перемещаться по этой области, используя только клавиатуру и средство чтения с экрана. Для добавления полей на страницу отчета можно использовать контекстное меню.

### <a name="administrator-settings"></a>Параметры администратора

В дополнительных свойствах среды SSMS для фермы серверов администраторы могут настроить следующие свойства:

**AllowedResourceExtensionsForUpload**. Набор расширений ресурсов, которые могут быть отправлены на сервер отчетов. Нет необходимости включать расширения для встроенных файлов, таких как &ast;.rdl и &ast;.pbix. По умолчанию набор включает: &ast;, &ast;.xml, &ast;.xsd, &ast;.xsl, &ast;.png, &ast;.gif, &ast;.jpg, &ast;.tif, &ast;.jpeg, &ast;.tiff, &ast;.bmp, &ast;.pdf, &ast;.svg, &ast;.rtf, &ast;.txt, &ast;.doc, &ast;.docx, &ast;.pps, &ast;.ppt, &ast;.pptx. 

**SupportedHyperlinkSchemes**. Задает разделенный запятыми список схем URI, которые можно определять для отображаемых действий с гиперссылками (Hyperlink), или значение "&ast;" для включения всех схем гиперссылок. Например, если указать "http, https", будут разрешены гиперссылки на "https://www. contoso.com", но при этом будут удалены гиперссылки на"mailto:bill@contoso.com" или "javascript:window.open ('www.contoso.com', '_blank')". Значение по умолчанию: "&ast;".

## <a name="august-2018"></a>Август 2018 г.

В выпуске Power BI Desktop за август 2018 г. появилось множество новых функций, оптимизированных для сервера отчетов Power BI. Они приведены ниже с группированием по областям:

- [Отчеты](#reporting)
- [Аналитика](#analytics)
- [Моделирование](#modeling)

### <a name="highlights-of-the-august-2018-release"></a>Основные особенности выпуска в августе 2018 г.

Из всего длинного списка новых возможностей приведенные ниже нам кажутся наиболее интересными. Дополнительные сведения см. в [записи блога](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/).

#### <a name="report-theming"></a>Темы отчетов

В выпуск сервера отчетов Power BI за август 2018 г. добавлена функция "Тема отчета", позволяющая быстро применять цветовую схему ко всему отчету в соответствии с его темой или корпоративной символикой. При импорте темы все диаграммы автоматически обновляются для использования цветов темы, а вы получаете доступ к цветам в цветовой палитре. Чтобы отправить файл темы, используйте параметр **Импортировать тему** под кнопкой **Переключить тему**.

Файл темы — это JSON-файл, включающий все цвета, которые требуется использовать в отчете вместе с форматированием по умолчанию, применяемым к визуальным элементам.
Ниже приведен простой пример темы JSON для обновления заданных по умолчанию цветов отчета.

```json
{
"name": "waveform",
"dataColors": [ "#31B6FD", "#4584D3", "#5BD078", "#A5D028", "#F5C040", "#05E0DB", "#3153FD", "#4C45D3", "#5BD0B0", "#54D028", "#D0F540", "#057BE0" ],
"background":"#FFFFFF",
"foreground": "#F2F2F2",
"tableAccent":"#5BD078"
}
```

#### <a name="conditional-formatting-by-a-different-field"></a>Условное форматирование по другому полю

Одним из значительных усовершенствований условного форматирования является форматирование столбца по дополнительному полю.

#### <a name="conditional-formatting-by-values"></a>Условное форматирование по значениям

Еще один новый тип условного форматирования — это значение **Форматировать по полю**. Значение форматирования по полю позволяет использовать меру или столбец, который задает цвет с помощью шестнадцатеричного кода или имени и применяет этот цвет к фону или шрифту.

#### <a name="report-page-tooltips"></a>Всплывающие подсказки на странице отчета

В выпуск обновления сервера отчетов Power BI за август 2018 г. добавлена функция всплывающих подсказок на странице отчета. Она позволяет создавать страницу отчета для использования в качестве настраиваемой всплывающей подсказки для других визуальных элементов в отчете.

#### <a name="log-axis-improvements"></a>Улучшения логарифмических осей

Мы значительно улучшили логарифмические оси в графиках в декартовой системе координат. Теперь если у вас есть данные, являющиеся вполне положительными или вполне отрицательными, вы можете выбирать логарифмическую шкалу для числовой оси на любом графике в декартовой системе координат, включая комбинированную диаграмму.

#### <a name="sap-hana-sso-direct-query"></a>Прямые запросы SSO для SAP HANA

Теперь для отчетов Power BI доступна поддержка прямых запросов SSO для SAP HANA с Kerberos.

>[!Note]
>Этот сценарий поддерживается только в том случае, если SAP HANA рассматривается как реляционный источник данных для отчетов, созданных в Power BI Desktop.  Чтобы включить эту поддержку в Power BI Desktop, в меню DirectQuery в разделе параметров установите флажок "Treat SAP HANA as a relational source" (Считать SAP HANA реляционным источником) и нажмите кнопку "ОК".

#### <a name="custom-visuals"></a>Пользовательские визуальные элементы

- В состав этого выпуска входит API версии 1.13.0.

- Теперь для настраиваемых визуальных элементов будет использоваться предыдущая версия, совместимая с текущей версией API сервера (если таковая доступна).

### <a name="reporting"></a>Отчеты 

- [Темы отчетов](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#theming)
- [Кнопки для запуска действий](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#buttons)
- [Стили для линий комбинированной диаграммы](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLines)
- [Улучшенный режим сортировки по умолчанию для визуальных элементов](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sort)
- [Числовой срез](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#numericSlicer)
- [Улучшенная синхронизация среза](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerSync)
- [Улучшения логарифмических осей](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#logAxis)
- [Параметры метки данных для воронкообразной диаграммы](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#funnelChart)
- [Установка нулевой толщины обводки](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#lineStroke)
- [Поддержка высокой контрастности в отчетах](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#highContrast)
- [Управление радиусом кольцевой диаграммы](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#donutRadius)
- [Управление положением меток сведений для круговых и кольцевых диаграмм](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#detailLabels)
- [Форматирование меток данных по отдельности для каждой меры в комбинированной диаграмме](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLabels)
- [Новый визуальный заголовок, обеспечивающий большую гибкость и дополнительные возможности форматирования](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#visualHeader)
- [Форматирование фонового рисунка](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#wallpaper)
- [Всплывающие подсказки для таблицы и матрицы](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tableTooltips)
- [Отключение всплывающих подсказок для визуальных элементов](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tooltips)
- [Специальные возможности для срезов](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerAccessibility)
- [Улучшения области форматирования](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#formattingPane)
- [Поддержка пошаговых линий для линейных и комбинированных диаграмм](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#steppedLine)
- [Улучшение процесса сортировки](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sorting)
- [Печать отчетов путем экспорта в PDF (в Power BI Desktop)](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#print)
- [Создание групп закладок](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#bookmarks)
- [Пересмотр среза](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicer)
- [Всплывающие подсказки на странице отчета](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#reportPageTooltips)

### <a name="analytics"></a>Аналитика

- [Новая функция DAX: COMBINEVALUES()](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#combineValues)
- [Детализация меры](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#measureDrillthrough)
- [Условное форматирование по другому полю](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingField)
- [Условное форматирование по значениям](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingValue)

### <a name="modeling"></a>Моделирование

- [Фильтрация и сортировка в представлении данных](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#filterAndSort)
- [Улучшенное форматирование языкового стандарта](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#locale)
- [Категории данных для мер](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dataCategory)
- [Статистические функции DAX](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dax)

## <a name="may-2018"></a>Май 2018

### <a name="configure-power-bi-ios-mobile-apps-for-report-servers-remotely"></a>Удаленная настройка доступа мобильных приложений Power BI для iOS к серверам отчетов

ИТ-администратор теперь может удаленно настраивать доступ мобильных приложений Power BI для iOS к серверу отчетов с помощью средства MDM. Подробные сведения см. в статье [Удаленная настройка доступа мобильных приложений Power BI для iOS к серверу отчетов](configure-powerbi-mobile-apps-remote.md).

## <a name="march-2018"></a>Март 2018 г.

В выпуске Power BI Desktop за март 2018 г. появилось множество новых функций, оптимизированных для Сервера отчетов Power BI. Они приведены ниже с группированием по областям:

- [Визуальные элементы](#visuals-updates)
- [Отчеты](#reporting)
- [Аналитика](#analytics)
- [Производительность](#performance)
- [Сервер отчетов](#report-server)
- [Другие](#other-improvements)

### <a name="highlights-of-the-march-2018-release"></a>Основные особенности выпуска в марте 2018 г.

Из всего длинного списка новых возможностей приведенные ниже нам кажутся наиболее интересными.

#### <a name="rule-based-conditional-formatting-for-table-and-matrixhttpspowerbimicrosoftcomblogpower-bi-desktop-november-2017-feature-summaryconditionalformatting"></a>[Условное форматирование на основе правил для визуальных элементов таблицы и матрицы](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#conditionalFormatting)

Вы можете создать правила, чтобы условно задать цвет фона или шрифта в столбце, основываясь на определенной бизнес-логике в таблице или матрице.

#### <a name="show-and-hide-pageshttpspowerbimicrosoftcomblogpower-bi-desktop-january-2018-feature-summaryhidepages"></a>[Отображение и скрытие страниц](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#hidePages)

Предположим, что вы хотите, чтобы читатели имели доступ к отчету, хотя еще не закончили работу с некоторыми страницами. Теперь их можно скрыть, пока они не будут готовы. Кроме того, можно скрыть страницы при нормальной навигации, при этом читатели смогут перейти на такую страницу с помощью закладок или детализации.

#### <a name="bookmarkinghttpspowerbimicrosoftcomblogpower-bi-desktop-march-2018-feature-summarybookmarking"></a>[Использование закладок](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#bookmarking)

Вы можете использовать закладки, чтобы упорядочить данные в отчете.

- [Перекрестное выделение для закладок](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkCrossHighlighting): закладки сохраняют и отображают состояние перекрестного выделения страницы отчета во время создания закладки.
- [Повышенная гибкость при работе с закладками](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkFlexibility): закладки отражают свойства, заданные вами в отчете, и затрагивают только указанные вами визуальные элементы.

#### <a name="multi-select-data-points-across-multiple-chartshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarycrosshighlight"></a>[Множественный выбор точек данных на нескольких диаграммах](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#crosshighlight)

Вы можете выбрать несколько точек данных на нескольких диаграммах и применить перекрестную фильтрацию ко всей странице.

#### <a name="sync-slicers-across-multiple-pages-of-your-reporthttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarysyncslicers"></a>[Синхронизация срезов на нескольких страницах отчета](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#syncSlicers)

Срез может применяться к одной или нескольким страницам в отчете.

#### <a name="quick-measureshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summaryquickmeasures"></a>[Быстрые меры](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#quickMeasures) 

Вы можете создавать меры на основе существующих мер и числовых столбцов в таблице.

#### <a name="drilling-down-filters-other-visualshttpspowerbimicrosoftcomblogpower-bi-desktop-december-feature-summarydrillfiltersothervisuals"></a>[Детализирующие фильтры для других визуализаций](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)

При детализации по заданной категории в одном визуальном элементе можно настроить его для фильтрации всех визуальных элементов на странице по этой же категории.

### <a name="visuals-updates"></a>Обновления визуальных элементов

- [Выравнивание ячеек для визуальных элементов таблицы и матрицы](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#alignment)
- [Отображение единиц измерения и управление точностью для столбцов таблицы и матрицы](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#displayUnits)
- [Метки данных переполнения для линейчатых диаграмм и гистограмм](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#overflow)
- [Управление цветом фона меток данных в визуализациях с декартовыми координатами и сопоставлениями](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#dataLabelBackground)
- [Управление отступами столбцов](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#padding)
- [Увеличение размера области, используемой для меток осей на диаграммах](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#axisSize)
- [Точечная диаграмма, созданная с помощью группирования осей X и Y](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#scatterChart)
- [Высокая плотность выборки для карт на основе широты и долготы](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#highDensityMaps)
- [Адаптивные срезы](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#responsive)
- [Добавление даты привязки для среза относительных дат](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#anchorDate)

### <a name="reporting"></a>Отчеты

- [Отключение заголовка визуального элемента в режиме чтения для отчета](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualHeader)
- [Параметры отчета для медленных источников данных](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#slowDataSource)
- [Улучшенное размещение визуальных элементов по умолчанию](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualPlacement)
- [Упорядочение визуальных элементов контроля через область выделения](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#selectionPane)
- [Блокировка объектов в отчете](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#lock)
- [Поиск по панели форматирования и аналитики](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#search)
- [Панель свойств поля и описания поля](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#fieldPropertiesPane)

### <a name="analytics"></a>Аналитика

- [UTCNOW() и UTCTODAY()](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#utcDAX)
- [Пометка таблицы настраиваемой даты](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#customDateTable)
- [Детализирующие фильтры для других визуальных элементов](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)
- [Форматирование на уровне ячейки для многомерных моделей AS для многострочной карточки](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#cellLevelFormatting)

### <a name="performance"></a>Производительность

- [Улучшения эффективности фильтрации](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#filtering)
- [Улучшения эффективности DirectQuery](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#dqPerf)
- [Повышение производительности при сохранении и открытии](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#savePerf)
- [Улучшения функции "Показать элементы без данных"](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#showItemsWithNoData)

### <a name="report-server"></a>Сервер отчетов

#### <a name="export-to-accessible-pdf"></a>Экспорт в доступный PDF

При экспорте отчета с разбивкой на страницы (язык определения отчетов) в формат PDF теперь можно получить доступный/помеченный тегами PDF-файл. Он больше по размеру, но упрощает чтение и навигацию для средств чтения с экрана и других специальных возможностей. Чтобы включить доступный PDF, задайте для параметра **AccessiblePDF** в сведениях об устройстве значение **True**. См. разделы [Параметры сведений об устройстве для PDF](https://docs.microsoft.com/sql/reporting-services/pdf-device-information-settings) и [Изменение параметров сведений об устройстве ](https://docs.microsoft.com/sql/reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config#changing-device-information-settings).

### <a name="other-improvements"></a>Другие усовершенствования

- [Усовершенствования функции "Добавить столбец из примеров"](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#addColumnFromExamples)
- [Быстрая ссылка "Консультационные услуги"](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#consultingServices)
- [Улучшенное ведение отчетов об ошибках](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#errors)
- [Просмотр возникших ранее ошибок](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#viewErrors)

## <a name="october-2017"></a>Октябрь 2017 г.

### <a name="power-bi-report-data-sources"></a>Источники данных отчетов Power BI

Отчеты Power BI в решении "Сервер отчетов Power BI" можно подключать к разным источникам данных. Вы можете импортировать данные и планировать их обновление или запрашивать данные напрямую, используя DirectQuery или активное подключение к SQL Server Analysis Services. Список источников данных, поддерживающих запланированное обновление и DirectQuery см. в статье об источниках данных для отчетов Power BI в решении "Сервер отчетов Power BI".

### <a name="scheduled-data-refresh-for-imported-data"></a>Запланированное обновление импортированных данных

В решении "Сервер отчетов Power BI" можно настроить запланированное обновление данных (чтобы обеспечить их актуальность в отчетах Power BI), используя внедренную модель вместо активного подключения или DirectQuery. Эта модель используется для импорта данных, поэтому отчет отключен от исходного источника данных. Но отчет необходимо обновлять, чтобы обеспечить актуальность данных. Это можно сделать с помощью запланированного обновления. Дополнительные сведения см. в статье о запланированном обновлении для отчетов Power BI в решении "Сервер отчетов Power BI".

### <a name="editing-power-bi-reports-from-the-server"></a>Изменение отчетов Power BI на сервере

Вы можете открывать и изменять файлы отчета Power BI (PBIX) на сервере, но обратно вы получите исходный файл, который отправили.  Это означает, что **если данные обновлены на сервере, эти обновления не будут отображаться при первом открытии файла**. Вам нужно обновить их вручную на локальном компьютере, чтобы увидеть изменения.

### <a name="large-file-uploaddownload"></a>Отправка и скачивание больших файлов

Вы можете отправлять файлы размером до 2 ГБ, хотя в настройках сервера отчетов в SQL Server Management Studio по умолчанию задано ограничение в 1 ГБ.  Как и файлы для SharePoint, эти файлы хранятся в базе данных, и для каталога SQL Server не требуются специальные настройки.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>Доступ к общим наборам данных как к каналам OData

Вы можете получить доступ к общим наборам данных из Power BI Desktop, используя веб-канал OData. Дополнительные сведения см. в статье о [доступе к общим наборам данных из решения "Сервер отчетов Power BI" через канал OData](access-dataset-odata.md).

### <a name="scale-out"></a>Горизонтальное масштабирование

Этот выпуск поддерживает горизонтальное масштабирование. Используйте подсистему балансировки нагрузки и настройте сходство с сервером для удобства работы пользователей. Обратите внимание, что сценарий еще не оптимизирован для масштабирования, поэтому модели возможно будут реплицироваться между несколькими узлами. Сценарий будет работать без подсистемы балансировки сетевой нагрузки и непрерывных сеансов. Вместе с этим вы отметите не только чрезмерное использование памяти на узлах из-за многократных загрузок модели. Также ухудшится производительность между подключениями при потоковой передаче модели из-за попадания на новый узел при выполнении запросов.  

### <a name="administrator-settings"></a>Параметры администратора

В дополнительных свойствах среды SSMS для фермы серверов администраторы могут настроить следующие свойства:

* EnableCustomVisuals: Истина/ложь
* EnablePowerBIReportEmbeddedModels: Истина/ложь
* EnablePowerBIReportExportData: Истина/ложь
* MaxFileSizeMb: по умолчанию задано 1000;
* ModelCleanupCycleMinutes: частота выполнения проверок для вытеснения моделей из памяти;
* ModelExpirationMinutes: время до истечения срока хранения модели и ее вытеснения на основе времени последнего использования;
* ScheduleRefreshTimeoutMinutes: длительность обновления данных для модели. По умолчанию указано два часа.  Жесткое верхнее ограничение отсутствует.

**Файл конфигурации rsreportserver.config**

```xml
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>API для разработчиков

В API для разработчиков (REST API), представленном для SSRS 2017, добавлена поддержка файлов Excel и PBIX в решении "Сервер отчетов Power BI". Один из возможных вариантов использования — скачивание файлов с сервера с помощью программных средств, обновление и повторная публикация этих файлов. Например, это единственный способ обновления книг Excel с моделями PowerPivot.

Обратите внимание — это новый отдельный API для работы с большими файлами с возможностью обновления в новой версии Swagger решения "Сервер отчетов Power BI". 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>SQL Server Analysis Services (SSAS) и используемый решением "Сервер отчетов Power BI" объем памяти

SSAS размещаются в решении "Сервер отчетов Power BI". Это связано не только с возможностью запланированного обновления. Размещение SSAS позволяет значительно увеличить объем памяти сервера отчетов. Файл конфигурации AS.ini доступен на узлах сервера. Поэтому, если вы работали со службами SSAS, вы можете обновить настройки, включая ограничение максимального объема памяти, кэширование диска и т. д. Дополнительные сведения см. в статье [Server properties in Analysis Services](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services) (Свойства сервера в службах Analysis Services).

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Просмотр книг Excel и работа с ними

Excel и Power BI включают ряд средств, уникальных в своей отрасли. Используемые вместе, эти средства вместе помогают бизнес-аналитикам собирать, формировать, анализировать и визуализировать данные. С помощью решения "Сервер отчетов Power BI" бизнес-пользователи теперь могут просматривать книги Excel, а не только отчеты Power BI на веб-портале. Это решение позволяет централизованно публиковать и просматривать данные самостоятельной бизнес-аналитики Майкрософт.

Мы опубликовали [пошаговое руководство по добавлению Office Online Server (OOS) в среду предварительной версии решения "Сервер отчетов Power BI"](excel-oos.md). Пользователи с учетной записью корпоративного лицензирования могут бесплатно скачать OOS на веб-сайте Microsoft Volume Licensing Service Center. Сервер Office Online Server будет доступен только для просмотра. Завершив настройку, пользователи смогут просматривать книги Excel и работать с ними следующим образом:

* не используя зависимости внешних источников данных;
* используя активное подключение к внешнему источнику данных SQL Server Analysis Services;
* используя модель данных PowerPivot.

### <a name="support-for-new-table-and-matrix-visuals"></a>Поддержка новых визуальных элементов — таблиц и матриц

В решение "Сервер отчетов Power BI" добавлена поддержка новых визуальных элементов — таблиц и матриц. Чтобы создавать отчеты с помощью этих визуальных элементов, требуется обновить Power BI Desktop до выпуска за октябрь 2017 г. Новый выпуск нельзя установить вместе с выпуском Power BI Desktop за июнь 2017 г. Чтобы получить последнюю версию Power BI Desktop, на [странице скачивания решения "Сервер отчетов Power BI"](https://powerbi.microsoft.com/report-server/) выберите **Дополнительные параметры скачивания**.

## <a name="june-2017"></a>Июнь 2017 г.

* Вышла общедоступная версия сервера отчетов Power BI.

## <a name="may-2017"></a>Май 2017 г.

* Доступна предварительная версия сервера отчетов Power BI Report Server
* Возможность локальной публикации отчетов Power BI
  * Поддержка настраиваемых визуальных элементов
  * Ожидается добавление поддержки **динамических подключений служб Analysis Services** только с дополнительными источниками данных.
  * Приложение Power BI Mobile обновляется для отображения отчетов Power BI, размещенных на сервере отчетов Power BI
* Оптимизированные возможности совместной работы в отчетах с комментариями

## <a name="next-steps"></a>Дальнейшие действия

Ознакомьтесь со следующими ресурсами, чтобы узнавать о новых возможностях сервера отчетов Power BI.

* [Блог Microsoft Power BI](https://powerbi.microsoft.com/blog/)
* [Блог команды разработчиков SQL Server Reporting Services](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [Канал YouTube Guy in a Cube](https://aka.ms/guyinacube)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)