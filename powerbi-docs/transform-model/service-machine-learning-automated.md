---
title: Автоматизированное машинное обучение в Power BI
description: Сведения об использовании автоматизированного машинного обучения (AutoML) в Power BI
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/18/2019
ms.author: davidi
LocalizationGroup: conceptual
ms.openlocfilehash: 481904a241abe9f5453db7ea0e83a6b92959835c
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83330573"
---
# <a name="automated-machine-learning-in-power-bi"></a>Автоматизированное машинное обучение в Power BI

Автоматизированное машинное обучение (AutoML) для потоков данных позволяет бизнес-аналитикам обучать, проверять и вызывать модели машинного обучения (ML) непосредственно из Power BI. Эта служба предоставляет простой интерфейс для создания модели машинного обучения, в которой аналитики могут указывать потоки данных для указания входных данных для обучения модели. Служба автоматически извлекает наиболее релевантные компоненты, выбирает подходящий алгоритм, настраивает и проверяет модель машинного обучения. После обучения модели Power BI автоматически создает отчет о производительности с результатами проверки. Эту модель затем можно вызвать для любых новых или обновленных данных в потоке данных.

![Экран машинного обучения](media/service-machine-learning-automated/automated-machine-learning-power-bi-01.png)

Автоматизированное машинное обучение доступно только для потоков данных, размещенных на емкостях Power BI Premium и Embedded.

## <a name="working-with-automl"></a>Работа с AutoML

[Потоки данных Power BI](service-dataflows-overview.md) позволяют самостоятельно подготавливать наборы для больших данных. Служба AutoML интегрирована в потоки данных и позволяет использовать процесс подготовки данных для создания моделей машинного обучения прямо в Power BI.

AutoML в Power BI позволяет аналитикам данных создавать модели машинного обучения на основе потоков данных, используя упрощенный интерфейс и навыки работы с Power BI. Большая часть действий по обработке и анализу данных, выполняемых для создания моделей машинного обучения, выполняется в Power BI автоматически. Определенные ограничения гарантируют хорошее качество создаваемой модели и полную прозрачность процесса, используемого для создания модели машинного обучения.

AutoML поддерживает создание моделей **двоичного прогнозирования**, **классификации** и **регрессии** для потоков данных. Это контролируемые типы моделей машинного обучения, то есть они используют известные результаты прошлых наблюдений для прогнозирования результатов других наблюдений. Входной набор данных для обучения модели AutoML содержит набор записей **с информацией** об известных результатах.

