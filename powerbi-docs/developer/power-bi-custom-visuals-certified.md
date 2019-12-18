---
title: Сертифицированные визуальные элементы Power BI
description: Требования к пользовательскому визуальному элементу для сертификации и процедура его отправки. А также список уже сертифицированных визуальных элементов Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 12/02/2019
ms.openlocfilehash: 0a39496ade27cd45fae116eea92ef4b472e04582
ms.sourcegitcommit: 5bb62c630e592af561173e449fc113efd7f84808
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2019
ms.locfileid: "74999751"
---
# <a name="get-a-power-bi-visual-certified"></a>Получите сертификацию для визуального элемента Power BI

Сертифицированными визуальными элементами Power BI называются визуальные элементы из магазина *Marketplace*, которые соответствуют определенным *требованиям к коду* и протестированы и одобрены *командой Microsoft Power BI*. Проверки гарантируют, что визуализация не обращается к внешним службам и ресурсам.

Сертифицированные и [стандартные визуализации Power BI](power-bi-custom-visuals.md) используются одинаково. Их можно добавлять в [Power BI Desktop](../desktop-what-is-desktop.md), [службу Power BI](../power-bi-service-overview.md), а также просматривать в [Power BI Mobile](../consumer/mobile/mobile-apps-for-mobile-devices.md) и [Power BI Embedded](embedding.md).

Процесс сертификации является необязательным. Разработчики сами решают, нужно ли сертифицировать визуализации Power BI, доступные в Marketplace. Сертифицированные визуализации Power BI предусматривают дополнительные возможности. Например, вы можете [экспортировать их в PowerPoint](../consumer/end-user-powerpoint.md) или добавлять для отображения в сообщениях электронной почты, получаемых при оформлении [подписки на страницы отчета](../consumer/end-user-subscribe.md).

Несертифицированные визуальные элементы Power BI необязательно являются небезопасными. Некоторые визуальные элементы не проходят сертификацию, так как не соответствуют одному или нескольким [требованиям сертификации](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements). Например, визуальный элемент может подключаться к внешней службе, такой как визуальные элементы карты, или использовать коммерческие библиотеки.

