---
title: Ограничение доступа к данным с помощью безопасности на уровне строк (RLS) для Power BI Desktop
description: Сведения о настройке безопасности на уровне строк для импортированных наборов данных и DirectQuery в приложении Power BI Desktop.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.custom: ''
ms.date: 01/31/2020
LocalizationGroup: Create reports
ms.openlocfilehash: 7a9aa0ca62ae4f1008d4cf47caa909841f9ec495
ms.sourcegitcommit: cde65bb8b1bed1ee8cf512651afeb829ddc155de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77464475"
---
# <a name="restrict-data-access-with-row-level-security-rls-for-power-bi-desktop"></a>Ограничение доступа к данным с помощью безопасности на уровне строк (RLS) для Power BI Desktop

Вы можете использовать функции безопасности на уровне строк (RLS) в Power BI Desktop, чтобы ограничить доступ к данным для определенных пользователей. Фильтры ограничивают доступ к данным на уровне строк. Задавать фильтры можно с помощью ролей.

Теперь можно настроить RLS для моделей данных, импортированных в Power BI с помощью Power BI Desktop. Вы также можете настроить RLS для наборов данных, которые используют [DirectQuery](desktop-use-directquery.md), таких как SQL Server. Раньше реализовывать RLS можно было только в локальных моделях служб Analysis Services за пределами Power BI. Для динамических подключений к службам Analysis Services безопасность на уровне строк настраивается в локальной модели. Параметр безопасности не отображается для наборов данных динамического подключения.

> [!IMPORTANT]
> Если у вас уже были заданы роли и правила в службе Power BI, вам нужно повторно создать их в Power BI Desktop и опубликовать отчет в службе. Узнайте больше о параметрах [RLS в службе Power BI](service-admin-rls.md).

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Дальнейшие действия

[Безопасность на уровне строк (RLS) в службе Power BI](service-admin-rls.md)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в Сообществе Power BI](https://community.powerbi.com/).