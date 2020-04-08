---
ms.openlocfilehash: 26f4b82301915524b65d9d2d6b39d61b54ed0321
ms.sourcegitcommit: 8eeb784fd46321680367ac913ef976aeedaa7766
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "80621570"
---
Субъект-служба — это метод проверки подлинности, который можно использовать, чтобы предоставить приложению Azure AD доступ к содержимому службы и API-интерфейсам Power BI.

При создании приложения Azure Active Directory (Azure AD) создается [объект субъекта-службы](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object). Объект субъекта-службы, также известный как *субъект-служба*, позволяет Azure AD проверить подлинность приложения. После проверки подлинности приложение может получить доступ к ресурсам клиента Azure AD.

Для проверки подлинности субъект-служба использует *идентификатор приложения* приложения Azure AD и один из этих идентификаторов:
* Секрет приложения
* Сертификат