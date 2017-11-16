---
title: "Создание плитки с большими числами с помощью функции \"Вопросы и ответы\""
description: "Создание плитки с большим числом для информационной панели Power BI с помощью вопроса"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 09/26/2017
ms.author: mihart
ms.openlocfilehash: 559484c341ec017890a4075a393d5ce211843b5f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-big-number-tile-from-qa"></a>Создание плитки с большими числами с помощью функции "Вопросы и ответы"
Иногда на информационной панели Power BI очень важно отслеживать одно число, например показатель общего объема продаж, долю на рынке в годовом исчислении или общее число возможных сделок. [Плитку с большим числом можно создать в отчете Power BI](power-bi-visualization-big-number-report.md) или с помощью вопроса в поле ввода вопросов. В этой статье содержатся сведения о создании плитки в поле вопросов.

![](media/power-bi-visualization-big-number/pbi_opptuntiescard.png)

Поле для ввода вопроса является самым простым способом создания плитки с числом.

1. Создайте [панель мониторинга](service-dashboards.md) и [получите данные](service-get-data.md). Здесь используется пример [Анализ возможностей](sample-opportunity-analysis.md).
2. В верхней части информационной панели начните вводить вопрос о данных в поле вопроса. Здесь используется пример "Анализ возможностей".
   
   ![](media/power-bi-visualization-big-number/power-bi-q-and-a-box.png)
3. Например, введите "количество возможных сделок".
   
   ![](media/power-bi-visualization-big-number/power-bi-ask.png)
   
   В поле "Вопрос" предлагается и переопределяется предложение **Показать число возможных сделок**, а также отображается общее число.  
4. В правом верхнем углу выберите значок закрепления ![](media/power-bi-visualization-big-number/pbi_pintile.png), чтобы добавить плитку с числом на информационную панель. 
   
   ![](media/power-bi-visualization-big-number/power-bi-pin.png)
5. Закрепите плитку на существующей или новой панели мониторинга. 
   
   * Существующая информационная панель: выберите имя панели в раскрывающемся списке. Вы сможете выбрать только информационные панели, доступные в текущей рабочей области.
   * "Новая информационная панель". Введите имя новой информационной панели, и она будет добавлена в текущую рабочую область.
6. Выберите **Закрепить**.
   
   Сообщение об успешном выполнении (рядом с правым верхним углом экрана) позволяет узнать, что визуализация была добавлена на панель мониторинга в качестве плитки.  
   
   ![](media/power-bi-visualization-big-number/power-bi-success.png)
7. Выберите **Перейти на информационную панель**, чтобы просмотреть новую плитку. Здесь вы можете [изменить имя или размер, добавить гиперссылку и переместить плитку, а также выполнить другие действия](service-dashboard-edit-tile.md) на панели мониторинга. 
   
   ![](media/power-bi-visualization-big-number/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Рекомендации и устранение неполадок
Если поле для вопроса не отображается, обратитесь к системному администратору или администратору клиента.

## <a name="next-steps"></a>Дальнейшие действия
[Плитки панели мониторинга в Power BI](service-dashboard-tiles.md)  
[Панели мониторинга в Power BI](service-dashboards.md)  
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

