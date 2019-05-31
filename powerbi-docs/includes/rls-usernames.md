---
ms.openlocfilehash: 3e89344ef1298864b485f465b28c56397a7e1511
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "61194088"
---
## <a name="using-the-username-or-userprincipalname-dax-function"></a>Использование функции DAX username() или userprincipalname()
Функции DAX *username()* и *userprincipalname()* в наборе данных обеспечивают определенные преимущества. Их можно использовать в выражениях в Power BI Desktop. При публикации модели она будет использоваться в службе Power BI.

В Power BI Desktop функция *username()* возвращает имя пользователя в формате *ДОМЕН\пользователь*, а функция *userprincipalname()* возвращает имя пользователя в формате <em>user@contoso.com</em>.

В службе Power BI *username()* и *userprincipalname()* возвращают имя участника-пользователя. Оно выглядит как адрес электронной почты.

