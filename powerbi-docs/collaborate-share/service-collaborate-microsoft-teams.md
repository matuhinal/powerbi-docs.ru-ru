---
title: Совместная работа в Microsoft Teams с использованием Power BI
description: Вы можете с легкостью предоставлять общий доступ к интерактивному содержимому Power BI и совместно работать с ним посредством каналов и обсуждений Microsoft Teams.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 07/31/2020
ms.openlocfilehash: 01e5b470e0beb189d64da18785a17e771bcaf59b
ms.sourcegitcommit: d9d67ee47954379c2df8db8d0dc8302de4c9f1e5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2020
ms.locfileid: "87478045"
---
# <a name="collaborate-in-microsoft-teams-with-power-bi"></a>Совместная работа в Microsoft Teams с использованием Power BI

По мере того как распределенная и удаленная работа становится нормой, все больше организаций используют Microsoft Teams для синхронизации усилий сотрудников. Power BI предлагает несколько вариантов предоставления общего доступа к интерактивному содержимому Power BI и совместной работы с ним посредством каналов и чатов Microsoft Teams. 

- С помощью вкладки **Power BI** для Microsoft Teams можно [внедрять интерактивные отчеты в каналы и чаты Microsoft Teams](service-embed-report-microsoft-teams.md). На вкладке **Power BI** ваши коллеги могут найти данные вашей команды и обсуждать данные в каналах команд. 
- Создайте [предварительный просмотр ссылок](service-teams-link-preview.md) при вставке ссылок на отчеты, панели мониторинга и приложения в поле сообщения Microsoft Teams, в которых отображаются сведения о ссылке. 
- Используйте кнопку [Поделиться в Teams](service-share-report-teams.md), чтобы быстро начать беседу при просмотре отчетов и панелей мониторинга в Power BI.
 
:::image type="content" source="media/service-collaborate-microsoft-teams/power-bi-embed-teams-report.png" alt-text="Снимок экрана: отчет Power BI, внедренный в канал Microsoft Teams.":::

## <a name="requirements"></a>Требования

Как правило, для работы Power BI с Microsoft Teams необходимо обеспечить следующее:

- У пользователей должна быть лицензия Power BI Pro, либо отчет должен находиться в [емкости Power BI Premium (номер SKU EM или P)](../admin/service-premium-what-is.md) с лицензией Power BI.
- Пользователи выполнили вход в службу Power BI и активировали свою лицензию Power BI.
- Пользователи должны соответствовать требованиям для использования вкладки **Power BI** в Microsoft Teams.

## <a name="grant-access-to-reports"></a>Предоставление доступа к отчетам

При внедрении отчета в Microsoft Teams или отправке ссылки на элемент разрешение на просмотр отчета не предоставляется пользователям автоматически. Вам нужно [разрешить пользователям просматривать отчет в Power BI](service-share-dashboards.md). Чтобы упростить эту задачу, можно воспользоваться группой Microsoft 365.

> [!IMPORTANT]
> Обязательно проверьте, кто может просматривать отчет в службе Power BI, и предоставьте доступ пользователям, которых нет в списке.

Один из способов обеспечить доступ всех членов команды к отчетам — поместить эти отчеты в одну рабочую область и предоставить доступ к ней группе Microsoft 365 вашей команды.

## <a name="known-issues-and-limitations"></a>Известные проблемы и ограничения

- Power BI не поддерживает те же языки с локализацией, что и Microsoft Teams. В результате внедренный отчет может быть не локализован должным образом.
- Панели мониторинга Power BI невозможно внедрить на вкладку **Power BI** для Microsoft Teams.
- Пользователи, у которых нет лицензии Power BI или разрешения на доступ к отчету, видят сообщение "Содержимое недоступно".
- При использовании Internet Explorer 10 могут возникнуть проблемы. <!--You can look at the [browsers support for Power BI](../consumer/end-user-browsers.md) and for [Microsoft 365](https://products.office.com/office-system-requirements#Browsers-section). -->
- [Фильтры URL-адресов](service-url-filters.md) не поддерживаются на вкладке **Power BI** для Microsoft Teams.
- В национальных облаках новая вкладка **Power BI** недоступна. Может быть доступна прежняя версия, которая не поддерживает новые возможности рабочих областей и отчеты в приложениях Power BI.
- После сохранения вкладки ее имя невозможно изменить в параметрах вкладки. Чтобы изменить его, используйте команду **Переименовать**.
- Единый вход не поддерживается для службы предварительного просмотра ссылок.
- Предварительный просмотр ссылок не работает в чате собрания и в частных каналах.

## <a name="next-steps"></a>Дальнейшие действия

- [Внедрение содержимого Power BI в Microsoft Teams](service-embed-report-microsoft-teams.md)
- [Получение предварительного просмотра ссылок Power BI в Microsoft Teams](service-teams-link-preview.md)
- [Предоставление общего доступа непосредственно в Teams из службы Power BI](service-share-report-teams.md)

Остались вопросы? [Попробуйте задать вопрос в Сообществе Power BI](https://community.powerbi.com/).
