---
title: Типы аналитики, поддерживаемые в Power BI
description: Краткая аналитика и ее просмотр в Power BI
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/31/2019
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 75462c2414854d0848254a36b89bcdd1de365ec5
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2019
ms.locfileid: "73863490"
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

![Пример выбросов по категориям](./media/end-user-insight-types/pbi-auto-insight-types-category-outliers.png)

## <a name="change-points-in-a-time-series"></a>Точки изменений во временных рядах
Выделяет существенные изменения в тенденциях, наблюдаемых во временном ряде данных.

![Пример точек изменений во временных рядах](./media/end-user-insight-types/pbi-auto-insight-types-changepoint.png)

## <a name="correlation"></a>Корреляция
Выявляет случаи корреляции  между несколькими показателями, нанесенными на график в зависимости от какого-либо измерения в наборе данных.

![Пример корреляции](./media/end-user-insight-types/pbi-auto-insight-types-correlation.png)

## <a name="low-variance"></a>Низкая вариативность
Выявляет случаи, когда точки данных близки к среднему значению.

![Пример низкой вариативности](./media/end-user-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Большинство (основные факторы)
Находит случаи, когда большую часть общего значения можно свести к одному фактору, выполнив детализацию по другому параметру.  

![Пример основных факторов](./media/end-user-insight-types/pbi-auto-insight-types-majority.png)

## <a name="overall-trends-in-time-series"></a>Общие тенденции во временных рядах
Определяет восходящие и нисходящие тенденция в данных временных рядов.

![Пример общих тенденций во временных рядах](./media/end-user-insight-types/pbi-auto-insight-types-trend.png)

## <a name="seasonality-in-time-series"></a>Сезонность во временных рядах
Находит повторяющийся рисунок в данных временных рядов, такие как недельная, месячная или годовая сезонность.

![Пример сезонности](./media/end-user-insight-types/pbi-auto-insight-types-seasonality-new.png)

## <a name="steady-share"></a>Постоянная доля
Выделяет случаи иерархической корреляции между долей дочернего значения и суммарным значением родительского элемента в непрерывной переменной.

![Пример постоянной доли](./media/end-user-insight-types/pbi-auto-insight-types-steadyshare.png)

## <a name="time-series-outliers"></a>Выбросы временных рядов
Определяет, есть ли во временном ряде значения даты или времени, которые существенно отличаются от остальных значений даты и времени.

![Пример выбросов временных рядов](./media/end-user-insight-types/pbi-auto-insight-types-time-series-outliers.png)

## <a name="next-steps"></a>Дальнейшие действия
[Аналитика Power BI](end-user-insights.md)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](https://community.powerbi.com/)

