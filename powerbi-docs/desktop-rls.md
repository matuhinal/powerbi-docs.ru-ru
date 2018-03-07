---
title: "Общие сведения о безопасности на уровне строк (RLS) в Power BI Desktop"
description: "Сведения о настройке безопасности на уровне строк для импортированных наборов данных и DirectQuery в приложении Power BI Desktop."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 10/12/2017
ms.author: maghan
LocalizationGroup: Create reports
ms.openlocfilehash: febe8cafb7be578be0dcf23a151f28deb544a4c8
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2018
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Безопасность на уровне строк (RLS) в Power BI Desktop
Функции безопасности на уровне строк (RLS) в Power BI Desktop позволяют ограничивать доступ к данным для определенных пользователей. Фильтры ограничивают доступ к данным на уровне строк. Задавать фильтры можно с помощью ролей.

Теперь можно настроить RLS для моделей данных, импортированных в Power BI с помощью Power BI Desktop. Вы также можете настроить RLS для наборов данных, которые используют DirectQuery, таких как SQL Server. Раньше реализовывать RLS можно было только в локальных моделях служб Analysis Services за пределами Power BI. Для динамических подключений к службам Analysis Services безопасность на уровне строк настраивается в локальной модели. Параметр безопасности не будет отображаться для наборов данных динамического подключения.

> [!IMPORTANT]
> Если у вас уже были заданы роли и правила в службе Power BI, вам потребуется повторно создать их в Power BI Desktop и опубликовать отчет в службе.
> 
> 

Узнайте больше о параметрах [RLS в службе Power BI](service-admin-rls.md).

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Дальнейшие действия
[Безопасность на уровне строк (RLS) в службе Power BI](service-admin-rls.md)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

