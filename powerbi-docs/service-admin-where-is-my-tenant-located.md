---
title: Где расположен мой клиент Power BI?
description: Узнайте, где расположен ваш клиент Power BI и как происходит выбор места расположения. Это важно знать, так как место расположения клиента может влиять на качество обмена данными со службой.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: c0c6de63292d3087aaa78dd97b73f868ef9d804e
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34293658"
---
# <a name="where-is-my-power-bi-tenant-located"></a>Где расположен мой клиент Power BI?
<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

Узнайте, где расположен ваш клиент Power BI и как происходит выбор места расположения. Это важно знать, так как место расположения клиента может влиять на качество обмена данными со службой.

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>Как определить, где расположен ваш клиент Power BI
Чтобы найти регион, в котором расположен ваш клиент, выполните следующие действия.

1. Нажмите кнопку **?** на странице службы Power BI.
2. Выберите **О Power BI**.
3. Посмотрите, какой регион указан после текста **Ваши данные сохранены в**. Это регион, в котором расположен ваш клиент.

![](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>Как происходит выбор региона
Выбор региона для хранения данных зависит от страны, которая была выбрана при создании клиента. Это относится к регистрации в Office 365 в дополнение к Power BI, так как эта информация является общей для указанных служб. Если вы создаете новый клиент, при заполнении регистрационной формы вы увидите раскрывающийся список стран.

![](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Выбор страны из этого списка влияет на выбор места хранения ваших данных. Служба Power BI выберет для хранения данных ближайший к выбранной стране регион.

> [!WARNING]
> Этот выбор нельзя изменить.
> 
> 

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

