---
title: Скачивание отчета из службы Power BI в Power BI Desktop (предварительная версия)
description: Скачивание отчета из службы Power BI в файл Power BI Desktop
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/12/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 61fc821e63889951aefd0ef815f885ffa8a880cf
ms.sourcegitcommit: d12bc6df16be1f1993232898f52eb80d0c9fb04e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68994824"
---
# <a name="download-a-report-from-the-power-bi-service-to-power-bi-desktop-preview"></a>Скачивание отчета из службы Power BI в Power BI Desktop (предварительная версия)
В Power BI Desktop можно опубликовать отчет (*PBIX*-файл) с локального компьютера в службе Power BI. Отчеты Power BI также могут передаваться и в другом направлении: Вы можете скачать отчет из службы Power BI в Power BI Desktop. В любом случае отчет Power BI имеет расширение PBIX.

Существует ряд ограничений и рекомендации, которые мы рассмотри далее в этой статье.

![Раскрывающийся список "Файл"](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix-file"></a>Скачивание отчета в виде PBIX-файла

Скачать можно только отчеты, [созданные в Power BI Desktop](guided-learning/publishingandsharing.yml?tutorial-step=2) после 23 ноября 2016 г. и обновленные позже этого дня. В противном случае команда **Скачать отчет** в меню службы Power BI будет неактивна.

Чтобы скачать PBIX-файл, сделайте следующее:

1. В службе Power BI откройте отчет, который нужно скачать, в [режиме правки](https://docs.microsoft.com/power-bi/service-interact-with-a-report-in-editing-view).

2. На верхней панели навигации выберите **Файл > Скачать отчет**.
   
3. Во время скачивания отчета отображается баннер состояния, показывающий ход выполнения. Когда PBIX-файл будет готов, вам будет предложено указать место для его сохранения. Имя файла по умолчанию соответствует названию отчета.
   
4. [Установите Power BI Desktop](desktop-get-the-desktop.md), если вы это еще не сделали, а затем откройте там PBIX-файл.
   
    Когда вы откроете отчет в приложении Power BI Desktop, возможно, отобразится сообщение с предупреждением, что некоторые функции отчета, доступные в службе Power BI, могут быть недоступны в Power BI Desktop.
   
    ![Диалоговое окно с предупреждением](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)

5. Редактор отчетов в Power BI Desktop похож на редактор отчетов в службе Power BI.  
   
    ![Редактор отчетов Power BI Desktop](media/service-export-to-pbix/power-bi-desktop.png)

## <a name="considerations-and-troubleshooting"></a>Рекомендации и устранение неполадок
Существует несколько важных рекомендаций и ограничений, которые следует учитывать при скачивании PBIX-файла из службы Power BI.

* Чтобы скачать файл, нужно обладать правами на редактирование отчета.
* Отчет должен быть создан в Power BI Desktop и *опубликован* в службе Power BI, либо PBIX-файл должен быть *отправлен* в службу Power BI.
* Отчеты должны быть опубликованы или изменены после 23 ноября 2016 г. Отчеты, опубликованные до этой даты, невозможно скачать.
* Эта функция не будет работать с отчетами и пакетами содержимого, которые изначально были созданы в службе Power BI.
* Скачанные файлы всегда нужно открывать в последней версии Power BI Desktop. Скачанные PBIX-файлы могут не открываться в неактуальных версиях Power BI Desktop.
* Если администратор отключил возможность скачивания данных, эта функция будет недоступна в службе Power BI.
* Наборы данных с добавочным обновлением невозможно скачать в PBIX-файл.

## <a name="next-steps"></a>Дальнейшие действия
Просмотрите короткий видеоролик от **Guy in a Cube** об этой функции.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

Ниже приведен ряд дополнительных статей, информация из которых поможет вам научиться использовать службу Power BI:

* [Отчеты в Power BI](consumer/end-user-reports.md)
* [Основные понятия для разработчиков в службе Power BI](service-basic-concepts.md)

После установки Power BI Desktop ознакомьтесь со следующей статьей, которая поможет вам быстро приступить к работе:

* [Начало работы с Power BI Desktop](desktop-getting-started.md)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI](http://community.powerbi.com/).

