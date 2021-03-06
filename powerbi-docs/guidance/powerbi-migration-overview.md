---
title: Общие сведения о миграции в Power BI
description: Узнайте, как спланировать и выполнить миграцию из другого стороннего средства бизнес-аналитики в Power BI.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: aa17e6293a4bd946b1d6b7acad45623fa2393c57
ms.sourcegitcommit: 84e75a2cd92f4ba4e0c08ba296b981b79d6d0e82
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88803517"
---
# <a name="power-bi-migration-overview"></a>Общие сведения о миграции в Power BI

Клиенты все чаще используют Power BI для формирования культуры данных, которая позволяет включать возможности управляемой самостоятельной бизнес-аналитики (SSBI) для рационализации доставки корпоративных решений бизнес-аналитики и устранения экономических проблем. В этой серии статей по миграции в Power BI содержатся рекомендации по планированию и проведению миграции из стороннего средства бизнес-аналитики в Power BI.

Доступны следующие статьи в серии по миграции в Power BI:

1. Общие сведения о миграции в Power BI (эта статья)
1. [Подготовка к миграции в Power BI](powerbi-migration-pre-migration-steps.md)
1. [Сбор требований для миграции в Power BI (стадия 1)](powerbi-migration-requirements.md)
1. [Планирование развертывания для миграции в Power BI (стадия 2)](powerbi-migration-planning.md)
1. [Проведение подтверждения концепции для миграции в Power BI (стадия 3)](powerbi-migration-proof-of-concept.md)
1. [Создание содержимого для миграции в Power BI (стадия 4)](powerbi-migration-create-validate-content.md)
1. [Развертывание в Power BI (стадия 5)](powerbi-migration-deploy-support-monitor.md)
1. [Знакомство с пользовательскими миграциями в Power BI](powerbi-migration-learn-from-customers.md)

В этом контексте следует принять во внимание два предположения: сейчас в вашей организации используется устаревшая платформа бизнес-аналитики, поэтому было решено официально перенести содержимое и пользователей в Power BI. Основной темой этих статей является миграция в службу Power BI. В отношении клиентов национальных облаков могут действовать дополнительные рекомендации помимо тех, которые рассматриваются в этой серии статей.

На следующей схеме показаны четыре основных этапа развертывания Power BI в организации.

:::image type="content" source="media/powerbi-migration-overview/migrate-to-powerbi-high-level-overview.png" alt-text="Изображение четырех основных этапов, описанных в следующей таблице.":::

|Этап|Описание|
|--------|-----------|
|![Фаза 1.](media/common/icon-01-red-30x30.png)|**Настройка и оценка Power BI.** На первом этапе происходит формирование начальной архитектуры Power BI. Здесь проводится планирование предварительного развертывания и управления, а также выполняются оценки Power BI, включая анализ рентабельности инвестиций и затрат и выгод.|
|![Этап 2.](media/common/icon-02-red-30x30.png)|**Быстрое создание решений в Power BI.** На втором этапе авторы самостоятельной бизнес-аналитики могут начать использовать и оценивать Power BI в соответствии со своими потребностями и быстро получать выгоду от работы с Power BI. В действиях на этапе 2 придается большое значение гибкости и ускоренной материальной отдаче для бизнеса, что очень важно для получения согласия на выбор нового средства бизнес-аналитики, такого как Power BI. Поэтому на диаграмме показано, что действия на этапе 2 выполняются параллельно с действиями по миграции на этапе 3.|
|![Этап 3.](media/common/icon-03-red-30x30.png)|**Перенос ресурсов бизнес-аналитики с устаревшей платформы в Power BI.** На третьем этапе происходит миграция в Power BI. Именно этот процесс находится в центре внимания этой серии статей о миграции Power BI. В следующем разделе рассматриваются пять стадий миграции.|
|![Этап 4.](media/common/icon-04-red-30x30.png)|**Внедрение, отслеживание Power BI и управление этой службой.** На последнем этапе выполняются текущие действия, такие как формирование культуры данных, взаимодействие и обучение. Они оказывают серьезное воздействие на эффективную реализацию Power BI. Очень важно иметь подходящие для организации политики и процессы управления и обеспечения безопасности, а также возможности аудита и мониторинга, которые позволят вам расширяться, развиваться и постоянно совершенствоваться.|

