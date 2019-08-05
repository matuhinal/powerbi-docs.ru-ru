---
title: События отрисовки
description: Визуальные элементы Power BI могут уведомлять Power BI о том, что они готовы к экспорту в Power Point/PDF
author: Yarovinsky
ms.author: alexyar
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 46166b3503a770e033b98474fcf9240235296cc2
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425098"
---
# <a name="event-service"></a>Служба событий

Новый API состоит из трех методов (started, finished или failed), которые должны вызываться во время отрисовки.

При запуске отрисовки код пользовательского визуального элемента вызывает метод renderingStarted, чтобы указать, что процесс отрисовки запущен.

Если отрисовка успешно завершена, код пользовательского визуального элемента немедленно вызовет метод `renderingFinished`, уведомляющий прослушиватели (**в основном это "экспорт в PDF" и "экспорт в PowerPoint**") о том, что изображение визуального элемента готово.

Во время процесса отрисовки может возникнуть проблема, препятствующая успешному выполнению пользовательского визуального элемента. Код пользовательского визуального элемента должен вызывать метод `renderingFailed`, уведомляющий прослушиватель о том, что процесс отрисовки не завершен. Этот метод также предоставляет необязательную строку, указывающую на причину сбоя.

## <a name="usage"></a>Usage

```typescript
export interface IVisualHost extends extensibility.IVisualHost {
    eventService: IVisualEventService ;
}

/**
 * An interface for reporting rendering events
 */
export interface IVisualEventService {
    /**
     * Should be called just before the actual rendering was started. 
     * Usually at the very start of the update method.
     *
     * @param options - the visual update options received as update parameter
     */
    renderingStarted(options: VisualUpdateOptions): void;

    /**
     * Shoudl be called immediately after finishing successfull rendering.
     * 
     * @param options - the visual update options received as update parameter
     */
    renderingFinished(options: VisualUpdateOptions): void;

    /**
     * Called when rendering failed with optional reason string
     * 
     * @param options - the visual update options received as update parameter
     * @param reason - the option failure reason string
     */
    renderingFailed(options: VisualUpdateOptions, reason?: string): void;
}
```

### <a name="simple-sample-the-visual-hasnt-any-animations-on-rendering"></a>Простой пример. Визуальный элемент не имеет никаких анимаций при отрисовке

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            this.events.renderingFinished(options);
        }
```

### <a name="sample-the-visual-with-animation"></a>Пример. Визуальный элемент с анимацией

Если визуальный элемент содержит анимации или асинхронные функции для отрисовки, метод `renderingFinished` должен вызываться после анимации или внутри асинхронной функции.

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        private element: HTMLElement;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            this.element = options.element;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            // read more https://github.com/d3/d3-transition/blob/master/README.md#transition_end
            d3.select(this.element).transition().duration(100).style("opacity","0").end().then(() => {
                // renderingFinished called after transition end
                this.events.renderingFinished(options);
            });
        }
```

## <a name="rendering-events-for-visual-certification"></a>События отрисовки для сертификации визуального элемента

Поддержка событий отрисовки визуальным элементом является одним из требований при сертификации визуальных элементов. Дополнительные сведения см. в [требованиях к сертификации](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements).
