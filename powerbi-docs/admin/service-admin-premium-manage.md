---
title: Настройка и администрирование емкостей Power BI Premium
description: Узнайте, как управлять Power BI Premium и разрешить доступ к содержимому для всей организации.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 05/11/2020
LocalizationGroup: Premium
ms.openlocfilehash: f4bf863d7d87bd908165976940b868be55e367f9
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83138431"
---
# <a name="configure-and-manage-capacities-in-power-bi-premium"></a>Настройка и администрирование емкостей Power BI Premium

Управление Power BI Premium включает в себя создание и мониторинг емкостей Premium, а также управление ими. В этой статье приводятся пошаговые инструкции. Общие сведения о емкостях см. в статье [Управление емкостями Premium](service-premium-capacity-manage.md).

Узнайте, как управлять емкостью Power BI Premium и Power BI Embedded, которая предоставляет выделенные ресурсы для вашего содержимого.

![Экран параметров емкости Power BI](media/service-admin-premium-manage/premium-capacity-management.png)

*Емкость* — это ключевая характеристика предложений Power BI Premium и Power BI Embedded. Это набор ресурсов, зарезервированных для монопольного использования вашей организацией. Наличие выделенной емкости позволяет публиковать панели мониторинга, отчеты и наборы данных для пользователей в организации без необходимости приобретать лицензии для них. Она также обеспечивает предсказуемую и согласованную производительность содержимого, размещенного в емкости. Дополнительные сведения см. в статье [Что такое Power BI Premium?](../service-premium.md)

## <a name="manage-capacity"></a>Управление емкостью

После приобретения узлов емкости в Office 365 можно задать емкость на портале администрирования Power BI. Управление емкостями Power BI Premium ведется в разделе **Параметры емкости** на портале.

![Параметры емкости на портале администрирования](media/service-admin-premium-manage/admin-portal-premium.png)

Чтобы управлять емкостью, выберите ее имя. После этого вы перейдете на экран управления емкостью.

![Выберите имя емкости, чтобы перейти на экран назначения емкости](media/service-admin-premium-manage/capacity-assignment.png)

