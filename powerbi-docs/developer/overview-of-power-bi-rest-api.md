---
title: "Что можно сделать с помощью API Power BI"
description: "Что можно сделать с помощью API Power BI"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 07/20/2017
ms.author: asaxton
ms.openlocfilehash: 5a6d760667608feb07932b9175b6949387b33f9a
ms.sourcegitcommit: 7517c068db806f12bb0b953e9a1bd4249ca12da5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="what-can-developers-do-with-power-bi"></a>Что могут разработчики сделать с помощью Power BI
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

