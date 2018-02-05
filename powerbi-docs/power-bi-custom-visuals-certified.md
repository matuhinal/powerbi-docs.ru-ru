---
title: "Сертифицированные пользовательские визуализации Power BI"
description: "Требования к пользовательскому визуальному элементу для сертификации и процедура его отправки. А также список уже сертифицированных пользовательских визуальных элементов."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: mihart
ms.openlocfilehash: f9824b29515481742c339bc76e766e5e62cf1716
ms.sourcegitcommit: be5223b62e9a5d57c52f8588d4e539d814751dd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2018
---
# <a name="getting-a-custom-visual-certified"></a>Получение *сертификации* для пользовательского визуального элемента
## <a name="what-is-meant-by-certified"></a>Что подразумевается под *сертификацией*
*Сертифицированным* является пользовательский визуальный элемент, который соответствует набору требований к коду и прошел строгие тесты безопасности.  После сертификации настраиваемый визуальный элемент можно [экспортировать в PowerPoint](service-publish-to-powerpoint.md) и отображать в электронных сообщениях, получаемых пользователем при [подписке на страницы отчетов](service-report-subscribe.md). Разумеется, вы также можете использовать его как [стандартную настраиваемую визуализацию](power-bi-custom-visuals.md), добавлять его в службу Power BI и отчеты Power BI Desktop, просматривать в Power BI Mobile и внедрять в свои материалы.

