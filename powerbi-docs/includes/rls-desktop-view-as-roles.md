---
ms.openlocfilehash: 8dc488a47ac2b5b4e7980b7404b2722b1120b6ab
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "77464413"
---
## <a name="validate-the-roles-within-power-bi-desktop"></a>Проверка ролей в Power BI Desktop
Создав роли, вы можете проверить их действие в приложении Power BI Desktop.

1. На вкладке **Моделирование** выберите **Просмотреть как роли**. 

    ![Выберите "Просмотреть как роли"](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

    В появившемся окне **Просмотреть как роли** показаны роли, которые вы создали.

    ![Окно "Просмотреть как роли"](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

3. Выберите созданную роль и нажмите кнопку **ОК**, чтобы применить ее. 

   В отчет будут включены данные, которые относятся к этой роли.

4. Кроме того, можно выбрать **Другой пользователь** и указать определенного пользователя. 

    ![Выберите "Другой пользователь"](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

   Рекомендуется указывать имя участника-пользователя, так как именно с ним работает служба Power BI и сервер отчетов Power BI.

   В Power BI Desktop результаты при выборе варианта **Другой пользователь** меняются только при использовании динамической системы безопасности на основе выражений DAX. 

5. Выберите **ОК**. 

   В отчет будет включена информация, которая доступна данному пользователю.



