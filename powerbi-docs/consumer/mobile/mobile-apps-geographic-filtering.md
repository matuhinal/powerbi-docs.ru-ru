---
title: Фильтрация отчета по географическому расположению в мобильном приложении Power BI
description: Узнайте, как фильтровать данные в отчете по географическому расположению в мобильных приложениях Microsoft Power BI, если владелец отчета настроил геотеги.
author: mshenhav
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 02/09/2018
ms.author: mshenhav
ms.openlocfilehash: 828dcb4aeb8b7c5e69292685470f112a2d85cb71
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "61349584"
---
# <a name="filter-a-report-by-geographic-location-in-the-power-bi-mobile-apps"></a>Фильтрация отчета по географическому расположению в мобильных приложениях Power BI
Область применения:

| ![iPhone](./media/mobile-apps-geographic-filtering/iphone-logo-50-px.png) | ![iPad](./media/mobile-apps-geographic-filtering/ipad-logo-50-px.png) | ![Телефон Android](./media/mobile-apps-geographic-filtering/android-phone-logo-50-px.png) | ![Планшет Android](./media/mobile-apps-geographic-filtering/android-tablet-logo-50-px.png) | ![Планшет Android](./media/mobile-apps-geographic-filtering/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone |iPad |Телефоны под управлением Android |Планшеты Android |Телефоны под управлением Windows 10 |

Отображается ли маленький значок канцелярской кнопки в правом верхнем углу экрана при просмотре отчета Power BI на мобильном устройстве? Если да, этот отчет можно отфильтровать по географическому расположению.

> [!NOTE]
> Фильтровать данные по географическому расположению можно только в том случае, если названия географических объектов в отчете указаны на английском языке (например, New York City или Germany). В отличие от телефонов под управлением Windows 10, планшеты и ПК под управлением Windows 10 не поддерживают фильтрацию по географическому расположению.
> 
> 

## <a name="filter-your-report-by-your-geographic-location"></a>Фильтрация отчета по географическому расположению
1. Откройте отчет в мобильном приложении Power BI на мобильном устройстве.
2. Если отчет содержит географические данные, появится сообщение с запросом на предоставление Power BI доступа к вашему расположению. Нажмите кнопку **Разрешить**, а потом еще раз щелкните **Разрешить**.
3. Коснитесь значка канцелярской кнопки ![Значок канцелярской кнопки](./media/mobile-apps-geographic-filtering/power-bi-mobile-geo-icon.png). Данные можно фильтровать по городу, региону или стране в зависимости от данных в отчете. В фильтре перечислены только те варианты, которые соответствуют вашему текущему местоположению.
   
    ![Фильтр в виде канцелярской кнопки](./media/mobile-apps-geographic-filtering/power-bi-mobile-geo-map-set-filter.png)

## <a name="why-dont-i-see-location-tags-on-a-report"></a>Почему я не вижу в отчете теги расположения?
Чтобы отобразить теги расположения, необходимо выполнить все три условия. 

* Пользователь, создавший отчет в Power BI Desktop, должен [упорядочить по категориям данные о географическом расположении](../../desktop-mobile-geofiltering.md) хотя бы для одного столбца (город, штат, страна или регион).
* Вы находитесь в одном из расположений, данные о котором содержит этот столбец.
* Вы используете один из следующих мобильных устройств:
  * iOS (iPad, iPhone, iPod);
  * телефоны или планшеты под управлением Android;
  * телефоны под управлением Windows 10 (другие устройства под управлением Windows 10, например планшеты и ПК, не поддерживают фильтрацию географических данных).

Дополнительные сведения о настройке фильтрации по географическим объектам в Power BI Desktop см. [здесь](../../desktop-mobile-geofiltering.md).

### <a name="next-steps"></a>Дальнейшие действия
* [Подключение к данным Power BI из реального мира](mobile-apps-data-in-real-world-context.md) с помощью мобильных приложений
* [Категоризация данных в Power BI Desktop](../../desktop-data-categorization.md) 
* У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