Вы являетесь веб-разработчиком и заинтересованы в том, чтобы создавать собственные визуальные элементы и добавлять их в [Microsoft AppSource](https://appsource.microsoft.com)? Чтобы узнать, как это сделать, см. статью о [начале работы со средствами для разработчиков](service-custom-visuals-getting-started-with-developer-tools.md).


## <a name="certification-requirements"></a>Требования к сертификации
* Утверждение Microsoft AppSource    
* Пользовательский визуальный элемент создан с помощью API версии 1.2 и выше.    
* Репозиторий кода доступен для просмотра (например, код визуального элемента, доступный на GitHub).    
* Используются только открытые, доступные для просмотра компоненты ОС.    
* Отсутствует доступ к внешним службам и ресурсам.    

> **СОВЕТ**. Корпорация Майкрософт рекомендует использовать EsLint с набором правил безопасности по умолчанию для предварительной проверки кода перед отправкой.
> 
> 

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>Порядок отправки пользовательских визуальных элементов для сертификации
Чтобы отправить пользовательский визуальный элемент для сертификации, сделайте следующее.

1. Отправьте сообщение электронной почты в службу поддержки пользовательских визуальных элементов Power BI (pbicvsupport@microsoft.com). В сообщение электронной почты включите следующие сведения.    
   
   * Заголовок: запрос сертификации визуального элемента    
   * Ссылка на репозиторий GitHub, где размещается исходный код визуального элемента.    
   * Подтверждение соблюдения требований (см. выше).    
   * Подтверждение прохождения проверки кода и безопасности.    
2. Группа пользовательских визуальных элементов корпорации Майкрософт уведомит вас о получении сертификации для пользовательского визуального элемента и добавлении его в список сертифицированных пользовательских визуальных элементов (см. ниже) или об отклонении запроса сертификации с отчетом о проблемах, которые должны быть исправлены. Разработчик несет ответственность за обеспечение открытого канала взаимодействия с корпорацией Майкрософт и за обновление визуальных элементов, включенных в список сертифицированных, если это необходимо.

## <a name="removal-of-power-bi-certified-custom-visuals"></a>Удаление сертифицированных пользовательских визуальных элементов Power BI
Корпорация Майкрософт по своему усмотрению может удалять визуальные элементы из списка сертифицированных.  

## <a name="list-of-custom-visuals-that-have-been-certified"></a>Список пользовательских визуальных элементов, которые прошли сертификацию
| Ссылка на AppSource | Ссылка на видео |
| --- | --- |
| [Правила взаимосвязей](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [Круговая диаграмма с индивидуальным радиусом срезов](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [BciCalendar (календарь Beyondsoft)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096?src=office&tab=Overview)  | |
| [Петлеобразная диаграмма от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838?src=office&tab=Overview) |[Видео](https://youtu.be/So5xKMSpVJI) |
| [Ящик с усами](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [Клетчатая диаграмма от MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | |
| [Пузырьковая диаграмма от Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340?src=office) | |
| [Диаграмма с маркерами](https://store.office.com/app.aspx?assetid=WA104380755) |[Видео 1](https://youtu.be/AOlsFYkfkcw)   [Видео 2](https://youtu.be/AQvd2FhRyCI) |
| [Диаграмма с маркерами от OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[Видео](https://youtu.be/mtvUNl9bMjA) |
| [Календарь от Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146?src=office&tab=Overview) | |
| [Диаграмма "японские свечи" от OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | |
| [Chiclet Slicer](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[Видео](https://youtu.be/iYOkJ1APueY) |
| [Хордовая диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761?src=office&tab=Overview) |[Видео](https://youtu.be/AQvd2FhRyCI) |
| [Круговой датчик от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [Цилиндрическая шкала](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | |
| [Датчик с циферблатом](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) |[Видео](https://youtu.be/AOlsFYkfkcw) |
| [Кольцевой график (кольцевая диаграмма) от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[Видео](https://youtu.be/pDToHDFHnq8) |
| [Точечная диаграмма от MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381101) | |
| [Точечная диаграмма от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104381101?src=office&tab=Overview) |[Видео](https://youtu.be/4lskRgcpFJY) |
| [Точечная диаграмма от Майкрософт](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760?src=office) | |
| [Детализированная кольцевая диаграмма от ZoomCharts](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | |
| [Детализированная картограмма](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045?src=office) | |
| [Детализированная фоновая картограмма](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044?src=office) | |
| [Детализированная гистограмма от ZoomCharts](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881?src=office) | |
| [Детализированная гистограмма временных данных от ZoomCharts](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | |
| [Детализированная кольцевая диаграмма от ZoomCharts](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | |
| [Dual KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[Видео](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| [Расширенная точечная диаграмма](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | |
| [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112?src=office&tab=Overview) | |
| [Enlighten Bubble Stack](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380868) | |
| [Enlighten Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380960?tab=Overview) | |
| [Enlighten Stack Shuffle](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Enlighten Waffle Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Enlighten World Flags](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380923) | |
| [График с направленной силой](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764) |[Видео](https://youtu.be/YsTa7uyJ4sg) |
| [Диаграмма прогнозирования TBATS](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381326?src=office) | |
| [Воронка с источником]() | || [Диаграмма Ганта](https://store.office.com/gantt-WA104380765.aspx) |[Видео](https://youtu.be/qJ7s_KrGiUU) |
| [Иерархическая диаграмма от Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333?src=office) | |
| [Гистограмма](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [Горизонтальная воронка](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) |[Видео](https://youtu.be/SudZei68PPo) |
| [Временная шкала с изображениями](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381254) | |
| [Конструктор инфографики](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898?src=office) | |
| [Индикатор ключевого показателя эффективности](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| [Область КПЭ от MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | |
| [Линейно-точечная диаграмма](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766?src=office) | |
| [Линейный датчик от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[Видео](https://youtu.be/AOlsFYkfkcw) |
| [Диаграмма Mekko](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785?src=office&tab=Overview)  | [Видео](https://youtu.be/90FLCKpgicA)|
| [Ось воспроизведения (динамический срез)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Ключевой показатель эффективности производительности](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[Видео](https://youtu.be/IvfIP3E6-1Q) |
| [Диаграмма "Пульс"](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006) | |
| [Лепестковая диаграмма](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [Кольцевой график (кольцевая диаграмма) от MAQSoftware](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824?src=office&tab=Overview) | [Видео](https://youtu.be/pDToHDFHnq8)|
| [Поворотная диаграмма от MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007?src=office) |  |
| [Диаграмма Sankey](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[Видео](https://youtu.be/WWP9wVUHGaA) |
| [Полоса прокрутки](https://store.office.com/scroller-WA104381018.aspx) |[Видео](https://youtu.be/uhRFQF2cGSY) |
| [Смарт-фильтр от SQLBI](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[Видео](https://youtu.be/gcJsDDRQq28) |
| [Спарклайн от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[Видео](https://youtu.be/0m3Vnvso9tY) |
| [График потока](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380772?tab=Overview) |  |
| [Диаграмма "Солнечные лучи"](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [Диаграмма "Тепловая карта"](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [Тахометр](https://store.office.com/tachometer-WA104380937.aspx?) |[Видео](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [Текстовая программа-оболочка](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [Термометр](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847?src=office&tab=Overview) | [Видео](https://youtu.be/SPX9mgrAdBc)|
| [Разбор временного ряда](https://appsource.microsoft.com/product/power-bi-visuals/WA104380897) | |
| [Timeline slicer](https://store.office.com/timeline-slicer-WA104380786.aspx) |[Видео](https://youtu.be/ozMtZ4_NZ10) |
| [Диаграмма-торнадо](https://store.office.com/tornado-chart-WA104380768.aspx) |[Видео](https://youtu.be/AQvd2FhRyCI) |
| [Диаграмма отклонений Ultimate Variance от Клауса Биррингера (Klaus Birringer)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140?src=office) | |
| [Каскадная диаграмма Ultimate Waterfall (бесплатно)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | |
| [VitaraCharts — MicroChart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381165) | |
| [Вафельная диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[Видео](https://youtu.be/1vRqYUsm3Vk) |
| [Облако Word](https://store.office.com/word-cloud-WA104380752.aspx?) |[Видео](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе со средствами разработчика пользовательских визуальных элементов (предварительная версия)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Список видео Майкрософт, посвященных пользовательским визуальным элементам, на сайте YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Визуализации в Power BI](power-bi-report-visualizations.md)  
[Пользовательские визуализации в Power BI](power-bi-custom-visuals.md)  
[Публикация настраиваемых визуальных элементов в Microsoft AppSource](developer/office-store.md)  
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

