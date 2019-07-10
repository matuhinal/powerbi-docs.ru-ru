---
title: Ознакомление с панелью "Фильтры" отчета
description: Добавление фильтра в отчет в службе Power BI для потребителей
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: ef7e4f556832f1323043a80cf219678a16511c9e
ms.sourcegitcommit: e67bacbfc5638ee97e3d2e0e7f5bd2d9aac78f9c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67532780"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Ознакомление с панелью "Фильтры" отчета

Эта статья содержит подробную информацию о панели **Фильтры** отчета в службе Power BI. Используйте фильтры, чтобы получать новые ценные сведения в данных.

Существует много различных способов фильтрации данных в Power BI. Дополнительные сведения см. в разделе [Фильтрация и выделение в отчетах Power BI](../power-bi-reports-filters-and-highlighting.md).

![Снимок экрана отчета в браузере со стрелкой к параметру "Фильтры".](media/end-user-report-filter/power-bi-browser-new2.png)

## <a name="working-with-the-report-filters-pane"></a>Работа с панелью "Фильтры" отчета

При совместной работе над отчетом следует найти панель **Фильтры**. В некоторых случаях она свертывается вдоль правого края отчета. Щелкните панель, чтобы развернуть ее.

![Снимок экрана отчета с раскрытой панелью "Фильтры".](media/end-user-report-filter/power-bi-filter-pane.png)

Панель **Фильтры** содержит фильтры, которые были добавлены в отчет *разработчиком*. *Пользователи*, такие как вы, могут взаимодействовать с существующими фильтрами и сохранять изменения, но не могут добавлять в отчет новые фильтры. Например, на снимке экрана выше конструктор добавил два фильтра уровня страницы: "Сегмент" и "Год". **Сегмент** и **Год**. Вы можете взаимодействовать с этими фильтрами и изменять их, однако добавить третий фильтр уровня страницы нельзя.

В службе Power BI отчеты сохраняют любые изменения, внесенные в панели **Фильтры**. Служба переносит эти изменения и в мобильную версию отчета.

Чтобы восстановить для панели **Фильтры** заданные разработчиком значения по умолчанию, выберите ![Снимок параметра "Вернуться к значениям по умолчанию".](media/end-user-report-filter/power-bi-reset.png) в строке меню вверху.

## <a name="view-all-the-filters-for-a-report-page"></a>Просмотр всех фильтров на странице отчета

На панели **Фильтры** отображаются все фильтры, добавленные разработчиком отчета. Панель **Фильтры** — это также область, где можно просмотреть сведения о фильтрах и работать с ними. Можно сохранить внесенные изменения или **Вернуться к значениям по умолчанию** для возврата к исходным параметрам фильтра.

Если вы хотите сохранить изменения, можно также создать личную закладку.  Дополнительные сведения см. в статье [Что такое закладки?](end-user-bookmarks.md).

Панель **Фильтры** отображает и контролирует несколько типов фильтров отчетов. Они могут применяться в визуальном элементе, на странице отчета и ко всему отчету.

В этом примере мы выбрали визуализацию с двумя фильтрами. Страница отчета также содержит фильтры, перечисленные в разделе **Фильтры на этой странице**. Кроме того, весь отчет также содержит фильтр **Дата**.

![Снимок экрана отчета с выделенными визуализацией и связанными с ней фильтрами.](media/end-user-report-filter/power-bi-all-filters2.png)

Рядом с некоторыми фильтрами указано **(все)** . **(Все)**  означает, что в фильтре включаются все значения. В примере выше поле **Segment(All)** означает, что эта страница отчета включает данные о всех сегментах продуктов. При выборе фильтра **Region is West** (Регион — Запад) на уровне страницы страница отчета содержит только данные для западного региона.

Вот как пользователи, просматривающие этот отчет, могут взаимодействовать с этими фильтрами

### <a name="view-only-those-filters-applied-to-a-visual"></a>Просмотр только фильтров, примененных в визуальном элементе

Чтобы получить подробный список фильтров, примененных для конкретного визуального элемента, наведите указатель мыши на визуальный элемент, чтобы увидеть значок фильтра ![Снимок экрана: значок фильтра.](media/end-user-report-filter/power-bi-filter-icon.png). Выберите его, чтобы отобразить всплывающее окно со всеми фильтрами, срезами и другими компонентами, которые влияют на этот визуальный элемент. Во всплывающем окне будут те же фильтры, которые отображаются в панели **Фильтры**.

![Снимок экрана: список фильтров со стрелками, указывающими на эти фильтры в панели "Фильтры".](media/end-user-report-filter/power-bi-hover-visual-filter.png)

Ниже приведены типы фильтров, которые отображаются в этом представлении:

- Базовые фильтры

- Срезы

- Перекрестное выделение

- Перекрестная фильтрация

- Расширенные фильтры

- Фильтры первых N элементов

- Фильтрация относительных дат

- Синхронизация срезов

- Фильтры включения и исключения

