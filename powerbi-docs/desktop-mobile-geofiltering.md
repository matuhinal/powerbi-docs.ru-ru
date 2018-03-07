---
title: "Настройка географической фильтрации в Power BI Desktop для мобильных приложений"
description: "Если в модели в Power BI Desktop настроена географическая фильтрация, вы можете автоматически фильтровать данные с учетом своего местоположения в мобильных приложениях Power BI."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/16/2018
ms.author: maggies
LocalizationGroup: Model your data
ms.openlocfilehash: 5fa7e303c51ac4e4a5ca0a949dabfafe3c166e74
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2018
---
# <a name="set-geographic-filters-in-power-bi-desktop-for-the-mobile-apps"></a>Настройка географической фильтрации в Power BI Desktop для мобильных приложений
В Power BI Desktop можно [задать для столбца географическую категорию данных](desktop-data-categorization.md), чтобы приложение Power BI Desktop понимало, как интерпретировать соответствующие значения в визуальных элементах отчета. Кроме того, при просмотре соответствующего отчета мобильное приложение Power BI автоматически предлагает фильтры с учетом местоположения пользователя. 

Например, предположим, что вы — директор по продажам, который ездит в командировки для переговоров с клиентами, и вам бывает нужно быстро отфильтровать данные по общему объему продаж и выручки для клиента, с которым вы планируете встретиться. Вы хотите выбрать данные для своего текущего местоположения (например, по региону, городу или фактическому адресу). Потом, если у вас останется время, вы можете заглянуть и к другим клиентам, которые расположены поблизости. Вы можете [отфильтровать отчет по своему местоположению, чтобы найти соответствующих клиентов](mobile-apps-geographic-filtering.md).

> [!NOTE]
> В мобильном приложении фильтровать данные по географическому расположению можно только в том случае, если названия географических объектов в отчете указаны на английском языке (например, New York City или Germany).
> 
> 

## <a name="identify-geographic-data-in-your-report"></a>Определение географических данных в отчете
1. В Power BI Desktop перейдите в представление данных. ![Значок представления данных](media/desktop-mobile-geofiltering/pbi_desktop_data_icon.png).
2. Выберите столбец, содержащий географические данные, например "Город".
   
    ![Столбец "Город"](media/desktop-mobile-geofiltering/power-bi-desktop-geo-column.png)
3. На вкладке **Моделирование** выберите **Категория данных** и укажите подходящую категорию (в нашем примере — **Город**).
   
    ![Поле "Категория данных"](media/desktop-mobile-geofiltering/power-bi-desktop-geo-category.png)
4. Затем вы можете задать географическую категорию и для других полей в модели. 
   
   > [!NOTE]
   > Для каждой категории данных в модели можно выбрать несколько столбцов, однако в этом случае модель не сможет фильтровать данные по географическому признаку в мобильном приложении Power BI. Для использования географической фильтрации в мобильных приложениях выберите для каждой категории данных не больше одного столбца (например, один столбец **Город**, один — **Область, республика, край**, а один — **Страна**). 
   > 
   > 

## <a name="create-visuals-with-your-geographic-data"></a>Создание визуальных элементов с помощью географических данных
1. Перейдите в представление отчетов ![Значок представления отчетов](media/desktop-mobile-geofiltering/power-bi-desktop-report-icon.png)и создайте визуальные элементы, использующие географические поля в данных. 
   
    ![Отчет с картой](media/desktop-mobile-geofiltering/power-bi-desktop-geo-report.png)
   
    В этом примере модель также содержит вычисляемый столбец, в котором объединены город и штат. Сведения о создании вычисляемых столбцов в Power BI Desktop см. [здесь](desktop-calculated-columns.md).
   
    ![Поле City + State (Город + штат)](media/desktop-mobile-geofiltering/power-bi-desktop-city-state-column.png)
2. Опубликуйте отчет в службе Power BI.

## <a name="view-the-report-in-power-bi-mobile-app"></a>Просмотр отчетов в мобильном приложении Power BI
1. Откройте отчет в любом из [мобильных приложений Power BI](mobile-apps-for-mobile-devices.md).
2. Если вы находитесь в каком-либо географическом расположении, данные о котором содержатся в отчете, программа может отфильтровать их автоматически.
   
    ![Фильтр по расположению в мобильном приложении](media/desktop-mobile-geofiltering/power-bi-mobile-geo-map-set-filter.png)

Дополнительные сведения о [фильтровании отчетов по расположению в мобильных приложениях Power BI](mobile-apps-geographic-filtering.md).

## <a name="next-steps"></a>Дальнейшие действия
* [Категоризация данных в Power BI Desktop](desktop-data-categorization.md)  
* У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

