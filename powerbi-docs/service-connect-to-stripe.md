---
title: Подключение к Stripe с помощью Power BI
description: Stripe для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 533a8ae7f0030c70ed5212c890215a2b43d8e870
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34246604"
---
# <a name="connect-to-stripe-with-power-bi"></a>Подключение к Stripe с помощью Power BI
Визуализация и исследование данных Stripe в Power BI с помощью пакета контента Power BI. Пакет контента Stripe в Power BI извлекает данные о клиентах, накладных расходах, событиях и счетах. Данные содержат последние десять тысяч событий и пять тысяч расходов за последние 30 дней. Контент будет обновляться автоматически один раз в день в указанное вами время. 

Подключите [пакет содержимого Stripe для Power BI](https://app.powerbi.com/getdata/services/stripe).

## <a name="how-to-connect"></a>Способы подключения
1. Выберите "Получить данные" в нижней части левой панели навигации.  
   
    ![](media/service-connect-to-stripe/getdata.png)
2. В поле **Службы** выберите **Получить**.  
   
    ![](media/service-connect-to-stripe/services.png)  
3. Выберите **Stripe** &gt; **Получить**.  
   
    ![](media/service-connect-to-stripe/stripe.png)  
4. Укажите [API-ключ](https://dashboard.stripe.com/account/apikeys) Stripe для подключения.  
   
    ![](media/service-connect-to-stripe/creds.png)
5. Процесс импорта начнется автоматически. После завершения в области навигации появятся новая панель мониторинга, отчет и модель, отмеченные звездочкой. Выберите панель мониторинга, чтобы просмотреть импортированные данные.
   
    ![](media/service-connect-to-stripe/dashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Получение данных для Power BI](service-get-data.md)

