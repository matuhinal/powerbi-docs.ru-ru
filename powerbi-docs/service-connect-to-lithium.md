---
title: "Подключение к Lithium с помощью Power BI"
description: "Lithium для Power BI"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: cac92465e36b87d2a59420f5a6265c219371ceba
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="connect-to-lithium-with-power-bi"></a>Подключение к Lithium с помощью Power BI
Lithium помогает строить доверительные отношения между лучшими торговыми марками и клиентами, находить ответы и обмениваться опытом. Подключив пакет содержимого Lithium для Power BI, вы сможете оценивать основные метрики, связанные с интернет-сообществом, для повышения объемов продаж, снижения затрат на обслуживание и повышения уровня доверия со стороны клиентов. 

Подключитесь к [пакету содержимого Lithium](https://app.powerbi.com/getdata/services/lithium) для Power BI.

>[!NOTE]
>Пакет содержимого Power BI использует API-интерфейс Lithium. Большое число вызовов API может повлечь за собой взимание дополнительных платежей за использование Lithium. Уточните этот момент у администратора Lithium.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. Выберите **Lithium** \> **Получить**.
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. Укажите URL-адрес вашего сообщества Lithium. Он имеет формат *https://community.yoursite.com*.
   
   ![](media/service-connect-to-lithium/params.png)
5. При появлении запроса введите учетные данные Lithium. Выберите **oAuth 2** в качестве механизма проверки подлинности, нажмите кнопку **Вход** и выполните процедуру проверки подлинности Lithium.
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. После завершения процедуры входа в систему начнется процесс импорта. После завершения в области навигации появятся новая панель мониторинга, отчет и модель. Выберите панель мониторинга, чтобы просмотреть импортированные данные.
   
    ![](media/service-connect-to-lithium/lithium.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="system-requirements"></a>Требования к системе
Для пакета содержимого Lithium требуется Lithium community версии 15.9 или более поздней. Для подтверждения обратитесь к администратору Lithium.

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Power BI — основные понятия](service-basic-concepts.md)

