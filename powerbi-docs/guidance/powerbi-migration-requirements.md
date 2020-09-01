---
title: Сбор требований для миграции в Power BI
description: Рекомендации по сбору требований и определению их приоритетности при миграции в Power BI.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: 29b821dc44f7eacb07f0df31100df2ff837c2189
ms.sourcegitcommit: 84e75a2cd92f4ba4e0c08ba296b981b79d6d0e82
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88803393"
---
# <a name="gather-requirements-to-migrate-to-power-bi"></a>Сбор требований для миграции в Power BI

В этой статье описывается **стадия 1**, на которой происходит сбор требований и определение их приоритетности при миграции в Power BI.

:::image type="content" source="media/powerbi-migration-requirements/migrate-to-powerbi-stage-1.png" alt-text="Изображение стадий миграции в Power BI. Для вопросов, рассматриваемых в этой статье, выделена стадия 1.":::

> [!NOTE]
> Полное описание приведенного выше изображения см. в статье с [общими сведениями о миграции в Power BI](powerbi-migration-overview.md).

Главный акцент на стадии 1 делается на сборе данных и планировании отдельного решения, которое будет перенесено в Power BI.

Выходными данными стадии 1 являются подробные требования, определенные в качестве приоритетных. Однако для полной оценки объема работы необходимо выполнить дополнительные действия на стадиях 2 и 3.

> [!IMPORTANT]
> На стадиях 1–5 реализуются действия, связанные с одним конкретным решением. На уровне организации или клиента существуют решения и действия, которые влияют на процесс на уровне решения. Некоторые из этих действий по планированию более высокого уровня рассматриваются в статье с [общими сведениями о миграции в Power BI](powerbi-migration-overview.md). В случае необходимости отложите принятие решений на организационном уровне для обеспечения эффективности и согласованности.

> [!TIP]
> Большинство тем, обсуждаемых в этой статье, применимы и к стандартному проекту реализации Power BI.

## <a name="compile-requirements"></a>Компиляция требований

Существующие артефакты бизнес-аналитики, собранные на [шагах по подготовке к миграции](powerbi-migration-pre-migration-steps.md), становятся входными данными для требований нового решения, которое будет создано в Power BI. При сборе требований необходимо понимать текущее состояние, а также знать, какие элементы пользователи хотели бы видеть измененными или оптимизированными после модернизации отчетов в Power BI. Подробные требования будут полезны при планировании развертывания решения на [стадии 2](powerbi-migration-planning.md), во время создания подтверждения концепции на [стадии 3](powerbi-migration-proof-of-concept.md), а также при создании готового к развертыванию в рабочей среде решения на [стадии 4](powerbi-migration-create-validate-content.md).

### <a name="gather-report-requirements"></a>Сбор требований к отчетам

Скомпилируйте подробную информацию об отчетах в удобной форме, например:

- **Назначение, аудитория и ожидаемое действие.** Определите назначение и бизнес-процесс, применимые к каждому отчету, а также аудиторию, аналитический рабочий процесс и ожидаемое действие, выполняемое потребителями отчетов.
- **Как потребители используют отчет.** Предложите потребителям отчетов ознакомиться с существующим отчетом, а затем пообщайтесь с ними, чтобы точно понять, каким образом они с ним работают. Вы можете узнать, что некоторые элементы отчета можно исключить или улучшить в новой версии Power BI. Этот процесс требует дополнительных временных затрат, но он ценен для критически важных или часто используемых отчетов.
- **Владелец и профильный специалист.** Определите владельца отчета и всех профильных специалистов, имеющих отношение к отчету или данным. В будущем они могут стать владельцами нового отчета Power BI. Включите любые конкретные требования к управлению изменениями (как правило, они разные для решений, управляемых ИТ-отделом, и решений, управляемых бизнес-специалистами), а также утверждения и подписания, которые потребуются при внесении изменений в будущем.
- **Метод доставки содержимого.** Уточните ожидания потребителей отчетов, связанные с доставкой содержимого. Это может быть интерактивное выполнение по запросу, внедренное в пользовательское приложение, или доставка по расписанию с помощью подписки по электронной почте. Кроме того, могут существовать требования по запуску уведомлений об оповещениях.
- **Требования к взаимодействию.** Определите _обязательные_ и _необязательные, но полезные_ требования к взаимодействию, такие как фильтры или детализация.
- **Источники данных.** Убедитесь, что обнаружены все требуемые для отчета источники данных и понятны потребности в задержке данных (актуальность данных). Определите требования к историческим данным, тенденциям и моментальным снимкам данных для каждого отчета, чтобы их можно было привести в соответствие с требованиями к данным. В дальнейшем при проверке нового отчета с его исходными данными также может быть полезна документация по источникам данных.
- **Требования безопасности.** Уточните требования безопасности (такие как разрешенные читатели, разрешенные редакторы, а также требования безопасности на уровне строк), включая любые исключения в отношении стандартной безопасности организации. Задокументируйте любые потребности для обеспечения надлежащего уровня конфиденциальности данных и степени соответствия нормативным требованиям.
- **Вычисления, ключевые показатели эффективности и бизнес-правила.** Выявите и задокументируйте все вычисления, ключевые показатели эффективности и бизнес-правила, которые в настоящее время определены в рамках существующего отчета, чтобы их можно было привести в соответствие с требованиями к данным.
- **Требования к удобству использования, макету и отображению данных.** Определите конкретные требования к удобству использования, расположению и отображению, связанные с визуализацией данных, группировкой и сортировкой, а также условной видимостью. Включите все конкретные рекомендации, связанные с доставкой решений на мобильные устройства.
- **Потребности в печати и экспорте.** Определите, существуют ли какие-либо особые требования к печати, экспорту или формированию макета с пиксельной точностью. Они влияют на выбор наиболее подходящего типа отчета (например, Power BI, Excel или отчет с разбивкой на страницы). Имейте в виду, что потребители отчетов обычно предпочитают использовать привычные методики, поэтому не бойтесь бросить вызов их образу мышления. В беседах с ними обязательно делайте акцент на _улучшениях_, а не _изменениях_.
- **Риски или проблемы.** Определите, существуют ли другие технические или функциональные требования к отчетам, а также любые риски или опасения в отношении представляемой в них информации.
- **Открытые проблемы и элементы невыполненной работы.** Определите направления будущего обслуживания, известные проблемы или отложенные запросы, которые можно добавить в невыполненную работу.

