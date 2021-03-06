---
title: Запуск и просмотр полезных сведений о плитках панели мониторинга
description: Узнайте, как получить полезные сведения о плитках панели мониторинга с помощью Power BI.
author: mihart
ms.reviewer: mihart
featuredvideoid: et_MLSL2sA8
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 09/09/2020
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 21bccbd11f8d2060b648e22c8ed8aa9471c820f0
ms.sourcegitcommit: 002c140d0eae3137a137e9a855486af6c55ad957
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2020
ms.locfileid: "89642517"
---
# <a name="view-data-insights-on-dashboard-tiles-with-power-bi"></a>Просмотр полезных сведений о плитках панели мониторинга с помощью Power BI

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

Каждая [плитка](end-user-tiles.md) визуального элемента на панели мониторинга предоставляет возможности исследования данных. Щелкнув любую плитку, вы перейдете в отчет или [Вопросы и ответы](end-user-q-and-a.md), где сможете фильтровать и сортировать наборы данных, использованные для отчета. Когда вы исследуете аналитические сведения, в Power BI выполняется поиск данных.

![Режим меню с многоточием с параметром "Просмотреть аналитику"](./media/end-user-insights/power-bi-insight.png)

Аналитика позволяет получить интересные интерактивные визуальные элементы на основе имеющихся данных. Аналитику можно выполнить для отдельной плитки панели мониторинга или даже для результатов предыдущей аналитики.

Функция аналитики основана на постоянно пополняемом [наборе усовершенствованных аналитических алгоритмов](end-user-insight-types.md), разработанных при сотрудничестве с подразделением Microsoft Research, которые мы продолжаем использовать, чтобы все больше людей могли анализировать данные новыми удобными способами.

## <a name="run-insights-on-a-dashboard-tile"></a>Запуск аналитики для плитки панели мониторинга
Когда вы выполняете аналитику для плитки панели мониторинга, Power BI использует для поиска только те данные, которые использовались для создания этой конкретной плитки. 

1. [Откройте панель мониторинга](end-user-dashboards.md).
2. Наведите указатель мыши на плитку. Щелкните **Дополнительные параметры** (…) и выберите команду **Просмотреть аналитические сведения**. 

    ![Снимок экрана: выбор многоточия и раскрывающийся список](./media/end-user-insights/power-bi-hover.png)


3. Плитка откроется в [режиме фокусировки](end-user-focus.md) с карточками аналитики, которые отображаются с правой стороны.    
   
    ![Режим фокусировки](./media/end-user-insights/power-bi-insights-tiles.png)    
4. Вас заинтересовали эти сведения? Выберите карту анализа, чтобы ознакомиться с ними детально. Данные выбранного анализа отображаются слева, а справа отображаются новые карты анализа, основанные только на данных этого анализа.    

 ## <a name="interact-with-the-insight-cards"></a>Работа с карточками аналитики
Получив аналитику по одной плитке, продолжим изучение.

   * Фильтрация визуальных элементов холста.  Чтобы отобразились фильтры, в правом верхнем углу экрана выберите стрелку для развертывания панели "Фильтры".

      ![Развернутое меню "Фильтры" аналитики](./media/end-user-insights/power-bi-filter.png)
   
   * Запустите аналитику для самой карточки аналитики. Часто это называют **связанными аналитическими сведениями**. Выберите карточку аналитики, чтобы сделать ее активной. Она будет перемещена в левую часть холста отчета, а новые карточки, основанные исключительно на данных в этом виде, будут отображаться справа.
   
      ![Развернутое меню "Фильтры" связанной аналитики](./media/end-user-insights/power-bi-insights-card.png)
   
     
Чтобы вернуться к отчету, щелкните в верхнем левом углу действие **Выйти из режима фокусировки**.

## <a name="considerations-and-troubleshooting"></a>Рекомендации и устранение неполадок
- **Просмотр аналитики** работает не со всеми типами плиток для панели мониторинга. Например, он недоступен для настраиваемых визуальных элементов Power BI.<!--[Power BI visuals](end-user-custom-visuals.md)-->


## <a name="next-steps"></a>Дальнейшие действия

Примените аналитику к визуальным элементам отчета [с помощью функции анализа](end-user-analyze-visuals.md)  .  
Дополнительные сведения о доступных типах аналитики см. [здесь](end-user-insight-types.md).

