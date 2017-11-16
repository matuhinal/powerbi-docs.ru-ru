---
title: "Представление связей в Power BI Desktop"
description: "Представление связей в Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 77dd801d6704c59cd88bf02f1f74aaefe73be26e
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="relationship-view-in-power-bi-desktop"></a>Представление связей в Power BI Desktop
**Представление связей** показывает все таблицы, столбцы и связи в модели. Это может быть особенно удобно, если модель содержит сложные связи между большим количеством таблиц.

Давайте взглянем подробнее.

![](media/desktop-relationship-view/relationshipview_fullscreen.png)

**A.**  Значок представления связей — щелкните для отображения своей модели в представлении связей.

**B.** Связь — можно навести на связь курсор для отображения используемых столбцов. Дважды щелкните связь, чтобы открыть ее в диалоговом окне **Изменение связи**. 

На приведенном выше рисунке видно, что таблица *Stores* имеет столбец *StoreKey*, связанный с таблицей *Sales*, которая также имеет столбец *StoreKey*. Мы видим, что это связь *многие к одному* (\*:1), а значок в середине линии показывает, что направление перекрестной фильтрации задано в *обе* стороны. Стрелка на значке показывает направление потока контекста фильтра.

Дополнительные сведения о связях см. в разделе [Создание связей и управление ими в Power BI Desktop](desktop-create-and-manage-relationships.md).