> [!TIP]
> Рассмотрите возможность ранжирования требований и их классификации как _обязательных_ или _необязательных, но полезных_. Часто потребители заранее просят предоставить все, что им может потребоваться, потому что считают, что эта возможность сделать запрос может оказаться их единственным шансом. Кроме того, при решении приоритетных задач в рамках нескольких итераций необходимо предоставлять заинтересованным сторонам информацию о невыполненной работе. Она будет полезна при взаимодействии, принятии решений и отслеживании ожидающих выполнения обязательств.

### <a name="gather-data-requirements"></a>Сбор требований к данным

Скомпилируйте подробные сведения, касающиеся данных, например:

- **Существующие запросы.** Определите, есть ли существующие запросы к отчетам или хранимые процедуры, которые могут использоваться [моделью DirectQuery](../connect-data/desktop-use-directquery.md) или [составной моделью](../transform-model/desktop-composite-models.md) либо могут быть преобразованы в модель импорта.
- **Типы источников данных.** Скомпилируйте типы необходимых источников данных, включая централизованные источники данных (например, корпоративное хранилище данных), а также нестандартные источники данных (например, неструктурированные файлы или файлы Excel, которые дополняют корпоративные источники данных в целях составления отчетов). Кроме того, для подключения к [шлюзу данных](../connect-data/service-gateway-onprem.md) важно определить место расположения источников данных.
- **Требования к структуре данных и очистке.** Определите структуру данных для каждого источника данных, а также оцените степень необходимости действий по [очистке данных](../transform-model/desktop-query-overview.md).
- **Интеграция данных.** Определите способы обработки интеграции данных при наличии нескольких источников данных, а также варианты определения [связей](../transform-model/desktop-create-and-manage-relationships.md) между каждой таблицей модели. Выявите конкретные элементы данных, необходимые для упрощения модели и [уменьшения ее размера](import-modeling-data-reduction.md).
- **Приемлемая задержка данных.** Определите требования к задержке данных для каждого источника данных. Это повлияет на принятие решений о том, какой [режим хранения данных](../transform-model/desktop-storage-mode.md) следует использовать. Кроме того, важно знать частоту обновления данных для таблиц модели импорта.
- **Объем и масштабируемость данных.** Оцените ожидаемые объемы данных, которые будут учитываться при принятии решений о поддержке [больших моделей](/admin/service-premium-large-models.md) и проектировании моделей DirectQuery или [составных моделей](../transform-model/desktop-composite-models.md). Важно также учитывать необходимость потребности в исторических данных. Для больших наборов данных также следует определить правила [добавочного обновления данных](../admin/service-premium-incremental-refresh.md).
- **Меры, ключевые показатели эффективности и бизнес-правила.** Оцените требования к мерам, ключевым показателям эффективности и бизнес-правилам. Они повлияют на принятие решений о месте применения логики: в наборе данных или процессе интеграции данных.
- **Основные данные и каталог данных.** Определите наличие проблем с основными данными, требующих внимания. Определите, подходит ли интеграция с корпоративным каталогом данных для улучшения возможностей обнаружения, доступа к определениям или создания соответствующей терминологии, принятой в организации.
- **Безопасность и конфиденциальность данных.** Определите наличие особых соображений относительно безопасности или конфиденциальности данных для наборов данных, в том числе наличие требований [безопасности на уровне строк](../admin/service-admin-rls.md).
- **Открытые проблемы и элементы невыполненной работы.** Добавьте в невыполненную работу известные проблемы, известные недостатки качества данных, направления будущего обслуживания или отложенные запросы.

