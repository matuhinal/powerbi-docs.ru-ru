---
title: Добавление нескольких полей в иерархический срез
description: Узнайте, как создать иерархический срез, содержащий несколько полей в иерархии.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 06/11/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 2b9c4a8f4695f8d701eba535180194d29dd8bdec
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85238192"
---
# <a name="add-multiple-fields-to-a-hierarchy-slicer"></a>Добавление нескольких полей в иерархический срез

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Если вы хотите отфильтровать несколько связанных полей в одном срезе, создайте так называемый *иерархический* срез. Эти срезы можно создать либо в Power BI Desktop, либо в службе Power BI.

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy.png" alt-text="Иерархический срез в Power BI":::

При добавлении нескольких полей в срез рядом с элементами, которые можно развернуть для отображения элементов на следующем уровне, по умолчанию отображается стрелка или *шеврон*.

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-arrow.png" alt-text="Раскрывающееся меню иерархического среза в Power BI":::
 
 
При выборе одного или нескольких дочерних элементов для элемента верхнего уровня появится круг, обозначающий частичный выбор.
 
:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-semi-selected.png" alt-text="Иерархический срез с одиночным выбором в Power BI":::

## <a name="format-the-slicer"></a>Форматирование среза

Поведение среза не изменилось. Вы также можете использовать для среза стиль на свое усмотрение. Например, использовать режим одиночного выбора либо простой или раскрывающийся список. 

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-dropdown.png" alt-text="Иерархический срез в формате раскрывающегося среза":::

### <a name="change-the-expandcollapse-icon"></a>Изменение значка "Развернуть/свернуть"

Для иерархических срезов предусмотрены также другие параметры форматирования. Значок "Развернуть/свернуть" можно изменить, чтобы вместо стрелки по умолчанию отображался знак "плюс/минус" либо курсор.

1. Выберите срез, а затем — **Формат**.
1. Разверните пункт **Элементы** и выберите **значок "Развернуть/свернуть"** .
1. Выберите **Шеврон**, **Плюс/минус** или **Курсор**.
 
    :::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-caret.png" alt-text="Выбор значка "Развернуть/свернуть" для иерархического среза":::
 
### <a name="change-the-indentation"></a>Изменение отступа

Если в вашем отчете мало места, возможно, вы захотите уменьшить размер отступа для дочерних элементов. По умолчанию отступ составляет 15 пикселей, однако это значение можно увеличить или уменьшить. 

1. Выберите срез, а затем — **Формат**.
1. Разверните пункт **Элементы**, а затем увеличьте или уменьшите значение параметра **Макет с пошаговым отступом**. Кроме того, вы можете просто ввести цифру в поле.

    :::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-indentation.png" alt-text="Задание отступа для иерархического среза":::

## <a name="next-steps"></a>Дальнейшие действия

- [Срезы в Power BI](../visuals/power-bi-visualization-slicers.md)
- Остались вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)