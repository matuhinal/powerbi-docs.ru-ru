---
title: Что можно сделать с помощью API Power BI
description: Что можно сделать с помощью API Power BI
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 07/20/2017
ms.author: maghan
ms.openlocfilehash: 47dd0ab87b78e344de176ebe22a1e5dc9753b9b0
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>Какие возможности API Power BI предоставляет разработчикам?
Power BI отображает интерактивные панели мониторинга, которые можно создать и обновлять посредством множества различных источников данных в режиме реального времени. С помощью любого языка программирования, поддерживающего вызовы REST, можно создавать приложения, которые интегрируются в панель мониторинга Power BI в режиме реального времени. В приложения также можно интегрировать плитки и отчеты Power BI.

Разработчики также могут создавать собственные визуализации данных, которые можно использовать в интерактивных отчетах и на панелях мониторинга. 

Ниже перечислено несколько задач, которые можно выполнить с помощью API-интерфейсов Power BI.

| **Действия** | **Инструкции** |
| --- | --- |
| Внедрение панелей мониторинга, отчетов и плиток для пользователей Power BI и пользователей, не работающих с Power BI (данные принадлежат приложению) |[Как внедрять панели мониторинга, отчеты и плитки Power BI](embedding-content.md) |
| Расширение существующего рабочего бизнес-процесса для принудительной отправки ключевых данных в панель мониторинга Power BI. |[Принудительная отправка данных на панель мониторинга](walkthrough-push-data.md) |
| Импорт файла Power BI Desktop |[Импорт PBIX-файла](https://msdn.microsoft.com/library/mt243837.aspx) |
| Аутентификация в Power BI. |[Аутентификация в Power BI](get-azuread-access-token.md) |
| Создание настраиваемого визуального элемента. |[Создание пользовательского визуального элемента с помощью средств разработчика](../service-custom-visuals-getting-started-with-developer-tools.md) |

> [!NOTE]
> В интерфейсах API Power BI рабочие области приложения по-прежнему называются группами. Если упоминаются группы, это означает, что вы работаете с рабочими областями приложения.
> 
> 

## <a name="power-bi-developer-samples"></a>Примеры для разработчиков Power BI
Примеры для разработчиков Power BI содержат элементы для внедрения панелей мониторинга, отчетов и плиток.

[Примеры для разработчиков Power BI](https://github.com/Microsoft/PowerBI-Developer-Samples)

* Примеры в **App Owns Data** (Данные приложения) предназначены для внедрения пользователями, не использующими Power BI.
* Примеры в **User Owns Data** (Данные пользователя) предназначены для внедрения пользователями Power BI.

## <a name="github-repositories"></a>Репозитории GitHub
* [Пакет SDK для .NET](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)
* [Пользовательские визуальные элементы](https://github.com/Microsoft/PowerBI-visuals)

## <a name="developer-tools"></a>Инструменты разработчиков
Ниже приведены инструменты, которые можно использовать для упрощения разработки элементов Power BI.

* [Пример внедрения JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo)

## <a name="next-steps"></a>Дальнейшие действия
[Принудительная отправка данных в панель мониторинга Power BI](walkthrough-push-data.md)  
[Создание пользовательского визуального элемента с помощью средств разработчика](../service-custom-visuals-getting-started-with-developer-tools.md) 
[Справочник по REST API Power BI](https://msdn.microsoft.com/library/mt147898.aspx)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

