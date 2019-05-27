---
title: Исходящий трафик Power BI и Azure
description: Узнайте, как взимается плата за исходящий трафик Azure и Power BI в зависимости от расположения клиента и Power BI Premium
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Data from databases
ms.openlocfilehash: 720ef2f059c3c87be84c3d8db98e89400c161ad0
ms.sourcegitcommit: 10a87c016f497dbeba32f94ed1f3688a70816fea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "65514410"
---
# <a name="power-bi-and-azure-egress"></a>Исходящий трафик Power BI и Azure

При использовании Power BI с источниками данных Azure платы за исходящий трафик Azure можно избежать, сделав так, чтобы ваш клиент Power BI находился в том же регионе, что и источники данных Azure.

Когда клиент Power BI развертывается в одном регионе Azure с развертываемыми источниками данных, плата за исходящий трафик для планового обновления и взаимодействия DirectQuery не взимается. 

## <a name="determining-where-your-power-bi-tenant-is-located"></a>Как определить, где расположен ваш клиент Power BI

Чтобы узнать, где расположен ваш клиент Power BI, см. статью [Где расположен мой клиент Power BI](service-admin-where-is-my-tenant-located.md).

Для клиентов Power BI Premium с несколькими регионами: если ваш клиент Power BI не в оптимальном расположении относительно некоторых источников данных в Azure, можно развернуть Power BI Premium с поддержкой нескольких регионов в нужном регионе Azure и использовать преимущества расположения вашего клиента Power BI и источников данных Azure в одном регионе Azure.

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения о Power BI Premium и размещении в различных регионах см. на следующих ресурсах:

* [Что такое Microsoft Power BI Premium?](service-premium-what-is.md)
* [Как купить Power BI Premium](service-admin-premium-purchase.md)
* [Поддержка нескольких регионов Power BI Premium (предварительная версия)](service-admin-premium-multi-geo.md)
* [Где расположен мой клиент Power BI?](service-admin-where-is-my-tenant-located.md)
* [Вопросы и ответы по Power BI Premium](service-premium-faq.md)


