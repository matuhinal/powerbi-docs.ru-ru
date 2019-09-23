---
title: Power BI и ExpressRoute
description: Power BI и ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: c7d12bf6a1a2a02c988f8351a1844be1080ad2b8
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71074805"
---
# <a name="power-bi-and-expressroute"></a>Power BI и ExpressRoute

**ExpressRoute** — это служба Azure, которая позволяет создавать частные подключения между центрами обработки данных Azure (где находится Power BI) и локальной инфраструктурой или создавать частные подключения между центрами обработки данных Azure и средой совместного размещения.

С помощью **Power BI** и **ExpressRoute** можно создать подключение между частной сетью организации и Power BI (или используя средство совместного размещения поставщика услуг Интернета), обходя Интернет для повышения безопасности конфиденциальных данных Power BI и подключений.

См. дополнительные сведения об [ExpressRoute](/azure/expressroute/expressroute-introduction). Служба Power BI совместима с ExpressRoute, кроме нескольких исключений, когда Power BI получает или отправляет данные через общедоступный Интернет. См. [список URL-адресов, используемых Power BI](power-bi-whitelist-urls.md).

![Схема ExpressRoute](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)