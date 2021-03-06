---
title: Проведение подтверждения концепции для миграции в Power BI
description: Рекомендации по проведению подтверждения концепции при миграции в Power BI.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/20/2020
ms.author: v-pemyer
ms.openlocfilehash: a7b7a848aafc3a581c1a19cf34366d61ba891f86
ms.sourcegitcommit: 84e75a2cd92f4ba4e0c08ba296b981b79d6d0e82
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88803362"
---
# <a name="conductproofofconcepttomigratetopowerbi"></a>Проведение подтверждения концепции для миграции в Power BI

В этой статье описывается **стадия 3**, которая связана с проведением подтверждения концепции для снижения риска и устранения неизвестных как можно раньше при миграции в Power BI.

:::image type="content" source="media/powerbi-migration-proof-of-concept/migrate-to-powerbi-stage-3.png" alt-text="Изображение стадий миграции в Power BI. Для целей этой статьи выделена стадия 3.":::

> [!NOTE]
> Полное описание приведенного выше изображения см. в статье с [общими сведениями о миграции в Power BI](powerbi-migration-overview.md).

На стадии 3 рассматриваются вопросы скорейшего устранения неизвестных проблем и нейтрализации рисков. Техническая проверка концепции полезна при проверке допущений. Ее можно выполнять итеративно параллельно с планированием развертывания решения (описано в [стадии 2](powerbi-migration-planning.md)).

Выходные данные этой стадии представляют собой решение Power BI с ограниченной областью действия, которое устраняет начальные открытые вопросы и готово к дальнейшей доработке на [стадии 4](powerbi-migration-create-validate-content.md) для подготовки его к работе.

> [!IMPORTANT]
> Мы не утверждаем, что проверка концепции должна быть одноразовым действием. Наоборот, мы предполагаем, что это будет первой итерацией готового к использованию производственного решения. В своей организации вы можете называть это прототипом, пилотной версией, макетом, быстрым запуском или минимально жизнеспособным продуктом. Проверка концепции требуется не всегда, и ее даже можно провести неофициально.

> [!TIP]
> Большинство тем, обсуждаемых в этой статье, применимы и к стандартному проекту реализации Power BI. По мере того как ваша организация будет набираться опыта работы с Power BI, необходимость в проведении проверки концепции будет снижаться. Однако из-за высокой частоты выпусков Power BI и непрерывного добавления новых функций может потребоваться регулярное выполнение технических проверок концепций в целях обучения.

## <a name="set-poc-goals-and-scope"></a>Задачи и область действия проверки концепции

При проведении проверки концепции сосредоточьтесь на следующих задачах.

- Проверьте предположения о том, как работает функция.
- Изучите, как Power BI работает в сравнении с устаревшей платформой бизнес-аналитики.
- Подтвердите первоначальное понимание определенных требований с экспертами в предметной области.
- Создайте небольшой набор данных с реальными данными, чтобы понять и обнаружить проблемы со структурой данных, связями, типами данных и значениями данных.
- Поэкспериментируйте с выражениями синтаксиса [DAX](/dax/), используемыми в вычислениях модели, и проверьте их правильность.
- Проверьте подключение к источнику данных с помощью шлюза (если это должен быть источник шлюза).
- Проверьте обновление с помощью шлюза (если это должен быть источник шлюза).
- Проверьте настройки безопасности, включая безопасность на уровне строк, если она необходима.
- Поэкспериментируйте с макетами и косметическими решениями.
- Убедитесь, что все функциональные возможности в службе Power BI работают должным образом.

Область подтверждения концепции зависит от того, что неизвестно и какие цели необходимо согласовать с коллегами. Чтобы снизить сложность, сделайте область подтверждения концепции как можно более узкой.

Чаще всего при миграции требования хорошо известны, так как есть существующее решение, которое можно взять за отправную точку. Однако в зависимости от степени улучшений или имеющихся навыков работы в Power BI проверка концепции по-прежнему обеспечивает значительную ценность. Кроме того, быстрое создание прототипов с учетом отзывов потребителей может быть полезно для быстрого уточнения требований, особенно в случае внесения усовершенствований.

> [!IMPORTANT]
> Даже если проверка концепции включает только подмножество данных или только ограниченные визуальные элементы, очень важно провести ее от начала до конца. То есть пройти от разработки в Power BI Desktop до развертывания в рабочей области разработки в службе Power BI. Это единственный способ полностью выполнить цели подтверждения концепции. Это особенно верно, когда служба Power BI должна доставлять критически важные функции, которые раньше не использовались, например набор данных DirectQuery, использующий единый вход. Во время проверки концепции сосредоточьтесь на аспектах, в которых вы не уверены или которые хотите проверить с другими пользователями.

## <a name="handle-differences-in-power-bi"></a>Устранение различий в Power BI

