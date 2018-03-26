---
title: Новые возможности сервера отчетов Power BI
description: Узнайте о новых возможностях сервера отчетов Power BI. Здесь приводятся сведения об основных функциях. Материалы обновляются по мере выпуска новых элементов.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/19/2018
ms.author: maggies
ms.openlocfilehash: 4f149baccf551762589c17bd6d6ba17c36f4da37
ms.sourcegitcommit: 0473a155495a7a9ba4b899d0815100426718b7ac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2018
---
# <a name="whats-new-in-power-bi-report-server"></a>Новые возможности сервера отчетов Power BI
Узнайте о новых возможностях сервера отчетов Power BI. Здесь приводятся сведения об основных функциях. Материалы обновляются по мере выпуска новых элементов.

Чтобы скачать сервер отчетов Power BI и службу Power BI Desktop, оптимизированную для сервера отчетов Power BI, перейдите на страницу [Локальная работа с отчетами с использованием сервера Power BI Report Server](https://powerbi.microsoft.com/report-server/).

Соответствующие сведения о новых функциях и возможностях см. в следующей статье:

* [Новые возможности службы Power BI](../service-whats-new.md)
* [Новые возможности Power BI Desktop](../desktop-latest-update.md)
* [Новые возможности мобильных приложений для Power BI](../mobile-whats-new-in-the-mobile-apps.md)
* [Блог команды Power BI](https://powerbi.microsoft.com/blog/)

## <a name="march-2018-release"></a>Выпуск за март 2018 г.

В выпуске Power BI Desktop за март 2018 г. появилось множество новых функций, оптимизированных для Сервера отчетов Power BI. Они приведены ниже с группированием по областям: 
- [Визуальные элементы](#visuals-updates)
- [Отчеты](#reporting)
- [Аналитика](#analytics)
- [Производительность](#performance)
- [Сервер отчетов](#report-server)
- [Другие](#other-improvements)

### <a name="highlights-of-this-release"></a>Краткое описание этого выпуска

Из всего длинного списка новых возможностей приведенные ниже нам кажутся наиболее интересными.

#### <a name="rule-based-conditional-formatting-for-table-and-matrixhttpspowerbimicrosoftcomblogpower-bi-desktop-november-2017-feature-summaryconditionalformatting"></a>[Условное форматирование на основе правил для визуальных элементов таблицы и матрицы](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#conditionalFormatting)
 
Вы можете создать правила, чтобы условно задать цвет фона или шрифта в столбце, основываясь на определенной бизнес-логике в таблице или матрице.

#### <a name="show-and-hide-pageshttpspowerbimicrosoftcomblogpower-bi-desktop-january-2018-feature-summaryhidepages"></a>[Отображение и скрытие страниц](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#hidePages)

Предположим, что вы хотите, чтобы читатели имели доступ к отчету, хотя еще не закончили работу с некоторыми страницами. Теперь их можно скрыть, пока они не будут готовы. Кроме того, можно скрыть страницы при нормальной навигации, при этом читатели смогут перейти на такую страницу с помощью закладок или детализации.

#### <a name="bookmarkinghttpspowerbimicrosoftcomblogpower-bi-desktop-march-2018-feature-summarybookmarking"></a>[Использование закладок](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#bookmarking)

Вы можете использовать закладки, чтобы упорядочить данные в отчете.

- [Перекрестное выделение для закладок](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkCrossHighlighting): закладки сохраняют и отображают состояние перекрестного выделения страницы отчета во время создания закладки.
- [Повышенная гибкость при работе с закладками](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkFlexibility): закладки отражают свойства, заданные вами в отчете, и затрагивают только указанные визуальные элементы.

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

 
## <a name="october-2017-release"></a>Выпуск за октябрь 2017 г.
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

* EnableCustomVisuals: True или False;
* EnablePowerBIReportEmbeddedModels: True или False;
* EnablePowerBIReportExportData: True или False;
* MaxFileSizeMb: по умолчанию задано 1000;
* ModelCleanupCycleMinutes: частота выполнения проверок для вытеснения моделей из памяти;
* ModelExpirationMinutes: время до истечения срока хранения модели и ее вытеснения на основе времени последнего использования;
* ScheduleRefreshTimeoutMinutes: длительность обновления данных для модели. По умолчанию указано два часа.  Жесткое верхнее ограничение отсутствует.

**Файл конфигурации rsreportserver.config**

```
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
  * Поддержка пользовательских визуализаций
  * Ожидается добавление поддержки динамических подключений служб Analysis Services только с дополнительными источниками данных.
  * Приложение Power BI Mobile обновляется для отображения отчетов Power BI, размещенных на сервере отчетов Power BI
* Оптимизированные возможности совместной работы в отчетах с комментариями

## <a name="next-steps"></a>Дальнейшие действия
[Руководство пользователя](user-handbook-overview.md)  
[Руководство администратора](admin-handbook-overview.md)  
[Краткое руководство по установке сервера отчетов Power BI](quickstart-install-report-server.md)  
[Install Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder) (Установка построителя отчетов)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714) (Скачивание SQL Server Data Tools (SSDT))

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

