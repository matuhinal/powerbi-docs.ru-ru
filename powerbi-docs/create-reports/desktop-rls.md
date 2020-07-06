---
title: Ограничение доступа к данным с помощью безопасности на уровне строк (RLS) для Power BI Desktop
description: Сведения о настройке безопасности на уровне строк для импортированных наборов данных и DirectQuery в приложении Power BI Desktop.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.custom: ''
ms.date: 01/31/2020
LocalizationGroup: Create reports
ms.openlocfilehash: 9036967c826dee83847c3bc3d4a903bbe749b2ce
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85238646"
---
# <a name="restrict-data-access-with-row-level-security-rls-for-power-bi-desktop"></a>Ограничение доступа к данным с помощью безопасности на уровне строк (RLS) для Power BI Desktop

Вы можете использовать функции безопасности на уровне строк (RLS) в Power BI Desktop, чтобы ограничить доступ к данным для определенных пользователей. Фильтры ограничивают доступ к данным на уровне строк. Задавать фильтры можно с помощью ролей.

Теперь можно настроить RLS для моделей данных, импортированных в Power BI с помощью Power BI Desktop. Вы также можете настроить RLS для наборов данных, которые используют [DirectQuery](../connect-data/desktop-use-directquery.md), таких как SQL Server. Раньше реализовывать RLS можно было только в локальных моделях служб Analysis Services за пределами Power BI. Для динамических подключений к службам Analysis Services безопасность на уровне строк настраивается в локальной модели. Параметр безопасности не отображается для наборов данных динамического подключения.

> [!IMPORTANT]
> Если у вас уже были заданы роли и правила в службе Power BI, вам нужно повторно создать их в Power BI Desktop и опубликовать отчет в службе. Узнайте больше о параметрах [RLS в службе Power BI](../admin/service-admin-rls.md).

[!INCLUDE [include-short-name](../includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](../includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](../includes/rls-limitations.md)]

[!INCLUDE [include-short-name](../includes/rls-faq.md)]

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения, связанные с темой этой статьи, см. в следующих ресурсах.

- [Row-level security (RLS) with Power BI](../admin/service-admin-rls.md) (Безопасность на уровне строк (RLS) в Power BI)
- [Руководство по обеспечению безопасности на уровне строк (RLS) в Power BI Desktop](../guidance/rls-guidance.md)
- Вопросы? [Задайте их в сообществе Power BI](https://community.powerbi.com/).
- У вас есть предложения? [Идеи по улучшению Power BI](https://ideas.powerbi.com/)
