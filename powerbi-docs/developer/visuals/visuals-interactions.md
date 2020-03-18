---
title: Взаимодействие визуальных элементов в Power BI
description: В этой статье описывается, как проверить, допускается ли взаимодействие визуальных элементов в Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: 1fb4f7d5950ab18a74dcacfdfef9c3ada90512c4
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79378945"
---
# <a name="visual-interactions-in-power-bi-visuals"></a>Взаимодействие визуальных элементов в Power BI

Визуальные элементы могут запрашивать значение флага `allowInteractions`, которое указывает, должен ли визуальный элемент допускать взаимодействие с визуальными элементами. Например, визуальные элементы допускают взаимодействие во время просмотра или редактирования отчета и не допускают его при просмотре на панели мониторинга. К таким видам взаимодействия относятся *щелчок*, *сдвиг*, *масштабирование*, *выделение* и другие. 

> [!NOTE]
> Независимо от настройки флага, необходимо включить всплывающие подсказки во всех сценариях.

Флаг `allowInteractions` передается в виде логического значения во время инициализации визуального элемента в качестве члена интерфейса IVisualHost.

В любом сценарии Power BI, требующем отсутствия взаимодействия визуальных элементов (например, для плиток панели мониторинга), для флага `allowInteractions` будет установлено значение `false`. В противном случае (например, для отчета), флагу `allowInteractions` присваивается значение `true`.

Дополнительные сведения см. в [репозитории визуальных элементов SampleBarChart](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/59a47935d8f5272ce145fe804193599ddb7e2001).

```typescript
   ...
   let allowInteractions = options.host.allowInteractions;
   bars.on('click', function(d) {
       if (allowInteractions) {
           selectionManager.select(d.selectionId);
           ...
       }
   });
```
