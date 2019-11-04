---
title: Подключение к Alpine Metrics Sales Prediction с помощью Power BI
description: Alpine Metrics Sales Prediction для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 97fb91018acb2123783f99cc4234cdcdf7f09975
ms.sourcegitcommit: d441d350504f8c6d9e100d229757add6237f0bef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73060629"
---
# <a name="connect-to-alpine-metrics-sales-predictions-with-power-bi"></a>Подключение к Alpine Metrics Sales Prediction с помощью Power BI
Alpine Metrics предоставляет современные средства оптимизации процессов для прогнозирования продаж в облачной среде и по запросу для малых и больших организаций. Пакет содержимого Alpine Metrics Sales Predictions для Power BI включает такие метрики, как потенциальные и прогнозируемые продажи и риски, что позволяет получить более глубокое представление о дальнейшем развитии вашего бизнеса. 

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

Подключитесь к [пакету содержимого Alpine Metrics Sales Predictions](https://app.powerbi.com/getdata/services/alpine-metrics) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Выберите "Получить данные" в нижней части левой панели навигации.  
   
    ![](media/service-connect-to-alpine-metrics/getdata.png)
2. В поле **Службы** выберите **Получить**.  
   
    ![](media/service-connect-to-alpine-metrics/services.png)
3. Выберите **AlpineMetrics Sales Predictions**, а затем — **Получить**.  
   
    ![](media/service-connect-to-alpine-metrics/alpine.png)
4. Выберите **OAuth 2**, и затем нажмите **Войти**. При появлении запроса введите учетные данные AlpineMetrics.
   
    ![](media/service-connect-to-alpine-metrics/creds.png)
   
    ![](media/service-connect-to-alpine-metrics/creds2.png)
5. После подключения автоматически загрузятся информационная панель, отчет и набор данных. После завершения плитки обновятся в соответствии с данными из вашей учетной записи.
   
    ![](media/service-connect-to-alpine-metrics/dashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="whats-included"></a>Содержимое
Пакет содержимого включает в себя данные из следующих таблиц.  

    - Account    
    - Бизнес    
    - Страна    
    - "Отрасль"    
    - Opportunity  
    - "Лицо"  
    - "Прогноз"    
    - "Журнал прогнозов"    
    - Product  
    - "Регион"    

## <a name="system-requirements"></a>Требования к системе
Чтобы создать этот пакет содержимого, требуется учетная запись Alpine Metrics с разрешениями для вышеперечисленных таблиц.

## <a name="next-steps"></a>Дальнейшие действия
[Что такое Power BI?](fundamentals/power-bi-overview.md)

[Основные понятия для разработчиков в службе Power BI](service-basic-concepts.md)

