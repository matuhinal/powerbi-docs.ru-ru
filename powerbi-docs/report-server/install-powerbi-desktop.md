---
title: Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI
description: Узнайте, как установить приложение Power BI Desktop, оптимизированное для сервера отчетов Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 09/19/2018
ms.author: maggies
ms.openlocfilehash: 54f49bf28019ba41df7d68e1d5312ee975023859
ms.sourcegitcommit: a739a99e1006834a0f56e387c0bd9d945fb8a76b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "51679071"
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI
Узнайте, как установить приложение Power BI Desktop, оптимизированное для сервера отчетов Power BI.

Чтобы создавать отчеты Power BI для решения "Сервер отчетов Power BI", скачайте и установите приложение Power BI Desktop, оптимизированное для этого решения. Этот выпуск отличается от выпуска Power BI Desktop, который используется в службе Power BI. Например, версия Power BI Desktop для службы Power BI включает функции предварительной версии, которые станут общедоступными после выпуска в версии Сервера отчетов Power BI. Использование этого выпуска позволяет обеспечить взаимодействие между сервером отчетов и известной версией отчетов и модели. 

Мы рады сообщить, что Power BI Desktop и приложение Power BI Desktop, оптимизированное для Сервера отчетов Power BI, можно устанавливать параллельно на одном компьютере.

## <a name="download-and-install-power-bi-desktop"></a>Загрузка и установка Power BI Desktop

Самый простой способ скачать последнюю версию приложения Power BI Desktop, оптимизированного для решения "Сервер отчетов Power BI", — запустить его из веб-портала сервера отчетов.

1. На веб-портале сервера отчетов последовательно выберите **Загрузка** > **Power BI Desktop**.

    ![Скачивание Power BI Desktop из веб-портала](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Вы также можете перейти непосредственно к приложению [Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=57271) (август 2018 г.), оптимизированному для сервера отчетов Power BI, в Центре загрузки Майкрософт.

2. На странице Центра загрузки нажмите кнопку **Скачать**.

3. В зависимости от компьютера выберите файл: 

    - **PBIDesktopRS.msi** (32-разрядная версия);

    - **PBIDesktopRS_x64.msi** (64-разрядная версия).

1. Скачав установщик, запустите мастер установки Power BI Desktop (август 2018 г.).

2. На завершающем этапе процесса установки выберите параметр **Start Power BI Desktop now** (Запустить Power BI Desktop).
   
    После автоматического запуска приложения вы будете готовы к работе.

## <a name="verify-you-are-using-the-correct-version"></a>Проверка используемой версии
Чтобы проверить используемую версию Power BI Desktop, просмотрите экран запуска или строку заголовка в Power BI Desktop. В строке заголовка отображаются месяц и год выпуска.

![Строка заголовка приложения Power BI Desktop, оптимизированного для решения "Сервер отчетов Power BI"](media/install-powerbi-desktop/power-bi-report-server-desktop-august-2018.png)

В строке заголовка версии Power BI Desktop для службы Power BI не указаны месяц и год выпуска.

## <a name="file-extension-association"></a>Сопоставление расширения файла
Если Power BI Desktop и приложение Power BI Desktop, оптимизированное для сервера отчетов Power BI, установлены на одном компьютере, экземпляр Power BI Desktop, который устанавливался последним, будет иметь сопоставление файлов с расширением PBIX. Следовательно, щелкнув дважды PBIX-файл, вы запустите экземпляр Power BI Desktop, который установлен последним.

Если у вас уже есть приложение Power BI Desktop, и вы устанавливаете приложение Power BI Desktop, оптимизированное для сервера отчетов Power BI, все PBIX-файлы будут по умолчанию открываться в приложении Power BI Desktop, оптимизированном для сервера отчетов Power BI. Если необходимо, чтобы при открытии PBIX-файлов по умолчанию запускалось приложение Power BI Desktop, переустановите Power BI Desktop в службе Power BI.

Всегда можно открыть ту версию Power BI Desktop, которую нужно использовать первой, а затем открыть файл в приложении Power BI Desktop.

При редактировании отчета Power BI на сервере отчетов Power BI или создании отчета Power BI на веб-портале всегда будет открываться правильная версия Power BI Desktop.

## <a name="considerations-and-limitations"></a>Рекомендации и ограничения
Отчеты в сервере отчетов Power BI и в службе Power BI (http://app.powerbi.com)), и в мобильных приложениях Power BI работают почти одинаково, но некоторые функции все же различаются.

### <a name="in-a-browser"></a>В браузере
Отчеты на сервере отчетов Power BI поддерживают все визуализации, в том числе:

* Пользовательские визуальные элементы

Отчеты на сервере отчетов Power BI не поддерживают:

* визуальные элементы R;
* карты ArcGIS;
* строки навигации;
* Функции предварительной версии Power BI Desktop

### <a name="in-the-power-bi-mobile-apps"></a>В мобильных приложениях Power BI
Отчеты на сервере отчетов Power BI поддерживают все функциональные возможности, доступные в [мобильных приложениях Power BI](../consumer/mobile/mobile-apps-for-mobile-devices.md), в том числе:

* [Макет мобильного отчета](../desktop-create-phone-report.md). Вы можете оптимизировать отчет для мобильных приложений Power BI. В отчетах, оптимизированных для мобильных телефонов, есть специальный значок ![Значок "Макет отчета для телефона"](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-icon.png) и макет.
  
    ![Отчет, оптимизированный для телефонов](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-report.png)

В мобильных приложениях Power BI отчеты на сервере отчетов Power BI не поддерживают:

* визуальные элементы R;
* карты ArcGIS;
* Пользовательские визуальные элементы
* строки навигации;
* географическую фильтрацию и штрихкоды.

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>Power BI Desktop для более ранних версий Сервера отчетов Power BI

Если вы используете более раннюю версию сервера отчетов, нужна подходящая версия Power BI Desktop. Ниже приведены две предыдущие версии.

- Microsoft Power BI Desktop ([оптимизировано для Сервера отчетов Power BI, октябрь 2017 г.](https://www.microsoft.com/download/details.aspx?id=56136))
- Microsoft Power BI Desktop ([оптимизировано для Сервера отчетов Power BI, июнь 2017 г.](https://www.microsoft.com/download/details.aspx?id=55330))

## <a name="next-steps"></a>Дальнейшие действия
Теперь, когда приложение Power BI Desktop установлено, можно приступить к созданию отчетов Power BI.

[Создание отчета Power BI для Сервера отчетов Power BI](quickstart-create-powerbi-report.md)  
[Что такое Сервер отчетов Power BI?](get-started.md)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

