---
title: API локального хранилища для визуальных элементов Power BI
description: В этой статье описывается получение доступа к локальному хранилищу браузера с использованием API визуальных элементов Power BI
author: uve
ms.author: v-grniki
ms.reviewer: KesemSharabi
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 01/21/2019
ms.openlocfilehash: 85517fcd7ec773f947135614c94c0c4e4638ea48
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2020
ms.locfileid: "76539332"
---
# <a name="local-storage-api"></a>API локального хранилища

С помощью API локального хранилища пользовательский визуальный элемент может отправлять узлу запросы на сохранение или загрузку данных из хранилища устройства. Этот API реализует изоляцию, обеспечивая раздельный доступ к хранилищу для разных типов визуальных элементов.

## <a name="sample"></a>Пример

Пользовательский визуальный элемент должен увеличивать значение счетчика каждый раз при вызове метода обновления, но при этом такое значение должно сохраняться и не должно сбрасываться при каждом запуске визуального элемента:

```typescript
export class Visual implements IVisual {
        // ...
        private updateCountName: string = 'updateCount';
        private updateCount: number;
        private storage: ILocalVisualStorageService;
        // ...

        constructor(options: VisualConstructorOptions) {
            // ...
            this.storage = options.host.storageService;
            // ...

            this.storage.get(this.updateCountName).then(count =>
            {
                this.updateCount = +count;
            })
            .catch(() =>
            {
                this.updateCount = 0;
                this.storage.set(this.updateCountName, this.updateCount.toString());
            });
            // ...
        }

        public update(options: VisualUpdateOptions) {
            // ...
            this.updateCount++;
            this.storage.set(this.updateCountName, this.updateCount.toString());
            // ...
        }
}
```

## <a name="known-limitations-and-issues"></a>Известные ограничения и проблемы

По умолчанию API локального хранилища для пользовательских визуальных элементов не активирован. Если вы хотите активировать его для пользовательского визуального элемента, направьте запрос в службу поддержки пользовательских визуальных элементов Power BI (`pbicvsupport@microsoft.com`).  
**Имейте в виду, что визуальный элемент должен быть доступен в [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals) и [сертифицирован](https://powerbi.microsoft.com/en-us/documentation/powerbi-custom-visuals-certified/).**
