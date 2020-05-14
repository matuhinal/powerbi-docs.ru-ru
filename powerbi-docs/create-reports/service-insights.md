---
title: Автоматическое создание аналитических сведений с помощью Power BI
description: Узнайте, как получить полезные сведения о наборах данных и плитках панели мониторинга.
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: et_MLSL2sA8
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/06/2019
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 4178d9cc5ce6f8e671c0d996bb64ee9a1389acdb
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83306607"
---
# <a name="generate-data-insights-automatically-with-power-bi"></a>Автоматическое создание аналитических сведений с помощью Power BI
Вы получили новый набор данных и не знаете, с чего начать?  Вам нужно быстро создать панель мониторинга?  Хотите найти полезные данные, которые вы могли пропустить?

Краткая аналитика позволяет получить интересные интерактивные визуализации на основе имеющихся данных. Краткую аналитику можно выполнить для всего набора данных (краткая аналитика) или для отдельной плитки панели мониторинга (краткая аналитика с заданной областью). Вы даже можете анализировать полученные результаты.

> [!NOTE]
> Аналитика не работает с DirectQuery — только с данными, отправленными в Power BI.
> 

Функция аналитики основана на постоянно пополняемом [наборе усовершенствованных аналитических алгоритмов](../consumer/end-user-insight-types.md), разработанных при сотрудничестве с подразделением Microsoft Research, которые мы продолжаем использовать, чтобы все больше людей могли анализировать данные новыми удобными способами.

## <a name="run-quick-insights-on-a-dataset"></a>Запуск краткой аналитики для набора данных
Узнайте, как Аманда выполняет аналитику для набора данных, открывает аналитику в режиме фокусировки, закрепляет один из результатов в виде плитки на своей панели мониторинга, а затем получает результаты аналитики для панели мониторинга.

<iframe width="560" height="315" src="https://www.youtube.com/embed/et_MLSL2sA8" frameborder="0" allowfullscreen></iframe>


Теперь ваша очередь. Узнайте, как работает аналитика данных, на примере [Анализ качества поставщика](sample-supplier-quality.md).

1. На вкладке **Наборы данных** щелкните **Дополнительные параметры** (…) и выберите **Получить краткую аналитику**.
   
    ![вкладка "Наборы данных"](media/service-insights/power-bi-ellipses.png)
   
    ![Меню с многоточием](media/service-insights/power-bi-tab.png)
2. Для поиска тенденций в наборе данных Power BI использует [различные алгоритмы](../consumer/end-user-insight-types.md).
   
    ![Диалоговое окно поиска ценных сведений](media/service-insights/pbi_autoinsightssearching.png)
3. Анализ занимает несколько секунд.  Нажмите кнопку **Просмотреть аналитику**, чтобы отобразить визуализации.
   
    ![Сообщение об успешном импорте](media/service-insights/pbi_autoinsightsuccess.png)
   
    > [!NOTE]
    > Для некоторых данных аналитические сведения не формируются, так как информация не является статистически значимой.  Дополнительные сведения см. в статье [Оптимизация данных для быстрого анализа данных в Power BI](service-insights-optimize.md).
    > 
    
4. Визуализация отображается на специальном холсте **краткой аналитики**, который может вмещать до 32 отдельных карт анализа. Каждая карта имеет диаграмму или график, а также краткое описание.
   
    ![Холст краткой аналитики](media/service-insights/power-bi-insights.png)

## <a name="interact-with-the-insight-cards"></a>Работа с карточками аналитики

1. Наведите указатель мыши на карту и выберите значок булавки, чтобы добавить визуализацию на панель мониторинга.

2. Наведите указатель мыши на карточку, щелкните **Дополнительные параметры** (…) и выберите команду **Просмотреть аналитику**. 

    Экран аналитики открывается в режиме фокусировки.
   
    ![Режим фокусировки для аналитики](media/service-insights/power-bi-insight-focus.png)
3. В режиме фокусировки можно выполнять следующие задачи.
   
   * Фильтровать визуализации. Если панель **Фильтры** еще не открыта, разверните ее, выбрав стрелку в правой части окна.

       ![Развернутое меню "Фильтры" аналитики](media/service-insights/power-bi-insights-filter-new.png)
   * Закрепите карточку аналитики на панели мониторинга, выбрав **Закрепить визуальный элемент**.
   * Запустите аналитику для самой карточки, что часто называют *аналитикой с заданной областью*. В правом верхнем углу щелкните значок лампочки ![значок получения аналитики](media/service-insights/power-bi-bulb-icon.png) или нажмите **Получить аналитику**.
     
       ![Значок "Получить аналитику"](media/service-insights/pbi-autoinsights-tile.png)
     
     Результаты аналитики отображаются слева, а справа отображаются новые карточки, основанные только на данных этой аналитики.
     
       ![Аналитика на данных аналитики](media/service-insights/power-bi-insights-on-insights-new.png)
4. Чтобы вернуться к первоначальному холсту аналитики, щелкните в верхнем левом углу **Выйти из режима фокусировки**.

## <a name="run-insights-on-a-dashboard-tile"></a>Запуск аналитики для плитки панели мониторинга
Вместо поиска аналитических данных по всему набору данных сузьте область поиска, чтобы выполнить аналитику с заданной областью для данных, используемых для создания отдельной плитки панели мониторинга. 

1. Откройте панель мониторинга.
2. Наведите указатель мыши на плитку. Щелкните **Дополнительные параметры** (…) и выберите команду **Просмотреть аналитические сведения**. Плитка откроется в [режиме фокусировки](../consumer/end-user-focus.md) с карточками аналитики, которые отображаются с правой стороны.    
   
    ![Режим фокусировки](media/service-insights/pbi-insights-tile.png)    
3. Вас заинтересовали эти сведения? Выберите карту анализа, чтобы ознакомиться с ними детально. Данные выбранного анализа отображаются слева, а справа отображаются новые карты анализа, основанные только на данных этого анализа.    
4. Продолжайте анализировать данные, а при нахождении интересных сведений закрепите их на панели мониторинга, выбрав **Закрепить визуальный элемент** в правом верхнем углу.

## <a name="next-steps"></a>Дальнейшие действия
- Если у вас есть набор данных, [оптимизируйте его для краткой аналитики](service-insights-optimize.md).
- См. дополнительные сведения о [доступных типах краткой аналитики](../consumer/end-user-insight-types.md).

У вас имеются и другие вопросы? [Ответы на них см. в сообществе Power BI](https://community.powerbi.com/).