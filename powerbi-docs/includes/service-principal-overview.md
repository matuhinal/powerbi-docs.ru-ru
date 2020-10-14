---
title: Обзор субъект-службы
description: Обзор субъект-службы
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 04/05/2020
ms.custom: include file
ms.openlocfilehash: 6086185fb671b9f418ef2ec070b762020fbe8f75
ms.sourcegitcommit: 02484b2d7a352e96213353702d60c21e8c07c6c0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "91989696"
---
Субъект-служба — это метод проверки подлинности, который можно использовать, чтобы предоставить приложению Azure AD доступ к содержимому службы и API-интерфейсам Power BI.

При создании приложения Azure Active Directory (Azure AD) создается [объект субъекта-службы](/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object). Объект субъекта-службы, также известный как *субъект-служба*, позволяет Azure AD проверить подлинность приложения. После проверки подлинности приложение может получить доступ к ресурсам клиента Azure AD.

Для проверки подлинности субъект-служба использует *идентификатор приложения* приложения Azure AD и один из этих идентификаторов:

* Секрет приложения
* Сертификат