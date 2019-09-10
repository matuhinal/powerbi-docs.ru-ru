---
title: Устранение неполадок с запланированным обновлением для баз данных SQL Azure
description: Устранение неполадок с запланированным обновлением для баз данных SQL Azure в Power BI
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/04/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 4bc14b9a3d863732c581e8a144d612d864d65af8
ms.sourcegitcommit: c799941c8169cd5b6b6d63f609db66ab2af93891
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70391831"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>Устранение неполадок с запланированным обновлением для баз данных SQL Azure в Power BI

Дополнительные сведения об обновлении см. в статьях [Обновление данных в Power BI](refresh-data.md) и [Настройка запланированного обновления](refresh-scheduled-refresh.md).

Если при настройке запланированного обновления базы данных SQL Azure во время редактирования учетных данных возникает ошибка с кодом 400, попробуйте выполнить следующие действия, чтобы настроить соответствующее правило брандмауэра:

1. Войдите на [портал Azure](https://portal.azure.com).

1. Перейдите в базу данных SQL Azure, для которой выполняется настройка обновления.

1. В верхней части колонки **Обзор** выберите **Настройка брандмауэра для сервера**.

1. Убедитесь, что в колонке **Параметры брандмауэра** для параметра **Разрешить доступ к службам Azure** задано значение **ВКЛ**.

    ![Разрешенные службы Azure](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)
