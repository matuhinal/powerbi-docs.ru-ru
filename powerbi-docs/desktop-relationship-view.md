---
title: Представление связей в Power BI Desktop
description: Представление связей в Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 178f3cd9015af503ff12875548822ba1ab5365c3
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54272773"
---
# <a name="relationship-view-in-power-bi-desktop"></a>Представление связей в Power BI Desktop
**Представление связей** показывает все таблицы, столбцы и связи в модели. Это может быть особенно удобно, если модель содержит сложные связи между большим количеством таблиц.

Давайте взглянем подробнее.

![](media/desktop-relationship-view/relationshipview_fullscreen.png)

**A.**  Значок представления связей — щелкните для отображения своей модели в представлении связей.

**B.** Связь — можно навести на связь курсор для отображения используемых столбцов. Дважды щелкните связь, чтобы открыть ее в диалоговом окне **Изменение связи**. 

На приведенном выше рисунке видно, что таблица *Stores* имеет столбец *StoreKey*, связанный с таблицей *Sales*, которая также имеет столбец *StoreKey*. Мы видим, что это связь *многие к одному* (\*:1), а значок в середине линии показывает, что направление перекрестной фильтрации задано в *обе* стороны. Стрелка на значке показывает направление потока контекста фильтра.

Дополнительные сведения о связях см. в разделе [Создание связей и управление ими в Power BI Desktop](desktop-create-and-manage-relationships.md).

