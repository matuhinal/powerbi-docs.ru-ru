---
title: Роли рабочей области Power BI
description: Таблица ролей рабочей области Power BI
services: powerbi
author: maggiesMSFT
ms.service: powerbi
ms.topic: include
ms.date: 05/26/2020
ms.author: maggies
ms.custom: include file
ms.openlocfilehash: 708599eb3f39d4c627a11753cb964d6425f75640
ms.sourcegitcommit: a7b142685738a2f26ae0a5fa08f894f9ff03557b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "84120418"
---
|Возможность   | Администратор  | Участник  | Участник  | Зритель |
|---|---|---|---|---|
| Обновлять и удалять рабочую область.  |  |   |   |   | 
| Добавлять и удалять пользователей, включая других администраторов.  |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |   |   |   |
| Добавлять членов или других пользователей с разрешениями более низкого уровня.  |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Публиковать и обновлять приложение. |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Предоставлять общий доступ к элементу или приложению.<sup>1</sup> |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Разрешать другим пользователям повторно предоставлять совместный доступ к элементам.<sup>1</sup> |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Добавлять приложения в подборку на главной странице коллег |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Добавлять панели мониторинга и отчеты в подборку на главной странице коллег |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |   |
| Создавать, редактировать и удалять содержимое в рабочей области.  |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |
| Публиковать отчеты в рабочей области, удалять содержимое.  |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |
| Создать отчет в другой рабочей области на основе набора данных в этой области.<sup>2</sup> |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |
| Копировать отчет.<sup>2</sup> | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |  |
| Данные расписания обновляются через локальный шлюз.<sup>3</sup> | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |  |
| Изменение параметров подключения через VPN-шлюз.<sup>3</sup> | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |  |
| Просматривать элемент и взаимодействовать с ним.<sup>4</sup> |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |
| Читать данные, хранящиеся в потоках данных рабочей области. | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |

<sup>1</sup> Участники и зрители также могут совместно использовать элементы в рабочей области, если у них есть разрешения на повторное предоставление общего доступа.

<sup>2</sup> Чтобы скопировать отчет или создать в другой рабочей области новый отчет на основе набора данных из текущей области, требуется [разрешение на создание набора данных](../connect-data/service-datasets-build-permissions.md). При использовании наборов данных из этой рабочей области пользователям с ролями администратора, члена или участника автоматически предоставляются разрешения на создание в рамках роли рабочей области.

<sup>3</sup> Учитывайте, что также требуются разрешения на шлюз. Эти разрешения управляются в других местах, независимо от ролей и разрешений рабочей области. Дополнительные сведения см. в разделе [Управление локальным шлюзом](https://docs.microsoft.com/data-integration/gateway/service-gateway-manage).

<sup>4</sup> Даже если у вас нет лицензии Power BI Pro, вы можете просматривать элементы и взаимодействовать с ними в службе Power BI, если они находятся в рабочей области в емкости Premium.

