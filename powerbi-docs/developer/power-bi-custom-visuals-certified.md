---
title: Сертифицированные визуальные элементы Power BI
description: Требования к пользовательскому визуальному элементу для сертификации и процедура его отправки. А также список сертифицированных визуальных элементов Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 12/02/2019
ms.openlocfilehash: c39b96122016746905ea09c0983adf50356f0c77
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2020
ms.locfileid: "75221972"
---
# <a name="get-a-power-bi-visual-certified"></a>Получите сертификацию для визуального элемента Power BI

Сертифицированными визуальными элементами Power BI называются визуальные элементы из магазина *Marketplace*, которые соответствуют определенным *требованиям к коду* и протестированы и одобрены *командой Microsoft Power BI*. Проверки гарантируют, что визуализация не обращается к внешним службам и ресурсам.

Сертифицированные и [стандартные визуализации Power BI](power-bi-custom-visuals.md) используются одинаково. Их можно добавлять в [Power BI Desktop](../desktop-what-is-desktop.md), [службу Power BI](../power-bi-service-overview.md), а также просматривать в [Power BI Mobile](../consumer/mobile/mobile-apps-for-mobile-devices.md) и [Power BI Embedded](embedding.md).

Процесс сертификации является необязательным. Разработчики сами решают, нужно ли сертифицировать визуальные элементы Power BI, доступные в Marketplace. Сертифицированные визуализации Power BI предусматривают дополнительные возможности. Например, вы можете [экспортировать их в PowerPoint](../consumer/end-user-powerpoint.md) или добавлять для отображения в сообщениях электронной почты, получаемых при оформлении [подписки на страницы отчета](../consumer/end-user-subscribe.md).

Несертифицированные визуальные элементы Power BI необязательно являются небезопасными. Некоторые визуальные элементы не проходят сертификацию, так как не соответствуют одному или нескольким [требованиям сертификации](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements). Например, визуальный элемент может подключаться к внешней службе, такой как визуальные элементы карты, или использовать коммерческие библиотеки.

