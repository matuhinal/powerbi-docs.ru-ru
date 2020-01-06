---
title: Что можно сделать с помощью API Power BI
description: Что можно сделать с помощью API Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 03/25/2019
ms.openlocfilehash: bbca4e5bf52ee0d4674cfcdc28edd53e90033a98
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2020
ms.locfileid: "74265228"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>Какие возможности API Power BI предоставляет разработчикам?

Интерфейс REST API для Power BI позволяет создавать приложения, которые интегрируются с отчетами, панелями мониторинга и плитками Power BI.

С помощью REST API для Power BI можно управлять объектами Power BI, такими как отчеты, наборы данных и рабочие области.

Ниже перечислено несколько задач, которые можно выполнить с помощью API-интерфейсов Power BI.

| **Интересующие темы** | **Справочные материалы** |
|----------------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| Внедрение отчетов, панелей мониторинга и плиток для пользователей Power BI и других программ. | [Как внедрять панели мониторинга, отчеты и плитки Power BI](embedding-content.md) |
| Выполняйте задачи управления объектами Power BI. | [Справочник по REST API Power BI](https://docs.microsoft.com/rest/api/power-bi/) |
| Расширение существующего рабочего бизнес-процесса для принудительной отправки ключевых данных в панель мониторинга Power BI. | [Принудительная отправка данных на панель мониторинга](walkthrough-push-data.md) |
| Аутентификация в Power BI. | [Аутентификация в Power BI](get-azuread-access-token.md) |

> [!NOTE]
> В интерфейсах API Power BI рабочие области по-прежнему называются группами. Если упоминаются группы, это означает, что вы работаете с рабочими областями.

## <a name="api-developer-tools"></a>Инструменты API для разработчика

| Инструменты | Описание |  |  |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|---|---|
| [Инструмент "Тестовая площадка"](https://microsoft.github.io/PowerBI-JavaScript/demo) | Воспользуйтесь полным примером использования API-интерфейсов JavaScript в Power BI. Этот инструмент также позволит быстро познакомиться с разными примерами Power BI Embedded. |  |  |
| [Вики-сайт по JavaScript для Power BI](https://github.com/Microsoft/powerbi-javascript/wiki) | Дополнительные сведения об API-интерфейсах JavaScript в Power BI. |  |  |
| [Postman](https://www.getpostman.com/) | Выполнение запросов, тестирование, отладка, мониторинг, запуск автоматических тестов и многое другое. |

## <a name="push-data-into-power-bi"></a>Принудительная отправка данных в Power BI

Вы можете использовать API Power BI для [принудительной отправки данных в набор](walkthrough-push-data.md). Этот компонент позволяет добавлять строки в таблицу в наборе данных. После этого новые данные отображаются на плитках панели мониторинга и в визуальных элементах отчета.

![Принудительная отправка данных](media/what-can-you-do/powerbi-push-data.png)

## <a name="github-repositories"></a>Репозитории GitHub

* [Примеры для разработчиков Power BI](https://github.com/Microsoft/PowerBI-Developer-Samples)
* [Пакет SDK для .NET](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

## <a name="next-steps"></a>Следующие шаги

* [Принудительная отправка данных в панель мониторинга Power BI](walkthrough-push-data.md)
* [Разработка пользовательского визуального элемента Power BI](visuals/custom-visual-develop-tutorial.md)
* [Справочник по REST API Power BI](rest-api-reference.md)
* [REST API в Power BI](https://docs.microsoft.com/rest/api/power-bi/)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
