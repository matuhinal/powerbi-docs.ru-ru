---
title: Предоставление общего доступа коллегам к отфильтрованному отчету Power BI
description: Узнайте, как отфильтровать отчет Power BI и предоставить общий доступ к нему коллегам в организации.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/21/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 05bdb9ccca7715b74cb18462f215f7d1bf640526
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279774"
---
# <a name="share-a-filtered-power-bi-report-with-your-coworkers"></a>Предоставление общего доступа коллегам к отфильтрованному отчету Power BI
Используя *Общий доступ*, вы можете предоставить нескольким пользователям доступ к информационным панелям и отчетам. В Power BI также доступны [другие способы совместной работы с отчетами и их распространения](service-how-to-collaborate-distribute-dashboards-reports.md).

Чтобы предоставить общий доступ, вам и получателям содержимого требуется [лицензия Power BI Pro](service-features-license-type.md) либо же содержимое должно находиться в [емкости Premium](service-premium.md). 

Вы можете предоставлять общий доступ к отчетам коллегам, у которых есть электронная почта в вашем домене, из большинства расположений в службе Power BI: из списка "Избранные", списка "Последние", страниц "Мне предоставлен доступ" (если это позволяет владельцу) и "Мои представления" или других рабочих областей. Когда вы предоставляете коллегам общий доступ к отчету, они могут просматривать его и взаимодействовать с ним, но не могут изменять его. Они видят в отчетах те же данные, что и вы, если не применяется [защита на уровне строк (RLS)](service-admin-rls.md). 

Что делать, если необходимо совместно использовать отфильтрованную версию отчета? Это может быть отчет, который отображает данные только по определенному городу, продавцу или году. Попробуйте создать пользовательский URL-адрес. Отчет будет отфильтрован, когда получатели откроют его в первый раз. Получатели могут удалить фильтр, изменив URL-адрес.

## <a name="filter-and-share-a-report"></a>Фильтрация и предоставление общего доступа

1. Откройте отчет в [режиме редактирования](consumer/end-user-reading-view.md), примените фильтр и сохраните отчет.
   
   В этом примере мы применяем фильтр к набору данных [Анализ розничной торговли — пример](sample-tutorial-connect-to-the-samples.md), чтобы отобразить только значения, у которых в поле **Территория** указано значение **NC**.
   
   ![Панель "Фильтр отчета"](media/service-share-reports/power-bi-filter-report2.png)
2. В конец URL-адреса страницы отчета добавьте следующий фрагмент:
   
   ?filter=*tablename*/*fieldname* eq *value*
   
    Поле должно иметь тип **string**. Значения *tablename* и *fieldname* не должны содержать пробелов.
   
   В нашем примере имя таблицы — **Store**, имя поля — **Territory**, а значение, по которому выполняется фильтрация — **NC**.
   
    ?filter=Store/Territory eq 'NC'
   
   ![URL-адрес отфильтрованного отчета](media/service-share-reports/power-bi-filter-url3.png)
   
   Браузер добавляет специальные знаки, представляющие косые черты, пробелы и апострофы, поэтому окончательный адрес будет следующим:
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

3. [Предоставьте общий доступ к отчету](service-share-dashboards.md), но снимите флажок **Отправлять получателям уведомления по электронной почте**. 

    ![Диалоговое окно предоставления общего доступа](media/service-share-reports/power-bi-share-report-dialog.png)

4. Отправьте ссылку с фильтром, который вы создали ранее.

## <a name="next-steps"></a>Дальнейшие действия
* Хотите оставить отзыв? Поделитесь своими предложениями на [веб-сайте сообщества Power BI](https://community.powerbi.com/).
* [Как предоставить общий доступ к панелям мониторинга, отчетам и плиткам?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [предоставление общего доступа к панелям мониторинга](service-share-dashboards.md).
* Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI](http://community.powerbi.com/).

