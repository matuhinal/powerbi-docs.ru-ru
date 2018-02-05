---
title: "Руководство. Анализ данных о продажах из Excel и веб-канала OData в Power BI Desktop"
description: "Учебник. Анализ данных о продажах из Excel и веб-канала OData"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 0723b3a7155626f875044fa813a522ef6d4923df
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2018
---
# <a name="tutorial-analyzing-sales-data-from-excel-and-an-odata-feed"></a>Учебник. Анализ данных о продажах из Excel и веб-канала OData
С помощью **Power BI Desktop** можно подключаться к различным источникам данных, объединять и обрабатывать их способами, которые упрощают создание интересных, привлекательных объектов анализа данных и визуализаций. В этом учебнике вы узнаете, как объединить данные из двух источников данных. 

Часто данные распределены по нескольким источникам, например сведения о продукте находятся в одной базе данных, а данные о продажах — в другой. В число методов, о которых вы узнаете в этом документе, входят книга Excel и веб-канал OData. Они также могут применяться к другим источникам данных, таких как запросы SQL Server, CSV-файлы, или любому источнику данных в Power BI Desktop.

В этом учебнике вы импортируете данные из Excel (они включают сведения о продукте) и из веб-канала OData (который содержит данные о заказах). Вы выполните преобразование и обработку, а также объедините данные из обоих источников для создания отчета **Общий объем продаж по продуктам и годам** , который содержит интерактивные визуализации. 

Вот как выглядит окончательный отчет:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

Чтобы выполнять действия, описанные в этом учебнике, потребуется книга Products, которую можно скачать**:**[ щелкните ](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)[здесь](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)[ для загрузки](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**[Products.xlsx](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**[.](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)

В диалоговом окне **Сохранение документа** присвойте файлу имя **Products.xlsx**.

## <a name="task-1-get-product-data-from-an-excel-workbook"></a>Задача 1. Получение данных о продуктах из книги Excel
В этой задаче вы импортируете продукты из файла Products.xlsx в Power BI Desktop.

### <a name="step-1-connect-to-an-excel-workbook"></a>Шаг 1. Подключение к книге Excel
1. Запустите Power BI Desktop.
2. На вкладке ленты "Главная" выберите **Получить данные**. Excel — один из **наиболее распространенных** подключений к данным, поэтому его можно выбрать непосредственно из меню **Получение данных** .
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
3. При нажатии кнопки "Получить данные" можно также выбрать **Файл \> Excel** и **Подключить**.
4. В диалоговом окне **Открытие файла** выберите файл **Products.xlsx** .
5. В области **Навигатор** выберите таблицу **Products** , а затем нажмите кнопку **Изменить**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)

### <a name="step-2-remove-other-columns-to-only-display-columns-of-interest"></a>Шаг 2. Удаление других столбцов для отображения только нужных столбцов
На этом шаге вы удалите все столбцы, кроме **ProductID**, **ProductName**, **UnitsInStock** и **QuantityPerUnit**. В Power BI Desktop выполнить эту задачу можно несколькими способами. Например, многие кнопки на ленте можно заменить контекстным меню в столбце или ячейке.

В состав Power BI Desktop входит редактор запросов, в котором выполняется обработка и преобразование подключений к данным. Редактор запросов открывается автоматически при выборе **Изменить** на панели **Навигатор**. Редактор запросов также можно открыть, выбрав **Изменить запросы** на вкладке ленты **Главная** в Power BI Desktop. В редакторе запросов выполняются следующие действия.

1. В редакторе запросов выберите столбцы **ProductID**, **ProductName**, **QuantityPerUnit**и **UnitsInStock** (используйте сочетание **CTRL + щелчок** , чтобы выбрать несколько столбцов, или **SHIFT + щелчок** , чтобы выбрать столбцы, которые находятся рядом друг с другом).
2. На ленте выберите **Удалить столбцы** \> **Удалить другие столбцы** или щелкните правой кнопкой мыши заголовок столбца и выберите команду **Удалить другие столбцы**.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_removeothercolumns.png)

### <a name="step-3-change-the-data-type-of-the-unitsinstock-column"></a>Шаг 3. Изменение типа данных столбца UnitsInStock
Когда редактор запросов подключается к данным, он просматривает каждое поле и определяет наилучший тип данных. В книге Excel продукты на складе всегда будут целым числом, поэтому на данном шаге вы подтверждаете, что столбец **UnitsInStock** имеет тип данных "Целое число".

1. Выберите столбец **UnitsInStock** .
2. Нажмите кнопку раскрывающегося списка **Тип данных** на вкладке ленты **Главная** .
3. В раскрывающемся списке выберите **Целое число** в качестве типа данных (кнопка **Тип данных:** также отображает тип данных для текущего выделения).
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_wholenumber.png)      

