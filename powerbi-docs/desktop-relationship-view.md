---
title: Представление связей в Power BI Desktop
description: Представление связей в Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/02/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 58886dc1ae5490113d4d0ba9af00d16aefecbe71
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34287033"
---
# <a name="relationship-view-in-power-bi-desktop"></a>Представление связей в Power BI Desktop
**Представление связей** показывает все таблицы, столбцы и связи в модели. Это может быть особенно удобно, если модель содержит сложные связи между большим количеством таблиц.

Давайте взглянем подробнее.

![](media/desktop-relationship-view/relationshipview_fullscreen.png)

**A.**  Значок представления связей — щелкните для отображения своей модели в представлении связей.

**B.** Связь — можно навести на связь курсор для отображения используемых столбцов. Дважды щелкните связь, чтобы открыть ее в диалоговом окне **Изменение связи**. 

На приведенном выше рисунке видно, что таблица *Stores* имеет столбец *StoreKey*, связанный с таблицей *Sales*, которая также имеет столбец *StoreKey*. Мы видим, что это связь *многие к одному* (\*:1), а значок в середине линии показывает, что направление перекрестной фильтрации задано в *обе* стороны. Стрелка на значке показывает направление потока контекста фильтра.

Дополнительные сведения о связях см. в разделе [Создание связей и управление ими в Power BI Desktop](desktop-create-and-manage-relationships.md).

