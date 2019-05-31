---
ms.openlocfilehash: eb7cba03daee47f6772fc46be50419731b41765e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "61194136"
---
## <a name="validate-the-roles-within-power-bi-desktop"></a>Проверка ролей в Power BI Desktop
Создав роли, вы можете проверить их действие в приложении Power BI Desktop.

1. Выберите **Просмотреть как роли**. 

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

    В разделе **Просмотреть как роли** показаны роли, которые вы создали.

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

3. Выберите созданную роль и нажмите кнопку **ОК**, чтобы применить ее. В отчет будут включены данные, которые относятся к этой роли. 

4. Кроме того, можно выбрать **Другой пользователь** и указать определенного пользователя. Рекомендуется указывать имя участника-пользователя, так как именно с ним работает служба Power BI и сервер отчетов Power BI.

    ![](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

1. Нажмите кнопку **ОК**, и в отчет будет включена информация, которая доступна данному пользователю. 

В Power BI Desktop результаты при выборе варианта **Другой пользователь** меняются только при использовании динамической системы безопасности на базе выражений DAX. 

