---
title: "Создание плитки с большим числом из отчета Power BI"
description: "Создание плитки с большим числом из отчета Power BI"
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
ms.openlocfilehash: 9f748ed1d3a34c6c6aceb14337bbb780598a15f9
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-big-number-tile-from-a-power-bi-report"></a>Создание плитки с большим числом из отчета Power BI
Иногда на информационной панели Power BI очень важно отслеживать одно число, например показатель общего объема продаж, долю на рынке в годовом исчислении или общее число возможных сделок. Плитку с большим числом можно создать с помощью [вопроса в поле ввода вопросов](power-bi-visualization-big-number.md) или в отчете Power BI. В этой статье содержатся сведения о создании плитки в отчете.

1. Создайте [панель мониторинга](service-dashboards.md) и [получите данные](service-get-data.md).
   
   Если вам нужны данные для практики, [скачайте образец "Анализ розничной торговли"](sample-retail-analysis.md). 
2. Откройте отчет в [режиме редактирования](service-reading-view-and-editing-view.md).
3. В отчете найдите страницу с пустым местом или [добавьте в отчет новую страницу](power-bi-report-add-page.md).
4. В списке "Поля" выберите числовое поле, которое будет отображаться.
   
   В данном примере это **Количество открытых магазинов** в таблице **Магазин** . Power BI создаст гистограмму с одним числом.
   
   ![](media/power-bi-visualization-big-number-report/pbi_rptnumbertilechart.png)
5. На панели "Визуализации" выберите значок карты.
   
   ![](media/power-bi-visualization-big-number-report/pbi_changechartcard.png)
6. Наведите указатель мыши на карту и выберите значок булавки ![](media/power-bi-visualization-big-number-report/pbi_pintile.png), чтобы добавить плитку на панель мониторинга. 
   
   ![](media/power-bi-visualization-big-number-report/power-bi-pin-icon.png)
7. Закрепите плитку на существующей или новой панели мониторинга. 
   
   * Существующая информационная панель: выберите имя панели в раскрывающемся списке.
   * Новая информационная панель: введите имя новой панели.
8. Выберите **Закрепить**.
   
   Сообщение об успешном выполнении (рядом с правым верхним углом экрана) позволяет узнать, что визуализация была добавлена на панель мониторинга в качестве плитки.
   
   ![](media/power-bi-visualization-big-number-report/power-bi-pin-success-message.png)
9. Выберите **Перейти к панели мониторинга**. Здесь вы можете [изменить и переместить](service-dashboard-edit-tile.md) закрепленную визуализацию.

## <a name="next-steps"></a>Дальнейшие действия
[Плитки панели мониторинга в Power BI](service-dashboard-tiles.md)

[Панели мониторинга в Power BI](service-dashboards.md)

[Power BI — основные понятия](service-basic-concepts.md)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

