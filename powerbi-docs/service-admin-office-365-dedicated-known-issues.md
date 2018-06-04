---
title: Выделенные пользователи Office 365. Известные проблемы
description: Поддержка выделенных пользователей Office 365 — известные проблемы. В этом разделе описаны вопросы, связанные с выделенными пользователями Office 365, включая ограничения для функции работы с группами, а также приложение для iPhone с именными доменами.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: cedb3e1572fbf20a32abe4f28b38030539502124
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34238152"
---
# <a name="office-365-dedicated-customers---known-issues"></a>Выделенные пользователи Office 365. Известные проблемы
Power BI теперь поддерживается для выделенных пользователей Office 365.  Если вы являетесь выделенным пользователем Office 365, то можете выполнить вход с учетной записью из данного клиента и использовать Power BI. В настоящее время известны две проблемы.

## <a name="groups"></a>Группы
При выборе пункта **Члены** или **Календарь** в контекстном меню группы пользователь будет перенаправлен на приложение работы с электронной почтой.  Пункты **Файлы** и **Беседы** работают должным образом.

![](media/service-admin-office-365-dedicated-known-issues/group-menu.png)

## <a name="iphone-app---sign-in-with-vanity-domain-leads-to-error"></a>Приложение для iPhone — вход с использованием именного домена приводит к ошибке
При выполнении входа в приложение для iPhone использование учетных данных с именным доменом может привести к ошибке.

*Ошибка входа*  
*Произошла непредвиденная внутренняя ошибка. Повторите попытку.*

Чтобы обойти эту проблему, при входе вместо именного домена используйте адрес электронной почты, который отображается при щелчке значка пользователя в службе Power BI.

![](media/service-admin-office-365-dedicated-known-issues/sign-in-address.png)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

