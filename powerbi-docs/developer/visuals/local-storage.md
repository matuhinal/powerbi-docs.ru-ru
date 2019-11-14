---
title: API локального хранилища для визуальных элементов Power BI
description: В этой статье описывается получение доступа к локальному хранилищу браузера с использованием API визуальных элементов Power BI
author: uve
ms.author: v-grniki
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 10/31/2019
ms.openlocfilehash: 3b6746b611a41ddfb471008f5aefa4f7dc391456
ms.sourcegitcommit: 8cc2b7510aae76c0334df6f495752e143a5851c4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73432804"
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

По умолчанию API локального хранилища для пользовательских визуальных элементов не активирован. Если вы хотите активировать его для пользовательского визуального элемента, направьте запрос в службу поддержки пользовательских визуальных элементов Power BI (`pbicvsupport@microsoft.com`)
