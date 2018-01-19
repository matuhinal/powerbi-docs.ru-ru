---
title: "Изменение способа взаимодействия визуальных элементов в отчете"
description: "Документация по настройке взаимодействия визуализаций в отчете службы Microsoft Power BI и отчете Power BI Desktop."
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
ms.date: 01/10/2018
ms.author: mihart
ms.openlocfilehash: a7c4db0044772c28a3cb7a62649de3001945246c
ms.sourcegitcommit: afd6e9e6f8b192b26486cd04d2cbc9de046911b3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2018
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Взаимодействия с визуализациями в отчете Power BI
При наличии разрешений на изменение отчета вы можете использовать **взаимодействие визуализаций**, чтобы задавать влияние друг на друга визуализаций на странице отчета. 

По умолчанию визуализации на странице отчета можно использовать для кроссфильтрации и перекрестного выделения других визуализаций на странице.
Например, при выборе состояния в визуализации карты выделяется диаграмма столбца и фильтруется график, чтобы отобразить только данные, применимые к этому состоянию.
См. раздел [Сведения о фильтрации и выделении](power-bi-reports-filters-and-highlighting.md). При наличии визуализации, которая поддерживает [детализацию](power-bi-visualization-drill-down.md), детализация одной визуализации по умолчанию не оказывает влияния на другие визуализации на странице отчета. Но вы можете переопределить оба этих способа работы по умолчанию и задать взаимодействия для каждой визуализации отдельно.

Эта статья описывает, как использовать **взаимодействие визуализаций** в [режиме редактирования](service-interact-with-a-report-in-editing-view.md) службы Power BI и в Power BI Desktop. Если отчет предоставлен вам другим пользователем, вы не сможете изменять настройки взаимодействия визуализаций.

> [!NOTE]
> Термины *кроссфильтрация* и *перекрестное выделение* используются для отделения поведения, описанного здесь, от того, что происходит при использовании области **Фильтры** для фильтрации и выделения визуализаций.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Выберите визуализацию, чтобы сделать ее активной.  
2. Откройте параметры **Взаимодействия визуализаций**.
    - В службе Power BI щелкните раскрывающийся список в строке меню отчета.

       ![](media/service-reports-visual-interactions/power-bi-visual-interaction.png)

    - В версии Desktop выберите **Формат > Взаимодействия**.

        ![](media/service-reports-visual-interactions/pbi-visual-interaction-desktop.png)

3. Чтобы включить элементы управления взаимодействиями визуализаций, выберите **Изменить взаимодействия**. Power BI добавит значки перекрестной фильтрации и выделения во все остальные визуализации на странице отчета.
   
    ![](media/service-reports-visual-interactions/power-bi-icons-on.png)
3. Укажите, как выбранная визуализация должна влиять на другие.  При необходимости повторите эти действия для всех остальных визуализаций на странице отчета.
   
   * Если нужно выполнить перекрестную фильтрацию визуализации, выберите значок **фильтра** ![](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png).
   * Если нужно выполнить перекрестное выделение визуализации, выберите значок **выделения** ![](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png).
   * Если влияния не должно быть, выберите значок **нет влияния** ![](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png).

4. Чтобы включить элементы управления детализации, выберите **Детализирующие фильтры для других визуализаций**.  Теперь при детализации (и обобщении) другие визуализации на странице отчета изменяются в зависимости от выбранных вариантов детализации. 

   ![](media/service-reports-visual-interactions/drill2.gif)

### <a name="next-steps"></a>Дальнейшие действия
[Использование фильтров отчетов](power-bi-how-to-report-filter.md)

[Фильтры и выделение в отчетах](power-bi-reports-filters-and-highlighting.md)

[Power BI — основные понятия](service-basic-concepts.md)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

