---
title: Добавление гиперссылок (URL-адресов) в таблицу
description: Из этого раздела вы узнаете, как добавлять гиперссылки (URL-адреса) в таблицу. Power BI Desktop можно использовать для добавления гиперссылок (URL-адресов) в таблицу или матрицу. Затем вы можете с помощью Power BI Desktop или службы Power BI добавить созданные гиперссылки в таблицы отчета и матрицы.
author: maggiesMSFT
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/29/2019
ms.author: maggies
LocalizationGroup: Visualizations
ms.openlocfilehash: e8cad7035e752e5e344d78a22ad5fd8ea0a072ad
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2020
ms.locfileid: "73874503"
---
# <a name="add-hyperlinks-urls-to-a-table"></a>Добавление гиперссылок (URL-адресов) в таблицу
Из этого раздела вы узнаете, как добавлять гиперссылки (URL-адреса) в таблицу. Power BI Desktop можно использовать для добавления гиперссылок (URL-адресов) в таблицу или матрицу. Затем вы можете с помощью Power BI Desktop или службы Power BI добавить созданные гиперссылки в таблицы отчета и матрицы. 

![Таблицы с гиперссылками](media/power-bi-hyperlinks-in-tables/hyperlinkedtable.png)

> [!NOTE]
> Вы можете оперативно создать гиперссылки на [плитках](service-dashboard-edit-tile.md) и в [текстовых полях панелей мониторинга](service-dashboard-add-widget.md) с помощью службы Power BI. Вы можете оперативно создать гиперссылки в [текстовых полях в отчетах](service-add-hyperlink-to-text-box.md) с помощью службы Power BI и Power BI Desktop.
> 

## <a name="to-create-a-hyperlink-in-a-table-or-matrix-using-power-bi-desktop"></a>Создание гиперссылки в таблице или матрице с использованием Power BI Desktop
Вы можете создать гиперссылки в таблицах и матрицах, используя Power BI Desktop, но не службу Power BI. Кроме того, можно создавать гиперссылки в Excel Power Pivot перед импортом книги в Power BI. Оба способа описаны ниже.

## <a name="create-a-table-or-matrix-hyperlink-in-power-bi-desktop"></a>Создание гиперссылки в таблице или матрице в Power BI Desktop
Процедура добавления гиперссылки зависит от того, были ли данные импортированы или подключены с помощью DirectQuery. Оба сценария описаны ниже.

### <a name="for-data-imported-into-power-bi"></a>Для данных, импортированных в Power BI
1. Если гиперссылка еще не существует как поле в наборе данных, добавьте ее как [пользовательский столбец](desktop-common-query-tasks.md) с помощью приложения Power BI Desktop.
2. В представлении данных выделите столбец, а затем на вкладке **Моделирование** выберите раскрывающийся список **Категория данных**.
   
    ![Раскрывающийся список категорий данных](media/power-bi-hyperlinks-in-tables/pbi_data_category.png)
