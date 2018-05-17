---
title: Импорт и отображение ключевых показателей эффективности в Power BI
description: Импорт и отображение ключевых показателей эффективности
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 5cb7370942cdd4b50c8315a075eb7a178b05a692
ms.sourcegitcommit: f679c05d029ad0765976d530effde744eac23af5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="import-and-display-kpis-in-power-bi"></a>Импорт и отображение ключевых показателей эффективности в Power BI
С помощью **Power BI Desktop** можно импортировать и отображать ключевые показатели эффективности в таблицах, матрицах и на картах.

Чтобы импортировать и отобразить ключевые показатели эффективности, выполните описанные ниже действия.

1. Начнем с книги Excel, которая содержит модель Power Pivot и ключевые показатели эффективности. В этом упражнении мы будем использовать книгу с именем *KPIs* (ключевые показатели эффективности).

1. Чтобы импортировать книгу, в Power BI, последовательно выберите **Файл -> Импорт -> Содержимое книги Excel**. Сведения о том, как импортировать книги, см. в [этой статье](desktop-import-excel-workbooks.md). 

1. Импортированный в Power BI ключевой показатель эффективности будет отображаться на панели **Поля**, отмеченный значком ![светофора](media/desktop-import-and-display-kpis/traffic.png). Чтобы использовать ключевой показатель эффективности в отчете, разверните его содержимое и поля **Значение**, **Цель** и **Состояние**.

    ![](media/desktop-import-and-display-kpis/desktoppreviewfeatureon2.png)

1. Импортированные ключевые показатели эффективности лучше всего использовать в стандартных визуализациях, например **табличного** типа. Power BI также включает тип визуализации **ключевого показателя эффективности**, который должен использоваться только для создания новых показателей.
   
    ![](media/desktop-import-and-display-kpis/desktoppreviewfeatureon3.png)

Вот, собственно, и все. Ключевые показатели эффективности можно использовать для демонстрации тенденций, хода выполнения или других важных индикаторов.
