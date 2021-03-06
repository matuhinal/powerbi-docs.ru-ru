---
title: Изучение данных на естественном языке с помощью модуля "Вопросы и ответы" в Power BI
description: Как использовать функцию "Вопросы и ответы" в Power BI для изучения данных и создания визуализаций с помощью естественного языка для запросов.
author: mohaali
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/01/2020
ms.author: mohaali
ms.openlocfilehash: d9339c0005f7f2af9fedd5cc5bfcce40469afb8c
ms.sourcegitcommit: 6bc66f9c0fac132e004d096cfdcc191a04549683
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91749168"
---
# <a name="intro-to-power-bi-qa"></a>Общие сведения о модуле "Вопросы и ответы" в Power BI

Иногда быстрее всего получить ответ из данных, выполнив поиск с использованием естественного языка. Функция "Вопросы и ответы" в Power BI позволяет изучать данные, формулируя запросы своими словами на естественном языке. Функция "Вопросы и ответы" интерактивна и даже интересна. Часто один вопрос приводит к многим другим, так как визуализации раскрывают новые пути для поиска. Задать вопрос — это только начало. Исследуйте данные, уточняя или расширяя вопросы, обнаруживая новую информацию, сосредотачиваясь на деталях или увеличивая поле зрения, чтобы получить более широкое представление. Взаимодействие происходит интерактивно и быстро благодаря тому, что функция основана на хранилище в памяти. 

Модуль "Вопросы и ответы" в Power BI является бесплатным и доступен всем пользователям. В Power BI Desktop разработчики отчетов могут использовать модуль "Вопросы и ответы" для изучения данных и создания визуализаций. В службе Power BI любой пользователь может исследовать эти данные с помощью модуля "Вопросы и ответы". Наши мобильные приложения также поддерживают функцию "Вопросы и ответы": в iOS для этого служит виртуальный помощник "Вопросы и ответы", а на устройствах Android — визуальный элемент "Вопросы и ответы". Если у вас есть разрешение на изменение панели мониторинга или отчета, можно также закрепить результаты модуля "Вопросы и ответы".

## <a name="how-to-use-qa"></a>Работа с модулем "Вопросы и ответы"

![Главная страница "Вопросы и ответы"](media/qna-visual.png)

Еще до начала ввода компонент вопросов и ответов открывает новое окно с полезными предложениями. Начните с одного из предлагаемых вопросов или введите собственный. Модуль "Вопросы и ответы" поддерживает широкий спектр вопросов, включая, помимо прочего, следующие:

- **Вопросы на естественном языке**. Какие продажи принесли максимальный доход?
- **Фильтрация относительных дат**. Показать продажи за последний год.
- **Возврат первых N элементов**. Первые 10 продуктов по объему продаж.
- **Фильтр**. Показать продажи в России.
- **Сложные условия**. Показать продажи продуктов, относящихся к категории 1 или категории 2.
- **Возврат определенного визуального элемента**. Показать продажи по продуктам в виде круговой диаграммы.
- **Сложные агрегаты**. Показать медианные продажи по продуктам.
- **Сортировка результатов**. Показать первые 10 стран по объему продаж, упорядоченные по коду страны.
- **Сравнение данных**. Показать даты по объему продаж в сравнении с общей стоимостью.
- **Просмотр тенденций**. Показать продажи с течением времени.

### <a name="autocomplete"></a>Автозавершение

В процессе ввода вопроса модуль "Вопросы и ответы" Power BI выводит актуальные и контекстные предложения, что позволяет ускорить работу. По мере ввода вы получаете мгновенные отзывы и результаты. Это похоже на ввод запроса в поисковой системе.

![Завершение фразы в модуле "Вопросы и ответы"](media/qna-suggestion-phrase-completion.png)

### <a name="redblueorange-underlines"></a>Подчеркивание красным, синим и оранжевым

В модуле "Вопросы и ответы" слова, распознанные и не распознанные системой, подчеркиваются. Сплошное синее подчеркивание означает, что система успешно соотнесла слово с полем или значением в модели данных. В приведенном ниже примере модуль "Вопросы и ответы" распознал словосочетание *Продажи в ЕС*.