### <a name="power-bi-desktop-steps-created"></a>Созданные действия Power BI Desktop
При выполнении действий запроса в редакторе запросов создаются действия запроса, которые отображаются в области **Параметры запроса** в списке **Примененные действия**. У каждого действия запроса есть соответствующая формула, также известная как язык "M". Подробнее о языке формул "M" см. в разделе [Дополнительные сведения о формулах Power BI](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f).

| Задача | Действие запроса | Формула |
| --- | --- | --- |
| Подключение к книге Excel |Источник |Source{[Name="Products"]}[Data] |
| Повышение уровня первой строки до заголовков столбцов таблицы |FirstRowAsHeader |[Table.PromoteHeaders](https://support.office.com/Article/TablePromoteHeaders-b8eaeb95-042a-42e1-9164-6d3c646acadc "Table.PromoteHeaders") <br /> (Products) |
| Удаление других столбцов для отображения только нужных столбцов |RemovedOtherColumns |[Table.SelectColumns](https://support.office.com/Article/TableSelectColumns-20bb9e28-9fd3-4cd2-a21b-97972c82ec22 "Table.SelectColumns")  <br />(FirstRowAsHeader,{"ProductID", "ProductName", "QuantityPerUnit", "UnitsInStock"}) |
| Изменение типа данных |Измененный тип |Table.TransformColumnTypes(\#"Удалены другие столбцы",{{"UnitsInStock", Int64.Type}}) |

## <a name="task-2-import-order-data-from-an-odata-feed"></a>Задача 2. Импорт данных о заказах из веб-канала OData
В этой задаче предстоит внести в данные о заказах. Этот шаг представляет подключение к системе продаж. Данные импортируются в Power BI Desktop из примера веб-канала OData для Northwind по следующему URL-адресу, который можно скопировать (и затем вставить) в следующие действия: <http://services.odata.org/V3/Northwind/Northwind.svc/>. 

### <a name="step-1-connect-to-an-odata-feed"></a>Шаг 1. Подключение к веб-каналу OData
1. На вкладке **Главная** ленты в редакторе запросов выберите **Получение данных**.
2. Перейдите к источнику данных **Веб-канал OData** .
3. В диалоговом окне **Веб-канал OData** вставьте **URL-адрес** для веб-канала OData Northwind.
4. Нажмите кнопку **ОК**.
5. В области **Навигатор** выберите таблицу **Заказы** , а затем нажмите кнопку **Изменить**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_odatafeed.png)

>[!NOTE]
>Для предварительного просмотра можно щелкнуть имя таблицы, не устанавливая флажок.

### <a name="step-2-expand-the-orderdetails-table"></a>Шаг 2. Развертывание таблицы Order\_Details
Таблица **Orders** (Заказы), к которой вы подключились, содержит ссылку на таблицу **Details**. В ней представлены отдельные продукты, включенные в каждый заказ. При подключении к источникам данных с несколькими таблицами (например, к реляционной базе данных) эти ссылки можно использовать для построения запроса. 

На этом шаге вы развернете таблицу **Order\_Details**, связанную с таблицей **Orders**, чтобы объединить столбцы **ProductID**, **UnitPrice** и **Quantity** из таблицы **Order\_Details** в таблицу **Orders**. Вот представление данных в этих таблицах.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/orderdetails.png)

Операция **Развернуть** объединяет столбцы из связанной таблицы с таблицей субъекта. При выполнении запроса строки из связанной таблицы (**Order\_Details**) объединяются со строками из таблицы субъекта (**Orders**).

После развертывания таблицы **Order\_Details** в таблицу **Orders** добавляются три новых столбца и дополнительные строки, по одной для каждой строки во вложенной или связанной таблице.

1. В **представлении запроса** перейдите к столбцу **Order\_Details**.
2. В столбце **Order\_Details** щелкните значок "Развернуть" (![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)).
3. В раскрывающемся списке **Развернуть** :
   1. Щелкните **(Выбрать все столбцы)** , чтобы отменить выбор всех столбцов.
   2. Щелкните **ProductID**, **UnitPrice**и **Quantity**.
   3. Нажмите кнопку **ОК**.
      ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)

### <a name="step-3-remove-other-columns-to-only-display-columns-of-interest"></a>Шаг 3. Удаление других столбцов для отображения только нужных столбцов
На этом шаге вы удалите все столбцы, кроме **OrderDate, ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** и **Order\_Details.Quantity**. В предыдущей задаче вы использовали операцию **Удалить другие столбцы**. Для этой задачи вы удалите выбранные столбцы.

1. В **представлении запроса** выберите все столбцы, выполнив действия a. и b.:
   1. Щелкните первый столбец (**OrderID**).
   2. Удерживая клавишу SHIFT, щелкните последний столбец (**Shipper**).
   3. Теперь, когда выбраны все столбцы, удерживайте нажатой клавишу CTRL и щелкайте мышью, чтобы отменить выбор следующих столбцов: **OrderDate**, **ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** и **Order\_Details.Quantity**.