Если вы как веб-разработчик заинтересованы в создании собственных визуализаций Power BI и их добавлении в  [Microsoft AppSource](https://appsource.microsoft.com), начните с руководства по  [разработке визуализаций Power BI](visuals/custom-visual-develop-tutorial.md).

> [!NOTE]
> **Корпорация Майкрософт***не* является автором сторонних визуализаций Power BI. Чтобы проверить функциональные возможности сторонних визуализаций, мы рекомендуем клиентам обращаться к автору напрямую.

> [!IMPORTANT]
> Корпорация Майкрософт может удалять визуальные элементы Power BI из [списка сертифицированных](#certified-power-bi-visuals).

## <a name="certification-requirements"></a>Требования к сертификации

Чтобы [сертифицировать](#get-a-power-bi-visual-certified) свою визуализацию Power BI, проверьте, соответствует ли она требованиям, перечисленным в этом разделе. 

> [!TIP]
> Мы рекомендуем использовать EsLint с набором правил безопасности по умолчанию для предварительной проверки кода перед отправкой.

* Визуализация должна быть утверждена на Панели мониторинга продаж или в Центре партнеров Майкрософт. Визуальный элемент Power BI должен быть опубликован в нашем магазине [Marketplace](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals).
* Визуализация Power BI должна быть создана с помощью *API версии 2.5* или выше.
* Репозиторий кода должен быть доступным команде Power BI для проверки. Например, вы должны предоставить нам доступ на чтение исходного кода (JavaScript или TypeScript) на GitHub.

    >[!NOTE]
    > Предоставлять код для общего доступа в Github не нужно.

* Требования к репозиторию кода:
  * Визуализация должна содержать следующие файлы:
    * .gitignore
    * capabilities.json
    * pbiviz.json
    * package.json
    * package-lock.json
    * tsconfig.json
  * Визуализация не должна содержать папку *node_modules* (добавьте *node_modules* в файл с расширением .gitingore*).
  * Команда *npm install* не должна возвращать ошибки.
  * Команда *npm audit* не должна возвращать предупреждения высокого или среднего уровня.
  * Команда *pbiviz package* не должна возвращать ошибки.
  * Визуализация должна содержать [TSlint от Майкрософт](https://www.npmjs.com/package/tslint-microsoft-contrib) без переопределенных конфигураций. Эта команда не должна возвращать ошибки, связанные с оформлением кода.
   * Скомпилированный пакет визуального элемента Power BI должен соответствовать отправленному пакету.
* Требования к исходному коду:
   * Визуализация Power BI должна поддерживать [API событий отображения](./visuals/event-service.md).
   * Убедитесь, что произвольный или динамический код не выполняется (плохо: eval(), небезопасно использовать settimeout(), requestAnimationFrame(), setinterval (некоторые функции с вводом данных пользователем), запуск введенных пользователем данных).
   * Убедитесь, что модель DOM обрабатывается безопасно (плохо: innerHTML, D3.html (<некоторые введенные пользователем данные>), применяйте очистку для введенных пользователем данных перед их добавлением в модель DOM.
   * Убедитесь, что в консоли браузера отсутствуют ошибки или исключения JavaScript для любых входных данных. Пользователи могут применять визуализацию Power BI с другим диапазоном непредвиденных данных, поэтому эта визуализация не должна приводить к сбою. В качестве тестового набора данных можно использовать [этот пример отчета](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix).

* Если некоторые свойства в файле *capabilities.json* были изменены, убедитесь, что существующие отчеты пользователя не нарушены.

* Убедитесь, что визуализация Power BI соответствует [этим рекомендациям](./guidelines-powerbi-visuals.md).
    
* В коде могут использоваться только открытые и доступные для просмотра компоненты OSS, например общедоступные библиотеки JavaScript или TypeScript. Исходный код должен быть доступен для просмотра и не содержать известные уязвимости. Мы не можем проверить пользовательский визуальный элемент, использующий коммерческие компоненты.

* Визуализация Power BI не должна обращаться к внешним службам и ресурсам. Например, запросы HTTP/S или WebSocket не должны отправляться из Power BI во внешние службы. 

## <a name="submitting-a-power-bi-visual-for-certification"></a>Отправка визуализации Power BI на сертификацию

Вы можете подать заявку на сертификацию визуализации Power BI командой Power BI через Центр партнеров.

>[!TIP]
>Процесс сертификации визуализации Power BI может занять некоторое время. Если вы создаете новую визуализацию Power BI, мы рекомендуем опубликовать ее в Центре партнеров, прежде чем подавать заявку на сертификацию Power BI. Так публикация визуализации не будет отложена.

Чтобы подать заявку на сертификацию визуализацию Power BI, сделайте следующее:

1. Войдите в Центр партнеров.
2. На странице **Обзор** выберите визуализацию Power BI и перейдите на страницу **настройки продукта**.
3. Установите флажок **Запросите сертификацию Power BI**.
4. На странице **Проверка и публикация** в текстовом поле **Примечания о сертификации** укажите ссылку на исходный код и учетные данные, требуемые для получения доступа.

>[!NOTE]
> Если в ходе отправки визуализации Power BI в AppSource вам потребуется [Панель мониторинга продаж](https://docs.microsoft.com/office/dev/store/use-the-seller-dashboard-to-submit-to-the-office-store) (старое средство управления), ознакомьтесь с [этими инструкциями](seller-dashboard.md#seller-dashboard-certification-submission-process).

## <a name="certified-power-bi-visuals"></a>Сертифицированные визуальные элементы Power BI

Ниже перечислены сертифицированные визуальные элементы Power BI. Чтобы открыть визуальный элемент Power BI в AppSource, щелкните ссылку. Если доступно видео, вы можете просмотреть его, щелкнув ссылку.

* [3AG Systems — линейчатая диаграмма абсолютного расхождения](https://appsource.microsoft.com/product/power-bi-visuals/WA104381802)
*  [3AG Systems — линейчатая диаграмма относительного расхождения](https://appsource.microsoft.com/product/power-bi-visuals/WA104381912)
*  [3AG Systems — гистограмма относительного расхождения](https://appsource.microsoft.com/product/power-bi-visuals/WA104381803)
*  [3AG Systems — гистограмма расхождения](https://appsource.microsoft.com/product/power-bi-visuals/WA104381724)
* [Расширенная визуализация кольцевого графика (полная версия)](https://appsource.microsoft.com/product/power-bi-visuals/WA104381941)
*  [Расширенная визуализация кольцевого графика (упрощенная версия)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858)
*  [Расширенная визуализация графа](https://appsource.microsoft.com/product/power-bi-visuals/WA104382086)
*  [Расширенная визуализация сети](https://appsource.microsoft.com/product/power-bi-visuals/WA104381942)
*  [Расширенная визуализация TimeSeries (полная версия)](https://appsource.microsoft.com/product/power-bi-visuals/WA104381943)
*  [Круговая диаграмма с индивидуальным радиусом срезов](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759)
*  [Календарь Beyondsoft](https://appsource.microsoft.com/product/power-bi-visuals/WA104381096)
*  [Петлеобразная диаграмма от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838)
*  [Диаграмма "Ящик с усами"](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831)
* [Диаграмма "ящик с усами" от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381351)
*  [Клетчатая диаграмма от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380836)
*  [Пузырьковая диаграмма от Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381340)
*  [Bullet Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755), **[ссылка на видео](https://youtu.be/AOlsFYkfkcw)**
* [Диаграмма с маркерами](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755)
*  [Bullet Chart by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380953), **[ссылка на видео](https://youtu.be/mtvUNl9bMjA)**
* [Календарь от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381844)
*  [Календарь от Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146)
*  [Диаграмма "японские свечи" от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380952), **[ссылка на видео](https://youtu.be/nT_18gyRxPo)**
*  [Карточки с состояниями от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380967)
*  [Срез Chiclet](https://appsource.microsoft.com/product/power-bi-visuals/WA104380756)
*  [Хордовая диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761), **[ссылка на видео](https://youtu.be/AQvd2FhRyCI)**
*  [Круговой датчик от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837)
*  [Таблица кластеров](https://appsource.microsoft.com/product/power-bi-visuals/WA104380806)
* [Настраиваемый календарь от Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381179)
* [Цилиндрический датчик от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874)
*  [Датчик с циферблатом](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184)
[Точечная диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380760)
*  [Точечная диаграмма от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380949), **[ссылка на видео](https://youtu.be/By16pX9KT40)**
*  [Детализированная картограмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104381045)
*  [Детализированная фоновая картограмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104381044)
*  [Детализированная гистограмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380857), **[ссылка на видео](https://youtu.be/lBy2gQQ5YsQ)**
*  [Детализированная гистограмма временных данных](https://appsource.microsoft.com/product/power-bi-visuals/WA104380881), **[ссылка на видео](https://youtu.be/T_mRou18vx0)**
*  [Детализированная кольцевая диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858), **[ссылка на видео](https://youtu.be/AUVFrSHmPeo)**
*  [Dual KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104380774)
*  [Динамическая подсказка от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380983)
*  [Расширенная точечная диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380762), **[ссылка на видео](https://youtu.be/xCfM0cjM4do)**
*  [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112)
*  [Enlighten Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380960)
*  [Enlighten Stack Shuffle](https://appsource.microsoft.com/product/power-bi-visuals/WA104380849)
*  [Вафельная диаграмма Enlighten](https://appsource.microsoft.com/product/power-bi-visuals/WA104380850)
*  [Filter by List от Devscope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381413), **[ссылка на видео](https://youtu.be/RetEWGwBu0I)**
*  [График с направленной силой](https://appsource.microsoft.com/product/power-bi-visuals/WA104380764), **[ссылка на видео](https://youtu.be/YsTa7uyJ4sg)**
*  [Воронка с источником от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381334)
*  [Диаграмма Ганта](https://appsource.microsoft.com/product/power-bi-visuals/WA104380765), **[ссылка на видео](https://youtu.be/qJ7s_KrGiUU)**
* [Ганта диаграмма от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381364)
*  [Гистограммы "Земной шар"](https://appsource.microsoft.com/product/power-bi-visuals/WA104381344)
*  [Сетка от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380825)
*  [Иерархическая диаграмма от Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381333), **[ссылка на видео](https://youtu.be/0ZGzJaq_KT4)**
*  [Гистограмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380776)
*  [Гистограмма с точками от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381032)
* [Горизонтальная линейчатая диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104381230)
*  [Горизонтальная воронка от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846)
*  [Изображение от CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381297)
*  [Сетка изображения](https://appsource.microsoft.com/product/power-bi-visuals/WA104381355)
*  [Конструктор инфографики](https://appsource.microsoft.com/product/power-bi-visuals/WA104380898)
*  [Диаграмма с ключевыми показателями эффективности от Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381432)
*  [Столбец КПЭ от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380996)
*  [Сетка ключевых показателей эффективности от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380947)
*  [Индикатор ключевого показателя эффективности](https://appsource.microsoft.com/product/power-bi-visuals/WA104380832)
*  [Область КПЭ от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380946)
* [Линейный датчик от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821)
*  [Линейно-точечная диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380766)
*  [Диаграмма Mekko](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785), **[ссылка на видео](https://youtu.be/90FLCKpgicA)**
*  [Несколько КПЭ](https://appsource.microsoft.com/product/power-bi-visuals/WA104381763)
*  [Обзор от CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381477)
*  [Ось воспроизведения (динамический срез)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380981)
*  [Ключевой показатель эффективности производительности](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083), [ссылка на видео](https://youtu.be/IvfIP3E6-1Q)
*  [Матрица КПЭ производительности](https://appsource.microsoft.com/product/power-bi-visuals/WA104381299), **[ссылка на видео](https://youtu.be/1enze8pcGzY)**
*  [Диаграмма "Пульс"](https://appsource.microsoft.com/product/power-bi-visuals/WA104381006), **[ссылка на видео](https://youtu.be/DQWdcQtjDVw)**
*  [Диаграмма с квадрантами от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381011)
*  [Лепестковая диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380771)
*  [Кольцевая диаграмма от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824)
*  [Поворотная диаграмма от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381007)
*  [Sankey](https://appsource.microsoft.com/product/power-bi-visuals/WA104380777), **[ссылка на видео](https://youtu.be/WWP9wVUHGaA)**
*  [Точечная диаграмма от Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381703)
*  [Полоса прокрутки](https://appsource.microsoft.com/product/power-bi-visuals/WA104381018)
*  [Смарт-фильтр от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380859), **[ссылка на видео](https://youtu.be/gcJsDDRQq28)**
*  [Спарклайн от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910), **[ссылка на видео](https://youtu.be/0m3Vnvso9tY)**
*  [График потока](https://appsource.microsoft.com/product/power-bi-visuals/WA104380772)
*  [Диаграмма "Солнечные лучи"](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767)
*  [Synoptic Panel от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380873)
*  [Диаграмма "Тепловая карта"](https://appsource.microsoft.com/product/power-bi-visuals/WA104380818)
*  [Тахометр](https://appsource.microsoft.com/product/power-bi-visuals/WA104380937), **[ссылка на видео](https://youtu.be/C3OXdETbS9o)**
*  [Фильтрация текста](https://appsource.microsoft.com/product/power-bi-visuals/WA104381309)
*  [Текстовая оболочка от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826)
*  [Thermometer от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847)
*  [Срез Time Brush](https://appsource.microsoft.com/product/power-bi-visuals/WA104380798)
*  [Срез временной шкалы](https://appsource.microsoft.com/product/power-bi-visuals/WA104380786), **[ссылка на видео](https://youtu.be/ozMtZ4_NZ10)**
*  [Временная шкала от CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381427), [ссылка на видео](https://youtu.be/szNi9YgXFJc)
*  [Диаграмма-торнадо](https://appsource.microsoft.com/product/power-bi-visuals/WA104380768), **[ссылка на видео](https://www.youtube.com/watch?v=AQvd2FhRyCI)**
*  [Диаграмма продаж от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380823)
* [Карточка КПЭ Ultimate](https://appsource.microsoft.com/product/power-bi-visuals/WA104381977)
*  [Диаграмма отклонений Ultimate](https://appsource.microsoft.com/product/power-bi-visuals/WA104381140), **[ссылка на видео](https://youtu.be/pDYF8iZxERs)**
*  [Каскадная диаграмма Ultimate](https://appsource.microsoft.com/product/power-bi-visuals/WA104380956), **[ссылка на видео](https://youtu.be/0BZsVCQdEkc)**
*  [Список пользователей от CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381426)
*  [Диаграмма Венна от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381231)
*  [График "Скрипка"](https://appsource.microsoft.com/product/power-bi-visuals/WA104381947)
*  [Визуальный элемент Visio](https://appsource.microsoft.com/product/power-bi-visuals/WA104381132)
*  [Вафельная диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049), **[ссылка на видео](https://youtu.be/1vRqYUsm3Vk)**
*  [Облако слов](https://appsource.microsoft.com/product/power-bi-visuals/WA104380752), **[ссылка на видео](https://youtu.be/AblTenl9fqo)**

## <a name="faq"></a>Часто задаваемые вопросы

Дополнительные сведения о визуальных элементах см. в разделе [Часто задаваемые вопросы о сертифицированных визуальных элементах](power-bi-custom-visuals-faq.md#certified-power-bi-visuals).

## <a name="next-steps"></a>Дальнейшие действия

* [Разработка пользовательского визуального элемента Power BI](../developer/custom-visual-develop-tutorial.md)
* [Список видео Майкрософт, посвященных пользовательским визуальным элементам, на сайте YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [Визуализации в Power BI](../visuals/power-bi-report-visualizations.md)  
* [Пользовательские визуализации в Power BI](power-bi-custom-visuals.md)  
* [Публикация визуальных элементов Power BI в Microsoft AppSource](../developer/office-store.md)  

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](https://community.powerbi.com/)
