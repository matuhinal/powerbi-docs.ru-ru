---
title: Как администраторы могут управлять формами для входа в Power BI Desktop
description: Узнайте, как управлять начальной формой для входа, отображаемой при открытии Power BI Desktop.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 04/15/2019
ms.author: davidi
ms.openlocfilehash: 44add6bf76e5bc4445df08a76859e05c8fa1638d
ms.sourcegitcommit: c18130ea61e67ba111be870ddb971c6413a4b632
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86160877"
---
# <a name="administrators-manage-the-power-bi-desktop-sign-in-form"></a>Администраторы Управление формой для входа в Power BI Desktop
При первом запуске Power BI Desktop отображается форма для входа. Вы можете заполнить эту форму или войти в Power BI, чтобы продолжить. Администраторы управляют этой формой с помощью раздела реестра. 

![Снимок экрана: начальная форма для входа в Power BI Desktop](media/desktop-admin-sign-in-form/sign-in-form.png)

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




Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

