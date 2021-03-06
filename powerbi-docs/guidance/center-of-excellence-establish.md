---
title: Создание центра компетенции
description: Узнайте, как центр компетенции помог корпорации Майкрософт создать стандартизированную платформу аналитики и данных для извлечения ценной информации благодаря правильной операционной модели, участию заинтересованных лиц и целевым инвестициям.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/19/2020
ms.author: v-pemyer
ms.openlocfilehash: 477b6a1e29fc05da3004a2dcf8466ef969df4531
ms.sourcegitcommit: f73ea4b9116ad186817ec5cc5d5f487d49cc0cb0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "88638619"
---
# <a name="establish-a-center-of-excellence"></a>Создание центра компетенции

Эта статья предназначена для ИТ-специалистов и ИТ-руководителей. Вы узнаете, как настроить центр компетенции для бизнес-аналитики в своей организации и как это сделала корпорация Майкрософт.

Некоторые ошибочно полагают, что центр компетенции — это просто служба поддержки. Однако это далеко не так.

Как правило, центр компетенции для бизнес-аналитики — это группа специалистов, ответственных за внедрение и обслуживание платформы бизнес-аналитики. Они также отвечают за создание единого источника достоверных данных и определение набора согласованных в масштабе всей компании метрик для быстрого извлечения полезных сведений. Однако центр компетенции — это широкое понятие. Его можно реализовать по-разному, по-разному управлять им, а его структура и масштаб в каждой организации могут быть особыми. Главная цель заключается в создании надежной платформы для предоставления нужных данных и возможностей аналитики нужным людям в нужное время. В идеале он также способствует популяризации бизнес-аналитики, обучению и поддержке. В корпорации Майкрософт центр компетенции реализуется в рамках концепции _[дисциплина в центре](center-of-excellence-microsoft-business-intelligence-transformation.md#discipline-at-the-core)_ в качестве платформы бизнес-аналитики и единого источника достоверных данных.

В крупных организациях может быть несколько центров компетенции —главный центр _дополняется_ вспомогательными, часто на уровне отделов. Вспомогательный центр компетенции — это группа экспертов, разбирающихся в таксономиях и определениях и знающих, как преобразовать основные данные в информацию, имеющую смысл _для отдела_. Аналитики отделов имеют разрешения на доступ к основным данным, которым они доверяют и которые используют в собственных отчетах. Они создают решения, работающие на основе тщательно подготовленных основных измерений, фактов и бизнес-логики, которые иногда также могут дополняться наборами данных меньшего размера и бизнес-логикой на уровне отдела. Важно отметить, что вспомогательные центры компетенции всегда связаны и никогда не работают изолированно. В корпорации Майкрософт вспомогательные центры компетенции действуют в рамках концепции _[гибкость на периферии](center-of-excellence-microsoft-business-intelligence-transformation.md#flexibility-at-the-edge)_ .

Чтобы такой расширенный сценарий имел успех, отделам _приходится платить_, то есть инвестировать средства в основной центр компетенции. В результате им не приходится беспокоиться о том, что их "несправедливо обделяют" или что их требованиям отдают меньший приоритет.

Для поддержки этого сценария основной центр компетенции должен масштабироваться в соответствии с потребностями отделов. При добавлении нескольких наборов данных начинает сказываться экономия за счет масштаба. В корпорации Майкрософт быстро стало очевидно, что централизованная работа выгоднее с экономической точки зрения и скорее приносит результаты. При введении каждой новой предметной области мы получали еще большую экономию за счет масштаба, что способствовало развитию платформы и лежащей в ее основе культуры данных.

Рассмотрим пример. Наша платформа бизнес-аналитики предоставляет основные измерения, факты и бизнес-логику для финансового отдела, отделов продаж и маркетинга. Она также определяет сотни ключевых показателей эффективности. Аналитику из отдела, занимающегося платформой Power Platform, необходимо подготовить панель мониторинга для руководства. Некоторые ключевые показатели эффективности, такие как доход и конвейеры, поступают непосредственно из платформы бизнес-аналитики. Другие, однако, связаны с более конкретными потребностями бизнеса. Одним из таких ключевых показателей эффективности является принятие пользователями такой функции Power BI, как потоки данных. Поэтому аналитик создает [составную модель](composite-model-guidance.md) Power BI, чтобы интегрировать основные данные платформы бизнес-аналитики с данными отдела. Затем он добавляет бизнес-логику для определения ключевых показателей эффективности своего отдела. Наконец, он создает панель мониторинга для руководства на основе новой модели, которая использует ресурсы центра компетенции компании, дополненные локальными знаниями и данными.

Важно отметить, что разделение ответственности между основным и вспомогательными центрами компетенции позволяет аналитикам отделов сосредоточиться на реализации новых возможностей, а не на управлении платформой данных. Иногда между вспомогательными и основным центрами компетенции может даже возникать взаимовыгодная связь. Например, вспомогательный центр компетенции может определить новые метрики, которые, доказав свою полезность для отдела, становятся основными метриками для всей компании и теперь поддерживаются основным центром компетенции.

## <a name="bi-platform"></a>Платформа бизнес-аналитики

В вашей организации центр компетенции может называться по-другому, например группой или отделом бизнес-аналитики. Важно не название, а суть. Если у вас нет такой официально оформленной команды, рекомендуем вам создать ее, включив в нее основных экспертов по бизнес-аналитике, которые будут реализовывать платформу бизнес-аналитики.

В корпорации Майкрософт центр компетенции называется платформой бизнес-аналитики. В нем участвует множество групп заинтересованных лиц, представляющих различные подразделения компании, такие как финансовый отдел, отделы продаж и маркетинга. Его целью является реализация [общих возможностей](#shared-capabilities) и [адресной доставки](#dedicated-deliveries).

:::image type="content" source="media/center-of-excellence-establish/business-intelligence-platform-operating-model.png" alt-text="Схема, на которой представлены общие возможности и адресная доставка, описываемые в следующих разделах":::

### <a name="shared-capabilities"></a>Возможности общего доступа

Общие возможности требуются для создания и эксплуатации платформы бизнес-аналитики. Они охватывают все группы заинтересованных лиц, которые инвестируют в платформу. К их числу относятся следующие группы.

- **Проектирование основной платформы**. При проектировании платформы бизнес-аналитики мы использовали инженерный подход. Она представляет собой набор платформ, поддерживающих прием данных, обработку с целью обогащения данных и доставку этих данных в рамках семантических моделей бизнес-аналитики для использования аналитиками. Инженеры несут ответственность за техническое проектирование и реализацию возможностей основной платформы бизнес-аналитики. Например, они проектируют и реализуют конвейеры данных.
- **Инфраструктура и размещение**. ИТ-инженеры несут ответственность за подготовку всех служб Azure и управление ими.
- **Поддержка и эксплуатация**. Эта группа отвечает за работу платформы. Служба поддержки отслеживает потребности пользователей, например необходимые разрешения на доступ к данным. Эксплуатационная группа обеспечивает работу платформы в соответствии с соглашениями об уровне обслуживания и оповещает о задержках и сбоях.
- **Управление выпусками**. Руководители технических программ отвечают за выпуск изменений. Изменения могут варьироваться от обновлений платформ до запросов на изменение семантических моделей бизнес-аналитики. Это последняя линия обороны, которая гарантирует, что изменения не навредят работе.

### <a name="dedicated-deliveries"></a>Адресная доставка

Для каждой группы заинтересованных лиц предусмотрена специальная группа доставки. Как правило, она состоит из инженера по обработке данных, инженера-аналитика и руководителя технической программы, работа которых финансируется соответствующей группой заинтересованных лиц.

## <a name="bi-team-roles"></a>Роли групп бизнес-аналитики

В корпорации Майкрософт за работу платформы бизнес-аналитики отвечают масштабируемые группы специалистов. Они сопоставлены с выделенными и общими ресурсами. В настоящее время имеются следующие роли.

- **Руководители программ**. Руководители программ — это выделенный ресурс. Они выступают в качестве основных контактных лиц для связи между группой бизнес-аналитики и заинтересованными лицами. Именно они отвечают за оформление бизнес-требований заинтересованных лиц в виде технической спецификации. Они также определяют приоритетность доставки результатов заинтересованным лицам.
- **Руководители баз данных**. Это выделенный ресурс, ответственный за ввод новых наборов данных в централизованное хранилище данных. Ввод набора данных может включать определение согласованных измерений, добавление бизнес-логики и настраиваемых атрибутов, а также стандартизацию имен и форматирования.
- **Руководители по аналитике**. Это выделенный ресурс, отвечающий за проектирование и разработку семантических моделей бизнес-аналитики. Они стараются реализовать единообразную архитектуру с использованием стандартных имен и форматирования. Важной частью их обязанностей является оптимизация производительности.
- **Эксплуатация и инфраструктура**. Это общий ресурс, отвечающий за управление заданиями и конвейерами данных. Он также отвечает за управление подписками Azure, емкостями Power BI, виртуальными машинами и шлюзами данных.
- **Поддержка**. Это общий ресурс, отвечающий за написание документации, организацию обучения, оповещение об изменениях в семантических моделях бизнес-аналитики и ответы на вопросы пользователей.

## <a name="governance-and-compliance"></a>Система управления и соответствие требованиям

Для каждой группы заинтересованных лиц руководители программ обеспечивают межпрограммное управление и контроль. Их главной целью является получение реальной выгоды для бизнеса от вложений в ИТ и снижение рисков. Регулярно проводятся собрания организационного комитета, на которых обсуждается ход работ и утверждаются основные инициативы.

## <a name="grow-your-own-community"></a>Развитие своего сообщества

Создайте и развивайте сообщество в своей организации с помощью следующих действий.

- Проводите регулярные мероприятия в рабочее время, на которых команде бизнес-аналитики можно будет задать вопросы, внести предложения, поделиться идеями и даже покритиковать их.
- Создайте канал в Teams для предоставления поддержки и призовите всех сотрудников задавать вопросы и отвечать на них.
- Создайте и продвигайте неформальные группы пользователей и поощряйте сотрудников вступать в них и участвовать в их работе.
- Проводите более формальное обучение по конкретным продуктам и по самой платформе бизнес-аналитики. Рассмотрите возможность проведения семинара [Панель мониторинга Power BI за один день](https://powerbi.microsoft.com/diad/), который доступен в виде бесплатного комплекта курсов и является отличным способом познакомить сотрудников с Power BI.

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения по этим вопросам см. в следующих ресурсах.

- [Архитектура решения BI в центре компетенции](center-of-excellence-business-intelligence-solution-architecture.md)
- У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
- У вас есть предложения? [Идеи по улучшению Power BI](https://ideas.powerbi.com/)

В [следующей статье из этой серии](center-of-excellence-business-intelligence-solution-architecture.md) вы узнаете об архитектуре решения бизнес-аналитики в центре компетенции и различных связанных технологиях.

### <a name="professional-services"></a>Профессиональные услуги

Также можно обратиться за помощью к сертифицированным партнерам по Power BI, которые помогут вашей организации в настройке центра компетенции. Они могут предоставить вам обучение или аудит данных по разумной цене. Чтобы обратиться к партнеру по Power BI, посетите [портал партнеров Power BI](https://powerbi.microsoft.com/partners/).

Вы также можете привлекать опытных партнеров-консультантов. Они помогут вам [оценить](https://appsource.microsoft.com/marketplace/consulting-services?product=power-bi&serviceType=assessment&country=ALL&region=ALL), [рассчитать](https://appsource.microsoft.com/marketplace/consulting-services?product=power-bi&serviceType=proof-of-concept&country=ALL&region=ALL) или [реализовать](https://appsource.microsoft.com/marketplace/consulting-services?product=power-bi&serviceType=implementation&country=ALL&region=ALL&page=1) Power BI.
