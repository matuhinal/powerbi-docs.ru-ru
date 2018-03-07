---
title: "Советы и рекомендации по формулировке вопросов в функции \"Вопросы и ответы\" в Power BI"
description: "Советы и рекомендации по формулировке вопросов в функции \"Вопросы и ответы\" в Power BI"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 01/18/2018
ms.author: jastru
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: bdf1f161e0a95bda5b37d9c43a3bdcc6bde1066a
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2018
---
# <a name="tips-for-asking-questions-in-power-bi-qa"></a>Советы по запросам в функцию "Вопросы и ответы" в Power BI
## <a name="words-and-terminology-that-qa-recognizes"></a>Слова и термины, распознаваемые функцией "Вопросы и ответы"
Этот список ключевых слов не является полным.  Чтобы понять, распознает ли Power BI то или иное ключевое слово, попробуйте ввести его в поле вопроса.  Если слово или термин затенены, Power BI не распознает их (вообще либо в текущем контексте).

В приведенном ниже списке используется настоящее время, однако в большинстве случаев распознаются все временные формы. Например, слово is включает формы are, was, were, will be, have, has, had, will have, has got, do, does, did.  А слово sort включает формы sorted и sorting.  Кроме того, Power BI распознает и использует формы слова в единственном и множественном числах. Например, Power BI распознает слова year и years.

> [!NOTE]
> Компонент "Вопросы и ответы" также доступен в [приложении Microsoft Power BI для iOS на устройствах iPad, iPhone и iPod Touch](mobile-apps-ios-qna.md).
> 
> 

Если вы являетесь владельцем набора данных, добавьте выражения и синонимы, чтобы улучшить результаты работы функции "Вопросы и ответы" для своих клиентов.

**Статистические функции**: total, sum, amount, number, quantity, count, average, most, least, fewest, largest, smallest, highest, biggest, maximum, max, greatest, lowest, littlest, minimum, min

**Артикли**: a, an, the

**Пустые значения и логические выражения**: blank, empty, null, префиксы non и non-, empty string, empty text, true, t, false, f

**Сравнение**: vs, versus, compared to, compared with

**Союзы**: and, or, each of, with, versus, &, and, but, nor, along with, in addition to

**Сокращения**: компонент "Вопросы и ответы" распознает практически все сокращения; просто попробуйте.  Вот несколько примеров: didn’t, haven’t, he’d, he’s, isn’t, it’s, she’ll, they’d, weren’t, where’ll, who’s, won’t, wouldn’t.

**Даты**: Power BI распознает большинство терминов, связанных с датами (day, week, month, year, quarter, decade и т. д.), а также даты, записанные в самых разных форматах (см. ниже). Power BI также распознает следующие ключевые слова: MonthName, Days 1-31, decade.

Примеры: January 3rd of 1995, January 3rd 1995, jan 03 1995, 3 Jan 1995, the 3rd of January, January 1995, 1995 January, 1995-01, 01/1995, названия месяцев.

**Относительные временные индикаторы**: today, right now, current time, yesterday, tomorrow, the current, next, the coming, last, previous, ago, before now, sooner than, after, later than, from, at, on, from now, after now, in the future, past, last, previous, within, in, over, N days ago, N days from now, next, once, twice.

Пример: count of orders in the past 6 days (количество заказов за последние 6 дней).

**Равенство (диапазоны)**: in, equal to, =, after, is more than, in, between, before

Примеры: Order year is before 2012 (год заказа до 2012)? Price equals between 10 and 20 (цена в диапазоне от 10 до 20)? Is the age of John greater than 40 (возраст Джона больше 40)? Total sales in 200-300 (общий объем продаж в диапазоне 200-300)?

**Равенство (значение)**: is, equal, equal to, in, of, for, within, is in, is on

Примеры: Which products are green (какие продукты зеленые)? Order date equals 2012 (год заказа равен 2012). Is the age of John 40 (возраст Джона 40)? Total sales that is not equal to 200 (общие продажи не равны 200)? Order date of 1/1/2016 (дата заказа 01.01.2016). 10 in price (10 в значении цены)? Green for color (зеленый цвет)? 10 in price (10 в значении цены)?