Power BI можно использовать в качестве _средства на основе моделей_ или в качестве _средства на основе отчетов_. Решение на основе модели включает в себя разработку модели данных, в то время как решение на основе отчета подключается к уже развернутой модели данных.

Благодаря чрезвычайной гибкости есть некоторые аспекты, связанные с Power BI, которые могут фундаментально отличаться от устаревшей платформы бизнес-аналитики, с которой выполняется миграция.

### <a name="consider-redesigning-the-data-architecture"></a>Рассмотрите возможность перепроектирования архитектуры данных

Если выполняется миграция с устаревшей платформы бизнес-аналитики, имеющей собственный семантический слой, то создание набора данных для импорта, скорее всего, будет хорошим вариантом. Power BI лучше всего работает со структурой таблиц типа [звезда](star-schema.md). Таким образом, если старый семантический слой не является схемой типа "звезда", возможно, потребуется некоторое перепроектирование, чтобы максимально воспользоваться возможностями Power BI. Приложение усилий для определения семантического слоя, следование принципам проектирования схемы "звезда" (включая связи, часто используемые меры и понятную организационную терминологию) служат отличной отправной точкой для авторов отчетов самообслуживания.

Если вы выполняете миграцию с устаревшей платформы бизнес-аналитики, в которой отчеты ссылаются на источники реляционных данных с помощью SQL-запросов или хранимых процедур, и если вы планируете использовать Power BI в [режиме DirectQuery](../connect-data/desktop-use-directquery.md), то можно добиться переноса модели данных почти "один к одному".

> [!CAUTION]
> Если вы видите, что для одной импортируемой таблицы создается большое количество файлов Power BI Desktop, то обычно это означает, что архитектура не является оптимальной. Если вы столкнулись с такой ситуацией, определите, может ли использование [общих наборов данных](../connect-data/service-datasets-across-workspaces.md), созданных с использованием схемы [звезда](star-schema.md), дать лучший результат.

### <a name="decide-how-to-handle-dashboard-conversions"></a>Выберите способ управления преобразованиями панели мониторинга

В отрасли бизнес-аналитики панель мониторинга — это коллекция визуальных элементов, отображающая ключевые метрики на одной странице. Однако в Power BI панель мониторинга представляет собой конкретную функцию визуализации, которую можно создать только в службе Power BI. При переносе панели мониторинга из устаревшей платформы бизнес-аналитики можно выбрать один из двух вариантов.

1. Панель мониторинга устаревшей версии можно воссоздать в виде _отчета_ Power BI. Большинство отчетов создаются с помощью Power BI Desktop. Отчеты с разбивкой на страницы и отчеты Excel также являются альтернативными вариантами.
2. Панель мониторинга устаревшей версии можно воссоздать в виде _панели мониторинга_ Power BI. [Панель мониторинга](../fundamentals/service-basic-concepts.md#dashboards) — это компонент визуализации службы Power BI. Визуальные элементы панели мониторинга часто создаются путем закрепления визуальных элементов из одного или нескольких отчетов, функции "вопросы и ответы" или краткой аналитики.

> [!TIP]
> Так как панели мониторинга являются типом содержимого Power BI, не следует использовать слово _dashboard_ (панель мониторинга) в именах отчетов и панелей мониторинга.

### <a name="focus-on-the-big-picture-when-recreating-visuals"></a>При воссоздании визуальных элементов сосредоточьтесь на общей картине

Все средства бизнес-аналитики имеют свои сильные и приоритетные области. По этой причине у конкретных визуальных элементов отчета, которые вы использовали в устаревшей платформе бизнес-аналитики, может не быть близкого аналога в Power BI.

При воссоздании визуальных элементов отчета сосредоточьтесь на общих бизнес-вопросах, которые решаются с помощью отчета. Это устраняет необходимость в точном воссоздании структуры каждого визуального элемента. Хотя пользователи содержимого оценят согласованность при использовании перенесенных отчетов, очень важно не уделять слишком много времени спорам по небольшим деталям.

## <a name="next-steps"></a>Дальнейшие действия

В [следующей статье в этой серии статей по миграции Power BI](powerbi-migration-create-validate-content.md) вы ознакомитесь с этапом 4, который связан с созданием и проверкой содержимого при переходе на Power BI.

Другие полезные ресурсы:

- [Преобразование бизнес-аналитики с Майкрософт](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [Технический документ по планированию развертывания Power BI Enterprise](https://aka.ms/PBIEnterpriseDeploymentWP)
- У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
- У вас есть предложения? [Идеи по улучшению Power BI](https://ideas.powerbi.com/)

Вы можете обратиться к опытным партнерам по Power BI, которые помогут вашей организации выполнить процесс переноса. Чтобы обратиться к партнеру по Power BI, посетите [портал партнеров Power BI](https://powerbi.microsoft.com/partners/).
