---
title: Фильтрация отчета и использовать их совместно с коллегами - Power BI
description: Узнайте, как отфильтровать отчет Power BI и предоставить общий доступ к нему коллегам в организации.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 5f3808884e63521ec1dd775d876f1cf707bbe56b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770683"
---
# <a name="filter-a-power-bi-report-and-share-it-with-coworkers"></a>Фильтрация отчета Power BI и использовать их совместно с коллегами
Используя *Общий доступ*, вы можете предоставить нескольким пользователям доступ к информационным панелям и отчетам. Что делать, если необходимо совместно использовать отфильтрованную версию отчета? Это может быть отчет, который отображает данные только по определенному городу, продавцу или году. Попробуйте фильтровании отчетов и общий доступ к ней или создании пользовательский URL-адрес. Отчет будет отфильтрован, когда получатели откроют его в первый раз. Получатели могут удалить фильтр, изменив URL-адрес. 

В Power BI также доступны [другие способы совместной работы с отчетами и их распространения](service-how-to-collaborate-distribute-dashboards-reports.md). Чтобы предоставить общий доступ, вам и получателям содержимого требуется [лицензия Power BI Pro](service-features-license-type.md) либо же содержимое должно находиться в [емкости Premium](service-premium-what-is.md). 

## <a name="two-ways-to-filter-a-report"></a>Два способа для фильтрации отчета

### <a name="set-a-filter"></a>Установка фильтра

Откройте отчет в [режиме редактирования](consumer/end-user-reading-view.md), примените фильтр и сохраните отчет.
   
В этом примере мы применяем фильтр к набору данных [Анализ розничной торговли — пример](sample-tutorial-connect-to-the-samples.md), чтобы отобразить только значения, у которых в поле **Территория** указано значение **NC**.
   
![Панель "Фильтр отчета"](media/service-share-reports/power-bi-filter-report2.png)

### <a name="create-a-filter-in-the-url"></a>Создать фильтр в URL-адрес

В конец URL-адреса страницы отчета добавьте следующий фрагмент:
   
?filter=*tablename*/*fieldname* eq *value*
   
Поле должно иметь тип number, datetime или строку. Значения *tablename* и *fieldname* не должны содержать пробелов.
   
В нашем примере имя таблицы — **Store**, имя поля — **Territory**, а значение, по которому выполняется фильтрация — **NC**.
   
?filter=Store/Territory eq 'NC'
   
![URL-адрес отфильтрованного отчета](media/service-share-reports/power-bi-filter-url3.png)
   
Браузер добавляет специальные знаки, представляющие косые черты, пробелы и апострофы, поэтому окончательный адрес будет следующим:
   
app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

См. в статье [Фильтрация с помощью параметров строки запроса в URL-АДРЕСЕ отчета](service-url-filters.md) для гораздо более подробно.

## <a name="share-the-filtered-report"></a>Совместное использование отфильтрованного отчета

1. Когда вы [общий доступ к отчету](service-share-dashboards.md), снимите флажок **отправки уведомлений по электронной почте получателям** "флажок".

    ![Диалоговое окно предоставления общего доступа](media/service-share-reports/power-bi-share-report-dialog.png)

4. Отправьте ссылку с фильтром, который вы создали ранее.

## <a name="next-steps"></a>Дальнейшие действия
* Хотите оставить отзыв? Поделитесь своими предложениями на [веб-сайте сообщества Power BI](https://community.powerbi.com/).
* [Как предоставить общий доступ к панелям мониторинга, отчетам и плиткам?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [предоставление общего доступа к панелям мониторинга](service-share-dashboards.md).
* Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI](http://community.powerbi.com/).

