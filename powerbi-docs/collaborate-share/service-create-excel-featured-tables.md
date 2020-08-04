---
title: Настройка рекомендуемых таблиц в Power BI Desktop (предварительная версия)
description: Создавайте рекомендуемые таблицы в Power BI Desktop, чтобы они отображались в коллекции типов данных в Excel.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 07/24/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: e39d2fe11a58691b259784c292fec6e5ee6cb322
ms.sourcegitcommit: 65025ab7ae57e338bdbd94be795886e5affd45b4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87254224"
---
# <a name="set-featured-tables-in-power-bi-desktop-preview"></a>Настройка рекомендуемых таблиц в Power BI Desktop (предварительная версия)

В Excel в коллекции типов данных находятся данные из *рекомендуемых таблиц* в наборах данных Power BI. В этой статье рассказывается, как настроить таблицы как *рекомендуемые* в наборах данных. Эти теги облегчают пользователям добавление корпоративных данных на свои листы Excel. Ниже приведены основные шаги по настройке и совместному использованию рекомендуемых таблиц.

1. [Повысьте или сертифицируйте наборы данных в Power BI](../connect-data/service-datasets-promote.md). 
1. Определите рекомендуемые таблицы в наборах данных в Power BI Desktop (в этой статье)
1. Сохраните эти наборы данных с рекомендуемыми таблицами в одной из новых рабочих областей. Создатели отчетов могут создавать отчеты с этими рекомендуемыми таблицами. 
1. Остальные пользователи организации могут подключаться к этим рекомендуемым таблицам, называемым *типами данных* в Excel, для получения актуальных и обновляемых данных. В статье [Доступ к рекомендуемым таблицам Power BI в Excel (предварительная версия)](service-excel-featured-tables.md) описывается использование этих рекомендуемых таблиц в Excel.

## <a name="turn-on-the-featured-table-preview"></a>Включение предварительной версии рекомендуемых таблиц

1. В Power BI Desktop последовательно выберите **Файл** > **Параметры и настройки** > **Параметры** > **Функции на этапе предварительного просмотра**.
2. Установите флажок **Featured tables** (Рекомендуемые таблицы).

    :::image type="content" source="media/service-excel-featured-tables/power-bi-preview-featured-tables.png" alt-text="Параметр предварительной версии рекомендуемых таблиц":::

## <a name="select-a-table"></a>Выбор таблицы

1. В Power BI Desktop перейдите в представление модели.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-model-view.png" alt-text="Представление модели":::
 
2. Выберите таблицу и задайте для параметра **Is featured table** (Рекомендуемая таблица) значение **Да**.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-featured-table-yes.png" alt-text="Для параметра Is featured table (Рекомендуемая таблица) задано значение Да":::

4. В окне **Set up this featured table** (Настройка этой рекомендуемой таблицы) заполните обязательные поля:

    - **Описание**. 
        > [!TIP]
        > Начните описание с "Рекомендуемая таблица", чтобы помочь создателям отчетов Power BI определить их.
    - Значение поля **Метка строки** используется в Excel, чтобы пользователи могли легко опознать эту строку. Он отображается как значение связанной ячейки, в области **Выбор данных** и на карточке **Информация**. 
    - Значение поля **Ключевой столбец** содержит уникальный идентификатор строки. Это значение позволяет Excel связать ячейку с определенной строкой в таблице.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-set-up-featured-table.png" alt-text="Настройка рекомендуемой таблицы":::

1. После публикации или импорта набора данных в службе Power BI рекомендуемая таблица отображается в Excel в коллекции "Типы данных". Вы и другие создатели отчетов также могут создавать отчеты, основанные на этом наборе данных.

1. В Excel 
    - Excel кэширует список типов данных, поэтому, чтобы увидеть только что опубликованные рекомендуемые таблицы, необходимо перезапустить Excel.
    - Некоторые наборы данных не поддерживаются в предварительной версии, поэтому рекомендуемые таблицы, определенные в этих наборах данных, не будут отображаться в Excel. См. следующий раздел со сведениями о рекомендациях и ограничениях.

## <a name="considerations-and-limitations"></a>Рекомендации и ограничения

Ниже приведены ограничения для первоначальной предварительной версии.

- В Excel не отображаются рекомендуемые таблицы из наборов данных Power BI, которые используют следующие возможности: 

    - безопасность на уровне строк;
    - Microsoft Information Protection;
    - DirectQuery;
    - активное подключение.

- В Excel отображаются только данные в столбцах и вычисляемых столбцах рекомендуемой таблицы. В первоначальной предварительной версии не предоставляются следующие данные:

    - меры, определенные в рекомендуемой таблице;
    - меры, определенные в связанных таблицах, и неявные меры, вычисленные на основе связей.

- В Excel отображаются только рекомендуемые таблицы, которые хранятся в новых рабочих областях Power BI. Рекомендуемые таблицы, хранящиеся в классических рабочих областях или в области "Моя рабочая область", не отображаются в Excel в виде типов данных. Вы можете [обновить классические рабочие области до новой версии](service-upgrade-workspaces.md) в Power BI.
- См. [Рекомендации и ограничения](service-excel-featured-tables.md#considerations-and-limitations) в статье "Доступ к рекомендуемым таблицам Power BI в Excel", чтобы ознакомиться с другими моментами, касающимися Excel.

## <a name="next-steps"></a>Дальнейшие действия

- [Доступ к рекомендуемым таблицам Power BI в Excel](service-excel-featured-tables.md)
- Сведения об использовании [типов данных Excel из Power BI](https://support.office.com/article/use-excel-data-types-from-power-bi-preview-cd8938ce-f963-444d-b82a-7140848241e9) приведены в документации по Excel.
- У вас появились вопросы? [Ответы на них см. в сообществе Power BI.](https://community.powerbi.com/)
