---
title: Публикация из Power BI Desktop
description: Публикация из Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 3a67c36b2594696e1c576693cc5808eb0227c1c7
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83333494"
---
# <a name="publish-datasets-and-reports-from-power-bi-desktop"></a>Публикация наборов данных и отчетов из Power BI Desktop
При публикации файла Power BI Desktop в службе Power BI вы публикуете данные в модели в рабочей области Power BI. Это относится и ко всем отчетам, созданным в представлении **Отчеты**. Новый набор данных с тем же именем и все отчеты появятся в навигаторе рабочей области.

Публикация из Power BI Desktop аналогична использованию функции **получения данных** в Power BI для подключения к файлу Power BI Desktop и его отправки.

> [!NOTE]
> Любые изменения, вносимые в отчет в Power BI, не будут сохранены в исходном файле Power BI Desktop. Это относится к добавлению, удалению или изменению визуализаций в отчетах.
> 
> 

## <a name="to-publish-a-power-bi-desktop-dataset-and-reports"></a>Публикация набора данных и отчетов Power BI Desktop
1. В Power BI Desktop последовательно выберите **Файл** \> **Опубликовать** \> **Опубликовать в Power BI** или щелкните **Опубликовать** на ленте.  

   ![Кнопка "Опубликовать"](media/desktop-upload-desktop-files/pbid_publish_publishbutton.png)

2. Войдите в Power BI.
3. Выберите место назначения.

   ![Выбор места публикации](media/desktop-upload-desktop-files/pbid_publish_select_destination.png)

По завершении публикации вы получите ссылку на отчет. Щелкните ссылку, чтобы открыть отчет на сайте Power BI.

![Диалоговое окно с сообщением об успешной публикации](media/desktop-upload-desktop-files/pbid_publish_success.png)

## <a name="republish-or-replace-a-dataset-published-from-power-bi-desktop"></a>Повторная публикация или замена набора данных, опубликованного из Power BI Desktop
Набор данных и все отчеты, созданные в Power BI Desktop, отправляются на сайт Power BI, когда вы публикуете файл Power BI Desktop. При повторной публикации файла Power BI Desktop набор данных на сайте Power BI будет заменен обновленным набором данных из файла Power BI Desktop.

Этот процесс очевиден, однако существуют некоторые моменты, которые следует знать.

* При наличии нескольких наборов данных в Power BI с названием, совпадающим с именем файла Power BI Desktop, публикация может завершиться ошибкой. Убедитесь, что в Power BI имеется только один набор данных с тем же именем. Можно также переименовать файл и опубликовать его, создав новый набор данных с тем же именем, что и у файла.
* При переименовании или удалении столбца или меры все визуализации, уже существующие в Power BI с этим полем, могут быть повреждены. 
* Power BI не учитывает некоторые изменения формата существующих столбцов. Например, если формат столбца меняется с 0,25 на 25 %.
* Предположим, что у вас есть расписание обновления, настроенное для существующего набора данных в Power BI. При добавлении новых источников данных в файл и последующей повторной публикации необходимо войти в них до следующего запланированного обновления.
* Если вы повторно публикуете набор данных, опубликованный из Power BI Desktop, и настроили расписание обновления, обновление набора данных инициируется сразу после повторной публикации. 