> [!IMPORTANT]
> Многократного использования данных можно достичь с помощью [общих наборов данных](../connect-data/service-datasets-share.md), которые при необходимости можно [сертифицировать](../connect-data/service-datasets-certify.md) для подтверждения надежности и улучшения возможности обнаружения. [Потоки данных](../transform-model/service-dataflows-overview.md) позволяют сократить повторяющуюся логику подготовки данных в нескольких наборах данных. Потоки данных также могут значительно снизить нагрузку на исходные системы, так как данные извлекаются реже — несколько наборов данных затем могут импортировать данные из потока данных.

## <a name="identify-improvement-opportunities"></a>Определение возможностей улучшения.

В большинстве случаев происходят некоторые изменения и улучшения. В редких ситуациях прямая миграция "одна к одной" выполняется без оптимизаций или совершенствований. Существует три типа усовершенствований, которые следует принять во внимание.

- **Консолидация отчетов.** Схожие отчеты можно объединять с помощью таких методов, как фильтры, закладки или персонализация. Наличие небольшого количества более гибких отчетов может значительно повысить эффективность работы пользователей отчетов. Рассмотрите возможность оптимизации наборов данных для [функции "Вопросы и ответы" (с запросами на естественном языке)](../natural-language/q-and-a-best-practices.md), чтобы предоставить потребителям отчетов еще больший уровень гибкости и позволить им создавать собственные визуализации.
- **Улучшения эффективности.** Во время сбора требований часто можно выявить моменты, требующие улучшений. Это могут быть, например, случаи компиляции данных вручную или необходимость упрощения рабочего процесса. Значительную роль в процессе замены действий, выполняемых в данный момент вручную, может сыграть [Power Query](../transform-model/desktop-query-overview.md). Если специалисты по анализу данных регулярно выполняют одни и те же действия по очистке и подготовке данных, повторяющиеся шаги по подготовке данных Power Query могут существенно сократить время и уменьшить количество ошибок.
- **Централизация модели данных.** Достоверный и сертифицированный набор данных является основой управляемой самостоятельной бизнес-аналитики. В этом случае управление данными осуществляется один раз, и специалисты по анализу могут гибко использовать и дополнять эти данные в соответствии с конкретными требованиями к отчетам и анализу.

> [!NOTE]
> Дополнительные сведения о централизации моделей данных см. в разделах [Дисциплина в центре ](center-of-excellence-microsoft-business-intelligence-transformation.md#discipline-at-the-core) и [Гибкость на периферии](center-of-excellence-microsoft-business-intelligence-transformation.md#flexibility-at-the-edge).

## <a name="prioritize-and-assess-complexity"></a>Определение приоритетов и оценка сложности

На этой стадии доступен первоначальный набор данных с определенными требованиями. При определении приоритета первоначального набора артефактов бизнес-аналитики, готовых к миграции, отчеты и данные следует рассматривать как совокупно, так и независимо друг от друга.

Установите отчеты с высоким приоритетом, в число которых могут входить следующие:

- отчеты, значительно повышающие ценность бизнеса:
- часто выполняющиеся отчеты;
- отчеты, необходимые высшему руководству;
- отчеты с разумным уровнем сложности (для повышения вероятности успеха во время начальной миграции).

Определите данные с высоким приоритетом, в число которых могут входить следующие:

- данные, содержащие важные элементы данных;
- стандартные данные организации, которые используются во многих случаях;
- данные, используемые для создания общего набора данных для многократного использования отчетами и многими авторами отчетов;
- данные с разумным уровнем сложности (для повышения вероятности успеха во время начальной миграции).

## <a name="next-steps"></a>Дальнейшие действия

В [следующей статье в этой серии статей по миграции Power BI](powerbi-migration-planning.md) вы ознакомитесь со стадией 2, на которой планируется миграция одного решения Power BI.

Другие полезные ресурсы:

- [Преобразование бизнес-аналитики с Майкрософт](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [Технический документ по планированию развертывания Power BI Enterprise](https://aka.ms/PBIEnterpriseDeploymentWP)
- У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
- У вас есть предложения? [Идеи по улучшению Power BI](https://ideas.powerbi.com/)

Вы можете обратиться к опытным партнерам по Power BI, которые помогут вашей организации выполнить процесс переноса. Чтобы обратиться к партнеру по Power BI, посетите [портал партнеров Power BI](https://powerbi.microsoft.com/partners/).