---
title: Примеры визуальных элементов Power BI
description: В этой статье представлены примеры визуальных элементов Power BI, в том числе срезы, более 20 типов диаграмм, WebGL, визуальные элементы и скрипты R.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 03/17/2019
ms.openlocfilehash: 5e2ad0fa43a186be76a58f1ab3bb4bf054a677a5
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83132952"
---
# <a name="samples-of-power-bi-visuals"></a>Примеры визуальных элементов Power BI

Вы можете скачать, использовать и изменить эти визуальные элементы Power BI на сайте GitHub. В этих примерах показано, как обрабатываются распространенные ситуации при разработке с помощью Power BI.

## <a name="slicers"></a>Срезы

Срез сужает часть данных, отображаемую в других визуализациях в отчете. Срезы — это один из нескольких способов фильтрации данных в Power BI.

| <img src="media/samples/chiclet-slicer.png" width="200">  | <img src="media/samples/timeline-slicer.png" width="200"> | <img src="media/samples/sample-slicer.png" width="200">|
| ------------- | ------------- | -------------|
| [Срез Chiclet](https://github.com/Microsoft/powerbi-visuals-chicletslicer/)  </br>Кнопки с изображениями и текстом, которые служат фильтром на холсте в других визуальных элементах | [Timeline slicer](https://github.com/Microsoft/powerbi-visuals-timeline/) </br>Графический селектор диапазонов дат, с помощью которого выполняется фильтрация по датам. | [Пример среза](https://github.com/Microsoft/powerbi-visuals-sampleslicer/) </br>Демонстрирует использование API расширенной фильтрации.

## <a name="charts"></a>Диаграммы

Используйте преимущества нашей коллекции, в том числе линейчатых диаграмм, круговых диаграмм, облака слов и др.

| <img src="media/samples/aster-plot.png" width="200">  | <img src="media/samples/bullet-chart.png" width="200"> | <img src="media/samples/Chord.png" width="200">|
| ------------- | ------------- | -------------|
| [Круговая диаграмма с индивидуальным радиусом срезов](https://github.com/Microsoft/powerbi-visuals-asterplot/)  </br>Изгиб на стандартной кольцевой диаграмме, где второе значение используется для указания угла поворота | [Диаграмма-шкала](https://github.com/Microsoft/powerbi-visuals-bulletchart/) </br>Линейчатая диаграмма с дополнительными визуальными элементами, предоставляющими контекст для отслеживания целей | [Хордовая диаграмма](https://github.com/Microsoft/powerbi-visuals-chord/) </br>Графический метод отображения взаимосвязей данных в матрице
| <img src="media/samples/dot-plot.png" width="200"> | <img src="media/samples/dual-kpi.png" width="200">| <img src="media/samples/enhanced-scatter.png" width="200"> 
| [Точечная диаграмма](https://github.com/Microsoft/powerbi-visuals-dotplot/) </br>Показывает распределение частот в виде удобной диаграммы. | [Dual KPI](https://github.com/Microsoft/powerbi-visuals-dualkpi/) </br>Эффективная визуализация двух мер с течением времени, отображающая их тенденцию на объединенной временной шкале | [Расширенная точечная диаграмма](https://github.com/Microsoft/powerbi-visuals-enhancedscatter/) </br>Улучшения на имеющейся точечной диаграмме
| <img src="media/samples/forcegraph.png" width="200">| <img src="media/samples/gantt.png" width="200">| <img src="media/samples/table-heatmap.png" width="200">
| [Force Graph](https://github.com/Microsoft/powerbi-visuals-forcegraph/) </br>Принудительно структурированная диаграмма с изогнутыми траекториями. Полезна для отображения связей между сущностями | [Диаграмма Ганта](https://github.com/Microsoft/powerbi-visuals-gantt/) </br>Линейчатая диаграмма, которая иллюстрирует временную шкалу или расписание проекта вместе с ресурсами | [Диаграмма "Тепловая карта"](https://github.com/Microsoft/powerbi-visuals-heatmap/) </br>Простое и интуитивно понятное сравнение данных в таблице с использованием цветов
| <img src="media/samples/histogram-chart.png" width="200"> | <img src="media/samples/linedot-chart.png" width="200"> | <img src="media/samples/mekko-chart.png" width="200"> 
| [Гистограмма](https://github.com/Microsoft/powerbi-visuals-histogram/) </br>Визуализация распределения данных за непрерывный интервал или определенный период времени | [Линейно-точечная диаграмма](https://github.com/Microsoft/powerbi-visuals-linedotchart/) </br>График с анимированными точками, который помогает привлечь внимание аудитории к данным | [Диаграмма Mekko](https://github.com/Microsoft/powerbi-visuals-mekkochart/) </br>Сочетание нормированной гистограммы и нормированной линейчатой диаграммы в одном представлении
| <img src="media/samples/multikpi.png" width="200"> | <img src="media/samples/powerkpi.png" width="200"> | <img src="media/samples/powerkpi-matrix.png" width="200"> 
| [Несколько КПЭ](https://github.com/microsoft/PowerBI-visuals-MultiKPI/) </br> Эффективная визуализация с несколькими КПЭ, содержащая ключевой показатель КПЭ и несколько спарклайнов для поддержки данных | [Ключевой показатель эффективности производительности](https://github.com/microsoft/PowerBI-visuals-PowerKPI/) </br>Эффективный индикатор КПЭ с многострочным графиком и метками для текущей даты, значения и расхождений. | [Матрица КПЭ производительности](https://github.com/microsoft/PowerBI-visuals-PowerKPIMatrix/) </br>Мониторинг сбалансированных систем показателей и неограниченного количества метрик и ключевых показателей эффективности в форме компактного, удобного для чтения списка
| <img src="media/samples/pulse-chart.png" width="200">| <img src="media/samples/radar-chart.png" width="200"> | <img src="media/samples/sankey-chart.png" width="200"> 
| [Диаграмма "Пульс"](https://github.com/Microsoft/powerbi-visuals-pulsechart/) </br>Этот график с примечаниями в виде ключевых событий идеально подходит для описания ситуаций с использованием данных| [Лепестковая диаграмма](https://github.com/Microsoft/powerbi-visuals-radarchart/) </br>Диаграмма с несколькими мерами, нанесенными на ось категорий для сравнения атрибутов | [Диаграмма Sankey](https://github.com/Microsoft/powerbi-visuals-sankey/) </br>Диаграмма потока, в которой ширина ряда пропорциональна объему потока
| <img src="media/samples/stream-graph.png" width="200"> | <img src="media/samples/sunburst.png" width="200">| <img src="media/samples/tornado.png" width="200">
| [График потока](https://github.com/Microsoft/powerbi-visuals-streamgraph/) </br>Диаграмма с областями и накоплением с плавной интерполяцией, которая часто используется для отображения значений за период времени | [Диаграмма "солнечные лучи"](https://github.com/Microsoft/powerbi-visuals-sunburst/) </br>Многоуровневая кольцевая диаграмма для визуализации иерархических данных| [Диаграмма-торнадо](https://github.com/Microsoft/powerbi-visuals-tornado/) </br>Сравнение относительной важности переменных между двумя группами
 | <img src="media/samples/word-cloud.png" width="200">
 | [Облако Word](https://github.com/Microsoft/powerbi-visuals-wordcloud/) </br>Интересный визуальный элемент, показывающий частоту использования слов в тексте

## <a name="webgl"></a>WebGL

WebGL позволяет веб-содержимому использовать API на основе OpenGL ES 2.0 для двумерной и трехмерной отрисовки на холсте HTML.

| <img src="media/samples/globe-map.png" width="250">|
| ------------- |
| [Схема земного шара](https://github.com/Microsoft/powerbi-visuals-globemap/) </br>График расположений на интерактивной трехмерной карте

## <a name="r-visuals"></a>Визуальные элементы R

В этих примерах показано, как использовать аналитические и визуальные возможности визуальных элементов и скриптов на основе R.

| <img src="media/samples/association-rules.png" width="200">| <img src="media/samples/clustering.png" width="200">| <img src="media/samples/clustering-with-outliers.png" width="200">|
|------------- |------------- |------------- |------------- |
| [Правила взаимосвязей](https://github.com/Microsoft/powerbi-visuals-assorules/) </br>Обнаружение связей между на первый взгляд несвязанными данными с помощью операторов if-then | [Кластеризация](https://github.com/Microsoft/powerbi-visuals-clustering-kmeans/) </br>Поиск групп сходства в данных с помощью алгоритма K-средних | [Кластеризация с использованием выбросов](https://github.com/microsoft/PowerBI-visuals-dbscan/) </br>Поиск групп сходства и выбросов в данных
| <img src="media/samples/correlation-plot.png" width="200"> | <img src="media/samples/decision-tree-chart.png" width="200"> | <img src="media/samples/forecasting-tbats.png" width="200"> 
| [Диаграмма корреляции](https://github.com/Microsoft/powerbi-visuals-corrplot/) </br>Выделение наиболее коррелированных переменных в таблице данных | [Схема дерева решений](https://github.com/Microsoft/powerbi-visuals-decision-tree/) </br>Схематическая диаграмма в виде дерева для определения статистической вероятности с использованием рекурсивного секционирования | [Диаграмма прогнозирования TBATS](https://github.com/Microsoft/powerbi-visuals-forcasting-tbats/) </br>Прогнозирование временных рядов с несколькими сезонностями с использованием модели TBATS
| <img src="media/samples/forecasting-with-ARIMA.png" width="200"> | <img src="media/samples/funnel-plot.png" width="200"> | <img src="media/samples/outliers-detection.png" width="200"> 
| [Прогнозирование с помощью ARIMA](https://github.com/Microsoft/powerbi-visuals-forcastingarima/) </br>Прогнозирование будущих значений на основе исторических данных с использованием авторегрессионного интегрированного скользящего среднего (ARIMA) | [Воронкообразная диаграмма](https://github.com/Microsoft/powerbi-visuals-funnel/) </br>Поиск выбросов в данных с помощью воронкообразного графика | [Обнаружение выбросов](https://github.com/Microsoft/powerbi-visuals-outliers-det/) </br>Поиск выбросов в данных с помощью наиболее подходящего метода и графика
| <img src="media/samples/spline-chart.png" width="200"> | <img src="media/samples/time-series-decomposition-chart.png" width="200"> | <img src="media/samples/time-series-forecasting-chart.png" width="200">
| [Сплайн-диаграмма](https://github.com/Microsoft/powerbi-visuals-spline/) </br>Визуализация и понимание искаженных данных | [Диаграмма декомпозиции временных рядов](https://github.com/Microsoft/powerbi-visuals-timeseriesdecomposition/) </br>Общие сведения о компонентах временных рядов с использованием "сезонных и трендовых декомпозиций с помощью Loess" | [Диаграмма прогнозирования временных рядов](https://github.com/Microsoft/powerbi-visuals-forcasting-exp/) </br>Использование модели экспоненциального сглаживания для прогнозирования будущих значений на основе ранее отслеживаемых значений

## <a name="next-steps"></a>Дальнейшие действия

Попробуйте создать визуальные элементы Power BI, выполнив инструкции, приведенные на странице [Руководство. Разработка визуального элемента Power BI](custom-visual-develop-tutorial.md).