Если вы как веб-разработчик заинтересованы в создании собственных визуализаций Power BI и их добавлении в  [Microsoft AppSource](https://appsource.microsoft.com), начните с руководства по  [разработке визуализаций Power BI](visuals/custom-visual-develop-tutorial.md).

> [!NOTE]
> **Корпорация Майкрософт** *не* является автором сторонних визуализаций Power BI. Чтобы проверить функциональные возможности сторонних визуализаций, мы рекомендуем клиентам обращаться к автору напрямую.

> [!IMPORTANT]
> Корпорация Майкрософт может удалять визуализации Power BI из [списка сертифицированных](#list-of-power-bi-visuals-that-have-been-certified).

## <a name="certification-requirements"></a>Требования к сертификации

Чтобы [сертифицировать](#get-a-power-bi-visual-certified) свою визуализацию Power BI, проверьте, соответствует ли она требованиям, перечисленным в этом разделе. 

> [!TIP]
> Мы рекомендуем использовать EsLint с набором правил безопасности по умолчанию для предварительной проверки кода перед отправкой.

* Визуализация должна быть утверждена на Панели мониторинга продаж или в Центре партнеров Майкрософт. Визуализация Power BI должна быть опубликована в нашем магазине [Marketplace](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals).
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
   * Скомпилированный пакет визуализации Power BI должен соответствовать отправленному пакету (хэш MD5 обоих файлов должен быть одинаковым).
* Требования к исходному коду:
   * Визуализация Power BI должна поддерживать [API событий отображения](https://microsoft.github.io/PowerBI-visuals/docs/how-to-guide/rendering-events/).
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

## <a name="list-of-power-bi-visuals-that-have-been-certified"></a>Список визуальных элементов Power BI, которые прошли сертификацию

| Ссылка | Видеотехника |
| --- | --- |
| [3AG Systems — линейчатая диаграмма относительного расхождения](https://appsource.microsoft.com/en/product/power-bi-visuals/WA104381912) | |
| [3AG Systems — гистограмма относительного расхождения](https://appsource.microsoft.com/product/power-bi-visuals/WA104381803) | |
| [Изображение расширенного кольцевого графика](https://appsource.microsoft.com/product/power-bi-visuals/WA104381941) | |
| [Расширенная визуализация сети](https://appsource.microsoft.com/product/power-bi-visuals/WA104381942) | |
| [Расширенная визуализация TimeSeries](https://appsource.microsoft.com/product/power-bi-visuals/WA104381943) | |
| [Изображение расширенной смешанной диаграммы](https://appsource.microsoft.com/product/power-bi-visuals/WA104381944) | |
| [Круговая диаграмма с индивидуальным радиусом срезов](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759) | |
| [Календарь Beyondsoft](https://appsource.microsoft.com/product/power-bi-visuals/WA104381096) | |
| [Петлеобразная диаграмма от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838) | [Видео](https://youtu.be/So5xKMSpVJI) |
| [Диаграмма "Ящик с усами"](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831) | |
| [Диаграмма "ящик с усами" от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381351) | [Видео](https://youtu.be/JoHaFLfhXdo) |
| [Клетчатая диаграмма от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380836) | [Видео](https://youtu.be/hA3DOsvn2xY) |
| [Пузырьковая диаграмма от Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381340) | |
| [Диаграмма с маркерами](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755) | [Видео](https://youtu.be/AOlsFYkfkcw) |
| [Диаграмма с маркерами от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380953) | [Видео](https://youtu.be/mtvUNl9bMjA) |
| [Календарь от Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146) | |
| [Диаграмма "японские свечи" от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380952) | [Видео](https://youtu.be/nT_18gyRxPo) |
| [Карточки с состояниями от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380967) | |
| [Срез Chiclet](https://appsource.microsoft.com/product/power-bi-visuals/WA104380756) | |
| [Хордовая диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761) | [Видео](https://youtu.be/AQvd2FhRyCI) |
| [Круговой датчик от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837) | [Видео](https://youtu.be/9NHXALkBXuY) |
| [Таблица кластеров](https://appsource.microsoft.com/product/power-bi-visuals/WA104380806) | |
| [Цилиндрический датчик от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | [Видео](https://youtu.be/DgdoWi7Gcxo) |
| [Датчик с циферблатом](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) | |
| [Точечная диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380760) | |
| [Точечная диаграмма от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380949) | [Видео](https://youtu.be/By16pX9KT40) |
| [Детализированная картограмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104381045) | |
| [Детализированная фоновая картограмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104381044) | |
| [Детализированная гистограмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380857) | [Видео](https://youtu.be/lBy2gQQ5YsQ) |
| [Детализированная гистограмма временных данных](https://appsource.microsoft.com/product/power-bi-visuals/WA104380881) | [Видео](https://youtu.be/T_mRou18vx0) |
| [Детализированная кольцевая диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | [Видео](https://youtu.be/AUVFrSHmPeo) |
| [Dual KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104380774) | |
| [Динамическая подсказка от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380983) | [Видео](https://youtu.be/Z-tl97BpEr0) |
| [Расширенная точечная диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380762) | [Видео](https://youtu.be/xCfM0cjM4do) |
| [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112) | |
| [Enlighten Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380960) | |
| [Enlighten Stack Shuffle](https://appsource.microsoft.com/product/power-bi-visuals/WA104380849) | |
| [Вафельная диаграмма Enlighten](https://appsource.microsoft.com/product/power-bi-visuals/WA104380850) | |
| [Filter by List от Devscope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381413) | [Видео](https://youtu.be/RetEWGwBu0I) |
| [График с направленной силой](https://appsource.microsoft.com/product/power-bi-visuals/WA104380764) | [Видео](https://youtu.be/YsTa7uyJ4sg) |
| [Воронка с источником от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381334) | [Видео](https://youtu.be/R_EcimsLI8U) |
| [Диаграмма Ганта](https://appsource.microsoft.com/product/power-bi-visuals/WA104380765) | [Видео](https://youtu.be/qJ7s_KrGiUU) |
| [Ганта диаграмма от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381364) | [Видео](https://youtu.be/vJLV9JRCpI8) |
| [Гистограммы "Земной шар"](https://appsource.microsoft.com/product/power-bi-visuals/WA104381344) | |
| [Сетка от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380825) | [Видео](https://youtu.be/VOPoDJgZfOY) |
| [Иерархическая диаграмма от Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381333) | [Видео](https://youtu.be/0ZGzJaq_KT4) |
| [Гистограмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380776) | |
| [Гистограмма с точками от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381032) | [Видео](https://youtu.be/-ILF--wExrw) |
| [Горизонтальная воронка от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) | [Видео](https://youtu.be/SudZei68PPo) |
| [Изображение от CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381297) | |
| [Сетка изображения](https://appsource.microsoft.com/product/power-bi-visuals/WA104381355) | |
| [Конструктор инфографики](https://appsource.microsoft.com/product/power-bi-visuals/WA104380898) | |
| [Диаграмма с ключевыми показателями эффективности от Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381432) | |
| [Столбец КПЭ от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380996) | [Видео](https://youtu.be/rU0xoOlIq1U) |
| [Сетка ключевых показателей эффективности от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380947) | [Видео](https://youtu.be/dM4PvZh71V0) |
| [Индикатор ключевого показателя эффективности](https://appsource.microsoft.com/product/power-bi-visuals/WA104380832) | |
| [Область КПЭ от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380946) | [Видео](https://youtu.be/cudG4gsZ2V8) |
| [Линейный датчик от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821) | [Видео](https://youtu.be/7_jFaM30dkc) |
| [Линейно-точечная диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380766) | |
| [Диаграмма Mekko](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785) | [Видео](https://youtu.be/90FLCKpgicA) |
| [Несколько КПЭ](https://appsource.microsoft.com/product/power-bi-visuals/WA104381763) | |
| [Обзор от CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381477) | |
| [Ось воспроизведения (динамический срез)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380981) | |
| [Ключевой показатель эффективности производительности](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) | [Видео](https://youtu.be/IvfIP3E6-1Q) |
| [Матрица КПЭ производительности](https://appsource.microsoft.com/product/power-bi-visuals/WA104381299) | [Видео](https://youtu.be/1enze8pcGzY) |
| [Диаграмма "Пульс"](https://appsource.microsoft.com/product/power-bi-visuals/WA104381006) | [Видео](https://youtu.be/DQWdcQtjDVw) |
| [Диаграмма с квадрантами от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381011) | [Видео](https://youtu.be/ppBnyhqWNC0) |
| [Лепестковая диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104380771) | |
| [Кольцевая диаграмма от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824) | [Видео](https://youtu.be/pDToHDFHnq8) |
| [Поворотная диаграмма от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381007) | [Видео](https://youtu.be/d5xBCMmb3hU) |
| [Диаграмма Sankey](https://appsource.microsoft.com/product/power-bi-visuals/WA104380777) | [Видео](https://youtu.be/WWP9wVUHGaA) |
| [Точечная диаграмма от Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381703) | |
| [Полоса прокрутки](https://appsource.microsoft.com/product/power-bi-visuals/WA104381018) | |
| [Смарт-фильтр от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380859) | [Видео](https://youtu.be/gcJsDDRQq28) |
| [Спарклайн от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910) | [Видео](https://youtu.be/0m3Vnvso9tY) |
| [График потока](https://appsource.microsoft.com/product/power-bi-visuals/WA104380772) | |
| [Диаграмма "Солнечные лучи"](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767) | |
| [Synoptic Panel от OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380873) | |
| [Диаграмма "Тепловая карта"](https://appsource.microsoft.com/product/power-bi-visuals/WA104380818) | |
| [Тахометр](https://appsource.microsoft.com/product/power-bi-visuals/WA104380937) | [Видео](https://youtu.be/C3OXdETbS9o) |
| [Фильтрация текста](https://appsource.microsoft.com/product/power-bi-visuals/WA104381309) | |
| [Текстовая оболочка от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [Thermometer от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847) | [Видео](https://youtu.be/SPX9mgrAdBc) |
| [Срез Time Brush](https://appsource.microsoft.com/product/power-bi-visuals/WA104380798) | |
| [Срез временной шкалы](https://appsource.microsoft.com/product/power-bi-visuals/WA104380786) | [Видео](https://youtu.be/ozMtZ4_NZ10) |
| [Временная шкала от CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381427) | [Видео](https://youtu.be/szNi9YgXFJc) |
| [Диаграмма-торнадо](https://appsource.microsoft.com/product/power-bi-visuals/WA104380768) | [Видео](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [Диаграмма продаж от MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380823) | [Видео](https://youtu.be/xhTR6y6J9Ko) |
| [Диаграмма отклонений Ultimate](https://appsource.microsoft.com/product/power-bi-visuals/WA104381140) | [Видео](https://youtu.be/pDYF8iZxERs) |
| [Каскадная диаграмма Ultimate](https://appsource.microsoft.com/product/power-bi-visuals/WA104380956) | [Видео](https://youtu.be/0BZsVCQdEkc) |
| [Список пользователей от CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381426) | |
| [Вафельная диаграмма](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049) | [Видео](https://youtu.be/1vRqYUsm3Vk) |
| [Облако Word](https://appsource.microsoft.com/product/power-bi-visuals/WA104380752) | [Видео](https://youtu.be/AblTenl9fqo) |

## <a name="faq"></a>ВОПРОСЫ И ОТВЕТЫ

Дополнительные сведения о визуальных элементах см. в разделе [Часто задаваемые вопросы о сертифицированных визуальных элементах](power-bi-custom-visuals-faq.md#certified-power-bi-visuals).

## <a name="next-steps"></a>Дальнейшие действия

* [Разработка пользовательского визуального элемента Power BI](../developer/custom-visual-develop-tutorial.md)
* [Список видео Майкрософт, посвященных пользовательским визуальным элементам, на сайте YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [Визуализации в Power BI](../visuals/power-bi-report-visualizations.md)  
* [Пользовательские визуализации в Power BI](power-bi-custom-visuals.md)  
* [Публикация визуальных элементов Power BI в Microsoft AppSource](../developer/office-store.md)  

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](https://community.powerbi.com/)
