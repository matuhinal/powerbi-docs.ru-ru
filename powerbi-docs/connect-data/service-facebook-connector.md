---
title: 'Служба сторонних разработчиков: Соединитель Facebook для Power BI Desktop'
description: 'Служба сторонних разработчиков: Соединитель Facebook для Power BI Desktop'
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/20/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 882cddf7728a27e78056a35c14fde20f00678e33
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83309551"
---
# <a name="use-the-facebook-connector-for-power-bi-desktop"></a>Используйте соединитель Facebook для Power BI Desktop
Соединитель Facebook в **Power BI Desktop** основывается на Facebook Graph API. поэтому его функции и доступность могут измениться в дальнейшем.

Можно ознакомиться с [учебником о соединителе Facebook для Power BI Desktop](desktop-tutorial-facebook-analytics.md).

> [!IMPORTANT]
> **Уведомление о прекращении поддержки соединителя данных Facebook** Функция импорта и экспорта данных из Facebook в Excel перестанет нормально работать в апреле 2020 г. До этого момента вы можете использовать соединитель Facebook *Get & Transform (Power Query)* (Получить и преобразовать [Power Query]). После этой даты вы не сможете подключиться к Facebook; вместо этого будет возникать сообщение об ошибке. Мы рекомендуем как можно скорее изменить или удалить все существующие запросы *Get & Transform (Power Query)* (Получить и преобразовать [Power Query]), которые используют соединитель Facebook, чтобы избежать непредвиденных результатов.


30 апреля 2015 года истек срок действия API Graph версии 1.0 для Facebook. Power BI использует Graph API в фоновом режиме для соединителя Facebook, позволяя подключаться к данным и анализировать их.

Запросы, которые были созданы до 30 апреля 2015 года, могут не работать или возвращать меньше данных. После 30 апреля 2015 года в Power BI во всех вызовах API Facebook используется версия 2.8. Если запрос был сформирован до 30 апреля 2015 года, скорее всего, потребуется снова пройти проверку подлинности, чтобы утвердить новый набор разрешений, который будет запрошен.

Несмотря на попытки выпуска обновлений в соответствии с любыми изменениями, API-интерфейс может измениться так, что изменения повлияют на результаты формируемых запросов. В некоторых случаях поддержка определенных запросов может отсутствовать. В связи с этой зависимостью мы не гарантируем наличие и правильность результатов запросов при использовании этого соединителя.

Дополнительные сведения об изменениях API Facebook доступны [здесь](https://developers.facebook.com/docs/apps/changelog#v2_0).

