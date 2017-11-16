---
title: "Срезы в Power BI (руководство)"
description: "Учебник: срезы в Power BI"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/30/2017
ms.author: mihart
ms.openlocfilehash: b6ce0c396f4a189489b97fe5cd86ab5cd8dbcc35
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="slicers-in-power-bi-service-tutorial"></a>Срезы в службе Power BI (руководство)
Ваш вице-президент по продажам хочет иметь возможность просматривать ряд метрик — по каждому подразделению и по каждому отдельному региональному менеджеру. Он может создать отдельную страницу отчета для каждого менеджера или воспользоваться срезом. Срез сужает часть набора данных, отображаемую в других визуализациях на странице.  Срезы — это альтернативный способ фильтрации.

![](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Способы применения среза
Срезы отлично подходят для следующих ситуаций:

* отображение часто применяемых и важных фильтров на холсте отчета для упрощения доступа к ним;
* упрощение определения текущего состояния фильтрации без необходимости открывать раскрывающийся список для поиска сведений о фильтрации;
* если требуется скрыть ненужные столбцы и при этом сохранить возможность их использования для фильтрации, что позволяет получить более сжатые и понятные таблицы;
* создание более подробных отчетов — поскольку срезы представляют собой перемещаемые объекты, вы можете поместить их в соответствующую часть отчета, к которой хотите привлечь внимание пользователей.

## <a name="create-a-slicer"></a>Создание среза
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>


1. Откройте пример [Анализ розничной торговли](sample-retail-analysis.md) в [режиме редактирования](service-interact-with-a-report-in-editing-view.md) и [добавьте новую страницу отчета](power-bi-report-add-page.md).
2. На панели "Поля" выберите **District > District Manager** (Округ > Региональный менеджер).
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_chartfirst.png)
3. Преобразуйте визуализацию в срез. На панели "Визуализации" выберите значок среза.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_select.png)

## <a name="format-the-slicer"></a>Форматирование среза
1. Выбрав срез, на панели "Визуализации" щелкните значок валика ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) для отображения параметров форматирования.
2. Выберите **Общие > Цвет контура**, выберите темно-синий цвет и измените значение **Вес** на **6**.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_outline2.png)
3. В разделе **Selection Controls**(Элементы управления выбора) для параметра **Select All** (Общий выбор) по умолчанию используется значение **Off** (Выкл.), а для параметра **Single Select** (Единичный выбор) значение **On**(Вкл.). Это означает, что для одновременного выбора нескольких имен нужно использовать клавишу CTRL. Установите для параметра **Select All** (Общий выбор) значение **On** (Вкл.), а для параметра **Single Select** (Единичный выбор) — значение **Off**(Выкл.).
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_selectioncontrols2.png)
   
   * Обратите внимание, что параметр **Select All** (Общий выбор) для данного теперь находится в начале списка. Переключайте параметр **Select All** (Общий выбор), чтобы выбрать все имена или отменить выбор всех имен.
   * Теперь вы можете выбрать несколько имен без использования клавиши CTRL.
4. В разделе **Элементы**увеличьте размер шрифта до 14 пт.  Мы хотим быть уверены, что наши коллеги заметят этот срез.
5. Наконец, выберите темно-красный цвет для параметра **Цвет шрифта** .  Это позволит отличить выбранные имена от невыбранных в нашем срезе.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_font2.png)
6. Исследуйте другие параметры, доступные для срезов.

## <a name="use-the-slicer-in-a-report"></a>Использование среза в отчете
1. Добавьте дополнительные средства визуализации на страницу отчета или откройте пример отчета [Анализ розничной торговли](sample-retail-analysis.md) и выберите вкладку **District Monthly Sales** (Продажи за месяц по округам).
   
    ![](media/power-bi-visualization-slicers/power-bi-retail-sample.png)
2. Откройте срез страницы отчета для пользователя Carlos. Обратите внимание на то, как обновляются другие визуализации, отражая сделанные изменения
   
    ![](media/power-bi-visualization-slicers/slicer2.gif)
3. Отсортируйте срез в алфавитном порядке по фамилии регионального менеджера.  Щелкните многоточие (...) в правом верхнем углу среза и выберите **District Manager**(Региональный менеджер).
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sort2.png)
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sorted.png)

## <a name="control-what-effect-the-slicer-has-on-other-visuals-on-the-page"></a>Управление взаимодействием среза с другими визуальными элементами на странице
Срез можно настроить таким образом, чтобы он выполнял фильтрацию только определенных визуальных элементов на странице отчета.  Для этого предназначен элемент управления **Интерактивное взаимодействие**.

**Примечание.** Если вкладка **Интерактивное взаимодействие** не отображается, поищите вместо нее этот значок: ![](media/power-bi-visualization-slicers/power-bi-slicer-visual-interactions.png). Если и его вы не находите, убедитесь, что вы используете [представление редактирования](service-reading-view-and-editing-view.md) отчета.

1. Выберите срез, чтобы активировать его, а затем в строке меню щелкните **Интерактивное взаимодействие**.
   
    ![](media/power-bi-visualization-slicers/pbi-slicer-interactions.png)
2. Над всеми визуальными элементами на странице появятся фильтры. Если вы хотите, чтобы срез выполнял фильтрацию визуального элемента, выберите соответствующий значок **фильтра**.  Чтобы срез не оказывал на элемент никакого воздействия, выберите значок **Нет**.
   
    ![](media/power-bi-visualization-slicers/filter-controls.png)

Дополнительные сведения см. в статье [Взаимодействия с визуализациями в отчете Power BI](service-reports-visual-interactions.md).

## <a name="considerations-and-troubleshooting-slicers-in-power-bi"></a>Рекомендации по срезам в Power BI и устранение неполадок при работе с ними
При использовании срезов в Power BI действуют следующие ограничения:

1. Срезы не поддерживают поля ввода.
2. Нельзя использовать один срез по всему отчету. Срез влияет только на текущую страницу.
3. Срезы нельзя закрепить на панели мониторинга.
4. Для срезов не поддерживается детализация.    
5. Срезы не поддерживают фильтры уровня визуального элемента.

У вас есть идеи по улучшению Power BI? [Отправка идеи](https://ideas.powerbi.com/forums/265200-power-bi-ideas).

## <a name="next-steps"></a>Дальнейшие действия
 [Добавление визуализации в отчет](power-bi-report-add-visualizations-i.md)

 [Типы визуализаций в Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

 [Power BI — основные понятия](service-basic-concepts.md)

[Бесплатная пробная версия](https://powerbi.com/)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

