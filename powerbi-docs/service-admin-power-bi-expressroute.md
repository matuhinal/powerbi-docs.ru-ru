---
title: Power BI и ExpressRoute
description: Power BI и ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 12/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 0c4618150094a4eabb0dc9745e9ac93e4f342ff1
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "61187899"
---
# <a name="power-bi-and-expressroute"></a>Power BI и ExpressRoute

**ExpressRoute** — это служба Azure, которая позволяет создавать частные подключения между центрами обработки данных Azure (где находится Power BI) и локальной инфраструктурой или создавать частные подключения между центрами обработки данных Azure и средой совместного размещения.

С помощью **Power BI** и **ExpressRoute** можно создать подключение между частной сетью организации и Power BI (или используя средство совместного размещения поставщика услуг Интернета), обходя Интернет для повышения безопасности конфиденциальных данных Power BI и подключений.

См. дополнительные сведения об [ExpressRoute](/azure/expressroute/expressroute-introduction). Служба Power BI совместима с ExpressRoute, кроме нескольких исключений, когда Power BI получает или отправляет данные через общедоступный Интернет. См. [список URL-адресов, используемых Power BI](power-bi-whitelist-urls.md).

![Схема ExpressRoute](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)