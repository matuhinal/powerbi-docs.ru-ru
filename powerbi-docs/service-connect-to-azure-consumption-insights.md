---
title: Подключение к Microsoft Azure Consumption Insights с помощью Power BI
description: Microsoft Azure Consumption Insights для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 31f1d4161801b45307e92ad3f654d30843897dc8
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34244164"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>Подключение к Microsoft Azure Consumption Insights с помощью Power BI
Просматривайте и отслеживайте данные об использовании Microsoft Azure в Power BI с помощью пакета содержимого Power BI. Данные автоматически обновляются раз в день.

Подключитесь к пакету содержимого [Microsoft Azure Consumption Insights](https://app.powerbi.com/getdata/services/azureconsumption) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. Выберите **Microsoft Azure Consumption Insights** \> **Получить**. 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. Укажите число месяцев, за которое необходимо импортировать данные, и номер регистрации Azure Enterprise. Сведения о том, как найти необходимые параметры, см. [ниже](#FindingParams).
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. Укажите ключ доступа для подключения. Ключ для вашей регистрации можно найти на портале Azure EA. 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. Процесс импорта начнется автоматически. После завершения в области навигации появятся новая панель мониторинга, отчет и модель. Выберите панель мониторинга, чтобы просмотреть импортированные данные.
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="whats-included"></a>Содержимое
Пакет содержимого Microsoft Azure Consumption Insights включает данные из ежемесячных отчетов за месяцы, которые вы указываете во время подключения. Диапазон динамический, поэтому входящие в него даты будут обновляться при обновлении набора данных.

## <a name="system-requirements"></a>Требования к системе
Для пакета содержимого требуется доступ к функциям Enterprise на портале Azure. 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Поиск параметров
Отчеты Power BI доступны для прямых клиентов EA, партнеров и непрямых клиентов, которые могут просматривать сведения об оплате. Ниже приведены дополнительные сведения о поиске каждого из значений, которые потребуются во время процедуры подключения.

**Число месяцев**

* Это число должно находиться в пределах от 1 до 36, обозначая число месяцев (с сегодняшнего дня), за которое вы хотите импортировать данные.

**Номер регистрации**

* Это номер соглашения о регистрации Azure Enterprise, который можно найти на домашней странице [портала Azure Enterprise](https://ea.azure.com/) в разделе "Сведения о соглашении о регистрации".
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**Ключ доступа**

* Ключ можно найти на портале Azure Enterprise в разделе "Скачать сведения об использовании" > "API Access Key" (Ключ доступа к API).
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**Дополнительная справка**

* Для дополнительной помощи в настройке пакета Azure Enterprise Power BI войдите на портал Azure Enterprise, чтобы просмотреть файл справки по API в разделе "Справка" и дополнительные инструкции в меню "Отчеты" -> "Скачать сведения об использовании" -> "Ключ доступа к API". 

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Получение данных в Power BI](service-get-data.md)

