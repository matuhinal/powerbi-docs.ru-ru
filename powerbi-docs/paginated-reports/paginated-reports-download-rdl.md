---
title: Скачивание RDL-файла из набора данных для отчета с разбивкой на страницы
description: Из этой статьи вы узнаете, как скачать RDL-файл для отчета Power BI с разбивкой на страницы из общего набора данных в службе Power BI.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: swgupt
ms.service: powerbi
ms.subservice: report-builder
ms.topic: how-to
ms.date: 09/16/2020
ms.openlocfilehash: a0b684403274a0ec69b184d8fb40486d6d2e3e27
ms.sourcegitcommit: cb606d3ae95300683caf1853e229d8981302a8e2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "90765078"
---
# <a name="download-the-rdl-for-a-power-bi-paginated-report-from-a-dataset"></a>Скачивание RDL-файла из набора данных для отчета Power BI с разбивкой на страницы

Из этой статьи вы узнаете, как скачать RDL-файл для отчета Power BI с разбивкой на страницы из набора данных в службе Power BI. Отчеты с разбивкой на страницы имеют формат файла *RDL*. Вы можете создать RDL-файл непосредственно из набора данных в службе Power BI.

1. Перейдите к представлению списка для любой рабочей области, включая "Моя рабочая область". 
1. Выберите **Дополнительные параметры** (…) для набора данных, а затем щелкните **Download the .rdl** (Скачать RDL-файл).

    :::image type="content" source="media/paginated-reports-download-rdl/power-bi-paginated-download-rdl.png" alt-text="Снимок экрана: параметр &quot;Скачать RDL-файл&quot; в службе Power BI.":::
1. Появится сообщение о том, что для Power BI Report Builder нужны обновления. Щелкните **Скачать**. 

    :::image type="content" source="media/paginated-reports-download-rdl/power-bi-report-builder-updates.png" alt-text="Снимок экрана: параметр &quot;Скачать RDL-файл&quot; в службе Power BI.":::

    Если вы уверены, что используете самую последнюю версию Power BI Report Builder, выберите **Я уже установил (-а) эти обновления**.

1. Установите Power BI Report Builder, выполнив приведенные ниже шаги. 

    1. Щелкните **Скачать**.  
    2. Выберите **Открыть файл** и выполните действия, описанные в мастере установки Power BI Report Builder.

1. По завершении установки Report Builder вернитесь в службу Power BI и выберите **Download the .rdl** (Скачать RDL-файл).

    :::image type="content" source="media/paginated-reports-download-rdl/power-bi-report-builder-finished-installing.png" alt-text="Снимок экрана: параметр &quot;Скачать RDL-файл&quot; в службе Power BI.":::

1. В окне браузера выберите **Открыть файл**.

    :::image type="content" source="media/paginated-reports-download-rdl/power-bi-paginated-open-file.png" alt-text="Снимок экрана: параметр &quot;Скачать RDL-файл&quot; в службе Power BI.":::

1. Power BI Report Builder откроется с автоматически созданным заголовком и PBIX-файлом набора данных Power BI в папке **Источники данных**. Имя источника данных совпадает с именем набора данных Power BI.

    :::image type="content" source="media/paginated-reports-download-rdl/power-bi-report-builder-design-canvas.png" alt-text="Снимок экрана: параметр &quot;Скачать RDL-файл&quot; в службе Power BI.":::

    В области конструктора также есть ссылка на видеокурс [Отчеты с разбивкой на страницы в Power BI за один день](../learning-catalog/paginated-reports-online-course.md). Если вы еще не создавали отчеты с разбивкой на страницы, этот курс поможет вам быстро начать работу.  Вы можете удалить его, когда начнете создавать свой отчет.

    Вы готовы приступить к созданию отчета с разбивкой на страницы.
 
## <a name="next-steps"></a>Дальнейшие действия 

- [Сведения об отчетах с разбивкой на страницы в Power BI Premium](paginated-reports-report-builder-power-bi.md)  
- [Руководство. Создание отчета с разбивкой на страницы и его отправка в службу Power BI (предварительная версия)](paginated-reports-quickstart-aw.md)
- [Публикация отчета с разбивкой на страницы в службе Power BI](paginated-reports-save-to-power-bi-service.md)

