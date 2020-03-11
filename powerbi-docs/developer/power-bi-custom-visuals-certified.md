---
title: Сертифицированные визуальные элементы Power BI
description: Требования и процесс отправки пользовательского визуального элемента для сертификации, а также список сертифицированных визуальных элементов Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 03/01/2020
ms.openlocfilehash: 8aea9041665de69b2c5be954dc8f13a6402a06e0
ms.sourcegitcommit: d55d3089fcb3e78930326975957c9940becf2e76
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260768"
---
# <a name="get-a-power-bi-visual-certified"></a>Получите сертификацию для визуального элемента Power BI

Сертифицированные визуальные элементы Power BI — это визуальные элементы Power BI в [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals), которые соответствуют [требованиям к коду](#certification-requirements) группы разработчиков Power BI в Microsoft. Эти визуальные элементы проверяются, не обращаются ли они к внешним службам или ресурсам и соответствуют ли шаблонам и рекомендациям по созданию безопасного кода.

Сертифицированные визуализации Power BI предусматривают дополнительные возможности. Например, вы можете [экспортировать их в PowerPoint](../consumer/end-user-powerpoint.md) или добавлять для отображения в сообщениях электронной почты, получаемых при оформлении [подписки на страницы отчета](../consumer/end-user-subscribe.md).

Процесс сертификации необязателен. Несертифицированные визуальные элементы Power BI не обязательно являются ненадежными визуальными элементами Power BI. Некоторые визуальные элементы Power BI не проходят сертификацию, так как не соответствуют одному или нескольким [требованиям сертификации](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements). Например, визуальный элемент Power BI сопоставления подключается к внешней службе или визуальный элемент Power BI использует коммерческие библиотеки.

> [!NOTE]
> Корпорация Майкрософт не является автором сторонних визуализаций Power BI. Чтобы проверить функциональные возможности сторонних визуализаций, обращайтесь к автору напрямую.

## <a name="certification-requirements"></a>Требования к сертификации

Чтобы [сертифицировать](#get-a-power-bi-visual-certified) свою визуализацию Power BI, она должна соответствовать требованиям, перечисленным в этом разделе. 

### <a name="general-requirements"></a>Общие требования

Визуальный элемент Power BI должен быть одобрен на панели мониторинга продавца или в Центре партнеров. Рекомендуется, чтобы визуальный элемент Power BI уже был в [AppSource](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals). Дополнительные сведения о публикации визуального элемента Power BI в AppSource см. в статье [Публикация визуальных элементов Power BI в Центре партнеров](office-store.md).

Перед отправкой визуального элемента Power BI для сертификации убедитесь, что он соответствует правилам [для визуальных элементов Power BI](./guidelines-powerbi-visuals.md).

При отправке визуального элемента Power BI убедитесь, что скомпилированный пакет точно соответствует отправляемому пакету.

### <a name="code-repository-requirements"></a>Требования к репозиторию кода

Хотя вам не нужно публиковать код в GitHub, репозиторий кода должен быть доступен команде разработчиков Power BI для ознакомления. Лучший способ сделать это — предоставить исходный код (JavaScript или TypeScript) в GitHub.

Репозиторий должен содержать следующие элементы:
* код только для одного визуального элемента Power BI; Он не может содержать код для нескольких визуальных элементов Power BI или несвязанного кода.
* ветвь с именем **certification** (обязательно в нижнем регистре). Исходный код в этой ветви должен соответствовать коду в отправленном пакете. Этот код можно обновить только во время следующей отправки, когда вы будете повторно отправлять визуальный элемент Power BI.

Если визуальный элемент Power BI использует частные пакеты NPM или подмодули Git, необходимо предоставить доступ к дополнительным репозиториям, содержащим этот код.

Чтобы понять, как выглядит репозиторий визуальных элементов Power BI, изучите репозиторий GitHub с [примерами линейчатых диаграмм визуальных элементов Power BI](https://github.com/microsoft/PowerBI-visuals-sampleBarChartgi).

### <a name="file-requirements"></a>Требования к файлу

Используйте последнюю версию API для создания визуального элемента Power BI.

Репозиторий должен содержать следующие файлы:
* Файл с расширением **.gitignore** — добавьте `node_modules`, `.tmp` и `dist` в этот файл. Код не может содержать папки *node_modules*, *.tmp* или *dist*.
* **capabilities.json** — если вы отправляете новую версию визуального элемента Power BI с изменениями в свойствах этого файла, убедитесь, что они не нарушают отчеты для существующих пользователей.
* **pbiviz.json** 
* **package.json**. Для визуального элемента должны быть установлены следующие пакеты:
   * [tslint](https://www.npmjs.com/package/tslint): 5.18.0 или более поздней версии;
   * [typescript](https://www.npmjs.com/package/typescript): 3.0.0 или более поздней версии.
   * [tslint-microsoftcontrib](https://www.npmjs.com/package/tslint-microsoft-contrib): 6.2.0 или более поздней версии.
   * Файл должен содержать команду для запуска анализатора кода: "lint": "tslint -c tslint.json -p tsconfig.json"
* **package-lock.json**
* **tsconfig.json**

### <a name="command-requirements"></a>Требования к командам

Убедитесь, что перечисленные ниже команды не возвращают ошибок.

* `npm install`
* `pbiviz package`
* `npm audit` — не должна возвращать предупреждения с высоким или умеренным уровнем.
* [TSlint от Майкрософт](https://www.npmjs.com/package/tslint-microsoft-contrib) с [необходимой конфигурацией](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/master/tslint.json). Эта команда не должна возвращать ошибки, связанные с оформлением кода.

### <a name="compiling-requirements"></a>Требования к компиляции

Для написания визуальных элементов Power BI используйте последнюю версию [powerbi-visuals-tools](https://www.npmjs.com/package/powerbi-visuals-tools).

Необходимо компилировать визуальный элемент Power BI с `pbiviz package`. Если вы используете собственные сборочные скрипты, укажите пользовательскую команду сборки `npm run package`.



### <a name="source-code-requirements"></a>Требования к исходному коду

Убедитесь, что вы следуете перечню политик [дополнительной сертификации визуальных элементов Power BI](https://docs.microsoft.com/legal/marketplace/certification-policies#1200-power-bi-visuals-additional-certification). Если отправка не будет соответствовать этим рекомендациям, сообщение из Центра партнеров об отклонении отправки будет содержать номера политик, перечисленные по этой ссылке.

Выполните приведенные ниже требования к коду, чтобы код соответствовал политикам сертификации Power BI.  

**Обязательно**
* Используйте только открытые и доступные для просмотра компоненты OSS, например общедоступные библиотеки JavaScript или TypeScript.
* Код должен поддерживать [API событий отрисовки](./visuals/event-service.md).
* Обеспечьте безопасную обработку DOM. Перед добавлением данных в модель DOM используйте очистку для пользовательского ввода или пользовательской информации.
* Используйте [образец отчета](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix) в качестве тестового набора данных.

**Не разрешено**
* Доступ к внешним службам или ресурсам. Например, запросы HTTP/S или WebSocket не должны отправляться из Power BI во внешние службы.
* С помощью `innerHTML` или `D3.html(user data or user input)`.
* Ошибки или исключения JavaScript для любых входных данных в консоли браузера.
* Произвольный или динамический код, например `eval()`, небезопасное использование `settimeout()`, `requestAnimationFrame()`, `setinterval(user input function)`, пользовательский ввод или данные пользователя.
* Минифицированные файлы или проекты JavaScript.

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

### <a name="private-repository-submission-process"></a>Процесс отправки частного репозитория

Если вы используете частный репозиторий, например GitHub, чтобы отправить визуальный элемент Power BI на сертификацию, следуйте инструкциям в этом разделе.
1. Создайте новую учетную запись для группы проверки.
2. Настройте [двухфакторную проверку подлинности для учетной записи](https://help.github.com/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa).
3. [Создайте новый набор кодов восстановления](https://help.github.com/github/authenticating-to-github/configuring-two-factor-authentication-recovery-methods#generating-a-new-set-of-recovery-codes).
4. При отправке визуального элемента Power BI предоставьте следующее:
    * ссылка на репозиторий;
    * учетные данные для входа (включая пароль);
    * коды восстановления;
    * разрешения на доступ к учетной записи только для чтения ([pbicvsupport](https://github.com/pbicvsupport)).

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
* Если вы как веб-разработчик заинтересованы в создании собственных визуализаций Power BI и их добавлении в  [Microsoft AppSource](https://appsource.microsoft.com), начните с руководства по  [разработке визуализаций Power BI](visuals/custom-visual-develop-tutorial.md). 

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](https://community.powerbi.com/)
