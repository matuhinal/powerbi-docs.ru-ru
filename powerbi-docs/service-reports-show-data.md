---
title: "Отображение данных, использованных для создания визуализации Power BI"
description: "Из этого документа вы узнаете, как отображать данные, которые используются для создания визуализации в Power BI, и как экспортировать эти данные в CSV-файл."
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 02/28/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: b85fe5cf70c915a3355c80a61f01a32216450f03
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2018
---
# <a name="show-the-data-that-was-used-to-create-the-visualization"></a>Отображение данных, использованных для создания визуализации
## <a name="show-data"></a>Отображение данных
Визуализация Power BI создается на основе данных из наборов данных. Если вы хотите копнуть поглубже, Power BI дает возможность *просмотреть* данные, лежащие в основе визуального элемента. Если выбрать функцию **Показать данные**, Power BI отобразит рядом с визуализацией или под ней связанную информацию.

Данные, используемые для создания визуализации, можно экспортировать в файл XLSX или CSV и просмотреть его в Excel. Дополнительные сведения см. в статье [Экспорт данных из визуализаций Power BI](power-bi-visualization-export-data.md).

> [!NOTE]
> Функции *Показать данные* и *Экспортировать данные* доступны как в службе Power BI, так и в приложении Power BI Desktop. Но в Power BI Desktop есть дополнительный уровень детализации: функция [*Показать записи* отображает фактические строки из набора данных](desktop-see-data-see-records.md).
> 
> 

## <a name="using-show-data-in-power-bi-service"></a>Использование функции *Показать данные* в службе Power BI
1. В службе Power BI откройте отчет в [режиме чтения или правки](service-reading-view-and-editing-view.md) и выберите визуальный элемент.  В приложении Power BI Desktop откройте представление отчетов.
2. Чтобы отобразить данные, лежащие в основе визуального элемента, выберите **Проводник** > **Показать данные**.
   
   ![выбор пункта "Показать данные"](media/service-reports-show-data/power-bi-show-data.png)
3. По умолчанию данные отображаются под визуальным элементом.
   
   ![вертикальное отображение визуального элемента и данных](media/service-reports-show-data/power-bi-explore-show-data.png)
4. Чтобы изменить ориентацию, в правом верхнем углу визуализации выберите вертикальный макет ![](media/service-reports-show-data/power-bi-vertical-icon-new.png).
   
   ![горизонтальное отображение визуального элемента и данных](media/service-reports-show-data/power-bi-explore-show-data2.png)
5. Чтобы экспортировать данные в CSV-файл, щелкните значок многоточия и выберите **Экспортировать данные**.
   
    ![выбор пункта "Экспортировать данные"](media/service-reports-show-data/power-bi-export-data-new.png)
   
    Дополнительные сведения об экспорте данных в Excel см. в статье [Экспорт данных из визуализаций Power BI](power-bi-visualization-export-data.md).
6. Чтобы скрыть данные, снимите флажок, выбрав **Проводник** > **Показать данные**.

### <a name="next-steps"></a>Дальнейшие действия
[Экспорт данных из визуализаций Power BI](power-bi-visualization-export-data.md)    
[Визуализации в Power BI](power-bi-report-visualizations.md)    
[Отчеты в Power BI](service-reports.md)    
[Power BI — основные понятия](service-basic-concepts.md)    
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

