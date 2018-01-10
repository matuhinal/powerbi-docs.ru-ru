---
title: "Создание панели мониторинга Power BI из отчета"
description: "Создание панели мониторинга Power BI из отчета"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/09/2017
ms.author: mihart
ms.openlocfilehash: 67cc9508d71fa29303d09e8901294a2d6b7f8a56
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2018
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>Создание панели мониторинга Power BI из отчета
Вы прочитали раздел [Панели мониторинга в Power BI](service-dashboards.md) и хотите создать свои собственные информационные панели. Существует много разных способов создавать панели мониторинга, среди которых: создание из отчета, с нуля, из набора данных, с помощью дублирования существующей панели мониторинга и многое другое.  В этом разделе и видео показано, как создать панель с помощью закрепления визуализаций из существующего отчета.

> **Примечание**. Панели мониторинга — это компонент службы Power BI, а не Power BI Desktop. Панели мониторинга нельзя создавать в Power BI Mobile, но их можно [просматривать и предоставлять для общего доступа](mobile-apps-view-dashboard.md).
> 
> 

![](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>Создание информационной панели путем закрепления визуальных элементов и изображений из отчета (видео)
Посмотрите, как Аманда создает новую панель мониторинга с помощью закрепления визуализаций из отчета. Затем попробуйте сделать это самостоятельно, используя пример анализа закупок и выполняя действия, указанные под видео.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

## <a name="import-a-dataset-with-a-report"></a>Импорт набора данных с помощью отчета
Мы импортируем один из примеров наборов данных Power BI и будем использовать его для создания панели мониторинга. Пример, который мы будем использовать, — это книга Excel с двумя листами PowerView. При импорте книги Power BI добавит в рабочую область набор данных, а также отчет.  Отчет автоматически создается из листов PowerView.

1. [Перейдите по этой ссылке](http://go.microsoft.com/fwlink/?LinkId=529784), чтобы скачать и сохранить файл Excel с примером анализа закупок. Рекомендуется сохранить его в приложении OneDrive для бизнеса.
2. Откройте службу Power BI в браузере (app.powerbi.com).
3. Создайте рабочую область приложения или выберите существующую.
4. На левой панели навигации выберите **Получить данные**.
   
    ![](media/service-dashboard-create/power-bi-get-data3.png)
5. Выберите **Файлы**.
   
   ![](media/service-dashboard-create/power-bi-select-files.png)
6. Перейдите к расположению, в котором вы сохранили файл Excel с примером анализа закупок. Выберите файл и щелкните **Подключить**.
   
   ![](media/service-dashboard-create/power-bi-connectnew.png)
7. Для этого упражнения выберите **Импорт**.
   
    ![](media/service-dashboard-create/power-bi-import.png)
8. Когда появится сообщение об успешном выполнении, щелкните **x**, чтобы закрыть его.
   
   ![](media/service-dashboard-create/power-bi-view-datasetnew.png)

### <a name="open-the-report-and-pin-some-tiles-to-a-dashboard"></a>Открытие отчета и закрепление некоторых плиток на панели мониторинга
1. В той же рабочей области откройте вкладку **Отчеты**. Только что импортированный отчет будет отмечен желтой звездочкой. Щелкните имя отчета, чтобы открыть его.
   
    ![](media/service-dashboard-create/power-bi-reports.png)
2. Отчет открывается в [режиме чтения](service-reading-view-and-editing-view.md). В нижней части отчета расположены две вкладки: Discount Analysis (Анализ скидок) и Spend Overview (Обзор затрат). Каждая вкладка представляет страницу отчета.
   
    ![](media/service-dashboard-create/power-bi-reading-view.png)
3. Наведите указатель мыши на визуализацию, чтобы отобразить доступные параметры. Чтобы добавить визуализацию на панель мониторинга, щелкните значок булавки ![](media/service-dashboard-create/power-bi-pin-icon.png).
   
    ![](media/service-dashboard-create/power-bi-hover.png)
4. Так как мы создаем новую панель, выберите параметр **Новая панель мониторинга** и присвойте панели имя. 
   
   ![](media/service-dashboard-create/power-bi-pin-tile.png)
5. Когда вы выберете параметр **Закрепить**, Power BI создаст панель мониторинга в текущей рабочей области. Когда появится сообщение **Закрепление на панели мониторинга**, выберите **Перейти к панели мониторинга**. Если будет предложено сохранить отчет, выберите **Сохранить**.
   
     ![](media/service-dashboard-create/power-bi-pin-success.png)
6. Power BI откроет новую панель мониторинга, и вы увидите одну плитку — это визуализация, которую мы только что закрепили. 
   
   ![](media/service-dashboard-create/power-bi-pinned.png)
7. Чтобы вернуться к отчету, щелкните плитку. Закрепите еще несколько плиток на новой панели мониторинга. В этот раз, когда отобразится окно **Закрепление на панели мониторинга**, выберите вариант **Существующая панель мониторинга**.  
   
   ![](media/service-dashboard-create/power-bi-existing-dashboard.png)

Поздравляем с созданием первой панели мониторинга! Теперь, когда у вас есть панель мониторинга, вы можете выполнять разные операции.  Попробуйте выполнить одно из предложенных ниже **действий** или запустите воспроизведение и продолжайте самостоятельное изучение материала.   

## <a name="next-steps"></a>Дальнейшие действия
* [Изменение размеров и перемещение плиток](service-dashboard-edit-tile.md)
* [Все о плитках панелей мониторинга](service-dashboard-tiles.md)
* [Создание и распространение приложения в Power BI](service-create-distribute-apps.md)
* [Power BI — основные понятия](service-basic-concepts.md)
* [Панели мониторинга в Power BI](service-dashboards.md)
* [Советы по созданию эффективной панели мониторинга Power BI](service-dashboards-design-tips.md)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

