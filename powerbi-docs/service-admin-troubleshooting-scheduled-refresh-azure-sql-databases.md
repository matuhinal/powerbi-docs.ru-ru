---
title: Устранение неполадок с запланированным обновлением для баз данных SQL Azure
description: Устранение неполадок с запланированным обновлением для баз данных SQL Azure в Power BI
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: d1cd68fbb995b7fac420a50f97a8930385086a10
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "53026070"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Устранение неполадок с запланированным обновлением для баз данных SQL Azure в Power BI
Подробные инструкции по настройке запланированного обновления см. в разделе [Обновление данных в Power BI](refresh-data.md).

Если при настройке запланированного обновления базы данных SQL Azure во время редактирования учетных данных возникает ошибка с кодом 400, попробуйте выполнить следующие действия, чтобы настроить соответствующее правило брандмауэра.

1. Войдите на портал управления Azure.
2. Перейдите на сервер SQL Azure, для которого вы настраиваете обновление.
3. Включите "Службы Microsoft Azure" в разделе разрешенных служб.

![Разрешенные службы Azure](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

