---
title: Подключение к PDF-файлу в Power BI Desktop (предварительная версия)
description: Простое и удобное подключение к данным из PDF-файлов с помощью приложения Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/10/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: fe13e5776648342aa4f7e86dce657e6ffcca11b9
ms.sourcegitcommit: c51461690e8faa121a1325957ca79b7a3975e8b8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44513290"
---
# <a name="connect-to-a-pdf-file-in-power-bi-desktop-preview"></a>Подключение к PDF-файлу в Power BI Desktop (предварительная версия)
С помощью Power BI Desktop вы можете подключиться к **PDF-файлу** и использовать данные из него аналогично любому другому источнику данных в Power BI Desktop.

![Подключение к данным в PDF-файлах](media/desktop-connect-pdf/connect-pdf_04.png)

В следующих разделах рассматривается процесс подключения к **PDF-файлу**, выбора данных и переноса этих данных в **Power BI Desktop**.

## <a name="enable-the-pdf-connector"></a>Включение соединителя PDF
Соединитель PDF доступен в предварительной версии для **Power BI Desktop** и должен быть включен. Чтобы включить соединитель PDF, выберите **Файл > Параметры и настройки > Параметры > Функции предварительной версии** и установите флажок рядом с пунктом **Получение данных из PDF-файлов**. 

![Чтобы включить соединитель PDF, выберите "Параметры" > "Функции предварительной версии"](media/desktop-connect-pdf/connect-pdf_01.png)

После этого изменения приложение **Power BI Desktop** необходимо перезапустить.

При первом запуске соединителя **PDF (бета-версия)** вы будете предупреждены, что соединитель PDF находится на стадии разработки и может быть изменен в будущем. Выберите **Продолжить**, чтобы использовать соединитель.

Мы всегда рекомендуем выполнять обновление до последней версии **Power BI Desktop**. Это можно сделать с помощью ссылки [Получить Power BI Desktop](desktop-get-the-desktop.md). 

## <a name="connect-to-a-pdf-file"></a>Подключение к PDF-файлу
Для подключения к **PDF-файлу** в ленте **Главная** в Power BI Desktop выберите **Получить данные**. В области слева выберите **Файл**. Отобразится пункт **PDF (бета-версия)**.

![Выбор PDF в интерфейсе получения данных](media/desktop-connect-pdf/connect-pdf_01.png)

Вам будет предложено указать расположение файла PDF-файла, который вы хотите использовать. После предоставления информации о расположении файла и его загрузки откроется окно **Навигатор**, содержащее данные из файла. В этом окне вы можете выбрать один или несколько элементов для импорта и использования в **Power BI Desktop**.

![Подключение к данным в PDF-файлах](media/desktop-connect-pdf/connect-pdf_04.png)

После установки флажка напротив обнаруженных в PDF-файле элементов они будут показаны в области справа. Когда вы будете готовы их импортировать, выберите кнопку **Загрузить**, чтобы перенести данные в **Power BI Desktop**.


## <a name="next-steps"></a>Дальнейшие действия
В Power BI Desktop можно подключаться к данным самых разных видов. Дополнительные сведения об источниках данных см. в перечисленных ниже статьях.

* [Что такое Power BI Desktop?](desktop-what-is-desktop.md)
* [Источники данных в Power BI Desktop](desktop-data-sources.md)
* [Формирование и объединение данных в Power BI Desktop](desktop-shape-and-combine-data.md)
* [Подключение к данным Excel в Power BI Desktop](desktop-connect-excel.md)   
* [Ввод данных непосредственно в Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

