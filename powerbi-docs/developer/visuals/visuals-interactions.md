---
title: Взаимодействие с визуальными элементами
description: Проверка того, что визуальный элемент Power BI допускает взаимодействие визуальных элементов
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 739e59c6da3c1e464e0462a928bc4f33ea0d01f8
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424500"
---
# <a name="visuals-interactions"></a>Взаимодействие с визуальными элементами

Визуальные элементы могут запрашивать значение флага "allowInteractions", которое указывает, должен ли визуальный элемент допускать взаимодействие с визуальными элементами.
Например, визуальные элементы допускают взаимодействие во время просмотра или редактирования отчета и не допускают его при просмотре на панели мониторинга.
К таким видам взаимодействия относятся щелчок, сдвиг, масштабирование, выделение и другие.
Обратите внимание, что подсказки должны быть включены во всех сценариях, независимо от этого флага.

Флаг "allowInteractions" передается в виде логического значения во время инициализации визуального элемента в качестве члена интерфейса IVisualHost.

В любом сценарии Power BI, требующем отсутствие взаимодействия визуальных элементов (например, для плиток панели мониторинга), для флага "allowInteractions" будет установлено значение false.
В противном случае (например, для отчета) флагу "allowInteractions" будет присвоено значение true.

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
