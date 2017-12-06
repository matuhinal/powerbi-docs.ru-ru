---
title: "Сторонняя служба соединитель Facebook для Power BI Desktop"
description: "Сторонняя служба соединитель Facebook для Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 4e8600aac79683a53b7c2075b3d81e91b3354901
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2017
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Соединитель Facebook для Power BI Desktop
Соединитель Facebook в **Power BI Desktop** основывается на Facebook Graph API. Таким образом, наличие функций и доступность со временем могут меняться.

Можно ознакомиться с [учебником о соединителе Facebook для Power BI Desktop](desktop-tutorial-facebook-analytics.md).

30 апреля <sup></sup>2015 года истек срок действия Facebook Graph API версии 1.0. Power BI использует Graph API в фоновом режиме для соединителя Facebook, позволяя подключаться к данным и анализировать их.

Запросы, которые были созданы до 30 апреля <sup></sup>2015 года, могут не работать или возвращать меньше данных. После 30 апреля <sup></sup>2015 года в Power BI во всех вызовах API Facebook используется версия 2.2. Если запрос был сформирован до 30 апреля 2015 года, скорее всего, потребуется снова пройти проверку подлинности, чтобы утвердить новый набор разрешений, который будет запрошен.

Несмотря на попытки выпуска обновлений в соответствии с любыми изменениями, API-интерфейс может измениться так, что изменения повлияют на результаты формируемых запросов. В некоторых случаях поддержка определенных запросов может отсутствовать. В связи с этой зависимостью мы не гарантируем наличие и правильность результатов запросов при использовании этого соединителя.

Дополнительные сведения об изменениях API Facebook доступны [здесь](https://developers.facebook.com/docs/apps/changelog#v2_0).

