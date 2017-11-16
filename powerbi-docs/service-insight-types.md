---
title: "Типы быстрого анализа данных, поддерживаемые Power BI"
description: "Быстрый анализ данных в Power BI."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/03/2017
ms.author: mihart
ms.openlocfilehash: 13f5614cf121b17d8ae4dff9653f5789372f7f49
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="types-of-quick-insights-supported-by-power-bi"></a>Типы быстрого анализа данных, поддерживаемые Power BI
## <a name="how-does-quick-insights-work"></a>Как работает быстрый анализ данных?
Power BI быстро ищет различные подмножества наборов данных, применяя ряд сложных алгоритмов для обнаружения интересных комбинаций. Power BI сканирует максимальный объем набора данных в течение выделенного количества времени.

Можно выполнять быстрый анализ данных для набора данных или плитки (связанная аналитика).   

## <a name="what-types-of-quick-insights-can-we-find"></a>Какие результаты краткой аналитики можно получить?
Ниже перечислены некоторые используемые нами алгоритмы.

## <a name="category-outliers-topbottom"></a>Провалы или всплески значений
Выделяет случаи, когда при измерении по модели значения одного или двух членов измерения намного превышают значения остальных  

![](media/service-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Точки изменений во временных рядах
Выделяет существенные изменения в тенденциях, наблюдаемых во временном ряде данных.

![](media/service-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Корреляция
Выявляет случаи корреляции  между несколькими показателями, нанесенными на график в зависимости от какого-либо измерения в наборе данных.

![](media/service-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Низкая вариативность
Выявляет случаи, когда точки данных близки к среднему значению.

![](media/service-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Большинство (основные факторы)
Находит случаи, когда большую часть общего значения можно свести к одному фактору, выполнив детализацию по другому параметру.  

![](media/service-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Общие тенденции во временных рядах
Определяет восходящие и нисходящие тенденция в данных временных рядов.

![](media/service-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Сезонность во временных рядах
Находит повторяющийся рисунок в данных временных рядов, такие как недельная, месячная или годовая сезонность.

![](media/service-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Постоянная доля
Выделяет случаи иерархической корреляции между долей дочернего значения и суммарным значением родительского элемента в непрерывной переменной.

![](media/service-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Выбросы временных рядов
Определяет, есть ли во временном ряде значения даты или времени, которые существенно отличаются от остальных значений даты и времени.

![](media/service-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Дальнейшие действия
[Быстрый анализ данных Power BI](service-insights.md)

Если у вас есть набор данных, [оптимизируйте его для краткой аналитики](service-insights-optimize.md).

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

