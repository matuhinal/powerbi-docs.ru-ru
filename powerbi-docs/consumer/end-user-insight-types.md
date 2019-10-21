---
title: Типы аналитики, поддерживаемые в Power BI
description: Краткая аналитика и ее просмотр в Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/02/2019
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 7f754c1164448be88a3269cb8e3d129b63a6115f
ms.sourcegitcommit: 5410a17c6325406c9d9364585d7c26de4d9488ae
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72379910"
---
# <a name="types-of-insights-supported-by-power-bi"></a>Типы аналитики, поддерживаемые в Power BI

Служба Power BI поддерживает автоматический поиск аналитических сведений в панелях мониторинга или отчетах.

## <a name="how-does-insights-work"></a>Как выполняется аналитика?
Power BI обеспечивает быстрый поиск различных подмножеств в вашем наборе данных. При поиске Power BI применяет набор оптимизированных алгоритмов для выявления потенциально полезных аналитических сведений. Power BI сканирует максимальный объем набора данных в течение выделенного количества времени.

Аналитика может выполняться с набором данных или данных на плитке панели мониторинга.   

## <a name="what-types-of-insights-can-we-find"></a>Какие результаты можно получить?
Ниже перечислены некоторые используемые нами алгоритмы.

## <a name="category-outliers-topbottom"></a>Провалы или всплески значений
Выделяет случаи, когда при измерении по модели значения одного или двух членов измерения намного превышают значения остальных  

![Пример выбросов по категориям](./media/end-user-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Точки изменений во временных рядах
Выделяет существенные изменения в тенденциях, наблюдаемых во временном ряде данных.

![Пример точек изменений во временных рядах](./media/end-user-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Корреляция
Выявляет случаи корреляции  между несколькими показателями, нанесенными на график в зависимости от какого-либо измерения в наборе данных.

![Пример корреляции](./media/end-user-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Низкая вариативность
Выявляет случаи, когда точки данных близки к среднему значению.

![Пример низкой вариативности](./media/end-user-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Большинство (основные факторы)
Находит случаи, когда большую часть общего значения можно свести к одному фактору, выполнив детализацию по другому параметру.  

![Пример основных факторов](./media/end-user-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Общие тенденции во временных рядах
Определяет восходящие и нисходящие тенденция в данных временных рядов.

![Пример общих тенденций во временных рядах](./media/end-user-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Сезонность во временных рядах
Находит повторяющийся рисунок в данных временных рядов, такие как недельная, месячная или годовая сезонность.

![Пример сезонности](./media/end-user-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Постоянная доля
Выделяет случаи иерархической корреляции между долей дочернего значения и суммарным значением родительского элемента в непрерывной переменной.

![Пример постоянной доли](./media/end-user-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Выбросы временных рядов
Определяет, есть ли во временном ряде значения даты или времени, которые существенно отличаются от остальных значений даты и времени.

![Пример выбросов временных рядов](./media/end-user-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Дальнейшие действия
[Аналитика Power BI](end-user-insights.md)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