AutoML в Power BI применяет [автоматизированное машинное обучение](https://docs.microsoft.com/azure/machine-learning/service/concept-automated-ml) из службы [Машинное обучение Azure](https://docs.microsoft.com/azure/machine-learning/service/overview-what-is-azure-ml) для создания моделей машинного обучения. Но для использования AutoML в Power BI не требуется подписка Azure. Процесс обучения и размещения моделей машинного обучения полностью управляется службой Power BI.

После обучения модели машинного обучения AutoML автоматически создает отчет Power BI с информацией о предполагаемой эффективности полученной модели машинного обучения. AutoML уделяет особое внимание объяснению причин, выделяя из входных данных ключевые факторы, влияющие на возвращаемые моделью прогнозы. Отчет также содержит ключевые метрики модели.

На других страницах созданного отчета отображаются статистические сведения о модели и процессе обучения. Эта статистическая сводка будет интересна тем пользователям, которые предпочитают видеть меры эффективности модели, стандартно используемые в отрасли обработки и анализа данных. В сведениях об обучении собрана сводная информация по всем итерациям, которые выполнялись для создания модели, с указанием параметров моделирования. Здесь также описывается, как использовался каждый вход при создании модели машинного обучения.

После этого вы сможете применить модель машинного обучения к данным для ее оценки. При обновлении потока данных прогнозы, полученные из модели машинного обучения, автоматически применяются к данным. Power BI также предоставляет подробное объяснение для каждого конкретного прогноза, который создает модель машинного обучения.

## <a name="creating-a-machine-learning-model"></a>Создание модели машинного обучения

В этом разделе описывается, как создать модель AutoML.

### <a name="data-prep-for-creating-an-ml-model"></a>Подготовка данных для создания модели машинного обучения

Чтобы создать модель машинного обучения в Power BI, необходимо сначала создать поток данных с результатами предыдущих измерений для обучения модели машинного обучения. Кроме того, есть смысл добавить вычисляемые столбцы для всех бизнес-метрик, которые могут быть надежными прогностическими факторами для прогнозируемого результата. Сведения о настройке потока данных см. в руководстве по [самостоятельной подготовке данных в Power BI](service-dataflows-overview.md).

AutoML налагает определенные требования на данные для обучения модели машинного обучения. Эти требования описаны в разделах ниже для каждого типа моделей.

### <a name="configuring-the-ml-model-inputs"></a>Настройка входных данных для модели машинного обучения

Чтобы создать модель AutoML, щелкните значок машинного обучения в столбце **Действия** для сущности потока данных и выберите действие **Добавить модель машинного обучения**.

![Добавление модели машинного обучения](media/service-machine-learning-automated/automated-machine-learning-power-bi-02.png)

Откроется несложный интерфейс мастера настройки, который поможет вам создать модель машинного обучения. Этот мастер содержит описанные ниже шаги.

**1. Выбор сущности с историческими данными и поля с результатами, для которого требуется прогноз**

Поле с результатами определяет атрибут метки для обучения модели машинного обучения, как показано на рисунке ниже.

![Выбор источника исторических результатов](media/service-machine-learning-automated/automated-machine-learning-power-bi-03.png)

**2. Выбор типа модели**

После выбора поля с результатами AutoML оценивает данные меток и рекомендует наиболее подходящий тип модели машинного обучения. Вы можете выбрать другую модель, щелкнув ссылку "Выбрать другую модель", как показано ниже.

![Выбор модели](media/service-machine-learning-automated/automated-machine-learning-power-bi-04.png)

> [!NOTE]
> Бывает так, что некоторые типы моделей не поддерживаются для выбранных данных и поэтому отключены. В приведенном выше примере отключен тип "Регрессия", так как в качестве поля с результатами выбран текстовый столбец.

**3. Выбор входных данных, которые модель будет использовать в качестве прогнозных сигналов**

AutoML анализирует выборку из выбранной сущности, чтобы предложить входные данные для обучения модели машинного обучения. Рядом с полями, которые не были выбраны, приводятся пояснения. Если поле имеет слишком много уникальных значений, только одно значение либо слишком низкую или высокую корреляцию с полем результата, оно не рекомендуется.

Не следует использовать для обучения модели машинного обучения любые входные данные, которые зависят от поля результатов (или от поля метки), так как это негативно влияет на эффективность модели. Такие поля помечаются как имеющие подозрительно высокую корреляцию с полем результата. Включение этих полей в обучающие данные приводит к утечке меток, то есть модель будет хорошо работать с проверочными или тестовыми данными, но не сможет показать такие же результаты при оценке рабочих данных. Одним из признаков утечки меток в моделях AutoML является неправдоподобно высокая эффективность обучения модели.

Признаки рекомендуются на основе выборки данных, поэтому вам стоит проверить используемые входные данные. Вы можете изменить выбранные поля, оставив только те, которые необходимо изучить в модели. Вы также можете выбрать все поля, установив флажок рядом с именем сущности.

![Настройка полей ввода](media/service-machine-learning-automated/automated-machine-learning-power-bi-05.png)

**4. Присвоение имени модели и сохранение конфигурации**

На последнем шаге можно присвоить модели имя и выбрать команду "Сохранить и обучить", чтобы начать ее обучение. Вы можете уменьшить время обучения, чтобы получить результаты быстро, или увеличить его, чтобы получить более точную модель.

![Присвоение имени модели](media/service-machine-learning-automated/automated-machine-learning-power-bi-06.png)

### <a name="ml-model-training"></a>Обучение модели машинного обучения

Обучение моделей AutoML является частью процесса обновления потока данных. Сначала AutoML готовит данные для обучения.
AutoML разделяет предоставленные исторические данные на обучающие и проверочные наборы данных. Тестовый набор данных выполняет роль контрольного набора для проверки эффективности модели, которая выполняется после обучения. Эти наборы представлены в потоке данных в виде сущностей **обучения и тестирования**. AutoML использует перекрестную проверку для проверки модели.

Затем каждое поле ввода анализируется и отсутствующие значения заполняются вычисляемыми данными. AutoML использует несколько разных стратегий подстановки отсутствующих значений. Для входных атрибутов, рассматриваемых как числовые признаки, для подстановки отсутствующих значений используется среднее значение столбца. Для входных атрибутов, рассматриваемых как категориальные признаки, для подстановки отсутствующих значений AutoML использует режим значений столбца. Среднее значение и мода значений, используемые для подстановки отсутствующих значений, рассчитываются платформой AutoML на основе подвыборки из набора обучающих данных.

После этого к данным применяются все необходимые методы выборки и нормализации. Для моделей классификации AutoML подвергает входные данные послойной выборке и уравновешивает классы, чтобы обеспечить для них равное количество строк.

AutoML применяет несколько преобразований для каждого выбранного входного поля, основываясь на типе данных и статистических свойствах этого поля. AutoML использует эти преобразования для извлечения компонентов, которые будут использоваться для обучения модели машинного обучения.

Процесс обучения для моделей AutoML состоит из нескольких итераций (до 50) с разными алгоритмами и параметрами моделирования, по итогам которых выбирается модель с лучшей эффективностью. Обучение может завершиться после меньшего количества итераций, если служба AutoML не будет наблюдать повышения эффективности. Эффективность каждой из моделей оценивается путем проверки по набору контрольных данных. На этом этапе обучения AutoML создает несколько конвейеров для обучения и проверки этих итераций. Процесс оценки производительности моделей может занять от нескольких минут до нескольких часов (но не более настроенного в мастере времени обучения) в зависимости от размера набора данных и доступных ресурсов для выделенной емкости.

В некоторых случаях итоговая модель создается как ансамбль, в котором участвует сразу несколько моделей для повышения эффективности прогнозирования.

### <a name="automl-model-explainability"></a>Доступность моделей AutoML для объяснения

После обучения модели AutoML анализирует связи между компонентами входных данных и выходными данными модели. Для каждого входного признака оценивается величина изменения, которое он оказывает на выходные данные модели по контрольному набору данных. Это называется _важностью компонентов_. Это происходит в процессе обновления после завершения обучения. Поэтому обновление может занять больше времени, чем настроенная в мастере длительность обучения.

![Важность компонентов](media/service-machine-learning-automated/automated-machine-learning-power-bi-07.png)

### <a name="automl-model-report"></a>Отчет по модели AutoML

AutoML формирует отчет Power BI, в котором собраны сводные данные о производительности модели во время проверки, а также глобальные данные о важности компонентов. Доступ к этому отчету можно получить на вкладке "Модель машинного обучения" после успешного обновления потока данных. В отчете собираются результаты применения модели машинного обучения к контрольным (тестовым) данным, а результаты прогнозов сравниваются с известными значениями результата.

Отчет по модели позволяет оценить ее эффективность. По нему также можно убедиться, что ключевые факторы влияния в модели соответствуют существующей бизнес-аналитике по известным результатам.

Диаграммы и меры, которые используются в отчете для описания эффективности модели, зависят от типа модели. Эти диаграммы и меры производительности описаны в следующих разделах.

Дополнительные страницы в отчете могут описывать статистические меры по модели с точки зрения обработки и анализа данных. Например, отчет по **двоичному прогнозу** включает диаграмму выгоды и кривую ROC для модели.

Отчеты также содержат страницу **сведений об обучении**, на которой есть описание процесса обучения модели и диаграмма эффективности модели в каждой итерации.

![Сведения об обучении](media/service-machine-learning-automated/automated-machine-learning-power-bi-08.png)

Другой раздел на этой странице описывает определенный тип поля входных данных и метод, который применялся для добавления отсутствующих значений. Он также включает параметры, используемые в конечной модели.

![Дополнительные сведения о модели](media/service-machine-learning-automated/automated-machine-learning-power-bi-09.png)

Если созданная модель использует ансамбль обучения, то на странице **сведений об обучении** добавляется диаграмма, на которой представлены вес и параметры каждой модели, составляющей этот ансамбль.

![Вес в ансамбле](media/service-machine-learning-automated/automated-machine-learning-power-bi-10.png)

## <a name="applying-the-automl-model"></a>Применение модели AutoML

Если вас устраивает эффективность созданной модели машинного обучения, вы можете применить ее к новым или обновленным данным при обновлении потока данных. Это можно сделать прямо из отчета о модели, нажав кнопку **Применить** в правом верхнем углу или кнопку "Применить модель ML" в разделе действий на вкладке "Модели машинного обучения".

Чтобы применить модель машинного обучения, необходимо указать имя сущности, к которой она будет применена, и префикс для столбцов, которые будут добавлены в эту сущность для выходных данных модели. По умолчанию префиксом для имен столбцов назначается имя модели. Функция _Применить_ может принимать дополнительные параметры в зависимости от типа модели.

При применении модели машинного обучения создаются две сущности потока данных, содержащие прогнозы, и контекстные пояснения для каждой строки, которая оценивается в выходной сущности. Например, если вы примените модель _PurchaseIntent_ к сущности _OnlineShoppers_, на выходе будут сформированы сущности **OnlineShoppers enriched PurchaseIntent** и **OnlineShoppers enriched PurchaseIntent explanations**. Для каждой строки в сущности enriched **пояснения** разбиваются на несколько строк в сущности enriched explanations на основе входного признака. **ExplanationIndex** помогает сопоставить строки из сущности enriched explanations со строкой в сущности enriched.

![Редактор запросов](media/service-machine-learning-automated/automated-machine-learning-power-bi-11.png)

После применения модели AutoML всегда поддерживает актуальность прогнозов при каждом обновлении потока данных.

Чтобы использовать аналитические сведения и прогнозы из модели ML в отчете Power BI, подключитесь к выходной сущности из Power BI Desktop с помощью соединителя **потоков данных**.

## <a name="binary-prediction-models"></a>Модели двоичного прогнозирования

Модели двоичного прогнозирования, официально именуемые **моделями двоичной классификации**, используются для классификации набора данных в две группы. Они используются для прогнозирования событий с двумя возможными исходами, например будет ли конвертирована возможность для продажи, уйдет ли клиент, будет ли счет своевременно оплачен, является ли транзакция мошеннической и т. д.

Выходные данные модели двоичного прогнозирования содержат оценку вероятности, то есть долю уверенности в том, что будет достигнут положительный результат.

### <a name="training-a-binary-prediction-model"></a>Обучение модели двоичного прогнозирования

Предварительные требования.

- Для каждого возможного исхода нужно предоставить не менее 20 строк исторических данных.

Процесс создания модели двоичного прогнозирования содержит те же шаги, что и для других моделей AutoML, как описано выше в разделе **Настройка входных данных для модели машинного обучения**. Единственное отличие имеется на шаге "Выбор модели", на котором можно выбрать положительный исход, который вас интересует. Кроме того, можно указать понятные метки для результатов, которые будут использоваться в автоматически создаваемом отчете с результатами проверки модели.

![Мастер двоичного прогнозирования](media/service-machine-learning-automated/automated-machine-learning-power-bi-12.png)

### <a name="binary-prediction-model-report"></a>Отчет о модели двоичного прогнозирования

Модель двоичного прогнозирования возвращает в качестве выходных данных оценку вероятности того, что для этой записи будет получен положительный результат. Отчет содержит срез по порогу вероятностей, который влияет на интерпретацию оценок выше и ниже порога вероятности.

Эффективность модели в этом отчете оценивается по категориям _истинные положительные результаты, ложные положительные результаты, истинные отрицательные результаты и ложные отрицательные результаты_. Истинные положительные и истинные отрицательные результаты — это правильно спрогнозированные исходы по двум классам. Ложные положительные результаты — это записи, для которых был спрогнозирован положительный исход, но на самом деле исход был иным. Напротив, ложные отрицательные результаты — это записи, которые имели положительный исход, хотя спрогнозированный исход был иным.

Дополнительные меры, такие как точность и полнота, описывают влияние значения порога на прогнозируемые результаты. Изменяя срез порога вероятности, вы можете выбрать такое пороговое значение, при котором достигается сбалансированный компромисс между точностью и полнотой.

![Просмотр точности](media/service-machine-learning-automated/automated-machine-learning-power-bi-13.png)

Отчет также содержит средство анализа затрат и выгод, помогающее определить целевое подмножество совокупности, позволяющее получить максимальную прибыль. Исходя из оценочных затрат на нацеливание и выгоды от достижения целевого результата для единицы, средство анализа затрат и выгод пытается добиться максимальной прибыли. Это средство можно использовать для выбора порога вероятности на основе максимальной точки на графике, чтобы максимально увеличить прибыль. График также можно использовать для расчета прибыли или затрат для выбранного порога вероятности.

![Затраты и выгоды](media/service-machine-learning-automated/automated-machine-learning-power-bi-14.png)

Страница **отчета о точности** в отчете о модели содержит диаграмму _совокупного прироста_ и кривую ROC для модели. Это статистические меры эффективности модели. В отчетах есть описания отображаемых диаграмм.

![Экран отчета о точности](media/service-machine-learning-automated/automated-machine-learning-power-bi-15.png)

### <a name="applying-a-binary-prediction-model"></a>Применение модели двоичного прогнозирования

Чтобы применить модель двоичного прогнозирования, необходимо указать сущность с данными, к которым вы хотите применить прогнозы по модели машинного обучения. Укажите такие параметры, как префикс имени для выходного столбца и порог вероятности для классификации прогнозируемого результата.

![Входные данные для прогнозирования](media/service-machine-learning-automated/automated-machine-learning-power-bi-16.png)

При применении модели двоичного прогнозирования она добавляет в расширенную выходную сущность четыре выходных столбца: **Outcome**, **PredictionScore**, **PredictionExplanation** и **ExplanationIndex**. Имена столбцов в сущности дополняются префиксом, который вы указали при применении модели.

**PredictionScore** — это вероятность в процентах, то есть доля уверенности в том, что будет достигнут положительный результат.

Столбец **Outcome** содержит прогнозируемую метку исхода. Для записей, для которых вероятность превышает пороговое значение, прогнозируется достижение положительного результата, и они получают метку "Истина". Для записей с вероятностью ниже порогового значения прогнозируется неблагоприятный исход, и они получают метку "Ложь".

Столбец **PredictionExplanation** содержит объяснение того, какое конкретное влияние оказали входные компоненты на оценку **PredictionScore**.

## <a name="classification-models"></a>Модели классификации

Модели классификации используются для распределения набора данных в несколько групп или классов. Они используются для прогнозирования событий, которые могут иметь один из нескольких возможных результатов, например очень высокая, высокая, средняя или низкая ценность клиента за время его существования; высокий, средний, низкий или очень низкий уровень риска невыплат и т. д.

Выходные данные модели классификации содержат оценку вероятности, то есть прогнозируемая уверенность в том, что для записи будут выполняться критерии определенного класса.

### <a name="training-a-classification-model"></a>Обучение модели классификации

Для модели классификации нужно предоставить входную сущность с обучающими данными, где существует строковое или целочисленное поле с результатами, то есть с данными об уже известных событиях.

Предварительные требования.

- Для каждого возможного исхода нужно предоставить не менее 20 строк исторических данных.

Процесс создания модели классификации содержит те же шаги, что и для других моделей AutoML, как описано выше в разделе **Настройка входных данных для модели машинного обучения**.

### <a name="classification-model-report"></a>Отчет о модели классификации

Отчет о модели классификации создается путем применения модели машинного обучения к контрольным (тестовым) данным и сравнения прогнозируемых результатов с фактическим значением для каждой записи.

Отчет о модели содержит диаграмму с разбивкой по правильным и неправильным результатам классификации для каждого известного класса.

![Отчет по модели](media/service-machine-learning-automated/automated-machine-learning-power-bi-17.png)

Более подробный анализ для каждого класса позволяет узнать, как распределялись прогнозы по каждому известному классу. Он показывает другие классы, в которые ошибочно относились записи конкретного класса.

Описание модели в отчете также включает самые важные прогностические факторы для каждого класса.

Отчет по модели классификации также содержит страницу с подробными сведениями о обучении, как и для других типов моделей, как описано в разделе **Отчет по модели AutoML** выше в этой статье.

### <a name="applying-a-classification-model"></a>Применение модели классификации

Чтобы применить модель классификации машинного обучения, нужно указать сущность со входными данными и префикс для имени выходного столбца.

При применении модели классификации она добавляет в расширенную выходную сущность пять выходных столбцов: **ClassificationScore**, **ClassificationResult**, **ClassificationExplanation**, **ClassProbabilities** и **ExplanationIndex**. Имена столбцов в сущности дополняются префиксом, который вы указали при применении модели.

Столбец **ClassProbabilities** содержит список с оценками вероятности для каждого возможного класса по этой записи.

**ClassificationScore** — это вероятность в процентах, то есть доля уверенности в том, что для записи будут выполняться критерии определенного класса.

Столбец **ClassificationResult** содержит наиболее вероятный прогнозируемый класс для записи.

Столбец **ClassificationExplanation** содержит объяснение того, какое конкретное влияние оказали входные признаки на оценку **ClassificationScore**.

## <a name="regression-models"></a>Модели регрессии

Модели регрессии используются для прогнозирования определенного значения, например дохода от продажи, ценности клиента за все время существования, оплаченной суммы по счету, даты оплаты счета и т. д.

Результатом модели регрессии является прогнозируемое значение.

### <a name="training-a-regression-model"></a>Обучение модели регрессии

Для модели регрессии нужно предоставить входную сущность с обучающими данными, где существует числовое поле с результатами, то есть с уже известными значениями.

Предварительные требования.

- Для модели регрессии нужно предоставить не менее 100 строк исторических данных.

Процесс создания модели регрессии содержит те же шаги, что и для других моделей AutoML, как описано выше в разделе **Настройка входных данных для модели машинного обучения**.

### <a name="regression-model-report"></a>Отчет по модели регрессии

Как и в отчетах по другим моделям AutoML, отчет по модели регрессии основан на результатах применения модели к контрольным (тестовым) данным.

Отчет по модели содержит диаграмму, где прогнозируемые значения сравниваются с фактическими. На этой диаграмме отклонение от диагонали означает ошибку в прогнозе.

На диаграмме "остаточная ошибка" представлено распределение доли среднего отклонения для разных значений в контрольном наборе данных. По горизонтальной оси откладывается среднее фактическое значение для группы, а размер пузырька обозначает частоту или число значений в этом диапазоне. По вертикальной оси отмечается средняя остаточная ошибка.

![Диаграмма остаточных ошибок](media/service-machine-learning-automated/automated-machine-learning-power-bi-18.png)

Отчет по модели регрессии также содержит страницу с подробными сведениями о обучении, как и для других типов моделей, как описано выше в разделе **Отчет по модели AutoML**.

### <a name="applying-a-regression-model"></a>Применение модели регрессии

Чтобы применить модель регрессии машинного обучения, нужно указать сущность со входными данными и префикс для имени выходного столбца.

![Применение регрессии](media/service-machine-learning-automated/automated-machine-learning-power-bi-19.png)

При применении модели регрессии она добавляет в расширенную выходную сущность три выходных столбца: **RegressionResult**, **RegressionExplanation** и **ExplanationIndex**. Имена столбцов в сущности дополняются префиксом, который вы указали при применении модели.

Столбец **RegressionResult** содержит прогнозируемое для записи значение, основанное на полях входных данных. Столбец **RegressionExplanation** содержит объяснение того, какое конкретное влияние оказали входные признаки на результат **RegressionResult**.

## <a name="next-steps"></a>Дальнейшие действия

В этой статье кратко описывается интеграция автоматизированного машинного обучения с потоками данных в службу Power BI. Следующие статьи также содержат полезные сведения на эти темы.

- [Руководство. Создание модели машинного обучения в Power BI](../connect-data/service-tutorial-build-machine-learning-model.md)
- [Руководство. Использование служб Cognitive Services в Power BI](../connect-data/service-tutorial-use-cognitive-services.md)
- [Руководство. Вызов модели Студии машинного обучения (классической) в Power BI (предварительная версия)](../connect-data/service-tutorial-invoke-machine-learning-model.md)
- [Использование Cognitive Services в Power BI](service-cognitive-services.md)
- [Интеграция Машинного обучения Azure в Power BI](service-machine-learning-integration.md)

См. дополнительные сведения о потоках данных в следующих статьях:

- [Creating and using dataflows in Power BI (Preview)](service-dataflows-create-use.md) (Создание и использование потоков данных в Power BI (предварительная версия))
- [Использование вычисляемых сущностей в Power BI Premium](service-dataflows-computed-entities-premium.md)
- [Использование потоков данных с локальными источниками данных](service-dataflows-on-premises-gateways.md)
- [Ресурсы для разработчиков потоков данных Power BI](service-dataflows-developer-resources.md)
- [Потоки данных и интеграция Azure Data Lake (предварительная версия)](service-dataflows-azure-data-lake-integration.md)