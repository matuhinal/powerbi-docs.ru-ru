---
title: Фильтрация и совместное использование отчета Power BI
description: Узнайте, как отфильтровать отчет Power BI и предоставить общий доступ к нему коллегам в организации.
author: maggiesMSFT
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/29/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 636aaf59a3a949b5b3571012d12cecc234e9763b
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83347960"
---
# <a name="filter-and-share-a-power-bi-report"></a>Фильтрация и совместное использование отчета Power BI
Используя *Общий доступ*, вы можете предоставить нескольким пользователям доступ к информационным панелям и отчетам. Что делать, если необходимо совместно использовать отфильтрованную версию отчета? Возможно, вы хотите, чтобы в отчете отображались данные только для определенного города, определенного продавца или за определенный год. В этой статье объясняется, как выполнить фильтрацию отчета и совместно использовать отфильтрованную версию отчета. Другим способом совместного использования отфильтрованного отчета является [добавление параметров запроса в URL-адрес отчета](service-url-filters.md). В обоих случаях фильтр применяется к отчету во время первого открытия отчета получателями. Они могут отключить фильтр в отчете.

![Отфильтрованный отчет](media/service-share-reports/power-bi-share-filter-pane-report.png)

В Power BI также доступны [другие способы совместной работы с отчетами и их распространения](service-how-to-collaborate-distribute-dashboards-reports.md). Чтобы предоставить общий доступ, вам и получателям содержимого требуется [лицензия Power BI Pro](../fundamentals/service-features-license-type.md) либо же содержимое должно находиться в [емкости Premium](../admin/service-premium-what-is.md). 

## <a name="follow-along-with-sample-data"></a>Повторение с демонстрационными данными

В этой статье используется пример шаблонного приложения "Маркетинг и продажи". Итак, приступим. 

1. Установите [пример шаблонного приложения "Маркетинг и продажи"](https://appsource.microsoft.com/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample?tab=Overview).
2. Выберите приложение и нажмите кнопку **Исследовать приложение**.

   ![Исследование образца данных](media/service-share-reports/power-bi-sample-explore-data.png)

3. Щелкните значок с изображением карандаша, чтобы открыть рабочую область, установленную вместе с приложением.

    ![Карандаш редактирования приложения](media/service-share-reports/power-bi-edit-pencil-app.png)

4. В списке содержимого рабочей области выберите **Отчеты**, а затем выберите отчет **Sales and Marketing Sample PBIX** (Продажи и маркетинг — пример (PBIX-файл)).

    ![Открытие образца отчета](media/service-share-reports/power-bi-open-sample-report.png)

    Теперь можно приступить к работе.

## <a name="set-a-filter-in-the-report"></a>Установка фильтра в отчете

Откройте отчет в [режиме правки](../consumer/end-user-reading-view.md) и примените фильтр.

В этом примере мы применим фильтр к странице данных за истекший год из примера шаблона приложения "Маркетинг и продажи", чтобы отобразить только те значения, у которых параметру **Region** соответствует значение **Central**. 
 
![Панель "Фильтр отчета"](media/service-share-reports/power-bi-share-report-filter.png)

Сохраните отчет.

## <a name="share-the-filtered-report"></a>Предоставление общего доступа к отфильтрованному отчету

1. Выберите **Общий доступ**.

   ![Выберите Share (Общий доступ)](media/service-share-reports/power-bi-share.png)

2. Снимите флажок **Отправлять получателям уведомления по электронной почте**, чтобы можно было отправить отфильтрованную ссылку, выберите **Публикация отчета с текущими фильтрами и срезами**, а затем нажмите кнопку **Поделиться**.

    ![Предоставление доступа к отчету с фильтрами](media/service-share-reports/power-bi-share-with-filters.png)

4. Выберите **Общий доступ** еще раз.

   ![Выберите Share (Общий доступ)](media/service-share-reports/power-bi-share.png)

5. Перейдите на вкладку **Доступ**, а затем выберите **Управление общими представлениями отчетов**.

    ![Управление общими представлениями отчетов](media/service-share-reports/power-bi-manage-shared-report-views.png)

6. Щелкните правой кнопкой мыши нужный URL-адрес и выберите команду **Копировать ссылку**.

    ![Копирование отфильтрованной ссылки](media/service-share-reports/power-bi-copy-filtered-link.png)

7. При совместном использовании этой ссылки получатели увидят отфильтрованный отчет. 


## <a name="next-steps"></a>Дальнейшие действия
* [Способы совместного использования работы в Power BI](service-how-to-collaborate-distribute-dashboards-reports.md)
* [предоставление общего доступа к панелям мониторинга](service-share-dashboards.md).
* У вас имеются и другие вопросы? [Ответы на них см. в сообществе Power BI](https://community.powerbi.com/).
* Хотите оставить отзыв? Поделитесь своими предложениями на [веб-сайте сообщества Power BI](https://community.powerbi.com/).
