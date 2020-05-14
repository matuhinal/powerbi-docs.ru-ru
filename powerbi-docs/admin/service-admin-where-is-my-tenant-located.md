---
title: Расположение клиента Power BI
description: Узнайте, где расположен ваш клиент Power BI и как происходит выбор места расположения. Это важно знать, так как место расположения клиента может влиять на качество обмена данными со службой.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 4a763b31333004a8cdecda5262967473817bc983
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83136000"
---
# <a name="where-is-my-power-bi-tenant-located"></a>Расположение клиента Power BI

<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

Узнайте, где расположен ваш клиент Power BI и как происходит выбор места расположения. Это важно знать, так как расположение клиента может влиять на взаимодействие со службой.

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>Как определить, где расположен ваш клиент Power BI

Чтобы найти регион, в котором расположен ваш клиент, выполните следующие действия.

1. В службе Power BI в верхнем меню выберите справку ( **?** ) и **О Power BI**.

1. Посмотрите, какой регион указан после текста **Ваши данные сохранены в**. Это регион, в котором расположен ваш клиент. Кроме того, это значение указывает на регион, где хранятся ваши данные, если только вы не используете для своих рабочих областей выделенные емкости в разных регионах.

    ![Область данных](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>Как происходит выбор региона

Регион для хранения данных зависит от страны, которая была выбрана при создании клиента. Это относится к регистрации в Office 365 и Power BI, так как эта информация является общей для указанных служб. Если это новый клиент, выберите нужную страну в списке при регистрации.

![Выбор страны](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Power BI выбирает регион, наиболее близкий к выбранному варианту, определяя, где будут храниться данные для вашего клиента.

> [!IMPORTANT]
> Этот выбор нельзя будет изменить после создания клиента.

У вас имеются и другие вопросы? [Ответы на них см. в сообществе Power BI.](https://community.powerbi.com/)
