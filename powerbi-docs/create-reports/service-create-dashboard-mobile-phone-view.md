---
title: Оптимизация панели мониторинга для мобильных телефонов — Power BI
description: Узнайте, как создать настраиваемое представление для панели мониторинга в Power BI для ее просмотра на мобильных устройствах.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/18/2019
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 93d94aadb8e7606fd6d55c463a2be88f87e48047
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83314864"
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

    ![](media/service-create-dashboard-mobile-phone-view/power-bi-service-phone-view-dashboard.png)

    Если вы не являетесь владельцем панели мониторинга, вы не увидите этот параметр.

    ![](media/service-create-dashboard-mobile-phone-view/power-bi-mobile-edit-phone-view-canvas.png)

    Откроется редактор представления панели для телефона. В нем вы можете откреплять плитки, менять их размер и порядок так, чтобы панель выглядела оптимальным образом на экране телефона. Веб-версия панели мониторинга при этом не изменится.


1. Чтобы перетащить или открепить плитку либо изменить ее размер, выберите ее. По мере перетаскивания плитки остальные плитки отходят в сторону.
   
    ![](media/service-create-dashboard-mobile-phone-view/power-bi-unpin-tile-phone-dashboard.png)
   
    Открепленные плитки можно найти в области открепленных плиток (они остаются там, пока вы снова не добавите их на панель).
   
    ![](media/service-create-dashboard-mobile-phone-view/power-bi-mobile-edit-phone-view-post-edit.png)
2. Если вы решите отменить изменения, щелкните **Сбросить плитки**, чтобы восстановить их исходный размер и порядок.
   
    ![](media/service-create-dashboard-mobile-phone-view/power-bi-service-phone-view-reset-tiles.png)
   
    При запуске редактора представления для телефона в Power BI размер и форма плиток на телефоне немного меняются. Следовательно, чтобы вернуть панель мониторинга в то состояние, в котором она была до запуска редактора, воспользуйтесь командой **Сбросить плитки**.
3. Настроив представление панели для телефона, нажмите стрелку рядом с элементом **Представление телефона** в правом верхнем углу и выберите параметр **Веб-представление**.
   
    Power BI автоматически сохраняет макет телефона.

## <a name="next-steps"></a>Дальнейшие действия
* [Создание отчетов, оптимизированных для мобильных приложений Power BI](desktop-create-phone-report.md)
* [Оптимизация визуальных элементов для любого размера](../visuals/desktop-create-responsive-visuals.md)
* У вас имеются и другие вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)