---
title: Как администраторы могут управлять формами для входа в Power BI Desktop
description: Узнайте, как управлять начальной формой для входа, отображаемой при открытии Power BI Desktop.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: davidi
ms.openlocfilehash: 98bf9579ae7ee551634eed765138c0e78156464c
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Как администраторы могут управлять формой для входа в Power BI Desktop
При первом запуске Power BI Desktop отображается форма для входа. Вы можете заполнить эту форму или войти в Power BI, чтобы продолжить. Администраторы могут управлять этой формой с помощью раздела реестра. 

![Начальная форма для входа в Power BI Desktop](media/desktop-admin-sign-in-form/sign-in-form.png)

Администраторы могут отключить форму для входа, используя следующий раздел реестра. Ее также можно отключить, применив глобальные политики для всей организации.

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

Задайте значение 0, чтобы отключить диалоговое окно.

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