2. Теперь, когда выбраны только столбцы, которые требуется удалить, щелкните правой кнопкой мыши заголовок любого выбранного столбца и выберите команду **Удалить столбцы**.

### <a name="step-4-calculate-the-line-total-for-each-orderdetails-row"></a>Шаг 4. Вычисление итога для каждой строки Order\_Details
Power BI Desktop позволяет создавать вычисления на основе импортируемых столбцов для обогащения данных, к которым вы подключены. На этом шаге вы создадите **настраиваемый столбец** для вычисления итогов для каждой строки **Order\_Details**.

Вычисление итога для каждой строки **Order\_Details**

1. На вкладке ленты **Добавить столбец** щелкните **Добавить** **настраиваемый столбец**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. В диалоговом окне **Добавление настраиваемого столбца** в текстовом поле **Формула настраиваемого столбца** введите **[Order\_Details.UnitPrice] \* [Order\_Details.Quantity]**.
3. В текстовом поле **Имя нового столбца** введите **LineTotal**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)
4. Нажмите кнопку **ОК**.

### <a name="step-5-set-the-datatype-of-the-linetotal-field"></a>Шаг 5. Установка типа данных поля LineTotal
1. Щелкните правой кнопкой мыши столбец **LineTotal** .
2. Выберите команду **Изменить тип** и выберите **Десятичное число**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

### <a name="step-6-rename-and-reorder-columns-in-the-query"></a>Шаг 6. Переименование и изменение порядка столбцов в запросе
На этом шаге вы завершите работу над моделью для упрощения создания отчетов, переименовав последние столбцы и изменив их порядок.

1. В **редакторе запросов**перетащите столбец **LineTotal** влево (после столбца **ShipCountry**).
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
2. Удалите префикс *Order\_Details*. из столбцов **Order\_Details.ProductID**, **Order\_Details.UnitPrice** и **Order\_Details.Quantity**, дважды щелкнув заголовок каждого столбца и удалив текст из имени столбца.

### <a name="power-bi-desktop-steps-created"></a>Созданные действия Power BI Desktop
При выполнении действий запроса в редакторе запросов создаются действия запроса, которые отображаются в области **Параметры запроса** в списке **Примененные действия**. У каждого действия запроса есть соответствующая формула Power Query, также известная как язык "M". Подробнее о языке формул "M" см. в разделе [Дополнительные сведения о формулах Power BI](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f "Дополнительные сведения о формулах Power BI").

| Задача | Действие запроса | Формула |
| --- | --- | --- |
| Подключение к веб-каналу OData |Источник |Source{[Name="Orders"]}[Data] |
| Развертывание таблицы Order\_Details |Развертывание Order\_Details |[Table.ExpandTableColumn](https://support.office.com/Article/TableExpandTableColumn-54903f25-75a2-4a44-a9a3-52a9d895ee98 "Table.ExpandTableColumn") <br /> (Orders, "Order\_Details", {"ProductID", "UnitPrice", "Quantity"}, {"Order\_Details.ProductID", "Order\_Details.UnitPrice", "Order\_Details.Quantity"}) |
| Удаление других столбцов для отображения только нужных столбцов |RemovedColumns |[Table.RemoveColumns](https://support.office.com/Article/TableRemoveColumns-6265190e-2f58-4300-85b8-df88fc1a67d3 "Table.RemoveColumns") <br />(\#"Порядок развертывания\_Details",{"OrderID", "CustomerID", "EmployeeID", "RequiredDate", "ShippedDate", "ShipVia", "Freight", "ShipName", "ShipAddress", "ShipCity", "ShipRegion", "ShipPostalCode", "ShipCountry", "Customer", "Employee", "Shipper"}) |
| Вычисление итога для каждой строки Order\_Details |InsertedColumn |[Table.AddColumn](https://support.office.com/Article/TableAddColumn-6c64d0a5-9654-4d15-bfb6-9cc380aaf3c0 "Table.AddColumn") <br /> (RemovedColumns, "Custom", each [Order\_Details.UnitPrice] \* [Order\_Details.Quantity]) |

## <a name="task-3-combine-the-products-and-total-sales-queries"></a>Задача 3. Объединение запросов продуктов и общего объема продаж
Power BI Desktop не требует объединения запросов для формирования отчетов для них. Вместо этого можно создать **связи** между наборами данных. Эти связи могут создаваться в любом столбце, общем для наборов данных. Дополнительные сведения см. в разделе [Создание связей и управление ими](desktop-create-and-manage-relationships.md).

В этом учебнике у нас есть данные о заказах и продуктах с общим полем ProductID, поэтому необходимо убедиться, что между ними в модели, используемой с Power BI Desktop, существует связь. Просто укажите в Power BI Desktop, что столбцы из каждой таблицы, связаны (т. е. столбцы имеют одинаковые значения). Power BI Desktop определяет направление и количество элементов связи для вас. В некоторых случаях Power BI Desktop обнаруживает связь автоматически.

В этой задаче вы подтверждаете наличие связи в Power BI Desktop между запросами **Продукты** и **Общий объем продаж** .

### <a name="step-1-confirm-the-relationship-between-products-and-total-sales"></a>Шаг 1. Подтверждение связи между запросами "Продукты" и "Общий объем продаж"
1. Сначала необходимо загрузить модель, созданную в редакторе запросов, в Power BI Desktop. На вкладке **Главная** ленты в редакторе запросов выберите **Закрыть и загрузить**.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Power BI Desktop загружает данные из двух запросов.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)      
3. После загрузки данных нажмите кнопку **Управление связями** на вкладке **Главная** ленты.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
4. Нажмите кнопку **Создать...** .
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
5. Если предпринимается попытка создания связи, мы видим, что она уже существует! Как показано в диалоговом окне **Создание связи** (затененные столбцы), поля **ProductsID** в каждом запросе уже имеют установленную связь.
   
    ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)
6. Выберите **Отмена**, а затем выберите представление **Связь** в Power BI Desktop.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
7. Мы видим следующую визуализацию связи между запросами.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)
8. Если дважды щелкнуть стрелку на линии, соединяющейся с запросами, откроется диалоговое окно **Изменить связь** .
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)
9. Вносить изменения не нужно, поэтому мы просто выберем **Отмена** , чтобы закрыть диалоговое окно **Изменение связи** .