> [!IMPORTANT]
> Официальная миграция в Power BI почти всегда происходит параллельно с разработкой нового решения Power BI. _Решение Power BI_ является универсальным термином, охватывающим использование как данных, так и отчетов. Один файл Power BI Desktop (PBIX-файл) может содержать модель данных или отчет либо и то, и другое. В целях многократного использования данных рекомендуется [отделить модель данных от отчетов](../guidance/report-separate-from-model.md), но делать это необязательно.
>
> Использование Power BI для написания новых требований во время планирования и проведения официальной миграции поможет получить поддержку заинтересованных лиц. На одновременно выполняющихся этапах авторы содержимого приобретают практический и реальный опыт работы с Power BI.

## <a name="five-stages-of-a-power-bi-migration"></a>Пять стадий миграции в Power BI

На приведенном на диаграмме этапе 3 происходит миграция в Power BI. Здесь выделяют пять общих стадий.

:::image type="content" source="media/powerbi-migration-overview/migrate-to-powerbi-five-stages.png" alt-text="Изображение стадий миграции в Power BI, которые описываются далее.":::

На предыдущей диаграмме показаны следующие стадии:

- [Шаги по подготовке к миграции](#pre-migration-steps)
- [Стадия 1. Сбор требований и определение приоритетов](#stage-1-gather-requirements-and-prioritize)
- [Стадия 2. Планирование развертывания](#stage-2-plan-for-deployment)
- [Стадия 3. Проведение подтверждения концепции](#stage-3-conduct-proof-of-concept)
- [Стадия 4. Создание и проверка содержимого](#stage-4-create-and-validate-content)
- [Стадия 5. Развертывание, поддержка и мониторинг](#stage-5-deploy-support-and-monitor)

### <a name="pre-migration-steps"></a>Шаги по подготовке к миграции

Шаги, выполняемые перед миграцией, включают действия, которые следует учесть перед началом проекта по переносу содержимого с устаревшей платформы бизнес-аналитики в Power BI. Как правило, это начальное планирование развертывания на уровне клиента. Дополнительные сведения об этих действиях см. в статье [Подготовка к миграции в Power BI](powerbi-migration-pre-migration-steps.md).

### <a name="stage-1-gather-requirements-and-prioritize"></a>Этап 1. Сбор требований и определение приоритетов

На стадии 1 основное внимание уделяется сбору информации и планированию миграции одного решения. Этот процесс должен быть итеративным с разумным объемом работ. Выходными данными стадии 1 являются приоритетные наборы отчетов и данных, подлежащих миграции. Однако для полной оценки объема работ необходимо выполнить дополнительные действия на стадиях 2 и 3. Дополнительные сведения о действиях на стадии 1 см. в статье [Сбор требований для миграции в Power BI](powerbi-migration-requirements.md).

### <a name="stage-2-plan-for-deployment"></a>Этап 2. Планирование развертывания

На стадии 2 делается упор на способах реализации требований, определенных на стадии 1, для каждого решения. Выходными данными стадии 2 является максимально возможное число специфических особенностей, которыми следует руководствоваться в этом итеративном и нелинейном процессе. Процесс создания подтверждения концепции (на стадии 3) может выполняться параллельно с этой стадией. Даже при создании решения (на стадии 4) может появиться дополнительная информация, которая повлияет на планирование развертывания. При планировании развертывания на стадии 2 во внимание принимается уровень решения и также учитываются положения, уже утвержденные на уровне организации. Дополнительные сведения о действиях на стадии 2 см. в статье [Планирование развертывания для миграции в Power BI](powerbi-migration-planning.md).

### <a name="stage-3-conduct-proof-of-concept"></a>Этап 3. Проведение подтверждения концепции

На стадии 3 рассматриваются вопросы скорейшего устранения неизвестных проблем и нейтрализации рисков. Техническое подтверждение концепции (POC) помогает проверить допущения и может выполняться итеративно и параллельно с планированием развертывания (стадия 2). Выходными данными этой стадии является решение Power BI, имеющее узкую сферу применения. Обратите внимание, что мы не заинтересованы в том, чтобы проверка концепции была одноразовым действием. Однако, скорее всего, на стадии 4 потребуется провести дополнительную работу, чтобы сделать решение готовым к развертыванию в производственной среде. В этом плане это решение можно называть прототипом, пилотной версией, макетом или стартом либо минимально жизнеспособным продуктом (MVP). Проверка концепции требуется не всегда, и ее можно провести неофициально. Дополнительные сведения о действиях на стадии 3 см. в статье [Проведение подтверждения концепции для миграции в Power BI](powerbi-migration-proof-of-concept.md).

### <a name="stage-4-create-and-validate-content"></a>Этап 4. Создание и проверка содержимого

На стадии 4 выполняются действия по преобразованию подтверждения концепции в готовое к работе решение. Выходными данными этой стадии является завершенное решение Power BI, которое было проверено в среде разработки. Оно должно быть готово к развертыванию на стадии 5. Дополнительные сведения о действиях на стадии 4 см. в статье [Создание содержимого для миграции в Power BI](powerbi-migration-create-validate-content.md).

### <a name="stage-5-deploy-support-and-monitor"></a>Стадия 5. Развертывание, поддержка и мониторинг

Основной целью стадии 5 является развертывание нового решения Power BI в рабочей среде. Выходными данными этой стадии является рабочее решение, активно используемое бизнес-пользователями. При применении методов гибкой разработки допускается наличие некоторых запланированных улучшений, которые будут реализованы в будущем. В зависимости от того, насколько хорошо вы знакомы с Power BI, можно выбрать поэтапное развертывание, чтобы минимизировать риски и обеспечить непрерывную работу пользователей. Или можно изначально развернуть решение для небольшой группы пилотных пользователей. На этой стадии и в рамках непрерывной работы решения большое значение имеют поддержка и мониторинг. Дополнительные сведения о действиях на стадии 5 см. в статье [Миграция в Power BI](powerbi-migration-deploy-support-monitor.md).

> [!TIP]
> Большинство концепций, рассматриваемых в этой серии статей о миграции в Power BI, применимы и к стандартному проекту внедрения Power BI.

## <a name="consider-migration-reasons"></a>Принятие во внимание причин миграции

Создание продуктивной и здоровой культуры данных является основной целью многих организаций. Power BI является отличным инструментом для ее достижения. Ниже приведены три распространенных причины, которые могут быть приняты по внимание при миграции в Power BI.

- **Включение управляемой самостоятельной бизнес-аналитики** путем внедрения новых функций, которые расширяют возможности сообщества пользователей самостоятельной бизнес-аналитики. Power BI предоставляет более широкий доступ к информации и данным, влияющим на принятие решений, и в то же время позволяет в меньшей степени полагаться на специальные навыки, которые зачастую могут отсутствовать.
- **Рационализация доставки корпоративной бизнес-аналитики** для удовлетворения требований, которые невозможно выполнить с помощью существующих средств бизнес-аналитики, снижения уровня сложности, сокращения стоимости владения и стандартизации нескольких используемых в настоящее время инструментов бизнес-аналитики.
- **Устранение экономического давления** в целях повышения производительности с меньшим объемом ресурсов, временных затрат и числом сотрудников.

## <a name="achieve-power-bi-migration-success"></a>Успешная миграция в Power BI

Каждая миграция имеет свои особенности. Они могут зависеть от организационной структуры, стратегий использования данных, уровня развития системы управления данными и целей организации. Однако существует ряд практик, которых постоянно придерживаются наши клиенты, успешно выполнившие миграцию в Power BI.

- **Спонсор из руководящего звена.** На ранних этапах процесса определите спонсора из числа руководителей. Этот человек должен активно поддерживать бизнес-аналитику в организации и вносить личный вклад в достижение положительного результата миграции. В идеале этот спонсор должен иметь высшие полномочия и нести конечную ответственность за результаты, связанные с Power BI.
- **Обучение, поддержка и взаимодействие.** Поймите и согласитесь, что это больше, чем просто технологическая инициатива. В любом аналитическом проекте задействованы люди, поэтому рекомендуется уже на ранних этапах предусмотреть возможности обучения и поддержки пользователей. Кроме того, создайте план взаимодействия, в котором всем заинтересованным сторонам четко и ясно объясняется, что и почему происходит, а также ставятся реалистичные цели. Обязательно включите в него механизм обратной связи для сбора данных от заинтересованных лиц.
- **Мгновенная выгода.** Сначала отдайте приоритет значимым элементам, которые представляют ощутимую ценность для бизнеса и являются актуальными. Вместо того чтобы всегда переносить отчеты именно так, как они отображаются на устаревшей платформе бизнес-аналитики, сосредоточьтесь на бизнес-вопросе, ответ на который должен быть получен из отчета, включая действия, которые должны быть предприняты.
- **Модернизации и улучшения.** Будьте готовы переосмыслить прежние методы выполнения задач. После миграции вам может быть доступно множество улучшений. Например, можно отказаться от подготовки данных вручную или перенести бизнес-правила, которые были ограничены одним отчетом. Если соответствующие усилия могут считаться оправданными, рассмотрите возможность рефакторинга, модернизации и консолидации существующих решений. Можно объединить несколько отчетов в один или исключить устаревшие артефакты, которые не использовались в течение некоторого времени.
- **Непрерывное обучение.** Будьте готовы использовать поэтапный подход при непрерывном изучении и адаптации. Работайте короткими итеративными циклами, чтобы быстро вносить ценный вклад. Регулярно проводите небольшие POC, чтобы снизить риск возникновения неизвестных проблем, проверить предположения и узнать о новых возможностях. Так как Power BI — это облачная служба, которая ежемесячно обновляется, важно идти в ногу с развитием событий и корректировать курс, когда это необходимо.
- **Сопротивление изменениям.** Поймите, что уровень сопротивления изменениям может быть разным; некоторые пользователи будут отказываться от изучения нового инструмента. Кроме того, некоторые специалисты, посвятившие значительное время и затратившие усилия на получение опыта работы с другим средством бизнес-аналитики, могут почувствовать угрозу снятия с должности. Будьте готовы к такой ситуации, так как она может привести к внутриполитической борьбе, особенно в организациях с высокой степенью децентрализации.
- **Ограничения.** Реалистично подходите к составлению планов миграции — учитывайте вопросы финансирования, оценки времени, а также принимайте во внимание роли и обязанности каждого участника.

## <a name="acknowledgments"></a>Благодарности

Автор этой серии статей — Мелисса Коутс (Melissa Coate), специалист MVP по платформе данных и владелец сайта [Coates Data Strategie](https://www.coatesdatastrategies.com/). Участники и рецензенты: Марк Регера (Marc Reguera), Венкатеш Титте (Venkatesh Titte), Патрик Баумгартнер (Patrick Baumgartner), Тамер Фараг (Tamer Farag), Ричард Ткачук (Richard Tkachuk), Мэтью Рош (Matthew Roche), Адам Сакстон (Adam Saxton), Крис Уэбб (Chris Webb), Марк Вэйллэнкорт (Mark Vaillancourt), Даниэль Рубиоло (Daniel Rubiolo), Дэвид Иземингер (David Iseminger) и Питер Майерс (Peter Myers).

## <a name="next-steps"></a>Дальнейшие действия

В [следующей статье в этой серии по миграции в Power BI](powerbi-migration-pre-migration-steps.md)содержатся сведения о шагах, выполняемых перед миграцией в Power BI.

Другие полезные ресурсы:

- [Преобразование бизнес-аналитики с Майкрософт](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [Технический документ по планированию развертывания Power BI Enterprise](https://aka.ms/PBIEnterpriseDeploymentWP)
- [Миграция отчетов SSRS в Power BI](migrate-ssrs-reports-to-power-bi.md)
- У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
- У вас есть предложения? [Идеи по улучшению Power BI](https://ideas.powerbi.com/)

Вы можете обратиться к опытным партнерам по Power BI, которые помогут вашей организации выполнить процесс переноса. Чтобы обратиться к партнеру по Power BI, посетите [портал партнеров Power BI](https://powerbi.microsoft.com/partners/).
