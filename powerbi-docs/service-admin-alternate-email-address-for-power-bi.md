---
title: "Использование запасного адреса электронной почты"
description: "Использование запасного адреса электронной почты"
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 08/09/2017
ms.author: asaxton
ms.openlocfilehash: 4d58c0dfb07153b9061aa572416be2d8bc7858bd
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="using-an-alternate-email-address"></a>Использование запасного адреса электронной почты
По умолчанию адрес электронной почты, используемый вами для входа в Power BI, также используется для отправки вам сообщений об обновлениях, связанных с действиями в Power BI.  Например, этот адрес будет задействован, когда другой пользователь отправляет вам приглашение к общему доступу.

Иногда требуется, чтобы сообщения электронной почты доставлялись на альтернативный адрес, не совпадающий с адресом электронной почты, который использовался для входа в Power BI.

## <a name="updating-through-office-365-personal-info-page"></a>Обновление с помощью страницы с личными сведениями Office 365
1. Откройте [страницу со своими личными сведениями Office 365](https://portal.office.com/account/#personalinfo).  При появлении запроса на вход укажите адрес электронной почты и пароль, используемые для входа в Power BI.
2. Щелкните ссылку "Изменить" в разделе контактных сведений.  
   
   > [!NOTE]
   > Если эта ссылка отсутствует, то ваш адрес электронной почты управляется администратором Office 365 и для изменения адреса электронной почты нужно обратиться к нему.
   > 
   > 
   
   ![](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)
3. В поле запасного адреса электронной почты введите адрес электронной почты, который вы хотели бы использовать для получения сообщений об обновлениях, отправляемых службой Power BI.

> [!NOTE]
> Изменение этого параметра не повлияет на то, какой адрес электронной почты будет использоваться для отправки сообщений об обновлениях служб, информационных бюллетеней и других рекламных материалов.  Такие сообщения всегда будут посылаться на электронный адрес, использованный при регистрации в Power BI.
> 
> 

## <a name="updating-with-powershell"></a>Обновление с помощью PowerShell
Вы также можете обновить альтернативный адрес электронной почты через PowerShell для Azure Active Directory. Это делается с помощью команды [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser).

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

Дополнительные сведения см. в статье [Azure Active Directory PowerShell Version 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (Azure Active Directory PowerShell версии 2).

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

