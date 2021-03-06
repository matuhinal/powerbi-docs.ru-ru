---
title: Настройка данных Excel для работы с функцией "Вопросы и ответы" в Power BI
description: Как настроить данные для работы с компонентом "Вопросы и ответы" в Power BI
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: f7760021966673b93313809a806473b94c7750d3
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85218707"
---
# <a name="make-excel-data-work-well-with-qa-in-power-bi"></a>Настройка данных Excel для работы с функцией "Вопросы и ответы" в Power BI
Этот материал предназначен для пользователей, создающих модели данных или формирующих книги Excel, которые будут использоваться в Power BI.

В Power BI функция "Вопросы и ответы" может выполнять поиск в структурированных данных и выбирать подходящую визуализацию для вашего вопроса — именно это и делает ее привлекательным средством для использования.   

Компонент "Вопросы и ответы" может работать в любом отправленном файле Excel, содержащем таблицы, диапазоны и модели PowerPivot, но чем больше операций оптимизации и очистки данных вы выполняете, тем лучше работает эта функция.  Если вы планируете совместно использовать отчеты и панели мониторинга, созданные на основе вашего набора данных, вам нужно предоставить коллегам простой способ задавать вопросы и получать на них ответы.

## <a name="how-qa-works-with-excel"></a>Как функция "Вопросы и ответы" работает с Excel
Функция "Вопросы и ответы" имеет набор основных возможностей понимания естественного языка, которые работают в данных. Она поддерживает контекстно зависимый поиск по ключевым словам для имен таблиц, столбцов и вычисляемых полей Excel. Она также содержит встроенные сведения о способах фильтрации, сортировки, статистической обработки, группирования и отображения данных. 

Например, в таблице Excel с именем "Продажи" и столбцами "Продукт", "Месяц", "Количество проданного товара", "Валовые продажи" и "Прибыль" можно задать вопросы по любому из этих объектов.  Можно попросить показать продажи, общую прибыль по месяцу, отсортировать продукты по количеству проданных единиц и так далее. Узнайте больше об [использовании функции "Вопросы и ответы" в панелях мониторинга и отчетах](power-bi-tutorial-q-and-a.md), а также о [типах визуализаций, которые можно указать при ее использовании](../visuals/power-bi-visualization-types-for-reports-and-q-and-a.md).

## <a name="prepare-an-excel-dataset-for-qa"></a>Подготовка набора данных Excel для функции "Вопросы и ответы"
Функция "Вопросы и ответы" основана на именах таблиц, столбцов и вычисляемых полей и использует их для ответов на вопросы по конкретным данных. Это означает, что объекты в книге имеют важное значение.

Ниже приведены некоторые советы по эффективному использованию функции "Вопросы и ответы" в книге.

* Убедитесь, что данные находятся в таблице Excel. Далее показано, [как создать таблицу Excel](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-e81aa349-b006-4f8a-9806-5af9df0ac664).
* Таблицы, столбцы и вычисляемые поля должны иметь понятные имена.
  
  Например, если имеется таблица с данными о продажах, назовите таблицу "Продажи". Для работы с функцией "Вопросы и ответы" хорошо подойдут такие имена столбцов, как "Год", "Продукт", "Торговый представитель" и "Объем".

* Если книга содержит модель данных Power Pivot, количество оптимизаций можно увеличить. Узнайте больше о [функции "Вопросы и ответы" в Power BI, часть 2](https://powerbi.microsoft.com/blog/demystifying-power-bi-q-amp-a-part-2/) от нашей группы экспертов естественного языка.

* Откройте набор данных в Power BI Desktop и создайте новые столбцы и меры. Объедините поля для создания уникальных значений, классификации данных по типу (например, даты, строки, география, изображения, URL-адреса) и других операций.

## <a name="next-steps"></a>Дальнейшие действия

- [Вопросы и ответы для потребителей](../consumer/end-user-q-and-a.md)  
- [Использование функции "Вопросы и ответы" в панелях мониторинга и отчетах](power-bi-tutorial-q-and-a.md)
- [Подготовка локальных наборов данных для функции "Вопросы и ответы"](service-q-and-a-direct-query.md)   
- [Получение данных (для Power BI)](../connect-data/service-get-data.md)  

Остались вопросы? [Ответы на них см. в сообществе Power BI.](https://community.powerbi.com/)
