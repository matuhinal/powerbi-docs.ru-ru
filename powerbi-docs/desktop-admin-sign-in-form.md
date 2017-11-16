---
title: "Как администраторы могут управлять формами для входа в Power BI Desktop"
description: "Узнайте, как управлять начальной формой для входа, отображаемой при открытии Power BI Desktop."
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
ms.date: 10/17/2017
ms.author: davidi
ms.openlocfilehash: eabb59b32234fce1ba5669b95abb41c4f7e04aa2
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
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

