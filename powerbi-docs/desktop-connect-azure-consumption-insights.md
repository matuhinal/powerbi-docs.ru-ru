---
title: Подключение к данным Azure Consumption Insights в Power BI Desktop (бета-версия)
description: Легко подключайтесь к Azure и получайте сведения о потреблении и использовании с помощью Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1e82ec988389790a3d96cb6f98f0db5d1a385fda
ms.sourcegitcommit: 00b4911ab5fbf4c2d5ffc000a3d95b3149909c28
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="connect-to-azure-consumption-insights-in-power-bi-desktop-beta"></a>Подключение к Azure Consumption Insights в Power BI Desktop (бета-версия)
С помощью соединителя **Azure Consumption Insights** можно использовать **Power BI Desktop** для подключения к Azure и получения подробных данных и сведений об использовании служб Azure в организации. Можно также создавать меры, настраиваемые столбцы и визуальные элементы для формирования отчетов об использовании Azure в организации и предоставления доступа к ним. Этот выпуск соединителя **Azure Consumption Insights** является бета-версией, которая может быть изменена.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_01.png)

Из этой статье вы узнаете, как подключиться к Azure с помощью соединителя **Azure Consumption Insights** и получить необходимые данные, выполнить миграцию из соединителя Azure Enterprise и найти сопоставление *столбцов со сведениями об использовании*  в API **ACI** (Azure Consumption Insights).

## <a name="connect-to-azure-consumption-insights"></a>Подключение к Azure Consumption Insights
Чтобы подключиться к Azure с помощью соединителя **Azure Consumption Insights**, нужен доступ к функциям Enterprise на портале Azure.

Чтобы подключиться с помощью соединителя **Azure Consumption Insights**, в **Power BI Desktop** на ленте **Главная** выберите элемент **Получение данных**. Выберите слева категорию **Веб-службы**. В списке справа вы увидите **Microsoft Azure Consumption Insights (бета-версия)**. Нажмите кнопку **Подключиться**.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_01b.png)

В открывшемся диалоговом окне укажите свой *номер регистрации*.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_02.png)

* Номер регистрации можно найти на портале [Azure Enterprise Portal](https://ea.azure.com) в расположении, которое показано на следующем рисунке:
  
  ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_08.png)
  
  Эта версия соединителя поддерживает только корпоративные регистрации с https://ea.azure.com. Регистрации из Китая сейчас не поддерживаются.

Теперь введите свой *ключ доступа* для подключения.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_03.png)

* Ключ доступа для регистрации можно найти на портале [Azure Enterprise Portal](https://ea.azure.com).
  
  ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_09.png)

Когда вы введете *ключ доступа* и нажмете кнопку **Подключиться**, откроется окно **навигатора** с четырьмя таблицами: *Сводка*, *Использование*, *Прайс-лист* и *MarketPlace*. Чтобы просмотреть сведения, установите флажок возле соответствующей таблицы. Чтобы выбрать одну или несколько таблиц, установите флажок рядом с именем таблицы, а затем нажмите кнопку **Загрузить**.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_04.png)

> [!NOTE]
> Таблицы *Сводка* и *Прайс-лист* доступны только для уровня регистрации ключа API. По умолчанию таблицы *Использование* и *Прайс-лист* содержат данные за текущий месяц. Данные в таблицах *Сводка* и *MarketPlace* не ограничены текущим месяцем.
> 
> 

После нажатия кнопки **Загрузить** данные загружаются в **Power BI Desktop**.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_05.png)

Когда выбранные данные будут загружены, соответствующие таблицы и поля отобразятся в области **Поля**.

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_06.png)

## <a name="using-azure-consumption-insights"></a>Использование Azure Consumption Insights
Чтобы использовать соединитель **Azure Consumption Insights**, нужен доступ к функциям Enterprise на портале Azure.

После загрузки данных с помощью соединителя **Azure Consumption Insights** вы можете создать собственные пользовательские меры и столбцы с помощью **редактора запросов**. Вы также можете создать визуальные элементы, отчеты и панели мониторинга, к которым вы можете предоставлять доступ в **службе Power BI**.

Azure также включает коллекцию примеров пользовательских запросов, которые можно извлечь с помощью пустого запроса. Чтобы сделать это, в **Power BI Desktop** на вкладке **Главная** выберите стрелку раскрывающегося списка **Получение данных**, а затем выберите **Пустой запрос**. Это также можно сделать в **редакторе запросов**: щелкните правой кнопкой мыши область **Запросы** слева и в открывшемся меню выберите элементы **Новый запрос > Пустой запрос**.

В **строке формул** введите следующее:

    = MicrosoftAzureConsumptionInsights.Contents

Открывается коллекция примеров, как показано на следующем рисунке:

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_07.png)

При работе с отчетами и создании запросов используйте следующие параметры:

