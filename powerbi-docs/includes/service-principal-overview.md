---
title: Обзор субъект-службы
description: Обзор субъект-службы
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 04/05/2020
ms.custom: include file
ms.openlocfilehash: 8482278d9054228dedafb6bd1b37368f5a4b5dce
ms.sourcegitcommit: cd64ddd3a6888253dca3b2e3fe24ed8bb9b66bc6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84315831"
---
Субъект-служба — это метод проверки подлинности, который можно использовать, чтобы предоставить приложению Azure AD доступ к содержимому службы и API-интерфейсам Power BI.

При создании приложения Azure Active Directory (Azure AD) создается [объект субъекта-службы](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object). Объект субъекта-службы, также известный как *субъект-служба*, позволяет Azure AD проверить подлинность приложения. После проверки подлинности приложение может получить доступ к ресурсам клиента Azure AD.

Для проверки подлинности субъект-служба использует *идентификатор приложения* приложения Azure AD и один из этих идентификаторов:

* Секрет приложения
* Сертификат