---
title: Ознакомление с панелью "Фильтры" отчета
description: Добавление фильтра в отчет в службе Power BI для потребителей
author: mihart
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 03/11/2020
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: cb3947ec7aaf6d67a22eb1d7543a57e66e87f5f3
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "79114441"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Ознакомление с панелью "Фильтры" отчета

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Эта статья содержит подробную информацию о панели **Фильтры** отчета в службе Power BI. Используйте фильтры, чтобы получать новые ценные сведения в данных.

Существует много различных способов фильтрации данных в Power BI. Дополнительные сведения см. в разделе [Фильтрация и выделение в отчетах Power BI](../power-bi-reports-filters-and-highlighting.md).

![Снимок экрана отчета в браузере со стрелкой к параметру "Фильтры".](media/end-user-report-filter/power-bi-report.png)

## <a name="working-with-the-report-filters-pane"></a>Работа с панелью "Фильтры" отчета

При совместной работе над отчетом следует найти панель **Фильтры**. В некоторых случаях она свертывается вдоль правого края отчета. Щелкните панель, чтобы развернуть ее.

![Снимок экрана отчета с раскрытой панелью "Фильтры".](media/end-user-report-filter/power-bi-expand-filter-pane.png)

Панель **Фильтры** содержит фильтры, которые были добавлены в отчет *разработчиком*. *Пользователи*, такие как вы, могут взаимодействовать с существующими фильтрами и сохранять изменения, но не могут добавлять в отчет новые фильтры. Например, на снимке экрана выше конструктор добавил три фильтра уровня страницы: **сегмент — все**, **год — 2014**, а **регион — центральный**. Вы можете взаимодействовать с этими фильтрами и изменять их, однако добавить четвертый фильтр уровня страницы нельзя.

В службе Power BI отчеты сохраняют любые изменения, внесенные в панели **Фильтры**. Служба переносит эти изменения и в мобильную версию отчета. 

Чтобы восстановить для **панели фильтров** заданные разработчиком значения по умолчанию, выберите **Вернуться к значениям по умолчанию** в верхней строке меню.

![Снимок экрана: значок "Вернуться к значениям по умолчанию".](media/end-user-report-filter/power-bi-reset-icon.png) 

> [!NOTE]
> Если параметр **Восстановить по умолчанию** не отображается, возможно, он был отключен *создателем отчета*. *Создатель* также может блокировать определенные фильтры, чтобы их нельзя было изменить.

## <a name="view-all-the-filters-for-a-report-page"></a>Просмотр всех фильтров на странице отчета

На панели **Фильтры** отображаются все фильтры, добавленные разработчиком отчета. Панель **Фильтры** — это также область, где можно просмотреть сведения о фильтрах и работать с ними. Сохраните внесенные изменения или используйте параметр **Вернуться к значениям по умолчанию** для возврата к исходным параметрам фильтра.

Если вы хотите сохранить изменения, можно также создать личную закладку. Дополнительные сведения см. в статье [Что такое закладки?](end-user-bookmarks.md).

Панель **Фильтры** отображает и контролирует несколько типов фильтров отчетов: отчет, страница отчетов и визуальный элемент.

В этом примере мы выбрали визуализацию с тремя фильтрами. Страница отчета также содержит фильтры, перечисленные в разделе **Фильтры на этой странице**. Кроме того, весь отчет также содержит фильтр **Дата**.

![Снимок экрана отчета с выделенными визуализацией и связанными с ней фильтрами.](media/end-user-report-filter/power-bi-filters-pane.png)

Рядом с некоторыми фильтрами указано **(все)** . **(Все)**  означает, что в фильтре включаются все значения. В примере выше поле **Segment(All)** означает, что эта страница отчета включает данные о всех сегментах продуктов. 

Вот как пользователи, просматривающие этот отчет, могут взаимодействовать с этими фильтрами

### <a name="view-only-those-filters-applied-to-a-visual"></a>Просмотр только фильтров, примененных в визуальном элементе

