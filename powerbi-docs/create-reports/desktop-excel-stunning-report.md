---
title: Руководство. Превращение книги Excel в привлекательный отчет в Power BI Desktop
description: В этом учебнике показано, как быстро создать привлекательный отчет из книги Excel.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 10/13/2020
ms.author: maggies
LocalizationGroup: Data from files
ms.openlocfilehash: 40c874e9178ffc3586c2dde83f32260bdb86bfad
ms.sourcegitcommit: eab5a02520c421a57019595c03e9ecfdb41d52ad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "92256939"
---
# <a name="tutorial-from-excel-workbook-to-stunning-report-in-power-bi-desktop"></a>Руководство. Превращение книги Excel в привлекательный отчет в Power BI Desktop

В этом руководстве вы создадите привлекательный отчет за 20 минут! 

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-excel-formatted-report.png" alt-text="Снимок экрана: готовый отчет Power BI"::: 

Ваш руководитель требует отчет по последним показателям продаж. Требуются общие сведения о следующем: 

- В каком месяце и году прибыль была наибольшей? 
- Где у компании наблюдается наибольший успех (по странам)? 
- В какой продукт и сегмент компании следует инвестировать? 

Используя наш пример финансовой книги, мы можем быстро создать требуемый отчет. Вот как выглядит окончательный отчет. Давайте начнем! 

Из этого руководства вы узнаете, как выполнять следующие задачи:

> [!div class="checklist"]
> * Скачивание примера данных двумя разными способами
> * Подготовка данных с помощью нескольких преобразований
> * Создание отчета с заголовком, тремя визуальными элементами и срезом
> * Публикация отчета в службе Power BI, где им можно поделиться с коллегами

## <a name="prerequisites"></a>Предварительные требования

