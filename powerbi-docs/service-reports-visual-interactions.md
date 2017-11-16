---
title: "Изменение способа взаимодействия визуальных элементов в отчете"
description: "Документация по настройке взаимодействий визуальных элементов в отчете Microsoft Power BI."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: N_xYsCbyHPw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 126bd40e98a88138a2732155f9792d65666e52c7
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Взаимодействия с визуализациями в отчете Power BI
По умолчанию визуализации на странице отчета можно использовать для кроссфильтрации и перекрестного выделения других визуализаций на странице.
Например, при выборе состояния в визуализации карты выделяется диаграмма столбца и фильтруется график, чтобы отобразить только данные, применимые к этому состоянию.
См. раздел [Сведения о фильтрации и выделении](power-bi-reports-filters-and-highlighting.md).

Чтобы изменить стандартное поведение визуализаций, используйте элемент управления **Взаимодействие визуальных элементов**. Этот элемент доступен только в [представлении редактирования](service-interact-with-a-report-in-editing-view.md). Если доступ к отчету вам предоставил другой пользователь, у вас не будет доступа к функции взаимодействия визуальных элементов.

> [!NOTE]
> Термины *кроссфильтрация* и *перекрестное выделение* используются для отделения поведения, описанного здесь, от того, что происходит при использовании области **Фильтры** для фильтрации и выделения визуализаций.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Выберите визуализацию, чтобы сделать ее активной.  
2. Включите **Интерактивное взаимодействие** , выбрав его в верхней части строки меню. Обратите внимание на значки фильтра и выделения, которые отображаются, если навести указатель мыши на другие визуализации на странице отчета.
   
    ![](media/service-reports-visual-interactions/pbi-visual-interaction-icon.png)
3. Укажите, как выбранная визуализация должна влиять на другие.  
   
   * Если следует выполнить кроссфильтрацию другой визуализации, выберите значок **фильтровать** ![](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png).
   * Если следует выполнить кроссфильтрацию этой визуализации, выберите значок **выделить** ![](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png).
   * Если влияния не должно быть, выберите значок **нет влияния** ![](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png).
4. При необходимости повторите эти действия для всех остальных визуализаций на странице отчета.

### <a name="next-steps"></a>Дальнейшие действия
[Использование фильтров отчетов](power-bi-how-to-report-filter.md)

[Фильтры и выделение в отчетах](power-bi-reports-filters-and-highlighting.md)

[Power BI — основные понятия](service-basic-concepts.md)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

