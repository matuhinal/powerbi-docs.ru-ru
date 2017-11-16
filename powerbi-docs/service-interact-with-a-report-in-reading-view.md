---
title: "Взаимодействие с отчетом в режиме чтения в Power BI"
description: "Взаимодействие с отчетом в режиме чтения в Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/15/2017
ms.author: mihart
ms.openlocfilehash: 54de712e0743801b3e8c565ca997bbc56e254c69
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="interact-with-a-report-in-reading-view-in-power-bi"></a>Взаимодействие с отчетом в режиме чтения в Power BI
## <a name="reading-view"></a>Режим чтения
Режим чтения не так интерактивен, как [режим редактирования](service-interact-with-a-report-in-editing-view.md), но также поддерживает разные функции для работы с данными. Они удобны при просмотре отчетов, к которым [вам предоставлен доступ](service-share-dashboards.md), так как их можно открывать только в режиме чтения.

Режим чтения удобен и безопасен для знакомства с данными и их изучения. В режиме чтения можно выполнять перекрестное выделение и фильтрацию визуальных элементов на странице.  Просто выделите или выберите значение в одном из визуальных элементов, и это тут же отразится на состоянии других элементов. С помощью области фильтрации можно добавлять и изменять фильтры на странице отчетов, а также менять параметры сортировки значений в визуализации. Любые фильтры и выделения, которые вы вносите, не будут сохранены в отчете.

## <a name="cross-highlight-the-related-visualizations-on-a-page"></a>Перекрестное выделение связанных визуализаций на странице
Все визуализации на одной странице отчета соединены друг с другом.  Это означает, что если выбрать одно или несколько значений в одной визуализации, другие визуализации, в которых также используются выбранные значение, изменятся соответствующим образом.

![](media/service-interact-with-a-report-in-reading-view/pagefilter3b.gif)

> [!NOTE]
> Чтобы выбрать несколько элементов в визуализации, удерживайте нажатой клавишу CTRL.
> 
> 

## <a name="hover-over-visual-elements-to-see-the-details"></a>Наводите указатель мыши на визуальные элементы для просмотра сведений.
![](media/service-interact-with-a-report-in-reading-view/amarillachart.png)

## <a name="sort-the-data-in-a-visualization"></a>Сортировка данных в визуализации
Выберите многоточие (...), чтобы открыть меню **сортировки**. Щелкните стрелку раскрывающегося списка, чтобы выбрать поля для сортировки, или щелкните значок AZ для переключения между сортировкой по возрастанию и убыванию. 

![](media/service-interact-with-a-report-in-reading-view/pbi_changechartsort.gif) 

## <a name="interact-with-filters"></a>Взаимодействие с фильтрами
Если автор отчета добавил фильтры на страницу отчета, их можно использовать в режиме чтения. Изменения, которые вы вносите, не будут сохранены в отчете.

1. Щелкните значок фильтра в правом верхнем углу.
   
   ![](media/service-interact-with-a-report-in-reading-view/filters.png)  
2. Вы увидите фильтры, примененные к выбранным визуальным элементам (фильтры уровня визуального элемента), ко всей странице отчета (фильтры уровня страницы) и ко всему отчету (фильтры уровня отчета).
   
   ![](media/service-interact-with-a-report-in-reading-view/power-bi-reading-filters.png)
3. Наведите указатель мыши на фильтр и откройте его, щелкнув стрелку вниз.
   
   ![](media/service-interact-with-a-report-in-reading-view/power-bi-expan-filter.png)
4. Внесите изменения в фильтры и посмотрите, как это повлияет на визуальные элементы.  
   
   * В этом примере выбран фильтр на уровне страницы для **сети магазинов**. Измените фильтрацию по свойству **Fashions Direct** вместо свойства **Lindseys**, сняв флажок напротив одного свойства и установив его напротив другого.
     
     ![](media/service-interact-with-a-report-in-reading-view/power-bi-filter-chain.png)
   * Или отмените фильтрацию для **сети магазинов**, щелкнув значок с изображением ластика ![](media/service-interact-with-a-report-in-reading-view/power-bi-eraser-icon.png) или выбрав оба магазина сети.
   * выберите фильтр уровня страницы **District** и задайте параметр **Расширенная фильтрация**. Настройте фильтрацию, чтобы отображались только районы, которые начинаются с букв **FD** и не содержат цифру 4.
     
     ![](media/service-interact-with-a-report-in-reading-view/power-bi-advanced-filter.png)

Дополнительные сведения см. в разделах [Добавление фильтра к отчету](power-bi-report-add-filter.md) и [О фильтрах и выделении в отчетах](power-bi-reports-filters-and-highlighting.md).

## <a name="zoom-in-on-individual-visuals"></a>Увеличение масштаба отдельных визуальных элементов
Наведите указатель мыши на визуальный элемент и выберите значок **режима фокусировки** ![](media/service-interact-with-a-report-in-reading-view/pbi_popouticon.jpg). Открытая визуализация в режиме фокусировки разворачивается, заполняя собой весь холст отчета.

![](media/service-interact-with-a-report-in-reading-view/powerbi-focus-mode.png)

Чтобы отобразить эту визуализацию без строк меню, области фильтров и других элементов интерфейса, щелкните значок перехода в **полноэкранный режим** в верхней строке меню ![](media/service-interact-with-a-report-in-reading-view/power-bi-focus-icon.png).

![](media/service-interact-with-a-report-in-reading-view/power-bi-full-screen.png)

Дополнительные сведения см. в статье об отображении отчетов [в режиме фокусировки](service-focus-mode.md) и [полноэкранном режиме](service-fullscreen-mode.md).

## <a name="adjust-the-display-dimensions"></a>Подстройка размеров отображения
Отчеты можно просматривать на различных устройствах с различными размерами экранов и соотношениями сторон.  Отрисовка по умолчанию может не соответствовать тому, что хотелось бы увидеть на устройстве.  Чтобы скорректировать внешний вид, выберите **Вид** и настройте перечисленные ниже параметры.

* Вписать в страницу: масштабировать контент так, чтобы он полностью вписывался в страницу.
* По ширине: масштабировать контент по ширине страницы.
* Фактический размер: отображать контент в полном размере.  

![](media/service-interact-with-a-report-in-reading-view/power-bi-view.png)

  В режиме чтения выбранный режим отображения является временным — он не сохраняется при закрытии отчета.

  Дополнительные сведения см. в статье [Изменение размера страницы отчета (руководство)](power-bi-change-report-display-settings.md).

## <a name="next-steps"></a>Дальнейшие действия
[Отчеты в Power BI](service-reports.md)

[Переход из режима чтения в режим правки в Power BI](service-reading-view-and-editing-view.md)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

