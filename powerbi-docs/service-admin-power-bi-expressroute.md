---
title: Power BI и ExpressRoute
description: Power BI и ExpressRoute
author: mgblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 59ddddcf1b02f07b850294fa314b7508f7f9fcdc
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2019
ms.locfileid: "73856948"
---
# <a name="power-bi-and-expressroute"></a>Power BI и ExpressRoute

**ExpressRoute** — это служба Azure, которая позволяет создавать частные подключения между центрами обработки данных Azure (где находится Power BI) и локальной инфраструктурой или создавать частные подключения между центрами обработки данных Azure и средой совместного размещения.

С помощью **Power BI** и **ExpressRoute** можно создать подключение между частной сетью организации и Power BI (или используя средство совместного размещения поставщика услуг Интернета), обходя Интернет для повышения безопасности конфиденциальных данных Power BI и подключений.

См. дополнительные сведения об [ExpressRoute](/azure/expressroute/expressroute-introduction). Служба Power BI совместима с ExpressRoute, кроме нескольких исключений, когда Power BI получает или отправляет данные через общедоступный Интернет. См. [список URL-адресов, используемых Power BI](power-bi-whitelist-urls.md).

![Схема ExpressRoute](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)