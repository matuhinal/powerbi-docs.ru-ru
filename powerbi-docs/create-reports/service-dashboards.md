---
title: Общие сведения о панелях мониторинга для разработчиков Power BI
description: Панели мониторинга — это главная особенность службы Power BI. Они представляют собой одну страницу, часто называемую полотном, на которой данные отображаются в виде визуализаций.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/19/2019
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: c687486af1293660af5496e27ea707bb1afeec80
ms.sourcegitcommit: a72567f26c1653c25f7730fab6210cd011343707
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564559"
---
# <a name="introduction-to-dashboards-for-power-bi-designers"></a>Общие сведения о панелях мониторинга для разработчиков Power BI

*Панель мониторинга* Power BI — это отдельная страница (часто называется полотном), на которой данные отображаются в виде визуализаций. Будучи ограниченной одной страницей, продуманная панель мониторинга содержит только самые важные элементы. Читатели могут просматривать связанные отчеты, чтобы узнать подробности.

![Панель мониторинга](media/service-dashboards/power-bi-dashboard2.png)

Панели мониторинга — это компонент только службы Power BI. Они недоступны в приложении Power BI Desktop. Тем не менее нельзя создавать панели мониторинга на мобильных устройствах, однако их можно на них [просматривать и предоставлять к ним доступ](../consumer/mobile/mobile-apps-view-dashboard.md).

## <a name="dashboard-basics"></a>Основные сведения о панелях мониторинга 

Визуализации, отображаемые на панели мониторинга, называются *плитками*. Вы *закрепляете* плитки на панели мониторинга из отчетов. Если вы недавно начали использовать службу Power BI, ознакомьтесь со статьей [Основные понятия для разработчиков в службе Power BI](../fundamentals/service-basic-concepts.md).

Визуализации на панели мониторинга поступают из отчетов, а каждый отчет создается на основе набора данных. Панель мониторинга можно рассматривать как средство представления базовых отчетов и наборов данных. Выбирая визуализацию, вы можете перейти к отчету (и набору данных), на котором она основана.

![Схема, показывающая связь между панелями мониторинга, отчетами, наборами данных](media/service-dashboards/power-bi-diagram.png)

## <a name="advantages-of-dashboards"></a>Преимущества панелей мониторинга
Панели мониторинга — прекрасный способ отслеживать положение дел в бизнесе и быстро просматривать наиболее важные метрики. Визуализации на панели мониторинга могут поступать из одного или нескольких базовых наборов данных и из одного или нескольких базовых отчетов. Панель мониторинга объединяет локальные и облачные данные независимо от того, где они расположены.

Панели мониторинга — это не просто симпатичные картинки. Это интерактивное средство, в котором обновление плиток происходит при изменении базовых данных.

## <a name="who-can-create-a-dashboard"></a>Кто может создавать панели мониторинга?
Создавать панель мониторинга может только *автор*, поскольку для этого требуются разрешения на изменение отчета. Такие разрешения доступны авторам отчетов и тем коллегам, которым автор предоставил доступ. Например, если Сергей создает отчет в рабочей области "АБВ" и добавляет вас в нее как участника, то у вас и у Сергея будут разрешения на редактирование. Но если вам предоставили общий доступ к этому отчету напрямую или в рамках [приложения Power BI](../collaborate-share/service-create-distribute-apps.md), вы *используете* отчет. Возможно, вы не сможете закрепить плитки на панели мониторинга. 

> [!IMPORTANT]
> Для создания панелей мониторинга в рабочих областях потребуется лицензия [Power BI Pro](../fundamentals/service-features-license-type.md). Вы можете создавать панели мониторинга в собственной рабочей области без лицензии на Power BI Pro.


## <a name="dashboards-versus-reports"></a>Панели мониторинга и отчеты
[Отчеты](../consumer/end-user-reports.md) и панели мониторинга чем-то похожи, так как являются полотнами, заполненными визуализациями. Тем не менее существуют ключевые отличия, которые описываются в следующей таблице.

| **Возможность** | **Панели мониторинга** | **Отчеты** |
| --- | --- | --- |
| Страницы |Одна страница |Одна или несколько страниц |
| Источники данных |Один или несколько отчетов и один или несколько наборов данных на каждую панель мониторинга |Один набор данных на каждый отчет |
| Доступность в Power BI Desktop |Нет | Да. Можно создавать и просматривать отчеты в Power BI Desktop |
| Подписаться |Да. Можно подписаться на панель мониторинга |Да. Можно подписаться на страницу отчета |
| Фильтрация |Нет. Невозможно выполнить фильтрацию и срез |Да. Множество различных способов для выполнения фильтрации, выделения и среза |
| Подборка |Да. Можно задать одну панель мониторинга в качестве *избранной* |Нет |
| Добавить в избранное | Да. Можно добавить несколько панелей мониторинга в *избранное* | Да. Можно добавить несколько отчетов в *избранное*
| Настройка оповещений |Да. Доступно на плитках панели мониторинга в определенных обстоятельствах |Нет |
| Запросы на естественном языке (Вопросы и ответы) |Да | Да, при условии, что у вас есть разрешения на изменение отчета и базового набора данных |
| Просмотр таблиц и полей базового набора данных |Нет. Можно экспортировать данные, но нельзя просматривать таблицы и поля непосредственно на панели мониторинга |Да |


## <a name="next-steps"></a>Дальнейшие действия
* Ознакомьтесь с обзорными сведениями об использовании на примере одной из наших [панелей мониторинга](sample-tutorial-connect-to-the-samples.md).
* Узнайте о [плитках панелей мониторинга](service-dashboard-tiles.md).
* Хотите отслеживать отдельную плитку панели мониторинга и получать сообщения электронной почты при достижении определенного порога? [Создайте оповещение для плитки](service-set-data-alerts.md).
* Узнайте, как использовать функцию ["Вопросы и ответы" Power BI](power-bi-tutorial-q-and-a.md), задавайте вопросы о своих данных и получайте ответы в виде визуализации.