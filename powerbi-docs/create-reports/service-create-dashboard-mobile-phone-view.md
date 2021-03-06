---
title: Оптимизация панели мониторинга для мобильных телефонов — Power BI
description: Узнайте, как создать настраиваемое представление для панели мониторинга в Power BI для ее просмотра на мобильных устройствах.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 04/18/2019
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: bc1c9987205e86ee9a123bf8ba9afd567c59ff52
ms.sourcegitcommit: e8ed3d120699911b0f2e508dc20bd6a9b5f00580
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2020
ms.locfileid: "86264721"
---
# <a name="optimize-a-dashboard-for-mobile-phones---power-bi"></a>Оптимизация панели мониторинга для мобильных телефонов — Power BI 
Когда вы просматриваете панели мониторинга в книжной ориентации на телефоне, плитки отображаются одна за другой и имеют одинаковый размер. В службе Power BI можно создать настраиваемое представление для панели мониторинга, в частности, для ее просмотра в книжной ориентации на телефонах. Даже если вы создали представление для телефонов, при повороте телефона набок вы увидите панель мониторинга так, как она отображается в службе.

Ищете информацию о просмотре панелей мониторинга на мобильном устройстве? Ознакомьтесь с этим кратким руководством по [просмотру панелей мониторинга и отчетов в мобильных приложениях Power BI](../consumer/mobile/mobile-apps-quickstart-view-dashboard-report.md).

> [!NOTE]
> По мере изменения представления для телефона все пользователи, просматривающие вашу панель на своих устройствах, смогут отслеживать ваши изменения в режиме реального времени. Например, если вы открепите все плитки в представлении панели для телефона, они внезапно пропадут при ее просмотре на экране телефона. 
> 
> 

## <a name="create-a-phone-view-of-a-dashboard"></a>Создание представления панели мониторинга для телефонов
1. Откройте панель мониторинга в службе Power BI.
2. Нажмите стрелку рядом с элементом **Веб-представление** в правом верхнем углу и выберите параметр **Представление телефона**.

    ![Снимок экрана: раскрывающееся меню "Веб-представление" со стрелкой, указывающей на "Представление телефона"](media/service-create-dashboard-mobile-phone-view/power-bi-service-phone-view-dashboard.png)

    Если вы не являетесь владельцем панели мониторинга, вы не увидите этот параметр.

    ![Снимок экрана: панель мониторинга телефона с параметром "Изменить представление" для открепления, изменения размера и переупорядочивания плиток в соответствии с представлением телефона](media/service-create-dashboard-mobile-phone-view/power-bi-mobile-edit-phone-view-canvas.png)

    Откроется редактор представления панели для телефона. В нем вы можете откреплять плитки, менять их размер и порядок так, чтобы панель выглядела оптимальным образом на экране телефона. Веб-версия панели мониторинга при этом не изменится.


1. Чтобы перетащить или открепить плитку либо изменить ее размер, выберите ее. По мере перетаскивания плитки остальные плитки отходят в сторону.
   
    ![Снимок экрана: плитки телефона с выбранной плиткой для перетаскивания, изменения размера или открепления](media/service-create-dashboard-mobile-phone-view/power-bi-unpin-tile-phone-dashboard.png)
   
    Открепленные плитки можно найти в области открепленных плиток (они остаются там, пока вы снова не добавите их на панель).
   
    ![Снимок экрана: панель мониторинга телефона с плитками в области "Открепленные плитки"](media/service-create-dashboard-mobile-phone-view/power-bi-mobile-edit-phone-view-post-edit.png)
2. Если вы решите отменить изменения, щелкните **Сбросить плитки**, чтобы восстановить их исходный размер и порядок.
   
    ![Снимок экрана: область "Открепленные плитки" со стрелкой, указывающей на элемент "Сбросить плитки"](media/service-create-dashboard-mobile-phone-view/power-bi-service-phone-view-reset-tiles.png)
   
    При запуске редактора представления для телефона в Power BI размер и форма плиток на телефоне немного меняются. Следовательно, чтобы вернуть панель мониторинга в то состояние, в котором она была до запуска редактора, воспользуйтесь командой **Сбросить плитки**.
3. Настроив представление панели для телефона, нажмите стрелку рядом с элементом **Представление телефона** в правом верхнем углу и выберите параметр **Веб-представление**.
   
    Power BI автоматически сохраняет макет телефона.

## <a name="next-steps"></a>Дальнейшие действия
* [Создание отчетов, оптимизированных для мобильных приложений Power BI](desktop-create-phone-report.md)
* [Оптимизация визуальных элементов для любого размера](../visuals/power-bi-report-visualizations.md)
* Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
