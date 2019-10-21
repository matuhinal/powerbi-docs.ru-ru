---
title: Подключение к Microsoft Azure Consumption Insights с помощью Power BI
description: Microsoft Azure Consumption Insights для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 09/25/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e51f936e44e8c8ee3442aedfb2389675774c0a47
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72020443"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Подключение к Microsoft Azure Consumption Insights с помощью Power BI
Просматривайте и отслеживайте данные об использовании Microsoft Azure в службе Power BI с помощью пакета содержимого Power BI. Данные автоматически обновляются раз в день.

Подключитесь к пакету содержимого [Microsoft Azure Consumption Insights](https://app.powerbi.com/getdata/services/azureconsumption) для службы Power BI.

> [!NOTE]
> Чтобы дополнительно настроить систему, можно использовать [соединитель Azure Consumption Insights](desktop-connect-azure-consumption-insights.md) в Power BI Desktop.

## <a name="how-to-connect"></a>Способы подключения
1. В службе Power BI нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
    ![Получение данных](media/service-connect-to-azure-consumption-insights/getdata.png)
2. В поле **Службы** выберите **Получить**.
   
   ![Получить службы](media/service-connect-to-azure-consumption-insights/services.png)
3. Выберите **Microsoft Azure Consumption Insights** \> **Получить**. 
   
   ![Получить](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Укажите число месяцев, за которое необходимо импортировать данные, и номер регистрации Azure Enterprise. Сведения о том, как найти необходимые параметры, см. [ниже](#FindingParams).
   
    ![Подключение к Microsoft Azure Consumption Insights](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Укажите ключ доступа для подключения. Ключ регистрации можно найти на портале Azure EA. 
   
    ![Microsoft Azure Consumption Insights: ключ](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. Процесс импорта начинается автоматически. После завершения в области навигации появится новая панель мониторинга, отчет и модель. Выберите панель мониторинга, чтобы просмотреть импортированные данные.
   
   ![Панель мониторинга Microsoft Azure Consumption Insights](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных ежедневно обновляется по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="whats-included"></a>Содержимое
Пакет содержимого Microsoft Azure Consumption Insights включает данные из ежемесячных отчетов за месяцы, которые вы указываете во время подключения. Диапазон динамический, поэтому входящие в него даты будут обновляться при обновлении набора данных.

## <a name="system-requirements"></a>Требования к системе
Для пакета содержимого требуется доступ к функциям Enterprise на портале Azure. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Поиск параметров
Отчеты Power BI доступны для прямых клиентов EA, партнеров и непрямых клиентов, которые могут просматривать сведения об оплате. Ниже приведены дополнительные сведения о поиске каждого из значений, которые потребуются в ходе потока операций подключения.

**Число месяцев**

* Число месяцев (1–36) данных начиная с сегодняшнего дня, которые вы хотите импортировать.

**Номер регистрации**

* Это номер соглашения о регистрации Azure Enterprise, который можно найти на домашней странице [портала Azure Enterprise](https://ea.azure.com/) в разделе **Сведения о регистрации**.
  
    ![Номер регистрации](media/service-connect-to-azure-consumption-insights/params2.png)

**Ключ доступа**

* Ключ можно найти на портале Azure Enterprise в разделе **Скачать сведения об использовании** > **Ключ доступа к API**.
  
    ![Ключ доступа](media/service-connect-to-azure-consumption-insights/creds2.png)

**Дополнительная справка**

* Чтобы получить дополнительные сведения о настройке пакета Azure Enterprise Power BI, войдите на корпоративный портал Azure и просмотрите файл справки API в разделе **Справка**. Дополнительные инструкции можно также найти в разделе **Отчеты** -> **Скачать сведения об использовании** -> **Ключ доступа к API**.
* Чтобы дополнительно настроить систему, можно использовать [соединитель Azure Consumption Insights](desktop-connect-azure-consumption-insights.md) в Power BI Desktop.

## <a name="next-steps"></a>Дальнейшие действия

[Соединитель Azure Consumption Insights](desktop-connect-azure-consumption-insights.md) в Power BI Desktop

[Получение данных в Power BI](service-get-data.md)

