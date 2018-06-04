---
title: Подключение к VMob с помощью Power BI
description: VMob для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: b1f2970ad73783acf3736856463915161056b801
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34237883"
---
# <a name="connect-to-vmob-with-power-bi"></a>Подключение к VMob с помощью Power BI
Отслеживание и исследование данных VMob упрощается благодаря Power BI и пакету содержимого VMob. Power BI извлекает следующие данные: статистика пользователей за весь период и за последние 30 дней, а также ключевые показатели эффективности розничных продаж и эффективность кампании за последние 30 дней.

Подключите [пакет содержимого VMob](https://app.powerbi.com/getdata/services/vmob) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
    ![](media/service-connect-to-vmob/getdata.png)
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-vmob/services.png)
3. Выберите **VMob** \> **Получить**.
   
   ![](media/service-connect-to-vmob/vmob.png)
4. При появлении запроса введите URL-адрес VMob и нажмите кнопку "Далее". VMob предоставляет этот URL-адрес отдельно.
   
    ![](media/service-connect-to-vmob/params.png)
5. Выберите параметр **Базовый** в раскрывающемся списке методов проверки подлинности, введите свое имя пользователя и пароль в VMob и нажмите кнопку **Вход** .
   
    ![](media/service-connect-to-vmob/creds.png)
6. Процедура импорта начнется автоматически, а Power BI извлечет ваши данные VMob для создания готовой к использованию панели мониторинга и соответствующего отчета.
   
   ![](media/service-connect-to-vmob/dashboard2.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Получение данных в Power BI](service-get-data.md)

