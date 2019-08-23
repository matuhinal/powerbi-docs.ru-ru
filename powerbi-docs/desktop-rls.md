---
title: Общие сведения о безопасности на уровне строк (RLS) в Power BI Desktop
description: Сведения о настройке безопасности на уровне строк для импортированных наборов данных и DirectQuery в приложении Power BI Desktop.
author: davidiseminger
ms.author: davidi
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.custom: ''
ms.date: 08/14/2019
LocalizationGroup: Create reports
ms.openlocfilehash: 91f2da65764480a0cf9cf298a052436b27e18c83
ms.sourcegitcommit: f6ac9e25760561f49d4257a6335ca0f54ad2d22e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2019
ms.locfileid: "69560973"
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Безопасность на уровне строк (RLS) в Power BI Desktop

Вы можете использовать функции безопасности на уровне строк (RLS) в Power BI Desktop, чтобы ограничить доступ к данным для определенных пользователей. Фильтры ограничивают доступ к данным на уровне строк. Задавать фильтры можно с помощью ролей.

Теперь можно настроить RLS для моделей данных, импортированных в Power BI с помощью Power BI Desktop. Вы также можете настроить RLS для наборов данных, которые используют [DirectQuery](desktop-use-directquery.md), таких как SQL Server. Раньше реализовывать RLS можно было только в локальных моделях служб Analysis Services за пределами Power BI. Для динамических подключений к службам Analysis Services безопасность на уровне строк настраивается в локальной модели. Параметр безопасности не отображается для наборов данных динамического подключения.

> [!IMPORTANT]
> Если у вас уже были заданы роли и правила в службе Power BI, вам нужно повторно создать их в Power BI Desktop и опубликовать отчет в службе.

Узнайте больше о параметрах [RLS в службе Power BI](service-admin-rls.md).

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Дальнейшие действия

[Безопасность на уровне строк (RLS) в службе Power BI](service-admin-rls.md)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)