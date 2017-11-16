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
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: 27af387a6d789b00837e6bbf8c6be9aa219c7198
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="getting-a-custom-visual-certified"></a>Получение *сертификации* для пользовательского визуального элемента
## <a name="what-is-meant-by-certified"></a>Что подразумевается под *сертификацией*
*Сертифицированным* является пользовательский визуальный элемент, который соответствует набору требований к коду и прошел строгие тесты безопасности.  После сертификации настраиваемый визуальный элемент можно [экспортировать в PowerPoint](service-publish-to-powerpoint.md) и отображать в электронных сообщениях, получаемых пользователем при [подписке на страницы отчетов](service-report-subscribe.md).

* Вы являетесь веб-разработчиком и заинтересованы в создании собственных визуализаций и добавлении их в магазин? Прочтите статью [Создание пользовательского визуального элемента с помощью средств разработчика](service-custom-visuals-getting-started-with-developer-tools.md) и посетите [Магазин Office](service-custom-visuals-office-store.md).
* Есть ли визуальный элемент магазина Office, который вы используете регулярно? Попросите разработчика визуальных элементов сертифицировать визуальный элемент в корпорации Майкрософт.  Контактные данные разработчиков указаны на странице **Дополнительные сведения** в разделе **Поставщик**.

## <a name="certification-requirements"></a>Требования к сертификации
* Пользовательский визуальный элемент одобрен Магазином Office.    
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
| Ссылка на магазин Office | Ссылка на видео |
| --- | --- |
| [Правила взаимосвязей](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [Круговая диаграмма с индивидуальным радиусом срезов](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| Выпуск [BciCalendar] ожидается в ближайшее время | |
| [Ящик с усами](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [Диаграмма с маркерами](https://store.office.com/en-us/app.aspx?assetid=WA104380755) |[Видео 1](https://youtu.be/AOlsFYkfkcw)   [Видео 2](https://youtu.be/AQvd2FhRyCI) |
| [Диаграмма с маркерами от OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[Видео](https://youtu.be/mtvUNl9bMjA) |
| [Карточки с состояниями от OKViz](https://store.office.com/card-with-states-by-okviz-WA104380967.aspx) |[Видео 1  ](https://youtu.be/myiX0BmZd8U) [Видео 2](https://youtu.be/AOlsFYkfkcw) |
| [Chiclet Slicer](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[Видео](https://youtu.be/iYOkJ1APueY) |
| [Круговой датчик от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [Цилиндрическая шкала](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | |
| [Датчик с циферблатом](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) |[Видео](https://youtu.be/AOlsFYkfkcw) |
| [Кольцевой график (кольцевая диаграмма) от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[Видео](https://youtu.be/pDToHDFHnq8) |
| [Подробная кольцевая диаграмма](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | |
| [Dual KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[Видео](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| Fly Wheel (скоро выйдет) | |
| [Диаграмма Ганта](https://store.office.com/gantt-WA104380765.aspx) |[Видео](https://youtu.be/qJ7s_KrGiUU) |
| [Гистограмма](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [Горизонтальная воронка](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) |[Видео](https://youtu.be/SudZei68PPo) |
| [Временная шкала (изображение)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381254) | |
| [Индикатор ключевого показателя эффективности](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| Датчик заполнения жидкостью — ожидается в ближайшее время |[Видео](https://youtu.be/wQ51TTqIZc4) |
| [Линейный датчик от MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[Видео](https://youtu.be/AOlsFYkfkcw) |
| Средство просмотра длинного текста — ожидается в скором времени | |
| [Ось воспроизведения (динамический срез)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Ключевой показатель эффективности производительности](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[Видео](https://youtu.be/IvfIP3E6-1Q) |
| [Диаграмма "Пульс"](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006?src=office&tab=Overview) |[Видео](https://www.youtube.com/watch?v=DQWdcQtjDVw) |
| [Лепестковая диаграмма](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [Диаграмма Sankey](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[Видео](https://youtu.be/WWP9wVUHGaA) |
| [Кольцевая диаграмма от MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) |[Видео](https://youtu.be/pDToHDFHnq8) |
| [Полоса прокрутки](https://store.office.com/scroller-WA104381018.aspx) |[Видео](https://youtu.be/uhRFQF2cGSY) |
| [Смарт-фильтр от OKViz](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[Видео](https://youtu.be/gcJsDDRQq28) |
| [Спарклайн от OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[Видео](https://youtu.be/0m3Vnvso9tY) |
| [Диаграмма "Солнечные лучи"](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [Тахометр](https://store.office.com/tachometer-WA104380937.aspx?) |[Видео](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [Разбор временного ряда](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380897) | |
| [Диаграмма "Тепловая карта"](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [Текстовая программа-оболочка](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [Timeline slicer](https://store.office.com/timeline-slicer-WA104380786.aspx) |[Видео](https://youtu.be/ozMtZ4_NZ10) |
| [Диаграмма-торнадо](https://store.office.com/tornado-chart-WA104380768.aspx) |[Видео](https://youtu.be/AQvd2FhRyCI) |
| [Предварительный просмотр в Visio](https://store.office.com/visio-visual-preview-WA104381132.aspx) |[Видео](https://www.youtube.com/watch?v=dCcd7rftjZA&list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x&index=2) |
| [Вафельная диаграмма](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[Видео](https://youtu.be/1vRqYUsm3Vk) |
| [Облако Word](https://store.office.com/word-cloud-WA104380752.aspx?) |[Видео](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>Дальнейшие действия
[Скачивание и использование настраиваемых визуализаций из Магазина Office](service-custom-visuals-office-store.md)  
[Приступая к работе со средствами разработчика пользовательских визуальных элементов (предварительная версия)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Список видео Майкрософт, посвященных пользовательским визуальным элементам, на сайте YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Визуализации в Power BI](power-bi-report-visualizations.md)  
[Пользовательские визуализации в Power BI](power-bi-custom-visuals.md)  
[Добавление пользовательского визуального элемента в отчет (Desktop)](power-bi-custom-visuals-use.md)  
[Публикация пользовательских визуализаций в Магазине Office](developer/office-store.md)  
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

