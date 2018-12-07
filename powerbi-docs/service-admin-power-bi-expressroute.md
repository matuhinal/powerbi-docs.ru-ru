---
title: Power BI и ExpressRoute
description: Power BI и ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 12/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 62289c974e25207f3a991e7f17a0ee965c729b8a
ms.sourcegitcommit: b03912343a5a214c6bb972aaa6aa051c2a5f4332
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2018
ms.locfileid: "52900136"
---
# <a name="power-bi-and-expressroute"></a>Power BI и ExpressRoute

**ExpressRoute** — это служба Azure, которая позволяет создавать частные подключения между центрами обработки данных Azure (где находится Power BI) и локальной инфраструктурой или создавать частные подключения между центрами обработки данных Azure и средой совместного размещения.

С помощью **Power BI** и **ExpressRoute** можно создать подключение между частной сетью организации и Power BI (или используя средство совместного размещения поставщика услуг Интернета), обходя Интернет для повышения безопасности конфиденциальных данных Power BI и подключений.

См. дополнительные сведения об [ExpressRoute](/azure/expressroute/expressroute-introduction). Служба Power BI совместима с ExpressRoute, кроме нескольких исключений, когда Power BI получает или отправляет данные через общедоступный Интернет. См. [список URL-адресов, используемых Power BI](power-bi-whitelist-urls.md).

![Схема ExpressRoute](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)