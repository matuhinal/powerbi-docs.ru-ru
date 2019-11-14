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
ms.date: 10/28/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: e25db5ab57e3a52ffc08020dc980553e515256bf
ms.sourcegitcommit: 2a61d8b1e2707a24fe1284a8a4034b11c3999842
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73048976"
---
# <a name="part-1-add-visualizations-to-a-power-bi-report"></a>Часть 1. Добавление визуализаций в отчет Power BI

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

В этой статье содержатся краткие вводные сведения о создании визуализации в отчете. Эта информация относится к службе Power BI и к Power BI Desktop. Дополнительные сведения см. в [части 2](power-bi-report-add-visualizations-ii.md) этой серии. В этом видео Аманда покажет вам несколько разных способов создания, изменения и форматирования визуальных элементов на холсте отчетов. Теперь попробуйте сделать это сами, использовав раздел [Продажи и маркетинг — пример](../sample-datasets.md) для создания собственного отчета.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

## <a name="prerequisites"></a>Предварительные требования

В этом руководстве используется [PBIX-файл "Продажи и маркетинг"](http://download.microsoft.com/download/9/7/6/9767913A-29DB-40CF-8944-9AC2BC940C53/Sales%20and%20Marketing%20Sample%20PBIX.pbix).

1. В верхнем левом разделе меню Power BI Desktop выберите пункты **Файл** > **Открыть**.
   
2. Найдите свою копию **PBIX-файла "Продажи и маркетинг"** .

1. Откройте PBIX-файл **Продажи и маркетинг** в представлении отчета ![Снимок экрана: значок представления отчета](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Выбрать ![Снимок экрана: желтая вкладка,](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) чтобы создать новую страницу.

## <a name="add-visualizations-to-the-report"></a>Добавление визуализаций к отчету

1. Создайте визуализацию, выбрав поле на панели **Поля** .

    Начните с числового поля, например **Sales** > **TotalSales** (Продажи - Общие продажи). Power BI создаст гистограмму с одним столбцом.

    ![Снимок экрана: гистограмма с одним столбцом.](media/power-bi-report-add-visualizations-i/power-bi-column-chart.png)

    Начните с поля категории, например **Имя** или **Продукт**. Создайте в Power BI таблицу и добавьте поле в область **Значения**.

    ![Снимок экрана таблицы с четырьмя категориями](media/power-bi-report-add-visualizations-i/power-bi-product.png)

    Кроме того, можно начать с поля для географических данных, такого как **Геообъект** > **Город**. Создание визуализации карты при помощи Power BI и Карт Bing.

    ![Снимок экрана: визуализация карты.](media/power-bi-report-add-visualizations-i/power-bi-maps.png)

## <a name="change-the-type-of-visualization"></a>Изменение типа визуализации

 Создайте визуализацию и измените ее тип. 
 
 1. Выберите **Продукт** > **Категория**, а затем **Продукт** > **Число продуктов**, чтобы добавить эти поля в раздел **Значения**.

    ![Снимок экрана: панель "Поля" с вызванным разделом "Значения".](media/power-bi-report-add-visualizations-i/power-bi-create-visual.png)

1. Измените визуализацию на гистограмму, выбрав значок **Гистограмма с накоплением**.

   ![Снимок экрана: панель "Визуализации" после нажатия значка "Гистограмма с накоплением".](media/power-bi-report-add-visualizations-i/power-bi-convert.png)

1. Чтобы изменить способ сортировки визуального элемента, выберите **Дополнительные действия** (...).  Используйте параметры сортировки, чтобы изменить направление сортировки (по возрастанию или по убыванию) и столбец, используемый для сортировки (**Сортировать по**).

   ![Снимок экрана с раскрывающимся списком "Другие действия".](media/power-bi-report-add-visualizations-i/power-bi-sort.png)
  
## <a name="next-steps"></a>Дальнейшие действия

 Дальнейшие действия

* [Часть 2. Добавление визуализаций в отчет Power BI](power-bi-report-add-visualizations-ii.md)

* [Взаимодействовать с визуализациями](../consumer/end-user-reading-view.md) в отчете.

