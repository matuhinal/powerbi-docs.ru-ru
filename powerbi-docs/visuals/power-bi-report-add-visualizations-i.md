---
title: Часть 1. Добавление визуализаций в отчет Power BI
description: Часть 1. Добавление визуализаций в отчет Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/17/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: c5838d12351c06d0a76a975c9c473b1c00856d97
ms.sourcegitcommit: 90aa7ea5fcc7cf0fd7f6c3c1efeff5f27e8ef0dd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2019
ms.locfileid: "67299265"
---
# <a name="part-1-add-visualizations-to-a-power-bi-report"></a>Часть 1. Добавление визуализаций в отчет Power BI

В этой статье содержатся краткие вводные сведения о создании визуализации в отчете. Эта информация относится к службе Power BI и к Power BI Desktop. Дополнительные сведения см. в [части 2](power-bi-report-add-visualizations-ii.md) этой серии. В этом видео Аманда покажет вам несколько разных способов создания, изменения и форматирования визуальных элементов на холсте отчетов. Теперь попробуйте сделать это сами, использовав раздел [Продажи и маркетинг — пример](../sample-datasets.md) для создания собственного отчета.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

## <a name="open-a-report-and-add-a-new-page"></a>Открытие отчета и добавление новой страницы

1. Откройте [отчет в режиме правки](../service-interact-with-a-report-in-editing-view.md).

    В этом руководстве используется [образец "Продажи и маркетинг"](../sample-datasets.md).

1. Если панель **Поля** не отображается, щелкните значок со стрелкой, чтобы ее открыть.

   ![](media/power-bi-report-add-visualizations-i/pbi_nancy_fieldsfiltersarrow.png)

1. Добавьте пустую страницу в отчет.

## <a name="add-visualizations-to-the-report"></a>Добавление визуализаций к отчету

1. Создайте визуализацию, выбрав поле на панели **Поля** .

    Начните с числового поля, например **Факт продажи** > **Продажи в долл. США**. Power BI создаст гистограмму с одним столбцом.

    ![Снимок экрана: гистограмма с одним столбцом.](media/power-bi-report-add-visualizations-i/pbi_onecolchart.png)

    Начните с поля категории, например **Имя** или **Продукт**. Создайте в Power BI таблицу и добавьте поле в область **Значения**.

    ![GIF-демонстрация пользователя, выбирающего продукт, а затем категорию при создании таблицы.](media/power-bi-report-add-visualizations-i/pbi_agif_createchart3.gif)

    Кроме того, можно начать с поля для географических данных, такого как **Геообъект** > **Город**. Создание визуализации карты при помощи Power BI и Карт Bing.

    ![Снимок экрана: визуализация карты.](media/power-bi-report-add-visualizations-i/power-bi-map.png)

1. Создайте визуализацию и измените ее тип. Выберите **Продукт** > **Категория**, а затем **Продукт** > **Число продуктов**, чтобы добавить эти поля в раздел **Значения**.

   ![Снимок экрана: панель "Поля" с вызванным разделом "Значения".](media/power-bi-report-add-visualizations-i/part1table1.png)

1. Измените визуализацию на гистограмму, выбрав значок **Гистограмма с накоплением**.

   ![Снимок экрана: панель "Визуализации" после нажатия значка "Гистограмма с накоплением".](media/power-bi-report-add-visualizations-i/part1converttocolumn.png)

1. Созданные в отчете визуализации можно [закреплять на панели мониторинга](../service-dashboard-pin-tile-from-report.md). Чтобы закрепить визуализацию, выберите значок закрепления ![Снимок экрана закрепленного значка.](media/power-bi-report-add-visualizations-i/pinnooutline.png).

   ![Снимок экрана: визуализация гистограммы с вызванным значком закрепления.](media/power-bi-report-add-visualizations-i/part1pin1.png)
  
## <a name="next-steps"></a>Дальнейшие действия

 Дальнейшие действия

* [Часть 2. Добавление визуализаций в отчет Power BI](power-bi-report-add-visualizations-ii.md)

* [Взаимодействовать с визуализациями](../consumer/end-user-reading-view.md) в отчете.

* [Выполнять дополнительные действия с визуализациями](power-bi-report-visualizations.md).

* [Сохранить отчет](../service-report-save.md).
