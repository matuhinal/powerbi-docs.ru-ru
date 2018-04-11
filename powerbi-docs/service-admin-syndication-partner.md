---
title: Невозможно добавить Power BI к партнеру по распространению Office 365
description: Невозможно добавить Power BI к партнеру по распространению подписок на Office 365. Модель распространения подписок — это модель приобретения, используемая для Office 365.
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 09/05/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: ace24b392668b5459d21a451319fd54eb6430371
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2018
---
# <a name="unable-to-add-power-bi-to-office-365-partner-subscription"></a>Невозможно добавить Power BI к партнерской подписке на Office 365
Office 365 позволяет компаниям перепродавать пакеты Office 365, интегрированные в их собственные решения. В этом случае такие компании и решения являются единой точкой контакта по вопросам приобретения, выставления счетов и поддержки.

Если вы заинтересованы в приобретении Power BI вместе с подпиской Office 365, мы рекомендуем обратиться к своему партнеру. Если ваш партнер не предлагает Power BI, вы можете рассмотреть другие варианты.

1. Вы можете приобрести службу по другому каналу — непосредственно в корпорации Майкрософт или у другого партнера. В зависимости от отношений с партнером этим вариантом могут воспользоваться лишь некоторые клиенты. Чтобы проверить наличие этой возможности, перейдите в следующий раздел на **портале администрирования Office 365** > **Выставление счетов** > **Подписки**. Если вы видите раздел **Подписки**, вы можете приобрести службу непосредственно в корпорации Майкрософт или обратиться к партнеру, который предлагает Power BI.
   
    ![](media/service-admin-syndication-partner/billingsub.png)
2. Если раздел **Подписки** в разделе **Выставление счетов**отсутствует, вы не сможете приобрести службу непосредственно в корпорации Майкрософт или у другого партнера. 
   
   ![](media/service-admin-syndication-partner/billing.png)

Если вы не можете приобрести Power BI напрямую и планируете приобрести определенную подписку Power BI, у вас все еще остаются некоторые варианты.

[Power BI (бесплатная версия)](#power-bi-free)

[Power BI Pro и Premium](#power-bi-pro)

## <a name="power-bi-free"></a>Power BI (бесплатная)
Если вам достаточно бесплатной версии, зарегистрируйтесь в бесплатной службе Power BI. По умолчанию индивидуальная регистрация (специализированная подписка) не поддерживается. При попытке регистрации в Power BI вы получите сообщение о том, что ваш ИТ-отдел отключил регистрацию в службе Microsoft Power BI.

    Your IT department has turned off signup for Microsoft Power BI.

![](media/service-admin-syndication-partner/sorry.png)

Чтобы включить специализированные подписки, свяжитесь со своим партнером и попросите его включить эту возможность. Если вы являетесь администратором клиента и знаете, как использовать команды PowerShell Azure Active Directory, вы можете включить специализированные подписки самостоятельно. [Дополнительные сведения](https://technet.microsoft.com/library/jj151815.aspx)

1. Сначала необходимо войти в Azure Active Directory с использованием учетных данных Office 365. В первой строке потребуется ввести учетные данные. Вторая строка используется для подключения к Azure Active Directory.
   
        $msolcred = get-credential
        connect-msolservice -credential $msolcred
   
    ![](media/service-admin-syndication-partner/aad-signin.png)
2. После входа выполните следующую команду, чтобы активировать бесплатные регистрации.
   
        Set-MsolCompanySettings -AllowAdHocSubscriptions $true

## <a name="power-bi-pro-and-premium"></a>Power BI Pro и Premium
Чтобы приобрести подписку на Power BI Pro и Power BI Premium, вам потребуется обратиться к партнеру для выяснения доступных вам вариантов.

* Ваш партнер соглашается добавить Power BI в свой портфель, после чего вы сможете купить подписку у него.
* Ваш партнер может перевести вас на использование модели, в соответствии с которой вы можете приобрести Power BI непосредственно в корпорации Майкрософт или у другого партнера, предлагающего Power BI.

В этом видео рассматривается распространение подписок на Office 365 и покупка Power BI:

<iframe width="560" height="315" src="https://www.youtube.com/embed/C357phT94A8" frameborder="0" allowfullscreen></iframe>

## <a name="next-steps"></a>Дальнейшие действия
[Управление Azure AD с помощью Windows PowerShell](https://technet.microsoft.com/library/jj151815.aspx)  
[Что такое Power BI Premium?](service-premium.md)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

