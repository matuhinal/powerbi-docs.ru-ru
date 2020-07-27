---
title: Ограничения субъектов-службы
description: Ограничения субъектов-службы
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 06/06/2020
ms.custom: include file
ms.openlocfilehash: 569d7dfe251183962a14de1c42d85ee2e58950af
ms.sourcegitcommit: d8acf2fb0318708a3e8e1e259cb3747b0312b312
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2020
ms.locfileid: "86401679"
---
## <a name="considerations-and-limitations"></a>Рекомендации и ограничения

* Субъекты-службы работают только с [новыми рабочими областями](../collaborate-share/service-create-the-new-workspaces.md).
* **Моя рабочая область** не поддерживается при использовании субъекта-службы.
* Для миграции в рабочую среду требуется выделенная емкость.
* С помощью субъекта-службы нельзя входить на портал Power BI.
* Для включения субъекта-службы в параметрах разработчика на портале администрирования Power BI требуются права администратора Power BI.
* [Внедренные для организации](../developer/embedded/embed-sample-for-your-organization.md) приложения не могут использовать субъект-службу.
* Управление [потоками данных](../transform-model/service-dataflows-overview.md) не поддерживается.
* Сейчас субъект-служба не поддерживает никакие API администратора.
* При использовании субъекта-службы с источником данных [Azure Analysis Services](https://docs.microsoft.com/azure/analysis-services/analysis-services-overview) сам субъект-служба должен иметь разрешения экземпляра Azure Analysis Services. Использовать для этой цели группу безопасности, содержащую субъект-службу, нельзя.
* Субъект-служба в настоящее время не может получить доступ к источникам данных в шлюзе. То есть вы не можете добавить субъект-службу в качестве пользователя источника данных в шлюзе.
