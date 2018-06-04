---
title: Кольцевые диаграммы в Power BI
description: Кольцевые диаграммы в Power BI
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/23/2017
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 5d8be3d160e8ea37ba9814c7bd78c3ad5a751d3b
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34294203"
---
# <a name="doughnut-charts-in-power-bi"></a>Кольцевые диаграммы в Power BI
Кольцевая диаграмма похожа на круговую диаграмму в том, что она показывает отношение между целым и частями. Единственное отличие в том, что центр диаграммы пуст и в него можно добавить подпись или значок.

## <a name="create-a-doughnut-chart"></a>Создание кольцевой диаграммы
В этих инструкциях используется набор данных "Анализ розничной торговли — прием" для создания кольцевой диаграммы, в которой отображаются продажи за этот год по категориям. Чтобы продолжить работу, [скачайте пример](sample-datasets.md) для службы Power BI (app.powerbi.com) или Power BI Desktop.

1. Начните с [пустой страницы отчета](power-bi-report-add-page.md) и выберите поле **Этап продажи**\>**Этап продажи**. Если вы используете службу Power BI, нужно открыть отчет в [режиме правки](service-interact-with-a-report-in-editing-view.md).

2. В области "Поля" выберите **Продажи**\>**Продажи за прошлый год**.  
   
3. В области "Визуализации" щелкните значок кольцевой диаграммы ![значок кольцевой диаграммы](), чтобы преобразовать линейчатую диаграмму в кольцевую. Если поля **Продажи за прошлый год** нет в области **Значения**, перетащите его туда.
     
   ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. Выберите **Элемент** \> **Категория**, чтобы добавить его в область **Условные обозначения**. 
     
    ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. При необходимости [настройте размер и цвет текста диаграммы](power-bi-visualization-customize-title-background-and-legend.md). 

## <a name="considerations-and-troubleshooting"></a>Рекомендации и устранение неполадок
* Сумма значений кольцевой диаграммы должна составлять 100 %.
* Слишком большое число категорий затрудняет чтение и понимание.
* Кольцевые диаграммы лучше подходят для сравнения определенной части с целым, а не отдельных частей друг с другом. 

## <a name="next-steps"></a>Дальнейшие действия
[Отчеты в Power BI](service-reports.md)

[Типы визуализаций в Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Визуализации в отчетах Power BI](power-bi-report-visualizations.md)

[Power BI — основные понятия](service-basic-concepts.md)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

