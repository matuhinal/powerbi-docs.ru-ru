---
title: Журнал изменений API визуальных элементов Power BI
description: В этой статье описываются основные изменения в различных версиях API визуальных элементов Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 03/13/2019
ms.openlocfilehash: fa8759d7edb519240140263bcd01bfdddd9c7d86
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83141054"
---
# <a name="power-bi-visuals-api-changelog"></a>Журнал изменений API визуальных элементов Power BI
На этой странице содержится краткий обзор версий API. Перечисленные здесь версии считаются стабильными, в них изменений не будет.

## <a name="api-v26"></a>API версии 2.6
  * Добавляет **isInFocus** в параметр обновления и метод **switchFocusModeState** в узел визуального элемента.
  * Поддерживает настройку **подытогов**.

## <a name="api-v25"></a>API версии 2.5
  * Поддерживает **[Панель аналитики](./analytics-pane.md)** .
  * Поддерживает методы `SelectionIdBuilder` **withMatrixNode** и **withTable**.
  * Больше не поддерживает интерфейс `DataRepetitionSelector` (заменено интерфейсом `data.CustomVisualOpaqueIdentity`).

## <a name="api-v23"></a>API версии 2.3
  * **[API целевой страницы](./landing-page.md)**
  * **[API локального хранилища](./local-storage.md)**
  * **[API фильтра кортежей (фильтр для нескольких столбцов)](./filter-api.md#the-tuple-filter-api-multi-column-filter)**
  * **[API событий отрисовки](./event-service.md#render-events-in-power-bi-visuals)**

## <a name="api-v22"></a>API версии 2.2
  * Поддерживает **[восстановление фильтра JSON из DataView](./filter-api.md#restore-the-json-filter-from-the-data-view)** .
  * **[API ContextMenu](./context-menu.md)**

## <a name="api-v21"></a>API версии 2.1
  * Повышение производительности:
    * Ускоренное время загрузки.
    * Меньше занимаемой памяти.
    * Оптимизированные транзакции данных и событий.  

**Заметки о выпуске**
* API фильтрации с рефакторингом будут доступны в API 2.2. Они не поддерживаются в API 2.1.
* Визуальные элементы получат только тип dataView, объявленный в их возможностях. В результате этого обновления визуальные элементы, использующие несколько типов dataView, будут отключены.
* Больше не поддерживает интерфейс `DataViewScopeIdentity` (заменено интерфейсом `data.DataRepetitionSelector`). Если вы использовали ключевое свойство интерфейса `DataViewScopeIdentity`, его можно заменить на `JSON.stringify(identity)`.
* `undefined` заменяется на `null` в dataView. При переборе массива с помощью `var item in myArray` `undefined` пропускается, а `null` — нет. Визуальные элементы, использующие этот шаблон, могут быть отключены в рамках этого обновления. Обязательно проверьте наличие `null` в массивах:
   ```typescript
   for (var item in myArray) {
     if (!item) {
       continue;
     }
     console.log(item);
   }
   ```
* Свойство `proto` больше не сохраняет скрытые метаданные и данные в dataView. Визуальные элементы, которые получают доступ к свойствам через `proto`, могут быть отключены в рамках этого обновления.

## <a name="api-v113"></a>API версии 1.13
* Поддерживает **[Синхронизацию срезов](./enable-sync-slicers.md)** . Обратите внимание, что эта функция применима только для отдельных срезов полей из-за текущего состояния кода PBI. Дополнительную информацию см. [здесь](/power-bi/desktop-slicers).
* Специальные возможности. [Поддержка высокой контрастности](./high-contrast-support.md) 
* Специальные возможности. Флажок Allow Keyboard Focus (Разрешить фокус клавиатуры)

## <a name="api-v112"></a>API версии 1.12
* Поддерживает темы.
* Поддерживает **[fetchMoreData](./fetch-more-data.md)** . Обратите внимание, что **API получения дополнительных данных** превышает строгое ограничение в 30 тысяч точек данных.
* **[API подсказок холста](./add-tooltips.md#add-report-page-tooltips)**

## <a name="api-v111"></a>API версии 1.11
* **[API FilterManager](./filter-api.md)**
* Поддерживает **[Закладки](./bookmarks-support.md)** . 

## <a name="api-v110"></a>API версии 1.10
* Добавляет `ILocalizationManager`.
* **API проверки подлинности**

## <a name="api-v19"></a>API версии 1.9
* **[API launchUrl](./launch-url.md)**

## <a name="api-v18"></a>API версии 1.8
* Поддерживает новый тип **fillRule** (градиент) в схеме возможностей.
* Поддерживает свойство **правил** в схеме возможностей для свойств объектов.

## <a name="api-v17"></a>API версии 1.7
* Поддерживает **[RESJSON](./localization.md#resource-file)** .

## <a name="api-v162"></a>API версии 1.6.2
* Поддерживает **[режим редактирования](./advanced-edit-mode.md)** для визуального элемента.
* Поддерживает **[интерактивные (HTML) визуальные элементы R в Power BI](https://microsoft.github.io/PowerBI-visuals/tutorials/building-r-powered-custom-visual/creating-r-visuals.md)** на основе HTML.

## <a name="api-v150"></a>API версии 1.5.0
* Поддерживает функцию **[разрешения взаимодействий](./visuals-interactions.md)** для взаимодействия визуальных элементов.

## <a name="api-v140"></a>API версии 1.4.0
* Поддерживает **[локализацию](./localization.md)** .

## <a name="api-v130"></a>API версии 1.3.0
* Поддерживает **[подсказки](./add-tooltips.md)** .

## <a name="api-v120"></a>API версии 1.2.0
* Добавляет **colorPalette** для управления цветами, используемыми в визуальном элементе.
* Поддерживает **выбор нескольких элементов**. selectionManager может принимать массив `SelectionId`.
* Поддерживает **[визуальные элементы R](https://microsoft.github.io/PowerBI-visuals/tutorials/building-r-powered-custom-visual/creating-r-visuals.md)** с помощью скриптов R.

## <a name="api-v110"></a>API версии 1.1.0
* Поддерживает визуальный элемент отладки в iFrame.
* Добавляет упрощенную песочницу с более быстрой инициализацией iFrame.
* Исправляет ошибку [Capabilities.objects не поддерживает тип "текст"](https://github.com/Microsoft/PowerBI-visuals-tools/issues/12).
* Поддерживает `pbiviz update` для обновления определений типов и схем API визуальных элементов.
* Поддерживает флажок `--api-version` в `pbiviz new` для создания визуальных элементов с помощью определенной версии API.
* Поддерживает альфа-выпуск API версии 1.2.0.

**Узел визуального элемента**
* Добавляет **createSelectionIdBuilder** для создания уникальных идентификаторов, используемых для выбора данных.
* Добавляет **createSelectionManager** для управления состоянием выбора визуального элемента и передает изменения в узел визуального элемента.
* Добавляет массив **цветов** по умолчанию для использования в визуальных элементах.

## <a name="api-v100"></a>API версии 1.0.0
* Первоначальный выпуск API
