---
title: Обзор закладки в отчетах службы Power BI
description: Раздел документации по запросам функции "Вопросы и ответы" Power BI на естественном языке.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/10/2019
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 55fafb00135908dc4f82151b96ed04d2cf2568da
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "65608323"
---
# <a name="what-are-bookmarks"></a>Что такое закладки?
Закладки сохранить текущие настройки представления страницы отчета, включая фильтры, срезы и состояние визуальных элементов. Если выбрать закладку, Power BI позволяет вернуться к этому представлению. Существует два типа функции закладок - созданные самостоятельно и расписаниями, создаваемыми отчетов *конструкторы*.

## <a name="use-bookmarks-to-share-insights-and-build-stories-in-power-bi"></a>Использование закладок для обмена аналитическими сведениями и создания историй в Power BI 
Существует множество вариантов применения закладок. Предположим, вы обнаруживаете интересных сведений и хотите сохранить его--создать закладку, чтобы можно было вернуться позже. Необходимо оставить и хотите сохранить текущей работы, создать закладку. Можно даже сделать закладку, вернуться в представление по умолчанию отчета, поэтому каждый раз при, сначала открывает представление страницы отчета. 

Кроме того, можно создать коллекцию закладок, расположить их в порядке и последовательно переходить к каждой закладке в презентации, чтобы выделить ряд аналитических сведений истории.  

![Отображение панели закладок, выбрав его из ленты.](media/end-user-bookmarks/power-bi-bookmarks-pane.png)

## <a name="using-bookmarks"></a>Использование закладок
Чтобы открыть панель закладок, выберите **закладки** в строке меню. Чтобы вернуться к исходному виду опубликованного отчета, выберите **восстановить значения по умолчанию**.

### <a name="report-bookmarks"></a>Отчет закладки
Если отчет *конструктор* включены в отчет закладки, вы найдете их в разделе **отчет закладки** заголовок. 

![Показать отчет закладки.](media/end-user-bookmarks/power-bi-report-bookmark.png)

Выберите закладку, чтобы изменить это представление отчета. 

![Видео о том, отчет закладки выбран.](media/end-user-bookmarks/power-bi-bookmarks.gif)

### <a name="personal-bookmarks"></a>Личные закладки

Когда создается закладка, вместе с ней сохраняются следующие элементы:

* текущая страница;
* Фильтры
* срезы, в том числе тип среза (например, раскрывающийся список или список) и состояние среза;
* состояние выбора визуального элемента (например, фильтры перекрестного выделения);
* порядок сортировки;
* расположение при детализации;
* видимость объекта, настраиваемая с помощью панели **выбора**;
* режим фокусировки или режим **В центре внимания** для любого видимого объекта.

Настройте вид страницы отчета для отображения в закладке. Когда вы упорядочите страницу отчета и визуальные элементы нужным образом, на панели **Закладки** щелкните **Добавить**, чтобы добавить закладку. В этом примере мы добавили некоторые фильтры для региона и даты. 

![Добавьте личные закладки.](media/end-user-bookmarks/power-bi-add-personal.png)

**Power BI** создает закладку и присваивает ему универсальное имя или ввести имя. Вы можете *Переименовать*, *удалить*, или *обновление* закладки, нажмите кнопку с многоточием рядом с именем закладки, а затем выберите действие в появившемся меню.

После закладки, можно отобразить его, просто выбрав закладку в **закладки** области. 

![Добавьте личные закладки.](media/end-user-bookmarks/power-bi-personal-bookmark.png)


<!--
## Arranging bookmarks
As you create bookmarks, you might find that the order in which you create them isn't necessarily the same order you'd like to present them to your audience. No problem, you can easily rearrange the order of bookmarks.

In the **Bookmarks** pane, simply drag-and-drop bookmarks to change their order, as shown in the following image. The yellow bar between bookmarks designates where the dragged bookmark will be placed.

![Change bookmark order by drag-and-drop](media/desktop-bookmarks/bookmarks_06.png)

The order of your bookmarks can become important when you use the **View** feature of bookmarks, as described in the next section. 

-->

## <a name="bookmarks-as-a-slide-show"></a>Представление закладок в виде слайд-шоу
Для представления или просматривать закладки, в порядке, выберите **представление** из **закладки** панели, чтобы начать слайд-шоу.

При использовании режима **Представление** обратите внимание на несколько возможностей.

1. Имя закладки отображается в строке заголовка закладки в нижней части холста.
2. В строке заголовка закладки есть кнопки со стрелками для перемещения к следующей или предыдущей закладке.
3. Вы можете выйти из режима **Представление**, нажав кнопку **Выход** на панели **Закладки** или щелкнув **X** в строке заголовка закладки. 

![Закладка слайд-шоу](media/end-user-bookmarks/power-bi-bookmark-slideshow.png)