Если емкости не назначена ни одна рабочая область, вы увидите сообщение, позволяющее [назначить рабочую область в емкость](#assign-a-workspace-to-a-capacity).

### <a name="setting-up-a-new-capacity-power-bi-premium"></a>Настройка новой емкости (Power BI Premium)

На портале администрирования показано количество использованных и оставшихся *виртуальных ядер*. Общее количество виртуальных ядер зависит от номера SKU Premium, который вы приобрели. Например, купив P3 и P2, вы получите 48 доступных ядер — 32 для P3 и 16 для P2.

![Используемые и доступные виртуальные ядра в Power BI Premium](media/service-admin-premium-manage/admin-portal-v-cores.png)

При наличии доступных виртуальных ядер настройка новой емкости осуществляется так:

1. Выберите **Задать новую емкость**.

1. Дайте имя своей емкости.

1. Определите администратора для этой емкости.

1. Выберите размер емкости. Предлагаемые варианты зависят от количества доступных виртуальных ядер. Нельзя выбрать вариант, количество виртуальных ядер в котором превышает доступное вам количество.

    ![Доступные размеры емкости Premium](media/service-admin-premium-manage/premium-capacity-size.png)

1. Выберите **Настроить**.

    ![Настройка новой емкости](media/service-admin-premium-manage/set-up-capacity.png)

Администраторы емкости, а также администраторы Power BI и глобальные администраторы Office 365 увидят емкость в списке на портале администрирования.

### <a name="capacity-settings"></a>Параметры емкости

1. На экране управления емкостью Premium в разделе **Действия** щелкните **значок шестеренки**, чтобы проверить и изменить параметры. 

    ![Действия с емкостью в области управления емкостью](media/service-admin-premium-manage/capacity-actions.png)

1. В параметрах показаны администраторы службы, SKU и размер емкости и регион, в котором она расположена.

    ![Параметры емкости](media/service-admin-premium-manage/capacity-settings.png)

1. Можно также переименовать или удалить емкость.

    ![Кнопки удаления и применения параметров емкости в Power BI Premium](media/service-admin-premium-manage/capacity-settings-delete.png)

> [!NOTE]
> Управление параметрами емкости Power BI Embedded осуществляется на портале Microsoft Azure.

### <a name="change-capacity-size"></a>Изменить размер емкости

Администраторы Power BI и глобальные администраторы Office 365 могут изменить емкость Power BI Premium. Администраторам емкости, которые не являются администраторами Power BI или глобальными администраторами Office 365, этот параметр недоступен.

1. Выберите пункт **Изменить размер емкости**.

    ![Изменение размера емкости Power BI Premium](media/service-admin-premium-manage/change-capacity-size.png)

1. На экране **Изменение размера емкости** можно повысить или понизить уровень емкости нужным образом.

    ![Раскрывающееся меню изменения размера емкости Power BI Premium](media/service-admin-premium-manage/change-capacity-size2.png)

    Администраторы могут создавать и удалять узлы, а также изменять их размер при условии, что в них есть необходимое число виртуальных ядер.

    SKU уровня P невозможно понизить до SKU уровня EM. Если навести указатель мыши на отключенные параметры, появится объяснение.



> [!IMPORTANT]
> Если емкость Power BI Premium подвергается большой нагрузке, из-за которой могут возникать проблемы с производительностью или надежностью, вы можете получать по электронной почте уведомления, чтобы устранять эти проблемы. Дополнительные сведения см. в статье [Уведомления о емкости и надежности](service-interruption-notifications.md#capacity-and-reliability-notifications).


### <a name="manage-user-permissions"></a>Проверка разрешений пользователя

Вы можете назначить дополнительных администраторов емкости, а также пользователей, которые будут иметь разрешения на *назначение емкости*. Пользователь, имеющий разрешения на назначение, может назначить рабочую область в емкость, если он является администратором этой рабочей области. Он также может назначить емкости свою *личную рабочую область*. У пользователей с разрешениями на назначение не будет доступа к порталу администрирования.

> [!NOTE]
> Администраторы емкости Power BI Embedded указываются на портале Microsoft Azure.

В разделе **Разрешения пользователя** разверните узел **Пользователи с разрешениями на назначение**, а затем добавьте пользователей или группы в зависимости от ситуации.

![Разрешения пользователя для емкости](media/service-admin-premium-manage/capacity-user-permissions2.png)

## <a name="assign-a-workspace-to-a-capacity"></a>Назначение рабочей области для емкости

Есть два способа назначить рабочую область в емкость: на портале администрирования и из рабочей области.

### <a name="assign-from-the-admin-portal"></a>Назначение на портале администрирования

Администраторы емкости вместе с администраторами Power BI и глобальными администраторами Office 365 могут выполнять массовое назначение рабочих областей в разделе управления емкостью Premium на портале администрирования. При управлении емкостью вы увидите раздел **Рабочие области**, который позволяет вам назначать рабочие области.

![Область назначения рабочей области в разделе управления емкостью](media/service-admin-premium-manage/capacity-manage-workspaces.png)

1. Выберите **Назначить рабочие области**. Этот параметр доступен в нескольких местах.

1. Сделайте выбор в разделе **Применяются к**.

    ![Назначить рабочие области](media/service-admin-premium-manage/assign-workspaces.png)

   | Выбор | Описание |
   | --- | --- |
   | **Рабочие области по пользователям** | При назначении рабочих областей пользователя или группы емкости Premium назначаются все рабочие области, принадлежащие этим пользователям, включая личные рабочие области. Эти пользователи автоматически получат разрешения на назначения рабочих областей.<br>Сюда входят рабочие области, уже назначенные другой емкости. |
   | **Определенные рабочие области** | Введите имя определенной рабочей области, чтобы назначить ее выбранной емкости. |
   | **The entire organization's workspaces** (Рабочие области всей организации) | Этот параметр назначит все рабочие области и личные рабочие области в вашей организации для емкости Premium. Кроме того, все текущие и будущие пользователи смогут переназначать отдельные рабочие области для этой емкости. |
   | | |

1. Нажмите кнопку **Применить**.

### <a name="assign-from-workspace-settings"></a>Назначение из рабочей области

Вы также можете назначить емкости Premium рабочую область из параметров этой области. Чтобы переместить рабочую область в емкость, необходимо иметь разрешения администратора этой рабочей области, а также разрешения на назначение для этой емкости. Обратите внимание, что администраторы рабочей области всегда могут удалить рабочую область из емкости Premium.

1. Чтобы изменить рабочую область, щелкните многоточие **(...)** и выберите команду **Изменить рабочую область**.

    ![Изменение рабочей области в контекстном меню (многоточие)](media/service-admin-premium-manage/edit-app-workspace.png)

1. В окне **Изменение рабочей области** разверните раздел **Дополнительно**.

1. Выберите емкость, куда вы хотите назначить эту рабочую область.

    ![Раскрывающийся список выбора емкости](media/service-admin-premium-manage/app-workspace-advanced.png)

1. Нажмите кнопку **Сохранить**.

После сохранения рабочая область вместе со всем содержимым будет перенесена в емкость Premium без нарушения работы пользователей.

## <a name="power-bi-report-server-product-key"></a>Ключ продукта сервера отчетов Power BI

На портале администрирования Power BI на вкладке **Параметры емкости** будет отображаться ключ продукта для сервера отчетов Power BI. Он будет доступен только глобальным администраторам или пользователям, которым назначена роль администратора службы Power BI, и только в том случае, если вы приобрели SKU определенного уровня Power BI Premium.

![Ключ Сервера отчетов Power BI в области параметров емкости](media/service-admin-premium-manage/pbirs-product-key.png)

Щелкните **Ключ сервера отчетов Power BI**, чтобы появилось диалоговое окно с ключом вашего продукта. Вы можете скопировать его и использовать при установке.

![Ключ продукта сервера отчетов Power BI](media/service-admin-premium-manage/pbirs-product-key-dialog.png)

Дополнительные сведения см. в статье [Установка сервера отчетов Power BI](../report-server/install-report-server.md).

## <a name="next-steps"></a>Дальнейшие действия

[Управление емкостями Premium](service-premium-capacity-manage.md)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)