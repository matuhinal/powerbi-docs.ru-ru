---
title: Часть 2. Добавление визуализаций в отчет Power BI
description: Часть 2. Добавление визуализаций в отчет Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: c42d96fea37a6309908dd357425c3d0504e18397
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "61410259"
---
# <a name="part-2-add-visualizations-to-a-power-bi-report"></a>Часть 2. Добавление визуализаций в отчет Power BI
В [части 1](power-bi-report-add-visualizations-ii.md) вы создали базовую визуализацию, установив флажки рядом с именами полей.  Во второй части вы узнаете, как использовать функцию перетаскивания и полностью реализовать возможности панелей **Поля** и **Визуализации** для создания и изменения визуализаций.

### <a name="prerequisites"></a>Предварительные требования
- [Часть 1](power-bi-report-add-visualizations-ii.md)
- Power BI Desktop — визуализации, которые можно добавлять в отчеты с помощью службы Power BI или Power BI Desktop. В этом руководстве используется Power BI Desktop. 
- [Анализ розничной торговли — пример](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

## <a name="create-a-new-visualization"></a>Создание новой визуализации
В этом руководстве мы подробно рассмотрим набор данных по анализу розничной торговли и создадим несколько ключевых визуализаций.

### <a name="open-a-report-and-add-a-new-blank-page"></a>Откройте отчет и добавьте в него новую пустую страницу.
1. Откройте PBIX-файл с примером "Анализ розничной торговли" в Power BI Desktop. 
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-desktop.png)   

2. Добавьте новую страницу, выбрав желтый значок плюса в нижней части холста.

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>Добавьте визуализацию с отображением показателей объема продаж текущего года по сравнению с продажами в предыдущем году.
1. В таблице **Продажи** последовательно выберите элементы **Продажи этого года** > **Значение** и **Продажи прошлого года**. Power BI создаст гистограмму.  Она представляет интерес и требует более глубокого анализа. Как продажи распределяются по месяцам?  
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-barchart.png)
2. Из таблицы времени перетащите **Финансовый месяц** в область **Оси**.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-month.png)
3. [Измените визуализацию](power-bi-report-change-visualization-type.md) на диаграмму с областями.  Для выбора доступно множество типов визуализации. Сведения об использовании нужного типа см. в статьях с [описаниями каждого типа, советами, рекомендациями и учебниками](power-bi-visualization-types-for-reports-and-q-and-a.md). На панели "Визуализации" выберите значок диаграммы с областями ![](media/power-bi-report-add-visualizations-ii/power-bi-areachart.png).
4. Отсортируйте визуальные элементы, нажав кнопку с многоточием и выбрав пункт **Сортировать по финансовым месяцам**.
5. [Измените размер визуализации](power-bi-visualization-move-and-resize.md). Для этого выберите визуализацию, щелкните и перетащите один из кругов. Сделайте ее достаточно широкой, чтобы исключить полосу прокрутки, и достаточно небольшой, чтобы оставить место для добавления другой визуализации.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [Сохраните отчет](../service-report-save.md).

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>Добавьте визуализацию карты для отслеживания продаж по расположению.
1. В таблице **Магазин** выберите **Территория**. Power BI распознает, что территория является расположением, и создает визуализацию карты.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-map.png)
2. Перетащите элемент **Всего магазинов** в область "Размер".  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-map2.png)
3. Добавьте условные обозначения.  Чтобы просмотреть данные по названию магазина, перетащите элемент **Цепочка** в область условных обозначений.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-legend.png)

## <a name="next-steps"></a>Дальнейшие действия
* Подробнее о [визуализациях в отчетах Power BI](power-bi-report-visualizations.md).  
* Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