- Прежде чем начать, необходимо [скачать Power BI Desktop](https://powerbi.microsoft.com/desktop/).
- Если вы планируете опубликовать отчет в службе Power BI и вы еще не зарегистрировались, [зарегистрируйтесь для получения бесплатной пробной версии](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="get-data"></a>Получение данных 

Данные для этого руководства можно получить с помощью одного из двух методов.

### <a name="get-data-in-power-bi-desktop"></a>Получение данных в Power BI Desktop

При открытии Power BI Desktop выберите **Try a sample dataset** (Попробовать пример набора данных) на пустом холсте.

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-desktop-canvas-sample-dataset.png" alt-text="Снимок экрана: готовый отчет Power BI"::: 

Если вы с этим руководством вы работаете, используя Power BI Desktop, нажмите кнопку **Загрузить данные** .

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-two-ways-load-data.png" alt-text="Снимок экрана: готовый отчет Power BI":::

### <a name="download-the-sample"></a>Скачивание примера приложения

Вы также можете скачать пример книги непосредственно. 

1. Скачайте[файл Excel с примером финансовых данных](https://go.microsoft.com/fwlink/?LinkID=521962).
1. Откройте Power BI Desktop.
1. В разделе **Данные** на ленте **Главная** выберите **Excel** .
1. Перейдите к месту сохранения примера книги и выберите **Открыть** .

## <a name="prepare-your-data"></a>Подготовка данных 

В **навигаторе** можно *преобразовать* или *загрузить* данные. В навигаторе также можно предварительно просмотреть данные, чтобы можно было убедиться в наличии правильного диапазона данных. Числовые типы данных выделены курсивом. Если необходимо внести изменения, преобразуйте данные перед загрузкой. Чтобы сделать визуализации более удобными для восприятия, преобразуем данные прямо сейчас. По мере выполнения каждого преобразования вы увидите, что данные добавляются в список в подразделе **Параметры запроса** раздела **Примененные действия.** 

1. Выберите таблицу **Финансы** и выберите **Преобразовать данные** . 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-financial-navigator.png" alt-text="Снимок экрана: готовый отчет Power BI"::: 

1. Выберите столбец **Единиц продано** . На вкладке **Главная** выберите **Тип данных** , а затем выберите **Целое число** . Выберите **Заменить текущее** , чтобы изменить тип столбца. 

    Наиболее часто при выполнении шагов по очистке данных пользователи изменяют типы данных. В этом случае единицы продаются в десятичной форме. Нет смысла иметь 0,2 или 0,5 проданного товара, верно? Так что давайте изменим его на целое число. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-query-whole-number.png" alt-text="Снимок экрана: готовый отчет Power BI"::: 

1. Выберите столбец **Сегмент** . На вкладке **Преобразование** выберите **Формат** , а затем выберите **ПРОПИСНЫЕ** .

    Кроме того, мы хотим сделать эти сегменты более удобными для просмотра на диаграмме. Теперь отформатируйте столбец "Сегмент". 

     :::image type="content" source="media/desktop-excel-stunning-report/power-query-upper-case.png" alt-text="Снимок экрана: готовый отчет Power BI":::

1. Сократите имя столбца с **Название месяца** до **Месяц** . Дважды щелкните столбец **Название месяца** и переименуйте его в **Месяц** .  

     :::image type="content" source="media/desktop-excel-stunning-report/power-query-month-name.png" alt-text="Снимок экрана: готовый отчет Power BI":::

1. В столбце **Продукт** выберите раскрывающийся список и снимите флажок **Монтана** . 

     Нам известно, что продукт Монтана был снят с продажи в прошлом месяце, поэтому нам нужно отфильтровать эти данные из нашего отчета, чтобы избежать путаницы. 

     :::image type="content" source="media/desktop-excel-stunning-report/power-query-montana.png" alt-text="Снимок экрана: готовый отчет Power BI":::

1. Вы увидите, что каждое преобразование добавлено в список в подразделе **Параметры запроса** раздела **Примененные шаги** .

    :::image type="content" source="media/desktop-excel-stunning-report/power-query-applied-steps.png" alt-text="Снимок экрана: готовый отчет Power BI":::

1. На вкладке **Главная** выберите **Закрыть и применить** . Данные почти готовы к созданию отчета. 

    Отображается ли в списке полей символ сигмы? Служба Power BI обнаружила, что эти поля являются числовыми. Power BI также указывает поле даты с символом календаря.

     :::image type="content" source="media/desktop-excel-stunning-report/power-bi-fields-list-sigmas-date.png" alt-text="Снимок экрана: готовый отчет Power BI":::

### <a name="extra-credit-write-a-measure-in-dax"></a>Дополнительные возможности. написание меры в DAX

Написание *мер* в языке формул *DAX* является эффективным средством для моделирования данных. Дополнительные сведения о DAX см. в документации по Power BI. Сейчас давайте напишем базовую меру и соединим две таблицы. 

1. Выберите **представление данных** слева. 
 
    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-data-view.png" alt-text="Снимок экрана: готовый отчет Power BI":::

1. На ленте **Главная** выберите **Новая таблица** . 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-new-table.png" alt-text="Снимок экрана: готовый отчет Power BI" со всеми датами в промежутке времени между 1 января 2013 г. и 31 декабря 2014 г.  

    `Calendar = CALENDAR(DATE(2013,01,01),Date(2014,12,31))` 

2. Щелкните зеленый флажок, чтобы зафиксировать изменения.

     :::image type="content" source="media/desktop-excel-stunning-report/power-bi-dax-expression.png" alt-text="Снимок экрана: готовый отчет Power BI":::

1. Теперь выберите **представление модели** слева. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-model-view.png" alt-text="Снимок экрана: готовый отчет Power BI" в поле **Дата** в таблице "Календарь", чтобы соединить таблицы и создать *связь* между ними.  

     :::image type="content" source="media/desktop-excel-stunning-report/power-bi-date-relationship.png" alt-text="Снимок экрана: готовый отчет Power BI":::

## <a name="build-your-report"></a>Создание отчета 

Теперь, когда данные преобразованы и загружены, пришло время создать отчет. На панели "Поля" справа отображаются поля в созданной модели данных. 

Давайте создадим окончательный отчет, по одному визуальному элементу за раз. 

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-report-by-numbers.png" alt-text="Снимок экрана: готовый отчет Power BI":::

### <a name="visual-1-add-a-title"></a>Визуальный элемент 1. Добавить заголовок 

1. На ленте **Вставка** выберите элемент **Текстовое поле** . Введите "Краткий обзор — финансовый отчет". 
1. Выберите набранный текст. Задайте размер шрифта равным 20 и выберите полужирное начертание. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-title-executive-summary.png" alt-text="Снимок экрана: готовый отчет Power BI" установите переключатель **Фон** в положение **Выкл** . 
1. Измените размер поля, чтобы оно поместилось на одной строке. 

### <a name="visual-2-profit-by-date"></a>Визуальный элемент 2. Прибыль по дате 

Теперь создайте график, чтобы узнать, в каком месяце и в каком году прибыль была наибольшей. 

1. В области "Поля" перетащите поле **Прибыль** на пустую область холста отчета. По умолчанию в Power BI отображается гистограмма с одним столбцом, "Прибыль". 
1. Перетащите поле **Дата** на тот же визуальный элемент. Power BI обновит гистограмму и покажет прибыль по датам.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-column-year.png" alt-text="Снимок экрана: готовый отчет Power BI" выберите в раскрывающемся списке значение **Ось** . Измените **Дата** с **Иерархия дат** на **Дата** .

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-date-hierarchy.png" alt-text="Снимок экрана: готовый отчет Power BI":::

    Power BI обновит гистограмму и покажет прибыль по каждому месяцу.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-column-month.png" alt-text="Снимок экрана: готовый отчет Power BI" измените тип визуализации на **График** . 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-profit-date-line-chart.png" alt-text="Снимок экрана: готовый отчет Power BI":::

    Теперь можно с легкостью увидеть, что в декабре 2014 г. прибыль была наибольшей.

### <a name="visual-3-profit-by-country"></a>Визуальный элемент 3. Прибыль по странам 

Создайте карту, чтобы узнать, в какой из стран прибыль была наибольшей.

1. В области "Поля" перетащите поле **Страна** в пустую область на холсте отчета, чтобы создать карту.
1. Перетащите поле **Прибыль** на карту.

    Power BI создаст визуализацию карты с пузырьками, представляющими относительную прибыль в каждом регионе. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-map-visual.png" alt-text="Снимок экрана: готовый отчет Power BI":::

    Похоже, что прибыль в Европе больше, чем в Северной Америке. 

### <a name="visual-4-sales-by-product-and-segment"></a>Визуальный элемент 4. Продажи по продукту и сегменту 

Создайте линейчатую диаграмму, чтобы определить, в какие компании и сегменты следует инвестировать средства.

1. Перетащите две созданные диаграммы, чтобы они были расположены рядом в верхней половине холста. Оставьте место в левой части холста. 
1. Выберите пустую область в нижней половине холста отчета. 

1. На панели "Поля" выберите поля **Продажи** , **Продукт** и **Сегмент** . 

    Power BI автоматически создаст гистограмму с группировкой. 

1. Перетащите диаграмму так, чтобы она была достаточно широкой для заполнения места под двумя верхними диаграммами.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-clustered-column-chart.png" alt-text="Снимок экрана: готовый отчет Power BI":::

    Похоже, компания должна продолжать инвестировать в продукт Paseo и ориентироваться на сегменты предприятий малого бизнеса и государственных организаций.  

### <a name="visual-5-year-slicer"></a>Визуальный элемент 5. Срез года 

Срезы — это полезный инструмент для фильтрации визуальных элементов на странице отчета в соответствии с конкретным выбором. В этом случае можно создать срез, чтобы уточнить данные о производительности для каждого месяца и года.  

1. В области "Поля" выберите поле **Дата** и перетащите его в пустую область слева от холста. 
2. В области "Визуализации" выберите пункт **Срез** . 
3. В разделе "Поля" панели "Визуализации" выберите раскрывающийся список **Поля** . Удалите "Квартал" и "День", чтобы остались только "Год" и "Месяц". 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-date-hierarchy-trim.png" alt-text="Снимок экрана: готовый отчет Power BI":::

4. Разверните каждый год и измените размер визуального элемента, чтобы отображались все месяцы.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-hierarchy-date-slicer.png" alt-text="Снимок экрана: готовый отчет Power BI":::

Теперь, если руководителю потребуются только данные за 2013 год, можно воспользоваться срезом для переключения между годами или конкретными месяцами каждого года. 

### <a name="extra-credit-format-the-report"></a>Дополнительные возможности. Форматирование отчета

Чтобы отформатировать отчет и сделать его более привлекательным, вот несколько простых действий. 

**Тема** .

- На ленте **Вид** измените тему на **Executive** .  

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-theme-executive.png" alt-text="Снимок экрана: готовый отчет Power BI"::: 

**Изменение визуальных элементов** 

Внесите следующие изменения на вкладке **Формат** в области "Визуализации".

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-format-tab-visualizations.png" alt-text="Снимок экрана: готовый отчет Power BI":::

1. Выберите визуальный элемент 2. В разделе **Заголовок** измените **Текст заголовка** на "Прибыль по месяцам и годам", а **Размер текста**  — на **16 пт** . Установите переключатель **Тень** в положение **Вкл.** . 

1. Выберите визуальный элемент 3. В разделе **Стили карт** измените значение параметра **Тема** на **Оттенки серого** . В разделе **Заголовок** измените значение параметра **Размер текста** на **16 пт** . Установите переключатель **Тень** в положение **Вкл.** .

1. Выберите визуальный элемент 4. В разделе **Заголовок** измените значение параметра **Размер текста** на **16 пт** . Установите переключатель **Тень** в положение **Вкл.** .

1. Выберите визуальный элемент 5. В разделе **Элементы управления выбором** установите переключатель **Показать параметр "Выбрать все"** в положение **Вкл.** . В разделе **Заголовок среза** увеличьте значение параметра **Размер текста** до **16 пт** . 

**Добавление фоновой фигуры для заголовка**

1. На ленте **Вставка** выберите **Фигуры** > **Прямоугольник** . Поместите его в верхнюю часть страницы и растяните по ширине страницы и высоты заголовка. 
1. В области **Формат фигуры** в разделе **Линия** измените значение параметра **Прозрачность** на **100%** . 
1. В разделе **Заливка** измените **Цвет заливки** на **Цвет темы 5 #6B91C9** (синий). 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-theme-color-5.png" alt-text="Снимок экрана: готовый отчет Power BI":::

1. На вкладке **Формат** выберите **Переместите назад** > **На задний план** . 
1. Выберите текст в визуальном элементе 1, в заголовке, и измените цвет шрифта на **Белый** . 

**Добавление фоновой фигуры для визуальных элементов 2 и 3**

1. На ленте **Вставка** выберите **Фигуры** > **Прямоугольник** и растяните его в соответствии с шириной и высотой визуальных элементов 2 и 3. 
1. В области **Формат фигуры** в разделе **Линия** измените значение параметра **Прозрачность** на **100%** . 
1. На вкладке **Формат** выберите **Переместите назад** > **На задний план** . 

### <a name="finished-report"></a>Готовый отчет

Вот как будет выглядеть окончательный отчет:  

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-excel-formatted-report.png" alt-text="Снимок экрана: готовый отчет Power BI":::

Данный отчет позволяет руководителю получить ответы на все его вопросы: 

- В каком месяце и году прибыль была наибольшей? 

    Декабрь 2014 г. 

- Где у компании наблюдается наибольший успех (по странам)? 

    В Европе, в частности во Франции и Германии. 

- В какой продукт и сегмент компании следует инвестировать? 

    Компания должна продолжать инвестировать в продукт Paseo и ориентироваться на сегменты предприятий малого бизнеса и государственных организаций. 

## <a name="save-your-report"></a>Сохранить отчет

- В меню **Файл** выберите пункт **Сохранить** .

## <a name="publish-to-the-power-bi-service-to-share"></a>Публикация в службе Power BI для предоставления общего доступа 

Чтобы предоставить общий доступ к отчету руководителю и коллегам, опубликуйте его в службе Power BI. При совместном использовании с коллегами, у которых есть учетная запись Power BI, они могут взаимодействовать с отчетом, но не могут сохранять изменения. 

1. В Power BI Desktop на ленте **Главная** выберите **Опубликовать** . 

    Возможно, потребуется войти в службу Power BI. Если у вас нет учетной записи, вы можете [зарегистрироваться и получить бесплатную пробную версию](https://app.powerbi.com/signupredirect?pbi_source=web).

1. Выберите назначение, например, **Моя рабочая область** , в службе Power BI > **Выбрать** .
1. Выберите **Открыть "имя_файла" в Power BI** .

    :::image type="content" source="media/desktop-excel-stunning-report/open-power-bi.png" alt-text="Снимок экрана: готовый отчет Power BI":::

    Готовый отчет откроется в браузере.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-excel-report-service.png" alt-text="Снимок экрана: готовый отчет Power BI"::: 

1. Выберите **Поделиться** в верхней части отчета, чтобы поделиться отчетом с другими пользователями.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-share-report.png" alt-text="Снимок экрана: готовый отчет Power BI":::

## <a name="next-steps"></a>Дальнейшие действия

- [Руководство. Анализ данных о продажах из Excel и канала OData](../connect-data/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed.md)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI](https://community.powerbi.com/).