- Фильтры, передаваемые по URL-адресу

Рассмотрим следующий пример.

1. Мы видим, что на гистограмме была применена перекрестная фильтрация.

1. **Включенные** сообщает о том, что фильтрация относится к **сегменту**, и три пункта включаются.

1. Срез был применен для **квартала**.

1. **Регион** — это фильтр, применяемый к этой странице отчета, а

1. **isVanArsdel** и **год** — это фильтры, примененные к этому визуальному элементу.

![Снимок экрана отчета и его фильтров со списком пронумерованных фильтров, совпадающих с нумерованным списком выше.](media/end-user-report-filter/power-bi-visual-pop-up.png)

### <a name="search-in-a-filter"></a>Поиск в фильтре

Иногда фильтр может иметь длинный список значений. Используйте поле поиска, чтобы найти и выбрать нужное значение.

![Снимок экрана поиска в фильтре.](media/end-user-report-filter/power-bi-fiter-search.png)

### <a name="display-filter-details"></a>Отображение сведений о фильтре

Чтобы понять суть фильтра, изучите доступные значения и счетчики.  Чтобы просмотреть данные о фильтре, наведите курсор мыши и выберите стрелку рядом с именем фильтра.
  
![Снимок экрана с фильтром, показывающий выбор западного региона.](media/end-user-report-filter/power-bi-expand-filter.png)

### <a name="change-filter-selections"></a>Изменение выбранных фильтров

Один из способов анализа данных — взаимодействовать с фильтрами. Вы можете изменить выбранные параметры фильтра с помощью стрелки раскрывающегося списка рядом с именем поля.  В зависимости от фильтра и типа данных, которые фильтрует Power BI, параметры находятся в диапазоне от простого выбора в списке до определения диапазонов дат или чисел. В расширенном фильтре ниже мы изменили фильтр **Total Units YTD** (Всего единиц за текущий год) на древовидной диаграмме, чтобы выбрать диапазон от 2000 до 3000. Обратите внимание на то, что это изменение удаляет Prirum с диаграммы.
  
![Снимок экрана отчета и фильтров с выбранным значением Fashions Direct.](media/end-user-report-filter/power-bi-filter-treemap.png)

> [!TIP]
> Чтобы одновременно выбрать более одного значения фильтра, удерживайте нажатой клавишу CTRL. Большинство фильтров поддерживает множественный выбор.

### <a name="reset-filter-to-default"></a>Восстановление значений фильтра по умолчанию

Если вы хотите отменить все изменения, которые вы внесли в фильтры, выберите команду **Вернуться к значениям по умолчанию** в верхней строке меню.  Фильтры вернутся в исходное состояние, заданное создателем отчета.

![Снимок экрана: вернуться к значениям по умолчанию.](media/end-user-report-filter/power-bi-reset.png)

### <a name="clear-a-filter"></a>Очистка фильтра

Если есть только один фильтр, который вы хотите задать как **(Все)** , очистите его, выбрав значок с изображением ластика ![снимок экрана: значок с изображением ластика.](media/end-user-report-filter/power-bi-eraser-icon.png) рядом с именем фильтра.
  
<!--  too much detail for consumers

## Types of filters: text field filters
### List mode
Ticking a checkbox either selects or deselects the value. The **All** checkbox can be used to toggle the state of all checkboxes on or off. The checkboxes represent all the available values for that field.  As you adjust the filter, the restatement updates to reflect your choices. 

![list mode filter](media/end-user-report-filter/power-bi-restatement-new.png)

Note how the restatement now says "is Mar, Apr or May".

### Advanced mode
Select **Advanced Filtering** to switch to advanced mode. Use the dropdown controls and text boxes to identify which fields to include. By choosing between **And** and **Or**, you can build complex filter expressions. Select the **Apply Filter** button when you've set the values you want.  

![advanced mode](media/end-user-report-filter/power-bi-advanced.png)

## Types of filters: numeric field filters
### List mode
If the values are finite, selecting the field name displays a list.  See **Text field filters** &gt; **List mode** above for help using checkboxes.   

### Advanced mode
If the values are infinite or represent a range, selecting the field name opens the advanced filter mode. Use the dropdown and text boxes to specify a range of values that you want to see. 

![advanced filter](media/end-user-report-filter/power-bi-dropdown-and-text.png)

By choosing between **And** and **Or**, you can build complex filter expressions. Select the **Apply Filter** button when you've set the values you want.

## Types of filters: date and time
### List mode
If the values are finite, selecting the field name displays a list.  See **Text field filters** &gt; **List mode** above for help using checkboxes.   

### Advanced mode
If the field values represent date or time, you can specify a start/end time when using Date/Time filters.  

![datetime filter](media/end-user-report-filter/pbi_date-time-filters.png)

-->

## <a name="next-steps"></a>Дальнейшие действия

Сведения о [взаимных кросс-фильтрации и перекрестном выделении визуальных элементов на странице отчета](end-user-interactions.md)