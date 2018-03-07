---
title: "Оптимизация визуальных элементов Power BI для любого размера"
description: "Узнайте, как оптимизировать визуальные элементы в Power BI Desktop и службе Power BI для мобильных приложений Power BI."
services: powerbi
documentationcenter: 
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 4c80048213b20365102bcb9c6842c342d8b9052b
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2018
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>Оптимизация визуальных элементов Power BI для любого размера
На панели мониторинга или в отчете можно настроить *адаптивность* визуальных элементов, чтобы они динамически изменялись, отображая как можно больше данных независимо от размера экрана.

При изменении размера визуального элемента Power BI определяет приоритеты в представлении данных — например, автоматически удаляет отступы и перемещает условные обозначения наверх, чтобы даже при уменьшении визуальный элемент оставался информативным. Адаптивность особенно важна для визуальных элементов, используемых в мобильном приложении Power BI на телефонах.

![Изменение размера адаптивного визуального элемента](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

Вы можете включить адаптивность для любого визуального элемента с осями X и Y или срезами.

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>Включение адаптивности в Power BI Desktop
1. В Power BI Desktop на вкладке **Представление** выберите **Макет рабочего стола**.
   
    ![Значок "Макет рабочего стола"](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. Выберите визуальный элемент, а затем в области **Визуализации** выберите раздел **Формат**.
3. Разверните раздел **Общие** и установите переключатель **Адаптивность (предварительная версия)** в положение **Вкл.**
   
    ![Параметр "Адаптивность" включен](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Теперь, когда вы добавите этот визуальный элемент в [отчет, оптимизированный для телефона](desktop-create-phone-report.md), его размер будет плавно изменяться.

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>Включение адаптивности в службе Power BI
Включите адаптивность для визуального элемента отчета в службе Power BI. Для этого необходимо иметь права на изменение отчета.

1. В отчете в службе Power BI ([https://powerbi.com](https://powerbi.com)) выберите **Изменить отчет**.
2. Выберите визуальный элемент, а затем в области **Визуализации** выберите раздел **Формат**.
3. Разверните раздел **Общие** и установите переключатель **Адаптивность (предварительная версия)** в положение **Вкл.**
   
    ![Параметр "Адаптивность" включен](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     Теперь, когда вы добавите этот визуальный элемент в [представление для телефона на панели мониторинга](service-create-dashboard-mobile-phone-view.md), его размер будет плавно изменяться.

## <a name="next-steps"></a>Дальнейшие действия
* [Создание отчетов, оптимизированных для мобильных приложений Power BI](desktop-create-phone-report.md)
* [Создание представления панели мониторинга для телефонов в Power BI](service-create-dashboard-mobile-phone-view.md)
* [Просмотр отчетов Power BI, оптимизированных для телефона](mobile-apps-view-phone-report.md)
* Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

