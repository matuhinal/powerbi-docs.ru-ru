---
title: "Кольцевые диаграммы в Power BI (руководство)"
description: "Учебник. Кольцевые диаграммы в Power BI"
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
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: 2f428095eb57c5358770f1d6d8572316d2b84c37
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="doughnut-charts-in-power-bi-tutorial"></a>Кольцевые диаграммы в Power BI (руководство)
Кольцевая диаграмма похожа на круговую диаграмму в том, что она показывает отношение между целым и частями. Единственное отличие в том, что центр диаграммы пуст и в него можно добавить подпись или значок.

## <a name="create-a-doughnut-chart"></a>Создание кольцевой диаграммы
Для выполнения этой процедуры войдите в службу Power BI и выберите **Получить данные** \> **Примеры** \> **Анализ розничной торговли — пример** \> **Подключение**. 

1. На панели мониторинга выберите **Total Stores** (Всего магазинов), чтобы открыть отчет "Анализ розничной торговли — пример".
2. Выберите пункт **Изменить отчет** , чтобы открыть отчет в режиме редактирования.
3. [Добавьте новую страницу отчета](power-bi-report-add-page.md).
4. Создайте кольцевую диаграмму, отображающую продажи за этот год по категориям.
   
   * В области **Поля** выберите **Продажи** \> **Продажи за прошлый год**.
   * Преобразуйте ее в кольцевую диаграмму. Если поля "Продажи за прошлый год" нет в области **Значения** , перетащите его туда.
     
       ![](media/power-bi-visualization-doughnut-charts/convertdonut.png)
   * Выберите **Элемент** \> **Категория**, чтобы добавить его в область **Условные обозначения**. 
     
       ![](media/power-bi-visualization-doughnut-charts/doughnuttutorial.png)

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

