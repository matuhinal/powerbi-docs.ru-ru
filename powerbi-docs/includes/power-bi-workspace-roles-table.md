---
title: Роли рабочей области Power BI
description: Таблица ролей рабочей области Power BI
services: powerbi
author: maggiesMSFT
ms.service: powerbi
ms.topic: include
ms.date: 06/23/2020
ms.author: maggies
ms.custom: include file
ms.openlocfilehash: 9ddf9df0feaed2a2a0177d11e9b36f34135801c6
ms.sourcegitcommit: caf60154a092f88617eb177bc34fb784f2365962
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365357"
---
|Функция   | Административный  | Участник  | Участник  | Зритель |
|---|---|---|---|---|
| Обновлять и удалять рабочую область.  |  |   |   |   | 
| Добавлять и удалять пользователей, включая других администраторов.  |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |   |   |   |
| Разрешить участникам обновлять приложение для этой рабочей области  |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |   |   |   |
| Добавлять членов или других пользователей с разрешениями более низкого уровня.  |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Публикация и изменение разрешений для приложения |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Обновление приложения |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |  Если разрешено<sup>1</sup>  |   |
| Предоставление общего доступа к элементу или приложению<sup>2</sup> |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Разрешать другим пользователям передавать предоставленные права доступа к элементам<sup>2</sup> |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Добавлять приложения в подборку на главной странице коллег |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |   |
| Добавлять панели мониторинга и отчеты в подборку на главной странице коллег |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |   |
| Создавать, редактировать и удалять содержимое в рабочей области.  |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |
| Публиковать отчеты в рабочей области, удалять содержимое.  |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |
| Создать отчет в другой рабочей области на основе набора данных в этой области.<sup>2</sup> |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |   |
| Копирование отчета<sup>3</sup> | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |  |
| Данные расписания обновляются через локальный шлюз<sup>4</sup> | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |  |
| Изменение параметров подключения через шлюз<sup>4</sup> | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |  |
| Просмотр элемента и взаимодействие с ним<sup>5</sup> |  ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png)  |
| Читать данные, хранящиеся в потоках данных рабочей области. | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) | ![Флажок "Да"](media/power-bi-workspace-roles-table/green-checkmark.png) |

<sup>1</sup> Участники могут обновлять метаданные приложения, но не публиковать новое приложение или изменять права доступа других пользователей к приложению, если [администратор рабочей области делегировал такие права участникам](../collaborate-share/service-create-the-new-workspaces.md#security-settings).

<sup>2</sup> Участники и читатели также могут совместно использовать элементы в рабочей области, если у них есть разрешения на передачу прав доступа другим пользователям.

<sup>3</sup> Чтобы скопировать отчет или создать в другой рабочей области новый отчет на основе набора данных из текущей области, требуется [разрешение на создание набора данных](../connect-data/service-datasets-build-permissions.md). При использовании наборов данных из этой рабочей области пользователям с ролями администратора, члена или участника автоматически предоставляются разрешения на создание в рамках роли рабочей области.

<sup>4</sup> Учитывайте, что вам также потребуются разрешения на шлюз. Эти разрешения управляются в других местах, независимо от ролей и разрешений рабочей области. Дополнительные сведения см. в разделе [Управление локальным шлюзом](https://docs.microsoft.com/data-integration/gateway/service-gateway-manage).

<sup>5</sup> Даже если у вас нет лицензии Power BI Pro, вы можете просматривать элементы и взаимодействовать с ними в службе Power BI, если они находятся в рабочей области в емкости Premium.
