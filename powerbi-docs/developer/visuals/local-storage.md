---
title: API локального хранилища для визуальных элементов Power BI
description: В этой статье описывается получение доступа к локальному хранилищу браузера с использованием API визуальных элементов Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 01/21/2019
ms.openlocfilehash: e2cb11ea9be85916e6b5557e7933f6a6b5a7159a
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "79380601"
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

По умолчанию API локального хранилища для визуальных элементов Power BI не активирован. Если вы хотите активировать его для визуального элемента Power BI, направьте запрос в службу поддержки визуальных элементов Power BI (`pbicvsupport@microsoft.com`).  
**Имейте в виду, что визуальный элемент должен быть доступен в [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals) и [сертифицирован](https://powerbi.microsoft.com/en-us/documentation/powerbi-custom-visuals-certified/).**
