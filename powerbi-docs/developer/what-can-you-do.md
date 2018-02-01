---
title: "Что могут разработчики сделать с помощью Power BI"
description: "Power BI предлагает целый ряд параметров для разработчиков, начиная от параметров внедрения и заканчивая настраиваемыми визуальными элементами и наборами данных потоковой передачи."
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
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 07/20/2017
ms.author: maghan
ms.openlocfilehash: b310562ac31694f398a659018743b8fa7aa46e35
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2018
---
# <a name="what-can-developers-do-with-power-bi"></a>Что могут разработчики сделать с помощью Power BI
Power BI предлагает целый ряд параметров для разработчиков, начиная от параметров внедрения и заканчивая настраиваемыми визуальными элементами и наборами данных потоковой передачи.

## <a name="embedding"></a>Внедрение
Возможности службы Power BI и Power BI Embedded в Azure были объединены, что позволило предоставить единый API для внедрения информационных панелей и отчетов. Это означает, что у вас будет одна область API, одинаковый набор возможностей и доступ к последним функциям Power BI, например информационным панелям, шлюзам и рабочим областям приложений, которые можно использовать при внедрении содержимого. Дополнительные сведения см. в статье [Внедрение в Power BI](embedding.md).

![](media/what-can-you-do/powerbi-embed-sample.png)

## <a name="custom-visuals"></a>Пользовательские визуальные элементы
Настраиваемые визуальные элементы позволяют создавать собственные визуальные элементы, которые можно использовать в отчетах Power BI. Настраиваемые визуальные элементы написаны на языке TypeScript (надмножество JavaScript), который поддерживает некоторые дополнительные возможности и ранний доступ к функциям ES6 и ES7. Стиль визуального элемента обрабатывается с помощью каскадных таблиц стилей (CSS). Для удобства предварительный компилятор Less используется для поддержки некоторых дополнительных функций, таких как вложения, переменные, примеси, условия, циклы и т. д. Если в любой из этих функций нет необходимости, можно просто записать обычные CSS в файле Less.

Дополнительные сведения о разработке и публикации настраиваемых визуальных элементов см. в статье [Публикация пользовательских визуализаций в Магазине Office](office-store.md).

![](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>Принудительная отправка данных в Power BI
Для принудительной отправки данных в набор данных можно использовать API-интерфейс Power BI. Это позволяет вам добавлять строки в таблицу в наборе данных. После этого новые данные могут отображаться на плитках информационной панели и в визуальных элементах отчета.

Дополнительные сведения см. в статье [Принудительная отправка данных в набор данных Power BI](walkthrough-push-data.md)

## <a name="next-steps"></a>Дальнейшие действия
[Внедрение в Power BI](embedding.md)  
[Как перенести содержимое коллекции рабочих областей Power BI Embedded в Power BI](migrate-from-powerbi-embedded.md)  
[Репозиторий Git JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)  
[Репозиторий Git Power BI C#](https://github.com/Microsoft/PowerBI-CSharp)  
[Публикация пользовательских визуализаций в Магазине Office](office-store.md)  
[Репозиторий Git настраиваемых визуальных элементов](https://github.com/Microsoft/PowerBI-visuals)  
[Пример внедрения JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Техническая документация по Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

