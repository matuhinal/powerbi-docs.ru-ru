---
title: Сравнение решения "Сервер отчетов Power BI" и службы Power BI
description: В этой статье сравниваются возможности решения "Сервер отчетов Power BI" и службы Power BI.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.custom: mvc
ms.date: 03/04/2020
ms.openlocfilehash: 4c48b9c2695c7feab5897527c9ff2fbf2a2d0455
ms.sourcegitcommit: ced8c9d6c365cab6f63fbe8367fb33e6d827cb97
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2020
ms.locfileid: "78920941"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>Сравнение решения "Сервер отчетов Power BI" и службы Power BI

Сервер отчетов Power BI и служба Power BI имеют много общего, но и ряд важных различий. В следующей таблице перечислены и те, и другие.

## <a name="features-of-power-bi-report-server-and-the-power-bi-service"></a>Функции Сервера отчетов Power BI и службы Power BI

| Функции | Cервере отчетов Power BI | Служба Power BI | Примечания |
|---------|---------|---------|---------|
| Развертывание | Локально или в размещенном облаке | Облако | Решение "Сервер отчетов Power BI" можно развернуть на виртуальных машинах Azure (размещенное облако), если используется лицензия Power BI Premium или SQL Server Enterprise с Software Assurance.|
| Исходные данные | Облачные и (или) локальные | Облачные и (или) локальные |  |
| Лицензия | Power BI Premium или SQL Server ЕЕ с правами системного администратора | Power BI Pro и (или) Power BI Premium | |  
| Жизненный цикл | Современная политика жизненного цикла | Полностью управляемая служба |  |
| Цикл выпуска | Три раза в год (январь, май, сентябрь) | Один раз в месяц | Новейшие функции и исправления сначала появляются в службе Power BI. Сводные обновления функций из выпусков Power BI Desktop для службы попадают в каждый новый выпуск решения "Сервер отчетов Power BI". Большинство других функций предназначены только для службы Power BI. |
| Создание отчетов Power BI в Power BI Desktop | Да | Да |  |
| Создание отчетов Power BI в браузере | Нет | Да |  |
| Размещение общих наборов данных Power BI и подключение к ним | Нет | Да | [Общие сведения об использовании наборов данных в рабочих областях](../service-datasets-across-workspaces.md) |
| Требуется шлюз | Нет | Да для локальных источников данных |  |
| Потоковая передача в реальном времени | Нет | Да | [Потоковая передача в реальном времени в Power BI](../service-real-time-streaming.md) |
| Панели мониторинга | Нет | Да | [Панели мониторинга в службе Power BI](../consumer/end-user-dashboards.md) |
| Распределение групп отчетов с помощью приложений | Нет | Да | [Создание и публикация приложений с панелями мониторинга и отчетами](../service-create-distribute-apps.md) |
| Пакеты содержимого | Нет | Да | [Знакомство с пакетами содержимого организации в Power BI](../service-organizational-content-pack-introduction.md) |
| Подключение к службам, таким как Salesforce | Да | Да | [Подключение к используемым службам](../service-connect-to-services.md) с помощью пакетов содержимого в службе Power BI. Используйте для этого сертифицированные соединители на Сервере отчетов Power BI. Дополнительные сведения: [Источники данных отчетов Power BI в решении "Сервер отчетов Power BI"](data-sources.md). |
| Вопросы и ответы | Нет | Да | ["Вопросы и ответы" в службе Power BI и Power BI Desktop](../power-bi-tutorial-q-and-a.md) 
| Краткая аналитика | Нет | Да | [Автоматическое создание аналитических сведений с помощью Power BI](../consumer/end-user-insights.md) |
| Анализ в Excel | Нет | Да | [Анализ в Excel](../service-analyze-in-excel.md) 
| Отчеты с разбивкой на страницы | Да | Да | [Отчеты с разбивкой на страницы доступны в службе Power BI](../paginated-reports/paginated-reports-report-builder-power-bi.md) в предварительной версии для емкости Premium. |
| Мобильные приложения Power BI | Да | Да | [Обзор мобильных приложений Power BI](../consumer/mobile/mobile-apps-for-mobile-devices.md) |
| Карты ArcGIS | Нет | Да | [Карты ArcGIS от ESRI в службе Power BI и Power BI Desktop](../visuals/power-bi-visualization-arcgis.md) |
| Подписки по электронной почте на отчеты Power BI | Нет | Да | [Создание подписки](../service-report-subscribe.md) на отчеты и панели мониторинга в службе Power BI для себя или других пользователей |
| Подписки по электронной почте на отчеты с разбивкой на страницы | Да | Да | [Создание подписки на отчет с разбивкой на страницы в службе Power BI для себя и других пользователей](../consumer/paginated-reports-subscriptions.md)<br><br>[Доставка электронной почты в Reporting Services](https://docs.microsoft.com/sql/reporting-services/working-with-subscriptions-web-portal)  |
| Оповещения о данных | Нет | Да | [Оповещения о данных](../service-set-data-alerts.md) в службе Power BI
| Безопасность на уровне строк (RLS) | Да | Да | Доступно в режимах DirectQuery (источник данных) и импорта <br><br>Безопасность на уровне строк в [службе Power BI](../service-admin-rls.md) <br><br>Безопасность на уровне строк на [Сервере отчетов Power BI](row-level-security-report-server.md) |
| Полноэкранный режим | Нет | Да | [Полноэкранный режим](../consumer/end-user-focus.md) в службе Power BI |
| Расширенные возможности совместной работы Office 365 | Нет | Да | [Совместная работа в рабочей области](../service-collaborate-power-bi-workspace.md) с Office 365 |
| Визуальные элементы R | Нет | Да | [Создание визуальных элементов R](../desktop-r-visuals.md) в Power BI Desktop и публикация их в службе Power BI. Отчеты Power BI с визуальными элементами R не поддерживают сохранение на сервере отчетов Power BI.  |
| Предварительная версия функций | Нет | Да | [Включение предварительных версий функций Power BI](../consumer/end-user-preview-features.md) |
| Настраиваемые визуальные элементы | Да | Да | [Пользовательские визуальные элементы в Power BI](../developer/power-bi-custom-visuals.md) |
| Составные модели | Нет | Да |
| Power BI Desktop | Версия, оптимизированная для сервера отчетов, доступна для скачивания вместе с сервером отчетов | Версия, оптимизированная для службы Power BI, доступна в Windows Store | [Power BI Desktop для сервера отчетов](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI Desktop для службы Power BI](https://aka.ms/pbidesktopstore) |

## <a name="next-steps"></a>Дальнейшие действия

[Установка сервера отчетов Power BI](install-report-server.md)
