---
title: включить файл
description: включить файл
services: powerbi
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 04/28/2020
ms.author: davidi
ms.openlocfilehash: d56988986cfd994bb21c9bc25d024903719472cf
ms.sourcegitcommit: c772c544ce2e1e2a147b9b62e5579ac3cb59d54c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2020
ms.locfileid: "82255846"
---
## <a name="single-sign-on"></a>Единый вход

Когда вы опубликуете набор данных Azure SQL DirectQuery в службе, вы сможете включить для пользователей единый вход с использованием OAuth2 Azure Active Directory (Azure AD).

Чтобы включить единый вход, перейдите к параметрам набора данных, откройте вкладку **Источники данных** и установите флажок единого входа.

![Настройка диалогового окна DQ для Azure SQL](media/direct-query-sso/sso-dialog.png)

Если включен параметр единого входа и пользователям предоставлен доступ к отчетам на основе источника данных, Power BI отправляет их учетные данные для проверки подлинности Azure AD в запросах к хранилищу данных или базе данных SQL Azure. Так Power BI может использовать параметры безопасности, настроенные на уровне источника данных.

Параметр единого входа применяется ко всем наборам данных, в которых используется этот источник. Это не влияет на метод аутентификации, который применяется для сценариев импорта.

