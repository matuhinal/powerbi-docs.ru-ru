---
title: "Подключение к CSV-файлам в Power BI Desktop"
description: "Простое и удобное подключение к данным из CSV-файлов в приложении Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
ms.openlocfilehash: 8fa6870a7ca7b362b9ce71224845a4194805bae8
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2017
---
# <a name="connect-to-csv-files-in-power-bi-desktop"></a>Подключение к CSV-файлам в Power BI Desktop
Файлы с разделителями-запятыми (формат *CSV*) подключаются в Power BI Desktop почти так же, как и книги Excel. Обе процедуры довольно просты, и в этой статье объясняется, как подключиться к любому CSV-файлу, к которому у вас есть доступ.

Для начала в Power BI Desktop выберите **Получение данных > CSV** на ленте **Главная**.

![](media/desktop-connect-csv/connect-to-csv_1.png)

Выберите CSV-файл в диалоговом окне **Открыть**.

![](media/desktop-connect-csv/connect-to-csv_2.png)

Когда вы нажмете кнопку **Открыть**, Power BI Desktop откроет файл и проанализирует некоторые его атрибуты, такие как источник, тип разделителя и количество строк, необходимых для определения типов данных в файле.

Эти атрибуты и доступные варианты отобразятся в раскрывающихся списках в верхней части диалогового окна **Импорт из формата CSV**, как показано на изображении ниже. Вы можете вручную изменить определенные автоматически параметры, выбрав нужный вариант из соответствующего раскрывающегося списка.

![](media/desktop-connect-csv/connect-to-csv_3.png)

Задав атрибуты, нажмите кнопку **Загрузить**, чтобы импортировать файл в приложение Power BI Desktop, или кнопку **Изменить**, чтобы открыть **редактор запросов** и отформатировать или преобразовать данные перед импортом.

После загрузки данных в Power BI Desktop таблица и ее столбцы (в Power BI Desktop они считаются полями) появятся в области **Поля** справа от представления отчета в Power BI Desktop.

![](media/desktop-connect-csv/connect-to-csv_4.png)

На этом импорт завершен: теперь данные из CSV-файла загружены в Power BI Desktop.

Теперь вы можете работать с ними в приложении Power BI Desktop: создавать визуальные элементы и отчеты, а также подключать и импортировать прочие сведения, например книги Excel, базы и любые другие источники данных.

### <a name="next-steps"></a>Дальнейшие действия
В Power BI Desktop можно подключаться к данным самых разных видов. Дополнительные сведения об источниках данных см. в перечисленных ниже статьях.

* [Начало работы с Power BI Desktop](desktop-getting-started.md)
* [Источники данных в Power BI Desktop](desktop-data-sources.md)
* [Формирование и объединение данных в Power BI Desktop](desktop-shape-and-combine-data.md)
* [Подключение к данным Excel в Power BI Desktop](desktop-connect-excel.md)   
* [Ввод данных непосредственно в Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

