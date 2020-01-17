---
title: 'Служба сторонних разработчиков: Соединитель Facebook для Power BI Desktop'
description: 'Служба сторонних разработчиков: Соединитель Facebook для Power BI Desktop'
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: dcfc695d0371cce21a827ddfe71b3b4b05863935
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "75762423"
---
# <a name="use-the-facebook-connector-for-power-bi-desktop"></a>Используйте соединитель Facebook для Power BI Desktop
Соединитель Facebook в **Power BI Desktop** основывается на Facebook Graph API. поэтому его функции и доступность могут измениться в дальнейшем.

Можно ознакомиться с [учебником о соединителе Facebook для Power BI Desktop](desktop-tutorial-facebook-analytics.md).

30 апреля 2015 года истек срок действия API Graph версии 1.0 для Facebook. Power BI использует Graph API в фоновом режиме для соединителя Facebook, позволяя подключаться к данным и анализировать их.

Запросы, которые были созданы до 30 апреля 2015 года, могут не работать или возвращать меньше данных. После 30 апреля 2015 года в Power BI во всех вызовах API Facebook используется версия 2.8. Если запрос был сформирован до 30 апреля 2015 года, скорее всего, потребуется снова пройти проверку подлинности, чтобы утвердить новый набор разрешений, который будет запрошен.

Несмотря на попытки выпуска обновлений в соответствии с любыми изменениями, API-интерфейс может измениться так, что изменения повлияют на результаты формируемых запросов. В некоторых случаях поддержка определенных запросов может отсутствовать. В связи с этой зависимостью мы не гарантируем наличие и правильность результатов запросов при использовании этого соединителя.

Дополнительные сведения об изменениях API Facebook доступны [здесь](https://developers.facebook.com/docs/apps/changelog#v2_0).