* Чтобы определить число месяцев начиная с текущей даты, используйте параметр *numberOfMonth*.
  * Чтобы указать число месяцев с текущей даты, данные которых требуется импортировать, используйте значение от 1 до 36. Рекомендуем выбирать не более 12 месяцев данных, чтобы не превысить пороговые значения ограничений импорта и допустимого объема данных для запросов в Power BI.
* Чтобы определить число месяцев в окне времени журнала, используйте параметры *startBillingDataWindow* и *endBillingDataWindow*.
* *Не* используйте параметр *numberOfMonth* вместе с параметрами *startBillingDataWindow* и *endBillingDataWindow*.

## <a name="migrating-from-the-azure-enterprise-connector"></a>Миграция из соединителя Azure Enterprise
Некоторые пользователи создавали визуальные элементы с помощью *соединителя Azure Enterprise (бета-версия)*, который рано или поздно перестанет поддерживаться и будет заменен соединителем **Azure Consumption Insights**. Соединитель **Azure Consumption Insights** содержит следующие функции и усовершенствования:

* Дополнительные источники данных для таблиц *Сводка баланса* и *Покупки Marketplace*.
* Новые и расширенные параметры, такие как *startBillingDataWindow* и *endBillingDataWindow*.
* Улучшенные производительность и скорость реагирования.

Ниже приведены инструкции, которые помогут клиентам перейти к использованию нового соединителя **Azure Consumption Insights** и сохранить все данные в пользовательских панелях мониторинга и отчетах.

### <a name="step-1-connect-to-azure-using-the-new-connector"></a>Шаг 1. Подключение к Azure с помощью нового соединителя
Сначала нужно подключиться к Azure с помощью соединителя **Azure Consumption Insights**. Эта процедура подробно описана ранее в этой статье. В **Power BI Desktop** на ленте **Главная** последовательно выберите элементы **Получение данных > Пустой запрос**.

### <a name="step-2-use-the-advanced-editor-to-create-a-query"></a>Шаг 2. Создание запроса с помощью расширенного редактора
В **редакторе запросов** на ленте **Главная** в разделе **Запрос** выберите **Расширенный редактор**. В открывшемся окне **Расширенный редактор** введите следующий запрос:

    let    
        enrollmentNumber = "100",
        optionalParameters = [ numberOfMonth = 6, dataType="DetailCharges" ],
        data = MicrosoftAzureConsumptionInsights.Contents(enrollmentNumber, optionalParameters)   
    in     
        data

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_10.png)

Разумеется, вам нужно заменить значение *enrollmentNumber* собственным номером регистрации, который можно найти на портале [Azure Enterprise Portal](https://ea.azure.com). Параметр *numberOfMonth* — это число месяцев начиная с текущей даты, данные за которые вы хотите просмотреть. Чтобы просмотреть данные за текущий месяц, укажите ноль (0).

Когда вы нажмете кнопку **Готово** в окне **Расширенный редактор**, предварительный просмотр обновится и вы увидите данные за месяцы, которые вы указали в таблице. Выберите **Закрыть и применить**.

### <a name="step-3-move-measures-and-custom-columns-to-the-new-report"></a>Шаг 3. Перемещение мер и настраиваемых столбцов в новый отчет
Теперь необходимо переместить все созданные пользовательские столбцы и меры в новую таблицу со сведениями. Это делается следующим образом.

1. Откройте Блокнот (или другой текстовый редактор).
2. Выберите меру, которую нужно переместить, скопируйте текст из поля *Формула* и вставьте его в Блокнот.
   
   ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_11.png)
3. Замените имя *Query1* исходным именем таблицы со сведениями.
4. Создайте новые меры и настраиваемые столбцы в таблице. Для этого щелкните правой кнопкой мыши таблицу и выберите элемент **Новая мера**, затем вырежьте и вставьте все сохраненные меры и столбцы.

### <a name="step-4-re-link-tables-that-had-relationships"></a>Шаг 4. Восстановление ссылок между связанными таблицами
На многих панелях мониторинга есть дополнительные таблицы, которые используются для поиска или фильтрации, например таблицы дат или таблицы, используемые для пользовательских проектов. Восстановление связей между таблицами решает большинство задач. Вот как это сделать.

- В **Power BI Desktop** на вкладке **Моделирование** выберите элемент **Управление связями**, чтобы открыть окно управления связями в модели. При необходимости восстановите связи между таблицами.
   
    ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_12.png)

### <a name="step-5-verify-your-visuals-and-adjust-field-formatting-as-needed"></a>Шаг 5. Проверка визуальных элементов и изменение форматирования полей при необходимости
После выполнения описанных выше шагов большая часть исходных визуальных элементов, таблиц и детализаций должна работать правильно. Но, возможно, нужно внести другие небольшие изменения, чтобы полностью завершить настройку. Просмотрите все свои панели мониторинга и визуальные элементы, чтобы убедиться, что они выглядят, как вы хотите.

