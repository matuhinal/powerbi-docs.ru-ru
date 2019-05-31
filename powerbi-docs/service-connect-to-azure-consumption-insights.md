---
title: Подключение к Microsoft Azure Consumption Insights с помощью Power BI
description: Microsoft Azure Consumption Insights для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/20/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 089f8c31a0b1eb11f6871268f2f848949be95d9b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222124"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Подключение к Microsoft Azure Consumption Insights с помощью Power BI
Просматривайте и отслеживайте данные об использовании Microsoft Azure в Power BI с помощью пакета содержимого Power BI. Данные автоматически обновляются раз в день.

Подключитесь к пакету содержимого [Microsoft Azure Consumption Insights](https://app.powerbi.com/getdata/services/azureconsumption) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. Выберите **Microsoft Azure Consumption Insights** \> **получить сейчас**. 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Укажите число месяцев, за которое необходимо импортировать данные, и номер регистрации Azure Enterprise. Сведения о том, как найти необходимые параметры, см. [ниже](#FindingParams).
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Укажите ключ доступа для подключения. Ключ регистрации можно найти на портале EA Azure. 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. Процесс импорта начинается автоматически. По завершении новой панели мониторинга, отчетов и модели отображаются в области навигации. Выберите панель мониторинга, чтобы просмотреть импортированные данные.
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных запланирована для ежедневного обновления, можно изменить график обновлений или попытаться выполнять обновления по запросу с помощью **Обновить сейчас**

## <a name="whats-included"></a>Содержимое
Пакет содержимого Microsoft Azure Consumption Insights включает в себя ежемесячных отчетов данные для диапазона месяц, который вы указали при подключении. Диапазон является скользящего окна, поэтому входящие в него даты обновляются по мере обновления набора данных.

## <a name="system-requirements"></a>Требования к системе
Пакет содержимого требуется доступ к функциям Enterprise на портале Azure. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Поиск параметров
Отчеты Power BI доступна для EA Direct, партнеров и непрямых клиентов, кто может просматривать сведения о выставлении счетов. Ниже приведены сведения о поиске каждого значения, которые ожидает подключения.

**Число месяцев**

* Число месяцев (от 1 до 36) данных, начиная с сегодняшнего дня, которые вы хотите импортировать.

**Номер регистрации**

* Номер регистрации Azure Enterprise, который можно найти в [Azure Enterprise Portal](https://ea.azure.com/) начального экрана в разделе **сведения о регистрации**.
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**Ключ доступа**

* Ключ доступа на портале Azure Enterprise, можно найти в разделе **скачать сведения об использовании** > **ключ доступа к API**.
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**Дополнительная справка**

* Для дополнительных сведения о настройке пакета Azure Enterprise Power BI, войдите на корпоративный портал Azure и просмотреть файл справки по API в разделе **помочь**. Также можно найти дополнительные инструкции в разделе **отчеты** -> **скачать сведения об использовании** -> **ключ доступа к API**.

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Получение данных в Power BI](service-get-data.md)

