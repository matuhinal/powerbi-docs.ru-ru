---
title: Подключение к Ziosk Survey Analytics с помощью Power BI
description: Ziosk для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: d22f67f52d0abe0621e244874def845c7d25c15b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "61138557"
---
# <a name="connect-to-ziosk-survey-analytics-with-power-bi"></a>Подключение к Ziosk Survey Analytics с помощью Power BI
Пакет содержимого Ziosk Survey Analytics для Power BI предлагает перечень ресторанов, где предоставляется уникальный доступ посредством планшетов Ziosk к аналитике, основанной на данных опросов Ziosk. Эти данные включают в себя сегментацию по дням, местоположение, сотрудников и многое другое.

Подключитесь к [пакету содержимого Ziosk Survey Analytics](https://app.powerbi.com/getdata/services/ziosk-survey-analytics) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.  
   
    ![](media/service-connect-to-ziosk/getdata.png)
2. В поле **Службы** выберите **Получить**.  
   
    ![](media/service-connect-to-ziosk/services.png)
3. Выберите **Ziosk Survey Analytics**, а затем нажмите кнопку **Получить**.  
   
    ![](media/service-connect-to-ziosk/ziosk.png)
4. Выберите **OAuth 2**, и затем нажмите **Войти**. При появлении запроса введите учетные данные Ziosk.
   
    ![](media/service-connect-to-ziosk/creds.png)
   
    ![](media/service-connect-to-ziosk/creds2.png)
5. После подключения автоматически загрузятся информационная панель, отчет и набор данных. После завершения плитки обновятся в соответствии с данными из вашей учетной записи Ziosk.
   
    ![](media/service-connect-to-ziosk/dashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="whats-included"></a>Содержимое
Пакет содержимого включает в себя данные из следующих таблиц.  

    - "Категория алкоголя"  
    - "Категория закусок"  
    - "Объяснение ключевых слов"  
    - Даты  
    - "Время суток"  
    - "Категория десертов"  
    - "Свободный"  
    - "Детская категория"  
    - "Сообщения"  
    - "Категория премиум-контента"  
    - "Вопросы"  
    - "Хранилище"  
    - "Опросы"  
    - "День недели"  


## <a name="system-requirements"></a>Требования к системе
Чтобы создать этот пакет содержимого, требуется учетная запись Ziosk с разрешениями для вышеперечисленных таблиц.

## <a name="next-steps"></a>Дальнейшие действия
[Что такое Power BI?](power-bi-overview.md)

[Power BI — основные понятия](consumer/end-user-basic-concepts.md)

