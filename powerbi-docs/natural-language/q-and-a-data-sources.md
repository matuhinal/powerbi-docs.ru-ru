---
title: Использование естественного языка при импорте, активном подключении и прямом запросе
description: В этой статье мы рассмотрим, как функция "Вопросы и ответы" работает с различными типами источников данных, доступных в Power BI. Мы также рассмотрим основные понятия индексирования и кэширования.
author: mohaali
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/19/2020
ms.author: mohaali
ms.openlocfilehash: 85ecc5adc55daee86922c39e417db1cac5ba4a52
ms.sourcegitcommit: 0f807d3c74e5202b6e6a95fad49f2787928b9613
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "88706218"
---
# <a name="use-natural-language-with-import-live-connect-and-direct-query"></a>Использование естественного языка при импорте, активном подключении и прямом запросе

Функция "Вопросы и ответы" в Power BI позволяет быстро получать ответы из данных с помощью вопросов на естественном языке. В этой статье описывается, как индексирование и кэширование используются для повышения производительности каждой поддерживаемой конфигурации.

## <a name="what-data-sources-are-supported-in-qa"></a>Какие источники данных поддерживаются в функции "Вопросы и ответы"?

"Вопросы и ответы" поддерживаются в следующих конфигурациях.

- Режим Import
- Режим активного подключения — использование локальных SQL Server Analysis Services, Azure Analysis Services или наборов данных Power BI.
- Прямой запрос — Azure Synapse, Azure SQL и SQL Server 2019. Хотя другие источники также могут работать в режиме прямого запроса, официально мы их не поддерживаем.

По умолчанию функция "Вопросы и ответы" включена внутри отчета, если используется визуальный элемент вопросов и ответов. Если вы используете прямой запрос или активное подключение, появится запрос. Вы можете явно включить или выключить возможности естественного языка для отчета, перейдя в параметры.

![Параметры функции "Вопросы и ответы" для рабочего стола](media/qna-desktop-options.png)

Дополнительные сведения см. в разделе [Ограничения модуля "Вопросы и ответы" в Power BI](q-and-a-limitations.md).

## <a name="how-does-indexing-work-with-qa"></a>Как работает индексирование в функции "Вопросы и ответы"?

Когда вы включаете функцию "Вопросы и ответы", создается индекс, позволяющий быстро предоставить пользователю ответ в режиме реального времени и помочь интерпретировать вопросы пользователя. Построение индекса может занять некоторое время и содержит следующие элементы и ограничения.

- Все имена столбцов и таблиц вставляются в индекс, если только они не были явно отключены в инструментарии "Вопросов и ответов".
- Индексируются все текстовые значения короче 100 символов. Текстовые значения длиннее 100 символов не индексируются. 
- "Вопросы и ответы" хранят не более 5 млн уникальных значений в своем индексе. При превышении этого порогового значения индекс не будет содержать все возможные значения, что может снизить точность результатов, полученных из "Вопросов и ответов".
- Если во время индексирования возникает ошибка, индекс остается в частичном состоянии и будет создан повторно при следующем обновлении, как описано в следующем разделе.

## <a name="how-often-is-the-index-refreshed-and-cached"></a>Как часто обновляется и кэшируется индекс?

В Power BI Desktop индекс создается во время использования "Вопросов и ответов". Появится небольшой значок, сообщающий, что создается индекс. В течение этого времени загрузка визуального элемента "Вопросов и ответов", включая предложения, может занимать некоторое время.

В службе Power BI индекс создается повторно при публикации, повторной публикации и обновлении. Индекс "Вопросов и ответов" не всегда создается автоматически, иногда это происходит по запросу для оптимизации обновлений набора данных. Для прямого запроса данные индексируются не чаще одного раза в день, чтобы снизить нагрузку на источник.

## <a name="next-steps"></a>Дальнейшие действия

Поддержку естественного языка можно интегрировать в отчеты различными способами. Дополнительные сведения см. в следующих статьях:

* ["Вопросы и ответы": визуализация](../visuals/power-bi-visualization-q-and-a.md)
* ["Вопросы и ответы": рекомендации](q-and-a-best-practices.md)
