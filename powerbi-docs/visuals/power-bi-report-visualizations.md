---
title: Общие сведения о визуализациях отчетов в службе Power BI и Power BI Desktop
description: Сведения о визуализациях отчетов (визуальных элементах) в Microsoft Power BI.
author: mihart
ms.author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: SYk_gWrtKvM
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/28/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: d470a262bd8a5e6590746fb07889b1230f5cfc25
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66375662"
---
# <a name="visualizations-in-power-bi-reports"></a>Визуализации в отчетах Power BI

Визуализации (также называемые визуальными элементами) отображают сведения, обнаруженные в данных. Отчет Power BI может содержать одну страницу с одной визуализацией или большое количество и тех, и других. Служба Power BI позволяет [закрепить визуальные элементы из отчетов на панели мониторинга](../service-dashboard-pin-tile-from-report.md).

Важно различать отчетов *конструкторы* и отчетов *потребителей* Если вы являетесь лицом, построении или изменении отчета, то вы не конструктора.  Конструкторы имеют разрешения на изменение для отчета и базового набора данных. В Power BI Desktop это означает, что вы сможете открывать набор данных в режиме представления данных и создавать визуальные элементы в представлении отчета. В службе Power BI, это означает, что набор данных или отчет можно открыть в редакторе отчетов в [правки](../consumer/end-user-reading-view.md). Если к отчету или панели мониторинга [вам предоставлен общий доступ ](../consumer/end-user-shared-with-me.md)другим лицом, вы считаетесь **потребителем** отчета. Вы сможете просматривать и взаимодействовать с отчетом и его визуальные элементы, но вы не сможете сохранить важные изменения.

Есть много разных типов визуальных элементов, которые вы можете добавить прямо из панели визуализаций в Power BI.

![](media/power-bi-report-visualizations/power-bi-templates.png)

Чтобы получить еще больше возможностей, посетите [веб-сайт сообщества Microsoft AppSource](https://appsource.microsoft.com). Там вы сможете найти и [скачать](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) [пользовательские визуальные элементы](../developer/custom-visual-develop-tutorial.md), созданные корпорацией Майкрософт и членами сообщества.

<iframe width="560" height="315" src="https://www.youtube.com/embed/SYk_gWrtKvM?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


  Если вы недавно начали использовать Power BI или вам необходимо вспомнить ранее изученные сведения, используйте приведенные ниже ссылки для изучения основ визуализации Power BI.  Кроме того, воспользуйтесь содержанием (в левой части этой статьи), чтобы найти больше полезной информации.

## <a name="add-a-visualization-in-power-bi"></a>Добавление визуализации в Power BI

[Создавайте визуализации](power-bi-report-add-visualizations-i.md) на страницах отчетов. Просматривайте [список доступных визуализаций и учебников по работе с визуализациями.](power-bi-visualization-types-for-reports-and-q-and-a.md) 

## <a name="upload-a-custom-visualization-and-use-it-in-power-bi"></a>Отправка пользовательской визуализации и ее использование в Power BI

Добавьте пользовательскую визуализацию, созданную вами или найденную на [сайте сообщества Майкрософт AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals). Чувствуете творческий порыв? Изучите наш исходный код и примените наши [средства разработчика](../developer/custom-visual-develop-tutorial.md), чтобы создать новый тип визуализации и [поделиться им с сообществом](../developer/office-store.md). См. дополнительные сведения о [разработке пользовательских визуальных элементов Power BI](../developer/custom-visual-develop-tutorial.md).

## <a name="change-the-visualization-type"></a>Изменение типа визуализации

Попробуйте [изменить тип визуализации](power-bi-report-change-visualization-type.md), чтобы выбрать наиболее эффективный способ отображения данных.

## <a name="pin-the-visualization"></a>Закрепление визуализации

В службе Power BI готовую визуализацию можно [закрепить на панели мониторинга](../service-dashboard-pin-tile-from-report.md) в виде плитки. Если вы позже измените визуализацию, которая используется в отчете и закреплена, плитка на панели мониторинга не изменится. График всегда останется здесь графиком, даже если исходная визуализация в отчете станет кольцевой диаграммой.

## <a name="limitations-and-considerations"></a>Рекомендации и ограничения
- В зависимости от источника данных и количество полей (мер или столбцы) может медленно загружаться визуальный элемент.  Рекомендуется ограничить количество визуальных элементов на 10-20 полей, для повышения удобства чтения и производительности. 

- Верхний предел для визуальных элементов — 100 полей (мер или столбцы). Если не удается загрузить визуальный элемент, уменьшите число полей.   

## <a name="next-steps"></a>Дальнейшие действия

* [Типы визуализаций в Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
* [Пользовательские визуальные элементы](../power-bi-custom-visuals.md)