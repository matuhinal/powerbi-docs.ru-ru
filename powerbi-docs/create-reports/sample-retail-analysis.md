---
title: 'Пример "Анализ розничной торговли" для Power BI: Узнайте о возможностях'
description: 'Пример "Анализ розничной торговли" для Power BI: Узнайте о возможностях'
author: maggiesMSFT
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/02/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 373e5bfe3d52bf319ad68d766f268518a167012f
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83349087"
---
# <a name="retail-analysis-sample-for-power-bi-take-a-tour"></a>Пример "Анализ розничной торговли" для Power BI: Узнайте о возможностях

Этот пример "Анализ розничной торговли" содержит панель мониторинга, отчет и набор данных для изучения сведений о розничных продажах товаров по нескольким магазинам и районам. Эффективность деятельности за текущий и прошлый год сравнивается в метриках по продажам, единицам продукции, валовой прибыли, расхождениям, а также анализу новых магазинов. 

![Пример панели мониторинга "Анализ розничной торговли".](media/sample-retail-analysis/retail1.png)

Этот пример входит в серию, демонстрирующую, как использовать Power BI с бизнес-данными, отчетами и панелями мониторинга. Он создан на основе реальных данных [obviEnce](http://www.obvience.com/), которые были анонимизированы. Данные доступны в нескольких форматах: пакет содержимого, PBIX-файл Power BI Desktop или книга Excel. См. сведения в статье [Примеры данных, доступные для использования в службе Power BI](sample-datasets.md). 

В этом руководстве описано, как использовать пример пакета содержимого "Анализ розничной торговли" в службе Power BI. Так как в Power BI Desktop и службе возможности работы с отчетами практически не отличаются, этот же пример PBIX-файла можно использовать и в Power BI Desktop. 

Вам не требуется лицензия Power BI для просмотра примеров в Power BI Desktop. Если у вас нет лицензии Power BI Pro, можно сохранить пример в личную рабочую область в службе Power BI. 

## <a name="get-the-sample"></a>Получение примера

 Прежде чем использовать пример, необходимо скачать его как [пакет содержимого](#get-the-content-pack-for-this-sample), [PBIX-файл](#get-the-pbix-file-for-this-sample) или [книгу Excel](#get-the-excel-workbook-for-this-sample).

### <a name="get-the-content-pack-for-this-sample"></a>Получение пакета содержимого для этого примера

1. Откройте службу Power BI (app.powerbi.com), войдите в систему и откройте рабочую область, где хотите сохранить пример. 

    Если у вас нет лицензии Power BI Pro, можно сохранить пример в личной рабочей области.

2. В левом нижнем углу выберите **Получить данные**.

    ![Выбор "Получить данные"](media/sample-datasets/power-bi-get-data.png)
3. На странице **Получение данных** выберите **Примеры**.
   
4. Выберите **Анализ розничной торговли — пример** и щелкните **Подключиться**.  
  
   ![Подключение к примеру](media/sample-retail-analysis/retail16.png)
   
5. Power BI импортирует пакет содержимого и добавляет новую панель мониторинга, отчет и набор данных в текущую рабочую область.
   
   ![Строка примера "Анализ розничной торговли"](media/sample-retail-analysis/retail-entry.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Получение PBIX-файла для этого примера

Кроме того, вы можете загрузить пример "Анализ розничной торговли" в виде [PBIX-файла](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix), который предназначен для работы с Power BI Desktop. 

### <a name="get-the-excel-workbook-for-this-sample"></a>Получение книги Excel для этого примера

Если вы хотите просмотреть источник данных для этого примера, он также доступен в виде [книги Excel](https://go.microsoft.com/fwlink/?LinkId=529778). Книга содержит листы Power View, которые можно просматривать и изменять. Чтобы просмотреть необработанные данные, включите надстройки анализа данных и выберите **Power Pivot > Управление**. Чтобы включить надстройки Power View и Power Pivot, перейдите к разделу [Просмотр примеров Excel непосредственно из Excel](sample-datasets.md#explore-excel-samples-inside-excel).

## <a name="start-on-the-dashboard-and-open-the-report"></a>Запуск на панели мониторинга и открытие отчета

1. В рабочей области с примером откройте вкладку **Панель мониторинга** и выберите панель мониторинга **Анализ розничной торговли — пример**. 
2. На этой панели мониторинга откройте вкладку **Всего магазинов — новые и существующие магазины**. Откроется страница **Обзор продаж в магазине** в отчете "Анализ розничной торговли". 

   ![плитка "Всего магазинов"](media/sample-retail-analysis/retail-analysis-7.png)  

   На этой странице отчета вы увидите, что работают 104 магазина, 10 из которых являются новыми. У нас есть две сети: Fashions Direct и Lindseys. В среднем магазины Fashions Direct крупнее.
3. На круговой диаграмме **Продажи за этот год по сетям магазинов** выберите сектор **Fashions Direct**.

   ![Продажи за этот год по сетям магазинов](media/sample-retail-analysis/retail3.png)  

   Обратите внимание на результат на пузырьковой диаграмме **Общее отклонение продаж, %** .

   ![Диаграмма "Общее отклонение продаж, %"](media/sample-retail-analysis/pbi_sample_retanlbubbles.png)  

   Район **FD-01** демонстрирует наибольший **средний объем продаж на квадратный метр**, а FD-02 имеет наименьшее **общее отклонение продаж** по сравнению с предыдущим годом. FD-03 и FD-04 имеют наихудшие показатели.
4. Выбирайте отдельные пузырьки или другие диаграммы, чтобы определить влияние выбранных вами параметров
5. На панели навигации сверху выберите пример **Анализ розничной торговли**, чтобы вернуться к панели мониторинга.

   ![Панель навигации](media/sample-retail-analysis/power-bi-breadcrumbs.png)
6. На панели мониторинга выберите плитку **Продажи за этот год — новые и существующие магазины** (аналогично вводу *Продажи за этот год* в поле вопроса).

   ![Плитка "Продажи за этот год"](media/sample-retail-analysis/pbi_sample_retanlthisyrsales.png)

   Отобразятся результаты функции "Вопросы и ответы":

   ![Вопросы и ответы, продажи за этот год](media/sample-retail-analysis/retail7.png)

## <a name="review-a-tile-created-with-power-bi-qa"></a>Просмотр плитки, созданной с помощью поля "Вопросы и ответы" Power BI
Давайте запросим более конкретные сведения.

1. Немного измените вопрос: _продажи за этот год **по районам**_ . Просмотрите результаты — Служба автоматически помещает ответ в линейчатую диаграмму и предлагает дополнительные фразы:

   ![Продажи за этот год в службе "Вопросы и ответы"](media/sample-retail-analysis/retail8.png)
2. Теперь измените вопрос следующим образом: _продажи за этот год **по почтовому индексу и сети**_ .

   Обратите внимание, как по мере ввода вопроса Power BI изменяет отображение, предлагая подходящую диаграмму.
3. Поэкспериментируйте с другими вопросами и посмотрите, какие результаты можно получить.
4. Когда все будет готово, возвращайтесь к панели мониторинга.

## <a name="dive-deeper-into-the-data"></a>Подробные сведения о данных
Теперь давайте рассмотрим все более подробно, определив производительность по районам.

1. На этой панели мониторинга выберите плитку **Продажи за этот год, продажи за прошлый год**. Откроется страница **Продажи района по месяцам** выбранного отчета.

   ![Плитка "Продажи за этот год, продажи за прошлый год"](media/sample-retail-analysis/pbi_sample_retanlareacht.png)

   Обратите внимание на значительное расхождение с прошлым годом на диаграмме **Суммарное отклонение продаж в % по финансовому месяцу**, где особенно неудачными месяцами являются январь, апрель и июль.

   ![Диаграмма "Суммарное отклонение продаж в % по финансовому месяцу"](media/sample-retail-analysis/pbi_sample_retanlsalesvarcol.png)

   Давайте посмотрим, сможем ли мы выявить источник проблем.
2. На пузырьковой диаграмме щелкните пузырек **020-Mens**.

   ![Выбор 020-Mens](media/sample-retail-analysis/retail11.png)  

   Обратите внимание, что категория мужских товаров в апреле не характеризуется спадом, как продажи в целом, но январь и июль остались проблемными месяцами.
1. Теперь щелкните пузырек **010-Womens**.

   ![Выбор 010-Womens](media/sample-retail-analysis/retail12.png)

   Обратите внимание, что по женским товарам во все месяцы показатели значительно ниже общих по продажам, а также почти всегда ниже аналогичных показателей за предыдущий год.
1. Выберите пузырек еще раз, чтобы очистить фильтр.

## <a name="try-out-the-slicer"></a>Попробуйте использовать срез
Давайте посмотрим, насколько эффективно осуществляются продажи по районам.

1. Щелкните **Allan Guinot** в срезе **Менеджер округа** вверху слева.

   ![Выбор Allan Guinot](media/sample-retail-analysis/retail13.png)

   Обратите внимание, что в марте и июне этот район перекрыл показатели прошлого года.
2. Сохраняя выбранным значение **Allan Guinot**, выберите пузырек **Womens-10** на пузырьковой диаграмме.

   ![Выбор Allan Guinot и Womens-10](media/sample-retail-analysis/power-bi-allan.png)

   Обратите внимание, что в категории Womens-10 этот район не смог повторить прошлогодний объем продаж.
3. Изучите результаты по другим региональным менеджерам и категориям. Какую дополнительную информацию вы сможете найти?
4. Завершив анализ, возвращайтесь на панель мониторинга.

## <a name="what-the-data-says-about-sales-growth-this-year"></a>Что сообщают данные о росте продаж в этом году
Последней мы изучим такую область данных, как рост путем открытия новых магазинов в этом году.

1. Щелкните плитку **Магазины, открытые в этом году по месяцам открытия и сетям**. Откроется страница **Анализ новых магазинов** в выбранном отчете.

   ![Страница "Анализ новых магазинов"](media/sample-retail-analysis/retail15.png)

   На этой плитке видно, что в этом году открыто больше магазинов Fashions Direct, чем магазинов Lindseys.
2. Просмотрите диаграмму **Продажи на единицу площади по имени**:

   ![Диаграмма "Продажи на единицу площади по имени"](media/sample-retail-analysis/retail14.png)

    Обратите внимание на различия в среднем уровне продаж на единицу площади у новых магазинов.
3. Выберите элемент **Fashions Direct** в легенде к диаграмме **Число открытых магазинов по месяцам открытия и сетям** вверху справа. Обратите внимание, что для одной и той же сети лучший магазин (Winchester Fashions Direct) значительно обходит по показателям худший магазин (Cincinnati 2 Fashions Direct) — 21,22 против 12,86 долл. США соответственно.

   ![Выбор Fashions Direct](media/sample-retail-analysis/power-bi-lindseys.png)
4. Щелкните **Winchester Fashions Direct** в срезе **Имя** и изучите диаграмму. Первый отчет с суммами продаж поступил в феврале.
5. Щелкните **Cincinnati 2 Fashions Direct** на том же срезе, и вы увидите на графике, что этот магазин был открыт в июне и, похоже, имеет самые низкие показатели.
6. Изучите данные, щелкая другие панели, графики и пузырьки на всех диаграммах, и попробуйте обнаружить ценные сведения.

## <a name="next-steps-connect-to-your-data"></a>Дальнейшие действия: Подключение к данным
В этой среде можно свободно экспериментировать, так как сохранять изменения не требуется. Однако если изменения сохраняются, всегда можно выбрать функцию **Получить данные** для получения новой копии этого примера.

Мы надеемся, что из этого обзора вы узнали, как с помощью панелей мониторинга, вопросов и ответов, а также отчетов Power BI можно получить представление о данных из примера. Теперь ваша очередь — выполните подключение к собственным данным. С помощью Power BI можно подключаться ко многим типам источников данных. Дополнительные сведения см. в руководстве по [началу работы со службой Power BI](../fundamentals/service-get-started.md).