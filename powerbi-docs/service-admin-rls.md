---
title: "Безопасность на уровне строк (RLS) в Power BI"
description: "Сведения о настройке безопасности на уровне строк для импортированных наборов данных и DirectQuery в службе Power BI."
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
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 08/11/2017
ms.author: asaxton
ms.openlocfilehash: ea51308d533dc97af9d06855d004b5bacc376247
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="row-level-security-rls-with-power-bi"></a>Безопасность на уровне строк (RLS) в Power BI
<iframe width="560" height="315" src="https://www.youtube.com/embed/67fK0GoVQ80?showinfo=0" frameborder="0" allowfullscreen></iframe>

Функции безопасности на уровне строк (RLS) в Power BI позволяют ограничивать доступ к данным для определенных пользователей. Фильтры ограничивают доступ к данным на уровне строк. Задавать фильтры можно с помощью ролей.

Вы можете настроить RLS для моделей данных, импортированных в Power BI с помощью Power BI Desktop. Вы также можете настроить RLS для наборов данных, которые используют DirectQuery, таких как SQL Server. Раньше реализовывать RLS можно было только в локальных моделях служб Analysis Services за пределами Power BI. Для динамических подключений к службам Analysis Services безопасность на уровне строк настраивается в локальной модели. Параметр безопасности не будет отображаться для наборов данных динамического подключения.

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

## <a name="manage-security-on-your-model"></a>Управление безопасностью в модели
Для управления безопасностью в модели данных можно выполнить следующие действия.

1. Нажмите значок **многоточие (...)** для определенного набора данных.
2. Выберите **Безопасность**.
   
   ![](media/service-admin-rls/rls-security.png)

В результате откроется страница RLS, где можно добавить участников к роли, созданной в Power BI Desktop. Параметр "Безопасность" отображается только владельцам набора данных. Если набор данных передается в составе группы, этот параметр будет доступен только администраторам. 

Создавать и изменять роли можно только в приложении Power BI Desktop.

## <a name="working-with-members"></a>Работа с участниками
### <a name="add-members"></a>Добавление участников
Можно добавить участника в роль, указав адрес электронной почты или имя добавляемого пользователя, группы безопасности или списка рассылки. Этот участник должен быть в пределах вашей организации. Невозможно добавить группы, созданные в Power BI.

![](media/service-admin-rls/rls-add-member.png)

Также по числу в скобках рядом с именем роли или рядом с участниками можно определить, сколько участников входит в данную роль.

![](media/service-admin-rls/rls-member-count.png)

### <a name="remove-members"></a>Удаление участников
Участников можно удалять, нажимая "X" рядом с их именем. 

![](media/service-admin-rls/rls-remove-member.png)

## <a name="validating-the-role-within-the-power-bi-service"></a>Проверка роли в службе Power BI
Чтобы убедиться в работоспособности роли, которую вы определили, выполните проверку роли. 

1. Щелкните **многоточие (…)** рядом с ролью.
2. Выберите пункт **Проверить данные в качестве роли**.

![](media/service-admin-rls/rls-test-role.png)

На экран будут выведены отчеты, доступные для этой роли. В этом представлении панели мониторинга не представлены. На синей панели выше вы увидите применяемые элементы.

![](media/service-admin-rls/rls-test-role2.png)

Другие роли или комбинации ролей можно проверить, выбрав **Теперь показать как**.

![](media/service-admin-rls/rls-test-role3.png)

Можно просмотреть данные для определенного пользователя или выбрать комбинацию из доступных ролей, чтобы проверить их работоспособность. 

Чтобы вернуться в обычный режим просмотра, выберите **Вернуться к безопасности на уровне строк**.

[!INCLUDE [include-short-name](./includes/rls-usernames.md)]

## <a name="using-rls-with-app-workspaces-in-power-bi"></a>Использование RLS с рабочими областями приложений в Power BI
При публикации отчета Power BI Desktop в рабочей области приложения в службе Power BI роли применяются к участникам с правами только для чтения. Вам потребуется указать, что участники могут только просматривать содержимое Power BI, в параметрах рабочей области приложения.

> [!WARNING]
> Если вы настроили рабочую область приложения таким образом, что ее участники обладают разрешениями на изменение, то роли RLS не будут применяться к этим участникам. Пользователи будут видеть все данные.
> 
> 

![](media/service-admin-rls/rls-group-settings.png)

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Дальнейшие действия
[Безопасность на уровне строк (RLS) в Power BI Desktop](desktop-rls.md)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

