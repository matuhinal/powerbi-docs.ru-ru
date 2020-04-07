---
title: Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI
description: Узнайте, как установить приложение Power BI Desktop, оптимизированное для сервера отчетов Power BI
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 02/13/2020
ms.openlocfilehash: dfb6c313e989514da2aa04facd6c6136a0eadc1a
ms.sourcegitcommit: 444f7fe5068841ede2a366d60c79dcc9420772d4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2020
ms.locfileid: "80404183"
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI

Чтобы создавать отчеты Power BI для сервера отчетов Power BI, скачайте и установите версию Power BI Desktop, которая оптимизирована для этого сервера. Этот выпуск отличается от выпуска Power BI Desktop, который используется в службе Power BI. Например, версия Power BI Desktop для службы Power BI включает функции предварительной версии, которые будут включены в состав сервера отчетов Power BI только после выпуска общедоступной версии. Использование этого выпуска позволяет обеспечить взаимодействие между сервером отчетов и известной версией отчетов и модели. 

Мы рады сообщить, что Power BI Desktop и приложение Power BI Desktop, оптимизированное для Сервера отчетов Power BI, можно устанавливать параллельно, на одном компьютере.

## <a name="download-and-install-power-bi-desktop"></a>Загрузка и установка Power BI Desktop

Самый простой способ скачать последнюю версию приложения Power BI Desktop, оптимизированного для решения "Сервер отчетов Power BI", — запустить его из веб-портала сервера отчетов.

1. На веб-портале сервера отчетов последовательно выберите **Загрузка** > **Power BI Desktop**.

    ![Скачивание Power BI Desktop из веб-портала](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Либо перейдите на домашнюю страницу [Сервера отчетов Power BI](https://powerbi.microsoft.com/report-server/) и выберите **Расширенные параметры загрузки**.

2. На странице центра загрузки выберите язык и нажмите кнопку **Скачать**.

3. В зависимости от компьютера выберите файл: 

    - **PBIDesktopRS.msi** (32-разрядная версия);
    - **PBIDesktopRS_x64.msi** (64-разрядная версия).

1. Когда вы скачаете установщик, запустите мастер установки Power BI Desktop (сентябрь 2019 г.).

2. На завершающем этапе процесса установки выберите параметр **Запустить Power BI Desktop**.

    После автоматического запуска приложения вы будете готовы к работе.

## <a name="verify-youre-using-the-correct-version"></a>Проверка используемой версии
Проверить используемую версию Power BI Desktop нетрудно: Посмотрите на экран запуска или заголовок окна Power BI Desktop. Если в строке заголовка вы видите **Power BI Desktop (сентябрь 2019 г.)** , вы установили правильную версию. Кроме того, цвета логотипа Power BI изменены на обратные: желтый на черном вместо черного на желтом.

![Power BI Desktop, сентябрь 2019 г.](media/install-powerbi-desktop/power-bi-report-server-desktop-sept-2019.png)

В строке заголовка версии Power BI Desktop для службы Power BI не указаны месяц и год выпуска.

## <a name="file-extension-association"></a>Сопоставление расширения файла
Если Power BI Desktop и приложение Power BI Desktop, оптимизированное для Сервера отчетов Power BI, установлены на одном компьютере, то с файлами с расширением PBIX будет связан тот экземпляр Power BI Desktop, который был установлен последним. Поэтому при двойном щелчке по PBIX-файлу будет запущен последний установленный экземпляр Power BI Desktop.

Если у вас уже есть приложение Power BI Desktop, и вы устанавливаете приложение Power BI Desktop, оптимизированное для Сервера отчетов Power BI, все PBIX-файлы будут по умолчанию открываться в приложении Power BI Desktop, оптимизированном для Сервера отчетов Power BI. Если необходимо, чтобы при открытии PBIX-файлов по умолчанию запускалось приложение Power BI Desktop, переустановите [Power BI Desktop из Microsoft Store](https://aka.ms/pbidesktopstore).

Всегда можно открыть ту версию Power BI Desktop, которую нужно использовать первой, а затем открыть файл в приложении Power BI Desktop.

При редактировании отчета Power BI на Сервере отчетов Power BI или при создании отчета Power BI на веб-портале всегда будет открываться правильная версия Power BI Desktop.

## <a name="considerations-and-limitations"></a>Рекомендации и ограничения

Отчеты на сервере отчетов Power BI и в службе Power BI (`https://app.powerbi.com`), а также в мобильных приложениях Power BI работают почти одинаково, но некоторые функции все же различаются.

### <a name="selecting-a-language"></a>Выбор языка

Для версии Power BI Desktop, оптимизированной для сервера отчетов Power BI, выбор языка осуществляется при установке приложения. Вы не можете изменить сделанный выбор, однако при необходимости можно установить версию на другом языке.

### <a name="report-visuals-in-a-browser"></a>Визуальные элементы отчетов в браузере

Отчеты на сервере отчетов Power BI поддерживают почти все визуализации, в том числе визуальные элементы Power BI. Отчеты на сервере отчетов Power BI не поддерживают:

* визуальные элементы R;
* карты ArcGIS;
* строки навигации;
* Функции предварительной версии Power BI Desktop

### <a name="reports-in-the-power-bi-mobile-apps"></a>Отчеты в мобильных приложениях Power BI

Отчеты на сервере отчетов Power BI поддерживают все функциональные возможности, доступные в [мобильных приложениях Power BI](../consumer/mobile/mobile-apps-for-mobile-devices.md), в том числе:

* [Макет отчета для мобильной версии](../desktop-create-phone-report.md). Вы можете оптимизировать отчет для мобильных приложений Power BI. На мобильных устройствах у оптимизированных отчетов есть специальный значок ![Макет отчета для телефона](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-icon.png) и макет.
  
    ![Отчет, оптимизированный для телефонов](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-report.png)

В мобильных приложениях Power BI отчеты на сервере отчетов Power BI не поддерживают:

* Визуальные элементы R
* карты ArcGIS;
* Визуальные элементы Power BI
* строки навигации;
* географическую фильтрацию и штрихкоды.

### <a name="custom-security"></a>Настраиваемая безопасность

Приложение Power BI Desktop, оптимизированное для сервера отчетов Power BI, не поддерживает настраиваемую безопасность. Если в сервере отчетов Power BI включен настраиваемый модуль безопасности, вы не сможете сохранить отчет Power BI из приложения Power BI Desktop (оптимизированного для сервера отчетов Power BI) на экземпляре сервера отчетов Power BI. Необходимо вместо этого сохранить PBIX-файл отчета из Power BI Desktop и отправить его на сайт портала сервера отчетов Power BI.

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>Power BI Desktop для более ранних версий Сервера отчетов Power BI

Если вы используете более раннюю версию сервера отчетов, нужна подходящая версия Power BI Desktop. Ниже приведена ссылка для скачивания предыдущей версии.

- Microsoft Power BI Desktop ([оптимизировано для сервера отчетов Power BI, сентябрь 2019 г.](https://go.microsoft.com/fwlink/?linkid=2103723))

## <a name="next-steps"></a>Дальнейшие действия

Теперь, когда приложение Power BI Desktop установлено, можно приступить к созданию отчетов Power BI.

[Создание отчета Power BI для Сервера отчетов Power BI](quickstart-create-powerbi-report.md)  
[Что такое Сервер отчетов Power BI?](get-started.md)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
