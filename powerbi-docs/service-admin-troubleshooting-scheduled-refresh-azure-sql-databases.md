---
title: "Устранение неполадок с запланированным обновлением для баз данных SQL Azure"
description: "Устранение неполадок с запланированным обновлением для баз данных SQL Azure в Power BI"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 0b2f5da3fccd1741cb5a9ea02a1aebbd8fbac96f
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2017
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Устранение неполадок с запланированным обновлением для баз данных SQL Azure в Power BI
Подробные инструкции по настройке запланированного обновления см. в разделе [Обновление данных в Power BI](refresh-data.md).

Если при настройке запланированного обновления базы данных SQL Azure во время редактирования учетных данных возникает ошибка с кодом 400, попробуйте выполнить следующие действия, чтобы настроить соответствующее правило брандмауэра.

1. Войдите на портал управления Azure.
2. Перейдите на сервер SQL Azure, для которого вы настраиваете обновление.
3. Включите "Службы Microsoft Azure" в разделе разрешенных служб.

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

