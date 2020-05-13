---
title: Уменьшение размера книги Excel для ее просмотра в Power BI
description: Уменьшение размера книги Excel для ее просмотра в Power BI
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/10/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 8c58c85ea46f9884586e1ff73f1ef9f7b1db9cdd
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83327238"
---
# <a name="reduce-the-size-of-an-excel-workbook-to-view-it-in-power-bi"></a>Уменьшение размера книги Excel для ее просмотра в Power BI
Вы можете передать в Power BI любую книгу Excel размером менее 1 ГБ. Книга Excel может состоять из двух частей: модели данных и оставшейся части отчета — основного содержимого листа. Если отчет удовлетворяет следующим ограничениям размера, можно сохранить его в **OneDrive для бизнеса**, подключиться к нему из Power BI и просмотреть его в Excel Online:

* Книги могут иметь общий размер до 1 ГБ.
* Основное содержимое листа может иметь размер до 30 МБ.

## <a name="what-makes-core-worksheet-contents-larger-than-30-mb"></a>Причины увеличения размера основного содержимого листа свыше 30 МБ
Ниже приведены некоторые элементы, которые могут привести к увеличению размера основного содержимого листа свыше 30 МБ.

* Изображения.
* Затененные ячейки. [Удалите формат заливки ячеек](https://support.office.com/article/Add-or-change-the-background-color-of-cells-ac10f131-b847-428f-b656-d65375fb815e).
* Цветные листы. [Удалите фон листов](https://support.office.com/article/add-or-remove-a-sheet-background-3577a762-8450-4556-96a2-cc265abc00a8).
* Текстовые поля.
* Коллекция картинок.

Рекомендуется удалить такие элементы, если это возможно. 

Если отчет содержит модель данных, доступны некоторые другие варианты. 

* Удалите данные из листов Excel и сохраните их в модели данных. Дополнительные сведения см. в разделе "Удаление данных из листов" ниже. 
* [Создайте модель данных, эффективно использующую память](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70), для уменьшения общего размера отчета.

Для внесения этих изменений необходимо изменить книгу в Excel.

Узнайте больше об [ограничениях размера файлов для книг Excel в SharePoint Online](https://support.office.com/article/File-size-limits-for-workbooks-in-SharePoint-Online-9e5bc6f8-018f-415a-b890-5452687b325e).

## <a name="remove-data-from-worksheets"></a>Удаление данных из листов
При импорте данных в Excel с вкладки Power Query или "Данные Excel" книга может иметь одинаковые данные в таблице Excel и в модели данных. Большие таблицы на листах Excel могут привести к увеличению основного содержимого листа свыше 30 МБ. Удаление таблицы в Excel и сохранение данных в модели данных может значительно уменьшить основное содержимое листа отчета. 

При импорте данных в Excel следуйте приведенным ниже советам.

* **В Power Query**: снимите флажок **Загрузить на лист**.
  
  Данные импортируются только в модель данных, а данные на листах Excel отсутствуют.
* **На вкладке "Данные Excel"** , если ранее вы установили флажок **Таблицы** в мастере импорта, Последовательно выберите **Существующие соединения** \> выберите подключение \> **Только создать соединение**. Удалите исходные таблицы, созданные во время первоначального импорта.
* **С вкладки "Данные Excel"** : не устанавливайте флажок **Таблица** в поле **Импорт данных** .

## <a name="workbook-size-optimizer"></a>Оптимизатор размер книги
Если книга содержит модель данных, можно запустить оптимизатор для уменьшения размера книги. [Скачайте оптимизатор размера книги](https://www.microsoft.com/download/details.aspx?id=38793).

## <a name="related-info"></a>См. также
[Создание модели данных с эффективным использованием памяти](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70)

[Использование ссылок OneDrive для бизнеса в Power BI Desktop](desktop-use-onedrive-business-links.md)

