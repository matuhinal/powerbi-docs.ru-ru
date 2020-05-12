---
title: Подключение к Office365Mon с помощью Power BI
description: Office365Mon для Power BI
author: paulinbar
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 11/26/2019
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 8e9563d10d80290a48e20cd2d6a889831d34924b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "74548593"
---
# <a name="connect-to-office365mon-with-power-bi"></a>Подключение к Office365Mon с помощью Power BI
С функциями Power BI и приложения-шаблона Office365Mon вам будет легко анализировать данные о перебоях в работе и состоянии служб Office 365. Power BI извлекает данные, в том числе сведения о сбоях в работе и проверках работоспособности, затем создает стандартную панель мониторинга и формирует на основе этой информации отчеты.

Подключите [приложение-шаблон Office365Mon](https://msit.powerbi.com/groups/me/getapps/services/office365mon.office365mon_powerbi_v3) для Power BI.

>[!NOTE]
>Для подключения и загрузки приложения шаблона Power BI необходима учетная запись администратора Office365Mon.

## <a name="how-to-connect"></a>Способы подключения
1. В нижней части области навигации выберите **Получить данные**.
   
   ![](media/service-connect-to-office365mon/pbi_getdata.png)
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-office365mon/pbi_getservices.png) 
3. Выберите **Office365Mon** \> **Получить**.
   
   ![](media/service-connect-to-office365mon/o365mon.png)
4. В качестве метода проверки подлинности выберите **oAuth2** \> **Вход**.
   
   При появлении запроса введите учетные данные администратора Office365Mon и пройдите проверку подлинности.
   
   ![](media/service-connect-to-office365mon/creds.png)
   
   ![](media/service-connect-to-office365mon/creds2.png)
5. После импорта данных в Power BI в области навигации слева появятся новая панель мониторинга, отчеты и набора данных. Новые элементы будут отмечены желтой звездочкой (\*). Выберите Office365Mon.
   
   ![](media/service-connect-to-office365mon/dashboard4.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="troubleshooting"></a>Устранение неполадок
Если после входа с учетными данными подписки Office365Mon возникает ошибка **Ошибка входа** , у вашей учетной записи отсутствуют разрешения на извлечение данных Office365Mon. Убедитесь, что это учетная запись администратора, и повторите попытку.

## <a name="next-steps"></a>Дальнейшие действия
[Что такое Power BI?](fundamentals/power-bi-overview.md)

[Получение данных для Power BI](service-get-data.md)

