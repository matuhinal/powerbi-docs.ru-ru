---
title: Как администраторы могут управлять формами для входа в Power BI Desktop
description: Узнайте, как управлять начальной формой для входа, отображаемой при открытии Power BI Desktop.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: davidi
ms.openlocfilehash: 5c31277b640b16882bef5c5f2cd9c56b441ede82
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "61329895"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Как администраторы могут управлять формой для входа в Power BI Desktop
При первом запуске Power BI Desktop отображается форма для входа. Вы можете заполнить эту форму или войти в Power BI, чтобы продолжить. Администраторы управляют этой формой с помощью раздела реестра. 

![Начальная форма для входа в Power BI Desktop](media/desktop-admin-sign-in-form/sign-in-form.png)

Администраторы могут отключить форму для входа, используя указанный ниже раздел реестра. Ее также можно отключить для всей организации с помощью глобальных политик.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```
Вы также можете воспользоваться следующим разделом. Такой способ подошел некоторым клиентам с учетом их конфигураций.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```

Задайте значение 0, чтобы отключить диалоговое окно.




Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

