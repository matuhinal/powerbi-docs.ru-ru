---
title: Рекомендации по производительности Power BI Embedded
description: Эта статья содержит руководство для рекомендаций по внедрению лучших методов встроенной аналитики.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: 7284532d95cce780f4022477faab9033adcd764a
ms.sourcegitcommit: a175faed9378a7d040a08ced3e46e54503334c07
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "79492613"
---
# <a name="power-bi-embedded-performance-best-practices"></a>Рекомендации по производительности Power BI Embedded

В этой статье приводятся рекомендации по ускорению отрисовки отчетов, панелей мониторинга и плиток в вашем приложении.

> [!Note]
> Помните, что время загрузки в основном зависит от элементов, относящихся к отчету и самим данным, включая визуальные элементы, размер данных, а также сложность запросов и вычисляемых показателей. См. сведения в руководстве по [оптимизации Power BI](../../guidance/power-bi-optimization.md).

## <a name="update-tools-and-sdk-packages"></a>Средства обновления и пакеты SDK

Сохраняйте средства и пакеты SDK обновленными.

* Всегда используйте последнюю версию Power BI Desktop, доступную [здесь](https://powerbi.microsoft.com/desktop/).

* Чтоб установить последнюю версию пакета SDK клиента Power BI, см. [здесь](https://github.com/Microsoft/PowerBI-JavaScript). Мы постоянно выпускаем улучшенные версии, поэтому время от время следите за нами.

## <a name="embed-parameters"></a>Параметры внедрения

Метод `powerbi.embed(element, config)` получает элемент и конфигурацию. В параметрах конфигурации есть поля, которые влияют на производительность.

### <a name="embed-url"></a>URL-адрес внедрения

Избегайте самостоятельного создания URL-адреса внедрения. Вместо этого убедитесь, что у вас есть URL-адрес внедрения, вызвав API [Получение отчетов](/rest/api/power-bi/reports/getreportsingroup), [Получение панелей мониторинга](/rest/api/power-bi/dashboards/getdashboardsingroup) или [Получение плиток](/rest/api/power-bi/dashboards/gettilesingroup). Новый параметр **_config_** добавлен в URL-адрес, который используется для улучшения производительности.

### <a name="permissions"></a>Разрешения

Если вы не собираетесь внедрить отчет в режим правки, укажите разрешения **Представление**. Таким образом код внедрения не инициализирует компоненты, которые используются в режиме правки.

### <a name="filters-bookmarks-and-slicers"></a>Фильтры, закладки и срезы

Обычно визуальные элементы отчета сохраняются с помощью кэшированных данных. Кэшированные данные используются для обеспечения воспринимаемой производительности. При выполнении запросов отчеты преобразовываются для просмотра кэшированных данных. Если предусмотрены фильтры, закладки или срезы, кэшированные данные не используются, а визуальные элементы отображаются только после завершения визуального запроса.

Если вы встраиваете отчеты с теми же фильтрами, закладками и срезами, для повышения производительности сохраните отчет с уже примененными фильтрами, закладками и срезами. Таким образом отчет будет преобразован для просмотра с кэшированными данными, которые включают в себя фильтры, закладки и срезы.

## <a name="switching-between-reports"></a>Переключение между отчетами

При встраивании нескольких отчетов в один и тот же компонент iFrame не создавайте новый компонент iFrame для каждого отчета. Вместо этого используйте `powerbi.embed(element, config)` с другой конфигурацией для встраивания нового отчета.

> [!NOTE]
> Переключение между отчетами для сценария "Данные, принадлежащие приложению" может быть неэффективным из-за необходимости создания токена внедрения.

## <a name="query-caching"></a>Кэширование запросов

Организации с емкостью Power BI Premium или Power BI Embedded могут воспользоваться кэшированием запросов для ускорения работы с отчетами, связанными с определенным набором данных.

[Узнайте больше о кэшировании запросов в Power BI Premium](../../power-bi-query-caching.md).

## <a name="preload"></a>Предварительная загрузка

Чтобы повысить производительность конечного пользователя, используйте `powerbi.preload()`. Метод `powerbi.preload()` загружает JavaScript, CSS-файлы и другие артефакты, которые позже используются для внедрения отчета.

Если внедрение отчета не выполняется сразу, вызовите `powerbi.preload()`. Так, если внедренное содержимое Power BI не отображается на домашней странице, используйте `powerbi.preload()` для скачивания и кэширования артефактов, которые используются для внедрения содержимого.

## <a name="bootstrapping-the-iframe"></a>Начальная загрузка iFrame

> [!NOTE]
> Для начальной загрузки iFrame требуется [пакет SDK клиента Power BI](https://github.com/Microsoft/PowerBI-JavaScript) версии 2.9.

`powerbi.bootstrap(element, config)` позволяет начать внедрение до того, как все необходимые параметры будут доступны. API начальной загрузки подготавливает и инициализирует iFrame.
При использовании API начальной загрузки все так же необходимо вызывать `powerbi.embed(element, config)` для одного и того же элемента HTML.

Например, одним из вариантов использования этой функции является параллельное выполнение начальной загрузки iFrame и внутренних вызовов для внедрения.
> [!TIP]
> Используйте API начальной загрузки, когда можно создать iFrame, прежде чем он будет виден конечному пользователю.

[Узнайте больше о начальной загрузке iFrame](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Bootstrap-For-Better-Performance).

## <a name="measure-performance"></a>Показатель производительности

### <a name="performance-events"></a>События производительности

Для измерения встроенной производительности можно использовать два события:

1. Событие загрузки: время до инициализации отчета (логотип Power BI исчезнет после завершения загрузки).
2. Событие отрисовки: время до полной отрисовки отчета с использованием фактических данных. Событие отрисовки вызывается каждый раз при повторном преобразовании отчета для просмотра (например, после применения фильтров). Чтобы измерить отчет, убедитесь, что вы выполняете вычисления в первом возникшем событии.

Кэшированные данные преобразовываются для просмотра, когда становятся доступны, но дополнительные события не создаются.

[Узнайте больше об обработке событий](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events).

### <a name="performance-analyzer"></a>Анализатор производительности

Чтобы проверить производительность элементов отчета, вы можете использовать Анализатор производительности в Power BI Desktop.
Анализатор производительности позволит вам просматривать и записывать журналы, которые измеряют производительность каждого элемента отчета.

[Узнайте больше об Анализаторе производительности](../../desktop-performance-analyzer.md).

> [!NOTE]
> Не забывайте сравнивать производительность встроенного отчета с производительностью на сайте powerbi.com. Это может помочь вам понять причину проблем с производительностью.

## <a name="next-steps"></a>Дальнейшие действия

* [Руководство по оптимизации Power BI](../../guidance/power-bi-optimization.md)
* [Устранение неполадок внедренного приложения](embedded-troubleshoot.md)
* [Часто задаваемые вопросы о Power BI Embedded](embedded-faq.md)