3. Выберите **URL-адрес веб-сайта**.
4. Переключитесь в представление отчета и создайте таблицу или матрицу, используя поле с категорией "URL-адрес веб-сайта". Гиперссылки будут выделены синим цветом и подчеркиванием.

    ![Синие и подчеркнутые ссылки](media/power-bi-hyperlinks-in-tables/power-bi-table-with-hyperlinks2.png)

    > [!NOTE]
    > URL-адреса должны начинаться с определенных префиксов. Полный список см. в разделе [Рекомендации и устранение неполадок](#considerations-and-troubleshooting).
    >
   
1. Вместо длинного URL-адреса в таблице можно отобразить значок гиперссылки  ![Значок гиперссылки](media/power-bi-hyperlinks-in-tables/power-bi-hyperlink-icon.png) . Обратите внимание, что значки в матрицах невозможно отобразить.
   
    Выберите диаграмму, чтобы сделать ее активной.

    Выбор значка форматирования ![Значок с изображением валика](media/power-bi-hyperlinks-in-tables/power-bi-paintroller.png) для открытия вкладки "Форматирование".

    Разверните узел **Значения**, найдите **значок URL-адреса** и установите для него значение **Вкл.**

    ![Включение значка URL-адреса](media/power-bi-hyperlinks-in-tables/power-bi-url-icon-on.png)

1. (Необязательно.) [Опубликуйте отчет из Power BI Desktop в службе Power BI](/learn/modules/publish-share-power-bi/2-publish-reports) и откройте его в этой службе. Гиперссылки там также будут работать.

### <a name="for-data-connected-with-directquery"></a>Для данных, подключенных с помощью DirectQuery
В режиме DirectQuery нельзя создать новый столбец.  Но если данные уже содержат URL-адреса, то их можно превратить в гиперссылки.

1. В представлении отчета создайте таблицу с помощью поля, которое содержит URL-адреса.
2. Выделите столбец, а затем на вкладке **Моделирование** выберите раскрывающийся список **Категория данных**.
3. Выберите **URL-адрес веб-сайта**. Гиперссылки будут выделены синим цветом и подчеркиванием.
4. (Необязательно.) [Опубликуйте отчет из Power BI Desktop в службе Power BI](/learn/modules/publish-share-power-bi/2-publish-reports) и откройте его в этой службе. Гиперссылки там также будут работать.

## <a name="create-a-table-or-matrix-hyperlink-in-excel-power-pivot"></a>Создание гиперссылки в таблице или матрице в Excel Power Pivot
Другим способом добавления гиперссылок в таблицы и матрицы Power BI является создание гиперссылок в наборе данных перед подключением к набору данных и его импортом из Power BI. В этом примере используется книга Excel.

1. Откройте книгу в Excel.
2. Перейдите на вкладку **PowerPivot** , а затем выберите **Управление**.
   
   ![Открытие PowerPivot в Excel](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot2.png)
1. В открывшемся окне Power Pivot выберите вкладку **Дополнительно**.
   
   ![Вкладка "Дополнительно" в PowerPivot"](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot3.png)
4. Поместите курсор в столбец, содержащий URL-адреса, которые вы хотите преобразовать в гиперссылки в таблицах Power BI.
   
   > [!NOTE]
   > URL-адреса должны начинаться с определенных префиксов. Полный список см. в разделе [Рекомендации и устранение неполадок](#considerations-and-troubleshooting).
   > 
   
5. В группе **Свойства отчетов** щелкните раскрывающийся список **Категория данных** и выберите **URL-адрес веб-сайта**. 
   
   ![Раскрывающийся список категорий данных в Excel](media/power-bi-hyperlinks-in-tables/createhyperlinksnew.png)

6. В службе Power BI или в Power BI Desktop подключитесь к этой книге или импортируйте ее.
7. Создайте визуализацию таблицы, содержащую поле URL-адреса.
   
   ![Создание таблицы в Power BI с полем URL-адреса](media/power-bi-hyperlinks-in-tables/hyperlinksintables.gif)

## <a name="considerations-and-troubleshooting"></a>Рекомендации и устранение неполадок

Значение URL-адреса может начинаться со следующих последовательностей:
- http
- https
- -mailto
- file
- ftp
- news
- telnet

Вопрос. Можно ли использовать настраиваемый URL-адрес в качестве гиперссылки в таблице или матрице?    
Ответ. Нет. Можно использовать значок ссылки. Если вам нужен настраиваемый текст для гиперссылок и ваш список URL-адресов короткий, попробуйте использовать текстовое поле.


## <a name="next-steps"></a>Дальнейшие действия
[Визуализации в отчетах Power BI](visuals/power-bi-report-visualizations.md)

[Основные понятия для разработчиков в службе Power BI](service-basic-concepts.md)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](https://community.powerbi.com/)

