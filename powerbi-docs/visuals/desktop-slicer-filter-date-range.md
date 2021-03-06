---
title: Использование среза или фильтра относительных дат в Power BI
description: Узнайте, как использовать срез или фильтр для ограничения диапазона относительных дат в Power BI.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 09/09/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 26e638e106f7bd11544d1d80dae543f06783bda7
ms.sourcegitcommit: 92b033ee7a6e36808371b247b7b41536cee6c2f6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "90008889"
---
# <a name="creating-a-relative-date-slicer-and-filter-in-power-bi"></a>Создание среза и фильтра относительных дат в Power BI

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

**Срез относительных дат** или **фильтр относительных дат** позволяют применять фильтры с учетом времени для любого столбца даты в модели данных. Например, вы можете использовать **срез относительных дат**, чтобы отобразились только данные по продажам за последние 30 дней (или месяц, календарный месяц и т. д). Когда вы обновляете данные, период относительного времени автоматически применяет ограничение относительной даты.

![Снимок экрана отчета со стрелкой, указывающей на срез относительных дат.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-01.png)

Для предоставления общего доступа к отчету Power BI и вам, и коллеге необходимо иметь отдельные лицензии Power BI Pro или сохранить отчет в емкости Премиум.

## <a name="create-the-relative-date-range-slicer"></a>Создание среза для диапазона относительных дат

Вы можете использовать срез диапазона относительных дат так же, как и любой другой срез. Создайте визуальный элемент **Срез** для отчета, а затем выберите значение даты для параметра **Поле**. На следующем изображении выбрано поле *OrderDate* (Дата заказа).

![Снимок экрана на панели визуализаций со стрелкой, указывающей на значок среза и воронку "Поле".](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-02.png)

Выберите срез на холсте, а затем угловую скобку в правом верхнем углу визуального элемента среза. Если визуальный элемент содержит данные даты, в меню будет отображаться параметр **Относительные**.

![Снимок экрана с визуальным элементом среза с выделенной угловой скобкой и стрелкой, указывающей на параметр "Относительные".](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-03.png)

Для среза относительных дат выберите *Относительное значение*.

Затем можно выбрать параметры.

Для первого параметра в *срезе относительных дат* можно выбрать один из следующих вариантов:

![Снимок экрана параметров конфигурации относительных дат с выделенным первым параметром.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-04.png)

* Последний
* Далее
* Эта

Второй параметр (средний) в *срезе относительных дат* позволяет ввести число, определяющее диапазон относительных дат.

![Снимок экрана параметров конфигурации относительных дат с выделенным вторым параметром.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-04a.png)

Третий параметр позволяет выбрать меру даты. Можно выбрать следующие значения:

![Снимок экрана параметров конфигурации относительных дат с выделенным третьим параметром.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-05.png)

* Дни
* Weeks (Недели);
* Weeks (Calendar) (Календарные недели);
* Months (Месяцы);
* Months (Calendar) (Календарные месяцы);
* Years (Годы);
* Годы (календарь)

Если выбрать в списке **Months** (Месяцы), а для среднего параметра ввести значение *2*, произойдет следующее.

* Если сегодня 20 июля,

    - в ограниченных срезом визуальных элементах будут показаны данные за два предыдущих месяца,
    - начиная с 21 мая и по 20 июля (текущая дата).

Для сравнения, если вы выбрали *Months (Calendar)* (Календарные месяцы), в ограниченных визуальных элементах отобразятся данные с 1 мая по 30 июня (за два последних полных календарных месяца).

## <a name="create-the-relative-date-range-filter"></a>Создание фильтра для диапазона относительных дат

Кроме того, вы можете создать фильтр диапазона относительных дат для всего отчета или его отдельной страницы. Для этого перетащите поле даты в области **Фильтры на уровне страницы** или **Фильтры на уровне отчета** на панели **Поле**.

![Снимок экрана: поле OrderDate, перетаскиваемое в фильтры уровня страницы.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-06.png)

После этого можно изменить диапазон относительных дат. Процесс аналогичен настройке **среза относительных дат**. В раскрывающемся списке **Тип фильтра** выберите **Фильтрация относительных дат**.

![Снимок экрана: раскрывающийся список "Тип фильтра" и указатель мыши на фильтре относительных дат.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-07.png)

После выбора **фильтрации относительных дат** отобразятся три раздела, которые можно изменить, включая цифровое поле посередине, как и для среза.

![Снимок экрана: фильтры уровня отчетов со стрелками, указывающими параметры "Показать элементы, когда значение...".](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-08.png)

## <a name="limitations-and-considerations"></a>Рекомендации и ограничения

В настоящее время к **срезу** и фильтру диапазона относительных дат применяются описанные ниже ограничения и рекомендации.

* Тип данных для поля в срезе должен быть датой, а не значением по умолчанию для текста. В противном случае относительные параметры не отображаются в срезе.
* Модели данных в **Power BI** не включают сведения о часовом поясе. В моделях можно сохранить данные времени, но без определения часового пояса, к которому они принадлежат.
* Срезы и фильтры всегда основаны на времени в формате UTC. Если задать фильтр в отчете и отправить его коллеге в другом часовом поясе, отобразятся те же данные. Если вы не находитесь в часовом поясе UTC, вам и вашим коллегам следует учитывать смещение времени, с которым придется столкнуться.
* Можно преобразовать данные, зафиксированные в местном часовом поясе, в формат UTC с помощью **редактора запросов**.

## <a name="next-steps"></a>Дальнейшие действия

- [Использование среза и фильтра относительного времени в Power BI](../create-reports/slicer-filter-relative-time.md)
- [Срезы в Power BI](power-bi-visualization-slicers.md)