Чтобы получить подробный список фильтров, примененных для конкретного визуального элемента, наведите указатель мыши на визуальный элемент, чтобы увидеть значок фильтра ![Снимок экрана: значок фильтра.](media/end-user-report-filter/power-bi-filter-icon.png). Выберите его, чтобы отобразить всплывающее окно со всеми фильтрами, срезами и другими компонентами, которые влияют на этот визуальный элемент. Фильтры во всплывающем окне включают в себя те же фильтры, которые отображаются на панели **Фильтры**, а также дополнительную фильтрацию, влияющую на выбранный визуальный элемент.

![Снимок экрана: список фильтров со стрелками, указывающими на эти фильтры в панели "Фильтры".](media/end-user-report-filter/power-bi-hover-filters.png)

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

В этом примере:
1. Фильтр **Включено** сообщает нам о перекрестной фильтрации визуального элемента. Это означает, что штаты Юта, Колорадо и Техас были выбраны на одном из визуальных элементов на этой странице отчетов. В этом случае, это карта. В результате выбора этих трех штатов были удалены данные для всех остальных штатов, отображаемых на выбранной линейчатой диаграмме.  

1. **Дата** — это фильтр, применяемый ко всем страницам в этом отчете.

1. Фильтры **регион — центральный** и **год — 2014** применяются к этой странице отчета.

4. **Производитель — VanArsdel, Natura, Aliqui или Pirum** — это фильтр, применяемый к этому визуальному элементу.


### <a name="search-in-a-filter"></a>Поиск в фильтре

Иногда фильтр может иметь длинный список значений. Используйте поле поиска, чтобы найти и выбрать нужное значение.

![Снимок экрана поиска в фильтре.](media/end-user-report-filter/power-bi-search.png)

### <a name="display-filter-details"></a>Отображение сведений о фильтре

Чтобы понять суть фильтра, изучите доступные значения и счетчики.  Чтобы просмотреть данные о фильтре, наведите курсор мыши и выберите стрелку рядом с именем фильтра.
  
![Снимок экрана с фильтром, показывающий выбор западного региона.](media/end-user-report-filter/power-bi-filter-expand.png)

### <a name="change-filter-selections"></a>Изменение выбранных фильтров

Один из способов анализа данных — взаимодействовать с фильтрами. Вы можете изменить выбранные параметры фильтра с помощью стрелки раскрывающегося списка рядом с именем поля.  В зависимости от фильтра и типа данных, которые фильтрует Power BI, параметры находятся в диапазоне от простого выбора в списке до определения диапазонов дат или чисел. В расширенном фильтре ниже мы изменили фильтр **Total Units YTD** (Всего единиц за текущий год) на древовидной диаграмме, чтобы выбрать диапазон от 2000 до 3000. Обратите внимание, что это изменение удаляет Pirum с диаграммы "дерево".
  
![Снимок экрана отчета и фильтров с выбранным визуальным элементом диаграммы "Дерево".](media/end-user-report-filter/power-bi-treemap-filters.png)

> [!TIP]
> Чтобы одновременно выбрать более одного значения фильтра, удерживайте нажатой клавишу CTRL. Большинство фильтров поддерживает множественный выбор.

### <a name="reset-filter-to-default"></a>Восстановление значений фильтра по умолчанию

Если вы хотите отменить все изменения, которые вы внесли в фильтры, выберите команду **Вернуться к значениям по умолчанию** в верхней строке меню.  Фильтры вернутся в исходное состояние, заданное создателем отчета.

![Снимок экрана: вернуться к значениям по умолчанию.](media/end-user-report-filter/power-bi-reset-icon.png)

### <a name="clear-a-filter"></a>Очистка фильтра

Чтобы сбросить фильтр до "(Все)", очистите его, выбрав значок ластика рядом с именем фильтра.

![Снимок значка ластика.](media/end-user-report-filter/power-bi-eraser.png)
  
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