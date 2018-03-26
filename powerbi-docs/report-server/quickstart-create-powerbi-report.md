---
title: Краткое руководство по созданию отчета Power BI для сервера отчетов Power BI
description: Узнайте, как создать отчет Power BI для сервера отчетов Power BI за несколько простых шагов.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 3/19/2018
ms.author: maggies
ms.openlocfilehash: 5295a62897c740872480b905f3aef4af37ca0942
ms.sourcegitcommit: 93e7362fc47319959b6992dfd037effdf831d010
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2018
---
# <a name="quickstart-create-a-power-bi-report-for-power-bi-report-server"></a>Краткое руководство по созданию отчета Power BI для сервера отчетов Power BI
Отчеты Power BI можно хранить и администрировать локально на веб-портале Сервера отчетов Power BI так же, как и в облачной службе Power BI (https://powerbi.com). Вы можете создавать и редактировать отчеты в приложении Power BI Desktop, а затем публиковать их на веб-портале. Затем можно сообщить читателям в вашей организации о том, что эти отчеты можно просматривать в браузере или мобильном приложении Power BI на мобильных устройствах.

![Отчет Power BI на веб-портале](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

Ниже описаны четыре шага, с помощью которых можно приступить к работе.

## <a name="step-1-install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Шаг 1. Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI

Если вы уже создавали отчеты Power BI в приложении Power BI Desktop, то вы практически готовы создавать отчеты Power BI для сервера отчетов Power BI. Рекомендуется установить версию Power BI Desktop, оптимизированную для сервера отчетов Power BI, так как это обеспечит постоянную синхронизацию сервера с приложением. Обе версии Power BI Desktop можно установить на одном компьютере.

1. На веб-портале сервера отчетов последовательно выберите **Загрузка** > **Power BI Desktop**.

    ![Скачивание Power BI Desktop из веб-портала](media/quickstart-create-powerbi-report/report-server-download-web-portal.png)

    Вы также можете перейти непосредственно к приложению [Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=56723) (март 2018 г.), оптимизированному для решения Сервера отчетов Power BI, в Центре загрузки Майкрософт.

2. На странице Центра загрузки нажмите кнопку **Скачать**.

3. В зависимости от компьютера выберите файл:

    - **PBIDesktopRS.msi** (32-разрядная версия);

    - **PBIDesktopRS_x64.msi** (64-разрядная версия).

4. Скачав установщик, запустите мастер установки Power BI Desktop (март 2018 г.).

2. На завершающем этапе процесса установки выберите параметр **Start Power BI Desktop now** (Запустить Power BI Desktop).
   
    После автоматического запуска приложения вы будете готовы к работе. Если в строке заголовка отображается Power BI Desktop (март 2018 г.), вы установили правильную версию.

    ![Версия Power BI Desktop (март 2018 г.)](media/quickstart-create-powerbi-report/report-server-desktop-october-2017-version.png)

3. Если вы не знакомы с Power BI Desktop, просмотрите видеоролики на экране приветствия.
   
    ![Начальный экран Power BI Desktop](media/quickstart-create-powerbi-report/report-server-powerbi-desktop-start.png)

## <a name="step-2-select-a-data-source"></a>Шаг 2. Выбор источника данных
Вы можете подключаться к разным типам источников данных. Узнайте больше о [подключении к источникам данных](connect-data-sources.md).

1. На экране приветствия выберите **Get Data** (Получить данные).
   
    На вкладке **Home** (Главная) выберите пункт **Get Data** (Получить данные).
2. Выберите источник данных (в этом примере **Analysis Services**).
   
    ![Выбор источника данных](media/quickstart-create-powerbi-report/report-server-get-data-ssas.png)
3. Заполните поле **Server** (Сервер) и при необходимости поле **Database** (База данных). Убедитесь, что установлен флажок **Connect live** (Подключение в реальном времени) и нажмите кнопку **ОK**.
   
    ![Имя сервера](media/quickstart-create-powerbi-report/report-server-ssas-server-name.png)
4. Выберите сервер отчетов, на котором вы будете хранить отчеты.
   
    ![Выбор сервера отчетов](media/quickstart-create-powerbi-report/report-server-select-server.png)

## <a name="step-3-design-your-report"></a>Шаг 3. Создание отчета
Здесь начинается самое интересное: нужно создать визуальные элементы, иллюстрирующие ваши данные.

Например, можно создать воронкообразную диаграмму на основе значений, отображающих годовой доход пользователей и групп.

![Создание отчета](media/quickstart-create-powerbi-report/report-server-create-funnel.png)

1. В разделе **Visualizations** (Визуализации) выберите элемент **Funnel chart** (Воронкообразная диаграмма).
2. Перетащите поле для подсчета в область **Values** (Значения). Если это не числовое поле, Power BI Desktop автоматически установит для него значение *Count of* (Количество).
3. Перетащите поле в группу в область **Group** (Группа).

См. дополнительные сведения о [создании отчетов Power BI](../desktop-report-view.md).

## <a name="step-4-save-your-report-to-the-report-server"></a>Шаг 4. Сохранение отчета на сервере отчетов
Когда отчет будет готов, вы сможете сохранить его на сервере отчетов Power BI, который вы выбрали на шаге 2.

1. В меню **Файл** выберите пункт **Сохранить как** > **Сервер отчетов Power BI**.
   
    ![Сохранение на сервере отчетов](media/quickstart-create-powerbi-report/report-server-save-as-powerbi-report-server.png)
2. Теперь вы можете просмотреть отчет на веб-портале.
   
    ![Просмотр отчета в веб-портале](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

## <a name="considerations-and-limitations"></a>Рекомендации и ограничения
Отчеты на Сервере отчетов Power BI и в службе Power BI (http://powerbi.com) работают почти одинаково, но некоторые функции все же различаются).

### <a name="in-a-browser"></a>В браузере
Отчеты на сервере отчетов Power BI поддерживают все визуализации, в том числе:

* Пользовательские визуальные элементы

Отчеты на сервере отчетов Power BI не поддерживают:

* визуальные элементы R;
* карты ArcGIS;
* строки навигации;
* Функции предварительной версии Power BI Desktop

### <a name="in-the-power-bi-mobile-apps"></a>В мобильных приложениях Power BI
Отчеты на сервере отчетов Power BI поддерживают все функциональные возможности, доступные в [мобильных приложениях Power BI](../mobile-apps-for-mobile-devices.md), в том числе:

* [Макет мобильного отчета](../desktop-create-phone-report.md). Вы можете оптимизировать отчет для мобильных приложений Power BI. В отчетах, оптимизированных для мобильных телефонов, есть специальный значок ![Значок "Макет отчета для телефона"](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-icon.png) и макет.
  
    ![Отчет, оптимизированный для телефонов](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-report.png)

В мобильных приложениях Power BI отчеты на сервере отчетов Power BI не поддерживают:

* визуальные элементы R;
* карты ArcGIS;
* Пользовательские визуальные элементы
* строки навигации;
* географическую фильтрацию и штрихкоды.

## <a name="next-steps"></a>Дальнейшие действия
### <a name="power-bi-desktop"></a>Power BI Desktop
Существует много отличных ресурсов для создания отчетов в Power BI Desktop. Советуем начать с этих ссылок:

* [Начало работы с Power BI Desktop](../desktop-getting-started.md)
* Интерактивное обучение. [Начало работы с Power BI Desktop](../guided-learning/gettingdata.yml#step-2)


### <a name="power-bi-report-server"></a>Power BI Report Server
* [Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI](install-powerbi-desktop.md)  
* [Руководство для пользователя сервера отчетов Power BI](user-handbook-overview.md)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