![Подчеркивание синим в модуле "Вопросы и ответы"](media/qna-blue-underline.png)

 Оранжевое подчеркивание означает, что слово или слова классифицируются как имеющие *низкий доверительный уровень*. При вводе неконкретного или неоднозначного слова поле подчеркивается оранжевым. Примером может служить слово "Продажи". Оно может содержаться в нескольких полях, поэтому система использует оранжевое подчеркивание, чтобы предложить выбрать нужное поле. Еще одним примером низкой степени достоверности может служить слово "область", которому соответствует столбец "регион". Модуль "Вопросы и ответы" в Power BI распознает слова, которые означают одно и то же, благодаря интеграции с Bing и Office, а также интерпретации переименований в отчете в качестве потенциальных предложений. Однако слово подчеркивается оранжевым, чтобы дать вам понять, что это не прямое соответствие.

Красное подчеркивание означает, что модуль "Вопросы и ответы" совершенно не распознает слово. Например, это может произойти при использовании термина, относящегося к определенной предметной области, который не упоминается нигде в данных, или при неправильном указании имен для полей данных. Примером может служить использование слова "Затраты", которое не встречается в данных. Это слово имеется в русском словаре, но модуль "Вопросы и ответы" подчеркивает его красным, чтобы указать, что этот термин не был найден в отношении данных.

![Слово "Продажи", подчеркнутое красным в модуле "Вопросы и ответы"](media/qna-red-underline-costs.png)

> [!NOTE]
> Цвета подчеркивания можно настроить в разделе **Форматирование визуального элемента** модуля "Вопросы и ответы". Кроме того, в статье [Средства модуля "Вопросы и ответы"](q-and-a-tooling-teach-q-and-a.md) описывается раздел *Вопросы и ответы: обучение*, в котором можно определить термины, не распознаваемые модулем "Вопросы и ответы".

### <a name="visualization-results"></a>Результаты визуализации

По мере ввода вопроса модуль "Вопросы и ответы" пытается мгновенно интерпретировать его и визуализировать ответ. После последних обновлений модуль "Вопросы и ответы" теперь пытается интерпретировать вопрос и автоматически отобразить поля на правильной оси. Например, если ввести "Продажи по годам", модуль "Вопросы и ответы" определит, что год является полем даты, и будет стараться разместить это поле в первую очередь на оси X. Чтобы изменить тип визуализации, введите фразу "в виде *тип диаграммы*" после вопроса. В настоящее время модуль "Вопросы и ответы" поддерживает следующие типы визуализаций:

- График
- Линейчатая диаграмма
- Матрица
- Таблица
- Карточка
- С областями
- Круговая диаграмма
- точечная или пузырьковая диаграмма.
 
![Результаты визуализации в модуле "Вопросы и ответы"](media/qna-visual-results-date.png)

## <a name="add-qa-to-a-report"></a>Добавление функции "Вопросы и ответы" в отчет

Функцию "Вопросы и ответы" можно добавить в отчет в Power BI Desktop или службе Power BI одним из двух способов:

- добавление визуального элемента модуля "Вопросы и ответы";
- добавление кнопки модуля "Вопросы и ответы".

Чтобы добавить визуальный элемент модуля "Вопросы и ответы" в отчет, щелкните новый значок **Вопросы и ответы**, а затем выберите новый визуальный элемент "Вопросы и ответы" в области "Визуализация". Чтобы вставить визуальный элемент модуля "Вопросы и ответы", можно также дважды щелкнуть в любом месте холста отчета.

![Значок визуального элемента "Вопросы и ответы"](media/qna-visual-icon.png)

Чтобы добавить кнопку, на ленте **Главная** выберите **Кнопки** > **Вопросы и ответы**. Изображение кнопки "Вопросы и ответы" можно настроить как угодно.

> [!NOTE]
> При запуске модуля "Вопросы и ответы" с помощью кнопки по-прежнему используется его старая версия. Эта проблема будет исправлена в одном из следующих выпусков Power BI.

## <a name="use-qa-for-dashboards"></a>Использование модуля "Вопросы и ответы" для панелей мониторинга

По умолчанию функция "Вопросы и ответы" находится в верхней части панелей мониторинга. Чтобы использовать "Вопросы и ответы", введите вопрос в поле **Задайте вопрос о своих данных**.

!["Вопросы и ответы" на панели мониторинга](media/qna-dashboard.png)

## <a name="next-steps"></a>Дальнейшие действия

Поддержку естественного языка можно интегрировать в отчеты различными способами. Дополнительные сведения см. в следующих статьях:

* ["Вопросы и ответы": визуализация](../visuals/power-bi-visualization-q-and-a.md)
* ["Вопросы и ответы": рекомендации](q-and-a-best-practices.md)