## <a name="task-4-build-visuals-using-your-data"></a>Задача 4. Создание визуальных объектов с помощью данных
Power BI Desktop позволяет создавать различные визуализации для получения полезных сведений из данных. Вы можете создавать отчеты из нескольких страниц, каждая из которых может содержать несколько визуальных элементов. Вы можете взаимодействовать с визуализациями для анализа и понимания данных. Подробнее об изменении отчетов см. в разделе [Редактирование отчета](service-interact-with-a-report-in-editing-view.md).

В этой задаче вы создаете отчет, основанный на ранее загруженных данных. Вы используете область полей для выбора столбцов, на основе которых будут созданы визуализации.

### <a name="step-1-create-charts-showing-units-in-stock-by-product-and-total-sales-by-year"></a>Шаг 1. Создание диаграмм, показывающие число единиц на складе по продуктам и общий объем продаж по годам
Перетащите **UnitsInStock** из области полей (она расположена вдоль правой части экрана) на пустое место на холсте. Создается визуализация таблицы. Затем перетащите ProductName в поле "Ось", расположенное в нижней половине области "Визуализации". Затем выберите **Сортировать по \> UnitsInStock** с помощью элементов в верхнем правом углу визуализации.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

Перетащите **OrderDate** на холст под первую диаграмму, затем перетащите LineTotal (вновь из области полей) на визуальный элемент, а затем выберите график. Создается следующая визуализация.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png)

 Затем перетащите **ShipCountry** в область на холсте вверху справа. Так как вы выбрали географическое поле, автоматически была создана карта. Теперь перетащите **LineTotal** в поле **Значения**. Круги на карте для каждой страны теперь имеют относительный размер для **LineTotal** для заказов, поставляемых в эту страну.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

### <a name="step-2-interact-with-your-report-visuals-to-analyze-further"></a>Шаг 2. Взаимодействие с визуальными элементами отчета для дальнейшего анализа
Power BI Desktop позволяет взаимодействовать с визуальными элементами, которые перекрестно выделяют и фильтруют друг друга, для поиска тенденций. Дополнительные сведения см. в разделе [Фильтрация и выделение в отчетах](power-bi-reports-filters-and-highlighting.md).

1. Щелкните голубой круг в центре **Канады**. Обратите внимание, что другие визуальные элементы отфильтрованы для отображения значений "Склад" (**ShipCountry**) и "Всего заказов" (**LineTotal**) только для Канады.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="complete-sales-analysis-report"></a>Полный отчет анализа продаж
После выполнения этих действий вы получите отчет о продажах, в котором объединяются данные из файла Products.xlsx и веб-канала OData Northwind. В отчете отображаются визуальные элементы, которые помогают анализировать сведения о продажах из разных стран. Вы можете скачать полный файл Power BI Desktop для этого учебника [здесь](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Sales_Data.pbix).

## <a name="next-steps"></a>Дальнейшие действия
* [Прочитайте другие руководства по Power BI Desktop.](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Посмотрите видеоматериалы по Power BI Desktop.](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Посетите форум Power BI.](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Прочитайте блог, посвященный Power BI.](http://go.microsoft.com/fwlink/?LinkID=519327)


