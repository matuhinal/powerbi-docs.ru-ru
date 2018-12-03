---
title: Сторонняя служба соединитель Facebook для Power BI Desktop
description: Сторонняя служба соединитель Facebook для Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 66f6fa32ecabecfbaa178b5744e71c80a6020ebd
ms.sourcegitcommit: 2ae660a7b70fce23eb58b159d049eca44a664f2c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/30/2018
ms.locfileid: "52669665"
---
# <a name="facebook-connector-for-power-bi-desktop"></a>Соединитель Facebook для Power BI Desktop
Соединитель Facebook в **Power BI Desktop** основывается на Facebook Graph API. Таким образом, наличие функций и доступность со временем могут меняться.

Можно ознакомиться с [учебником о соединителе Facebook для Power BI Desktop](desktop-tutorial-facebook-analytics.md).

30 апреля <sup></sup>2015 года истек срок действия Facebook Graph API версии 1.0. Power BI использует Graph API в фоновом режиме для соединителя Facebook, позволяя подключаться к данным и анализировать их.

Запросы, которые были созданы до 30 апреля <sup></sup>2015 года, могут не работать или возвращать меньше данных. После 30 апреля<sup> </sup>2015 года в Power BI во всех вызовах API Facebook используется версия 2.8. Если запрос был сформирован до 30 апреля 2015 года, скорее всего, потребуется снова пройти проверку подлинности, чтобы утвердить новый набор разрешений, который будет запрошен.

Несмотря на попытки выпуска обновлений в соответствии с любыми изменениями, API-интерфейс может измениться так, что изменения повлияют на результаты формируемых запросов. В некоторых случаях поддержка определенных запросов может отсутствовать. В связи с этой зависимостью мы не гарантируем наличие и правильность результатов запросов при использовании этого соединителя.

Дополнительные сведения об изменениях API Facebook доступны [здесь](https://developers.facebook.com/docs/apps/changelog#v2_0).