## <a name="using-the-azure-consumption-and-insights-aci-api-to-get-consumption-data"></a>Использование API Azure Consumption Insights (ACI) для получения данных потребления
В Azure также доступен [**API Azure Consumption Insights (ACI)**](https://azure.microsoft.com/blog/announcing-general-availability-of-consumption-and-charge-apis-for-enterprise-azure-customers/). Вы можете создавать собственные пользовательские решения для сбора, создания отчетов и визуализации сведений об использовании служб Azure с помощью ACI.

### <a name="mapping-names-and-usage-details-between-the-portal-the-connector-and-the-api"></a>Сопоставление имен и сведений об использовании между порталом, соединителем и API
Столбцы и имена сведений на портале Azure похожи на столбцы и имена в API и соединителе, но они не всегда совпадают. Чтобы вы могли увидеть разницу, см. следующую таблицу. Она содержит сопоставления между API, соединителем и столбцы, отображаемые на портале Azure. Также в таблице указано, является ли столбец устаревшим. Дополнительные сведения и определения этих терминов см. в статье [API-интерфейсы отчетов для корпоративных клиентов: сведения об использовании](https://docs.microsoft.com/azure/billing/billing-enterprise-api-usage-detail).

| Соединитель ACI/Имя столбца пакета содержимого | Имя столбца API ACI | Имя столбца EA | Устаревший/представлен для обеспечения обратной совместимости |
| --- | --- | --- | --- |
| AccountName |accountName |Account Name |Нет |
| AccountId |accountId | |Да |
| AcccountOwnerId |accountOwnerEmail |AccountOwnerId |Нет |
| AdditionalInfo |additionalInfo |AdditionalInfo |Нет |
| AdditionalInfold | | |Да |
| Consumed Quantity |consumedQuantity |Consumed Quantity |Нет |
| Consumed Service |consumedService |Consumed Service |Нет |
| ConsumedServiceId |consumedServiceId | |Да |
| Cost |cost |ExtendedCost |Нет |
| Cost Center |costCenter |Cost Center |Нет |
| Дата |date |Дата |Нет |
| День | |День |Нет |
| DepartmentName |departmentName |Department Name |Нет |
| DepartmentID |departmentId | |Да |
| Instance ID | | |Да |
| InstanceId |instanceId |Instance ID |Нет |
| Расположение | | |Да |
| Meter Category |meterCategory |Meter Category |Нет |
| Meter ID | | |Да |
| Meter Name |meterName |Meter Name |Нет |
| Meter Region |meterRegion |Meter Region |Нет |
| Meter Sub-Category |meterSubCategory |Meter Sub-Category |Нет |
| MeterId |meterId |Meter ID |Нет |
| Месяц | |Месяц |Нет |
| Продукт |product |Продукт |Нет |
| ProductId |productId | |Да |
| Resource Group |resourceGroup |Resource Group |Нет |
| Resource Location |resourceLocation |Resource Location |Нет |
| ResourceGroupId | | |Да |
| ResourceLocationId |resourceLocationId | |Да |
| ResourceRate |resourceRate |ResourceRate |Нет |
| ServiceAdministratorId |serviceAdministratorId |ServiceAdministratorId |Нет |
| ServiceInfo1 |serviceInfo1 |ServiceInfo1 |Нет |
| ServiceInfo1Id | | |Да |
| ServiceInfo2 |serviceInfo2 |ServiceInfo2 |Нет |
| ServiceInfo2Id | | |Да |
| Store Service Identifier |storeServiceIdentifier |Store Service Identifier |Нет |
| StoreServiceIdentifierId | | |Да |
| Subscription Name |subscriptionName |Subscription Name |Нет |
| Теги |tags |Теги |Нет |
| TagsId | | |Да |
| Unit Of Measure |unitOfMeasure |Unit Of Measure |Нет |
| Год | |Год |Нет |
| SubscriptionId |subscriptionId |SubscriptionId |Да |
| SubscriptionGuid |subscriptionGuid |SubscriptionGuid |Нет |

## <a name="next-steps"></a>Дальнейшие действия
В Power BI Desktop можно подключаться к данным самых разных видов. Дополнительные сведения об источниках данных см. в перечисленных ниже статьях.

* [Начало работы с Power BI Desktop](desktop-getting-started.md)
* [Источники данных в Power BI Desktop](desktop-data-sources.md)
* [Формирование и объединение данных в Power BI Desktop](desktop-shape-and-combine-data.md)
* [Подключение к данным Excel в Power BI Desktop](desktop-connect-excel.md)   
* [Ввод данных непосредственно в Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