**Имена**: если столбец в наборе данных содержит слово Name (Имя) (например, EmployeeName — Имена сотрудников), функция "Вопросы и ответы" понимает значения в этом столбце как имена и позволяет задавать вопросы вида "какие сотрудники имеют имя Роман".

**Местоимения**: he, him, himself, his, she, herself, her, hers, it, itself, its, they, their, them, themselves, theirs, this, these, that, those

**Команды запросов**: sorted, sort by, direction, group, group by, by, show, list, display, give me, name, just, only, arrange, rank, compare, to, with, against, alphabetically, ascending, descending, order

**Диапазон**: greater, more, larger, above, over, >, less, smaller, fewer, below, under, <, at least, no less than, >=, at most, no more than, <=, in, between, in the range of, from, later, earlier, sooner, after, on, at, later than, after, since, starting with, starting from, ending with

**Время**: am, pm, o'clock, noon, midnight, hour, minute, second, hh:mm:ss

Примеры: 10 pm, 10:35 pm, 10:35:15 pm, 10 oclock, noon, midnight, hour, minute, second.

**Первые N** (порядок, ранг): top, bottom, highest, lowest, first, last, next, earliest, newest, oldest, latest, most recent, next

**Типы визуальных элементов**: все типы визуальных элементов, встроенные в Power BI.  Если соответствующий параметр есть в области "Визуализации", его можно использовать в вопросе.  Исключением являются [пользовательские визуальные элементы](power-bi-custom-visuals.md), которые вы добавили в область визуализации вручную.

Пример: show districts by month and sales total as bar chart (показать районы по месяцам и общие продажи как линейчатую диаграмму)

**Слова-вопросы (связи, признаки)**: when, where, which, who, whom, how many, how much, how many times, how often, how frequently, amount, number, quantity, how long, what

## <a name="qa-helps-you-phrase-the-question"></a>Функция "Вопросы и ответы" помогает сформулировать вопрос
Функция "Вопросы и ответы" следит за тем, чтобы ответ максимально точно соответствовал заданному вопросу. Для этого применяется несколько способов. В каждом случае действие можно принимать полностью, частично или не принимать совсем. При вводе вопроса функция "Вопросы и ответы":

* автоматически заканчивает слова и вопросы. При этом применяются различные стратегии, включая автозавершение узнаваемых слов, популярных вопросов по соответствующим книгам и уже заданных ранее вопросов, на которые был предоставлен действительный ответ. Если вариантов автозавершения несколько, они будут перечислены в раскрывающемся списке;
* исправляет орфографические ошибки;
* обеспечивает предварительный просмотр ответов в форме визуализации; визуализация обновляется по мере ввода и изменения вопроса (до нажатия клавиши ВВОД);
* при повторном наведении указателя мыши на поле вопроса автоматически предлагает замены для соответствующих наборов данных;
* изменяет формулировку вопроса в зависимости от того, какие данные входят в соответствующий набор. Это позволяет убедиться в том, что функция "Вопросы и ответы" понимает вопрос, так как она заменяет указанные вами слова на синонимы из соответствующего набора или наборов данных.
* затемняет нераспознанные слова.

## <a name="combine-results-from-more-than-one-dataset"></a>Объединение результатов из нескольких наборов данных
Одна из самых полезных функций Power BI — это объединение данных из разных наборов данных.  Не ограничивайтесь отдельным набором данных, задавайте вопросы, извлекающие данные сразу из нескольких наборов данных. Например, если панель мониторинга включает плитки из примера анализа розничной торговли и набор данных о заполненности магазинов, можно задать *отображение числа магазинов по состоянию заполненности в виде линейчатой диаграммы по убыванию*.

## <a name="dont-stop-now"></a>Не останавливайтесь
Продолжайте диалог даже после того, как получите ответы на заданные вопросы. Воспользуйтесь интерактивными функциями — и функция "Вопросы и ответы" поможет вам узнать больше.

## <a name="next-steps"></a>Дальнейшие действия
Назад к статье [Вопросы и ответы в Power BI](power-bi-q-and-a.md)  

[Power BI — основные понятия](service-basic-concepts.md)  

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

