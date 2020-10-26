---
title: Ограничения субъектов-службы
description: Ограничения субъектов-службы
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 06/06/2020
ms.custom: include file
ms.openlocfilehash: a8dd57b84f016ed798366898f4172ac9379ca26f
ms.sourcegitcommit: 02484b2d7a352e96213353702d60c21e8c07c6c0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "91989558"
---
## <a name="considerations-and-limitations"></a>Рекомендации и ограничения

* Субъекты-службы работают только с [новыми рабочими областями](../collaborate-share/service-create-the-new-workspaces.md).
* **Моя рабочая область** не поддерживается при использовании субъекта-службы.
* Для миграции в рабочую среду требуется емкость.
* С помощью субъекта-службы нельзя входить на портал Power BI.
* Для включения субъекта-службы в параметрах разработчика на портале администрирования Power BI требуются права администратора Power BI.
* [Внедренные для организации](../developer/embedded/embed-sample-for-your-organization.md) приложения не могут использовать субъект-службу.
* Управление [потоками данных](../transform-model/service-dataflows-overview.md) не поддерживается.
* Сейчас субъект-служба не поддерживает никакие API администратора.
* При использовании субъекта-службы с источником данных [Azure Analysis Services](/azure/analysis-services/analysis-services-overview) сам субъект-служба должен иметь разрешения экземпляра Azure Analysis Services. Использовать для этой цели группу безопасности, содержащую субъект-службу, нельзя.