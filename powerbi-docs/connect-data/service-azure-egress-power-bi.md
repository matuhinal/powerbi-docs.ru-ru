---
title: Исходящий трафик Power BI и Azure
description: Узнайте, как взимается плата за исходящий трафик Azure и Power BI в зависимости от расположения клиента и Power BI Premium
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Data from databases
ms.openlocfilehash: c93299a2066dd2f15843048742e857495db7242a
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85230593"
---
# <a name="power-bi-and-azure-egress"></a>Исходящий трафик Power BI и Azure

При использовании Power BI с источниками данных Azure платы за исходящий трафик Azure можно избежать, сделав так, чтобы ваш клиент Power BI находился в том же регионе, что и источники данных Azure.

Когда клиент Power BI развертывается в одном регионе Azure с развертываемыми источниками данных, плата за исходящий трафик для планового обновления и взаимодействия DirectQuery не взимается. 

## <a name="determining-where-your-power-bi-tenant-is-located"></a>Как определить, где расположен ваш клиент Power BI

Чтобы узнать, где расположен ваш клиент Power BI, см. статью [Где расположен мой клиент Power BI](../admin/service-admin-where-is-my-tenant-located.md).

Для клиентов Power BI Premium с несколькими регионами: если ваш клиент Power BI не в оптимальном расположении относительно некоторых источников данных в Azure, можно развернуть Power BI Premium с поддержкой нескольких регионов в нужном регионе Azure и использовать преимущества расположения вашего клиента Power BI и источников данных Azure в одном регионе Azure.

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения о Power BI Premium и размещении в различных регионах см. на следующих ресурсах:

* [Что такое Microsoft Power BI Premium?](../admin/service-premium-what-is.md)
* [Как купить Power BI Premium](../admin/service-admin-premium-purchase.md)
* [Поддержка нескольких регионов Power BI Premium (предварительная версия)](../admin/service-admin-premium-multi-geo.md)
* [Where is my Power BI tenant located?](../admin/service-admin-where-is-my-tenant-located.md) (Расположение клиента Power BI)
* [Вопросы и ответы по Power BI Premium](../admin/service-premium-faq.md)
