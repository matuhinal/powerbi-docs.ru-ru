---
title: Планирование отчета в построителе отчетов Power BI
description: Построитель отчетов с разбивкой на страницы Power BI позволяет создавать разные типы отчетов с разбивкой на страницы. Чтобы создать полезный и понятный отчет, рекомендуется сначала составить план.
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: 79113505-1ce8-4f8c-9260-d861838f7813
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: fd4a318d7a61f6f2298de6b9d5d23ad2ae063d28
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840517"
---
# <a name="planning-a-report-in-power-bi-report-builder"></a>Планирование отчета в построителе отчетов Power BI
  Построитель отчетов с разбивкой на страницы Power BI позволяет создавать разные типы отчетов с разбивкой на страницы. Например, можно создать отчеты, показывающие сводные или подробные сведения о продажах, маркетинговые и торговые тренды, рабочие отчеты или панели мониторинга. Кроме того, можно создать отчеты, которые используют преимущества сложно форматированного текста, такого как заказы на продажу, каталоги продукции или документы на бланках. Все эти отчеты создаются с помощью различных сочетаний одних и тех же базовых блоков в построителе отчетов. Чтобы создать полезный и понятный отчет, рекомендуется сначала составить план. Ниже указано, что именно следует принять во внимание перед началом работы:  
  
## <a name="in-what-format-do-you-want-the-report-to-appear"></a>В каком формате должен отображаться отчет?
  
Вы можете преобразовать отчеты для просмотра в сети с помощью браузера, например на портале Power BI, или экспортировать их в другие форматы, такие как Excel, Word или PDF. Окончательная форма, принимаемая отчетом, имеет важное значение, так как не все функции доступны во всех форматах экспорта. 
  
## <a name="in-what-structure-do-you-want-to-present-the-data"></a>В виде какой структуры требуется представить данные?
  
Для преставления данных можно использовать структуру с таблицами, матрицами (похожа на отчет с перекрестными ссылками или PivotTable), диаграммами, структуру свободной формы или их сочетание. Дополнительные сведения см. в статье [Таблицы, матрицы и списки в построителе отчетов Power BI](report-builder-tables-matrices-lists.md).  
  
## <a name="how-do-you-want-your-report-to-look"></a>Как должен выглядеть ваш отчет?
  
Построитель отчетов предоставляет множество элементов отчета, которые можно добавить в отчет, чтобы упростить его чтение, выделить важную информацию, облегчить навигацию по отчету и т. д. Зная, как должен выглядеть отчет, можно определить нужные элементы отчета, например текстовые поля, прямоугольники, изображения и линии. Также можно отображать или скрывать элементы, добавить схему документа, включить детализированные или вложенные отчеты либо указать ссылки на другие отчеты.   
  
## <a name="should-the-data-be-filtered"></a>Нужно ли фильтровать данные?
  
Вам может потребоваться сузить область действия отчета до отдельных пользователей или расположений либо до определенного периода времени. Чтобы отфильтровать данные отчета, используйте параметры для получения и отображения только нужных сведений. Дополнительные сведения см. в статье [Параметры отчетов в построителе отчетов Power BI](paginated-reports-parameters.md).  
  
## <a name="do-you-need-to-create-calculations"></a>Требуется ли создавать вычисления? 
  
     Sometimes, your data source and datasets do not contain the exact fields that you need for your report. In that situation, you might have to create your own calculated fields. For example, you might want to multiply the price per unit times the quantity to get a line item sales amount. Expressions are also used to provide conditional formatting and other advanced features. For more information, see [Expressions in Power BI Report Builder](report-builder-expressions.md).  
  
## <a name="do-you-want-to-hide-report-items-initially"></a>Нужно ли изначально скрыть элементы отчета?
  
Решите, нужно ли скрывать элементы отчета, включая области данных, группы и столбцы, при первом запуске отчета. Например, можно изначально отобразить сводную таблицу и затем детализировать до нужных данных. 
  
## <a name="how-are-you-going-to-deliver-your-report"></a>Как вы собираетесь доставлять отчет?  
  
     You can save your report to your local computer and continue to work on it, or run it locally for your own information. However, to share your report with others, you need to save the report to Power BI. Saving it to Power BI lets others run it whenever they want to. Alternatively, you can set up a subscription and e-mail delivery of the report to other individuals. You can have the report delivered in a specific export format if you prefer. 
  
## <a name="next-steps"></a>Дальнейшие действия

- [Сведения об отчетах с разбивкой на страницы в Power BI Premium](paginated-reports-report-builder-power-bi.md)