При работе в режиме **Представление** вы можете закрыть панель **Закладки** (щелкнув X на этой панели), чтобы предоставить дополнительное пространство для презентации. Также в режиме **Представление** все визуальные элементы являются интерактивными и доступными для перекрестного выделения (как и во всех остальных случаях). 

<!--
## Visibility - using the Selection pane
With the release of bookmarks, the new **Selection** pane is also introduced. The **Selection** pane provides a list of all objects on the current page and allows you to select the object and specify whether a given object is visible. 

![Enable the Selection pane](media/desktop-bookmarks/bookmarks_08.png)

You can select an object using the **Selection** pane. Also, you can toggle whether the object is currently visible by clicking the eye icon to the right of the visual. 

![Selection pane](media/desktop-bookmarks/bookmarks_09.png)

When a bookmark is added, the visible status of each object is also saved based on its setting in the **Selection** pane. 

It's important to note that **slicers** continue to filter a report page, regardless of whether they are visible. As such, you can create many different bookmarks, with different slicer settings, and make a single report page appear very different (and highlight different insights) in various bookmarks.


## Bookmarks for shapes and images
You can also link shapes and images to bookmarks. With this feature, when you click on an object, it will show the bookmark associated with that object. This can be especially useful when working with buttons; you can learn more by reading the article about [using buttons in Power BI](desktop-buttons.md). 

To assign a bookmark to an object, select the object, then expand the **Action** section from the **Format Shape** pane, as shown in the following image.

![Add bookmark link to an object](media/desktop-bookmarks/bookmarks_10.png)

Once you turn the **Action** slider to **On** you can select whether the object is a back button, a bookmark, or a Q&A command. If you select bookmark, you can then select which of your bookmarks the object is linked to.

There are all sorts of interesting things you can do with object-linked bookmarking. You can create a visual table of contents on your report page, or you can provide different views (such as visual types) of the same information, just by clicking on an object.

When you are in editing mode you can use ctrl+click to follow the link, and when not in edit mode, simply click the object to follow the link. 


## Bookmark groups

Beginning with the August 2018 release of **Power BI Desktop**, you can create and use bookmark groups. A bookmark group is a collection of bookmarks that you specify, which can be shown and organized as a group. 

To create a bookmark group, hold down the CTRL key and select the bookmarks you want to include in the group, then click the ellipses beside any of the selected bookmarks, and select **Group** from the menu that appears.

![Create a bookmark group](media/desktop-bookmarks/bookmarks_15.png)

**Power BI Desktop** automatically names the group *Group 1*. Fortunately, you can just double-click on the name and rename it to whatever you want.

![Rename a bookmark group](media/desktop-bookmarks/bookmarks_16.png)

With any bookmark group, clicking on the bookmark group's name only expands or collapses the group of bookmarks, and does not represent a bookmark by itself. 

When using the **View** feature of bookmarks, the following applies:

* If the selected bookmark is in a group when you select **View** from bookmarks, only the bookmarks *in that group* are shown in the viewing session. 

* If the selected bookmark is not in a group, or is on the top level (such as the name of a bookmark group), then all bookmarks for the entire report are played, including bookmarks in any group. 

To ungroup bookmarks, just select any bookmark in a group, click the ellipses, and then select **Ungroup** from the menu that appears. 

![Ungroup a bookmark group](media/desktop-bookmarks/bookmarks_17.png)

Note that selecting **Ungroup** for any bookmark from a group takes all bookmarks out of the group (it deletes the group, but not the bookmarks themselves). So to remove a single bookmark from a group, you need to **Ungroup** any member from that group, which deletes the grouping, then select the members you want in the new group (using CTRL and clicking each bookmark), and select **Group** again. 
-->





## <a name="limitations-and-considerations"></a>Рекомендации и ограничения
К этому выпуску функции **Закладки** применяется ряд ограничений и рекомендаций.

* Большинство пользовательских визуальных элементов должны нормально работать с использованием закладок. Если у вас возникли трудности при использовании закладок и пользовательского визуального элемента, обратитесь к его разработчику с просьбой добавить поддержку закладок в соответствующий визуальный элемент. 
* Если на страницу отчета добавить визуальный элемент после создания закладки, он будет отображаться в состоянии по умолчанию. Это также означает, что, если добавить срез на страницу с созданными ранее закладками, срез останется в состоянии по умолчанию.
* Перемещение визуальных элементов после создания закладки будет отражаться в закладке. 
* Как правило, закладок не будут затронуты при отчете *конструктор* обновляет или повторной публикации отчета. Тем не менее если конструктор вносит значительные изменения к отчету, например удаление полей, используемых с закладкой, вы получите сообщение об ошибке при очередном попытаться открыть ее. 

<!--
## Next steps
spotlight?
-->
