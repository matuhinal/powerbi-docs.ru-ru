---
title: Безопасность на уровне строк (RLS) в Power BI
description: Сведения о настройке безопасности на уровне строк для импортированных наборов данных и DirectQuery в службе Power BI.
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
ms.date: 01/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 2e1eb3b366fba3201d54a2b2016542c39f7ee8c4
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2018
---
# <a name="row-level-security-rls-with-power-bi"></a>Безопасность на уровне строк (RLS) в Power BI
<iframe width="560" height="315" src="https://www.youtube.com/embed/67fK0GoVQ80?showinfo=0" frameborder="0" allowfullscreen></iframe>

Функции безопасности на уровне строк (RLS) в Power BI позволяют ограничивать доступ к данным для определенных пользователей. Фильтры ограничивают доступ к данным на уровне строк. Задавать фильтры можно с помощью ролей.

Вы можете настроить RLS для моделей данных, импортированных в Power BI с помощью Power BI Desktop. Вы также можете настроить RLS для наборов данных, которые используют DirectQuery, таких как SQL Server. Раньше реализовывать RLS можно было только в локальных моделях служб Analysis Services за пределами Power BI. Для динамических подключений к службам Analysis Services безопасность на уровне строк настраивается в локальной модели. Параметр безопасности не будет отображаться для наборов данных динамического подключения.

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

По умолчанию при фильтрации с обеспечением безопасности на уровне строк используются однонаправленные фильтры, независимо от установленного типа связи (однонаправленной или двунаправленной). Вы можете вручную включить двунаправленный кросс-фильтр с обеспечением безопасности на уровне строк. Для этого выберите связь и установите флажок **Применить фильтр безопасности в обоих направлениях**. Этот флажок следует установить, если реализуется функция [динамической безопасности на уровне строк](https://docs.microsoft.com/en-us/sql/analysis-services/supplemental-lesson-implement-dynamic-security-by-using-row-filters). При этом безопасность на уровне строк обеспечивается на основе имени пользователя. 

Дополнительные сведения см. в статье [Двунаправленная перекрестная фильтрация при работе с DirectQuery в Power BI Desktop](desktop-bidirectional-filtering.md) и техническом документе по [обеспечению безопасности в табличной семантической модели бизнес-аналитики](http://download.microsoft.com/download/D/2/0/D20E1C5F-72EA-4505-9F26-FEF9550EFD44/Securing the Tabular BI Semantic Model.docx).

![Применение фильтра безопасности](media/service-admin-rls/rls-apply-security-filter.png)


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

