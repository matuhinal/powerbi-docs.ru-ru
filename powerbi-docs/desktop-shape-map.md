---
title: Использование карт фигур в Power BI Desktop (предварительная версия)
description: С помощью карт фигур в Power BI Desktop можно проводить относительные сравнения разных регионов.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 4e8e620ca8737e37fb129212fd15e1b131954217
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2018
ms.locfileid: "39329254"
---
# <a name="shape-maps-in-power-bi-desktop-preview"></a>Карты фигур в Power BI Desktop (предварительная версия)
В Power BI Desktop с помощью визуального элемента **Карта фигур** можно проводить относительное сравнение регионов на карте, применяя к ним разные цвета. В отличие от визуального элемента **Карта**, элемент **Карта фигур** не демонстрирует географическое расположение точек данных на карте: его основная задача — помочь сравнить регионы карты, окрасив их в разные цвета.

Визуальные элементы типа **Карта фигур** созданы на базе карт ESRI/TopoJSON, позволяющих создавать и использовать собственные настраиваемые карты (например, географические, планы залов и помещений и т. д.). Эта предварительная версия **Карт фигур** не поддерживает настраиваемые карты.

## <a name="creating-shape-maps"></a>Создание карт фигур
Вы можете проверить элемент управления **Карта фигур** с помощью карт, которые поставляются вместе с этой предварительной версией, или использовать свою карту, если она соответствует требованиям, приведенным в следующем разделе под названием **Использование пользовательских карт**.

Визуальный элемент **Карта фигур** представляет собой предварительную версию, поэтому его необходимо сначала включить в Power BI Desktop. Чтобы включить **карту фигур**, выберите **Файл > Параметры и настройки > Параметры > Предварительная версия функций** и установите флажок **Визуальный элемент "Карта фигур"**. После этого изменения приложение Power BI Desktop необходимо перезапустить.

![](media/desktop-shape-map/shape-map_1a.png)

Один раз **карта фигур** — включено, щелкните **карта фигур** управления из **визуализации** области.

![](media/desktop-shape-map/shape-map_2.png)

Power BI Desktop создаст пустой холст для визуального элемента **Карта фигур**.

![](media/desktop-shape-map/shape-map_3.png)

Чтобы создать **карту фигур**, выполните указанные ниже действия.

1. В области **Поля** перетащите поле данных с названиями (в том числе сокращенными) регионов в контейнер **Расположение**, а поле меры данных — в контейнер **Насыщенность цвета** (карта пока не отображается).

   > [!NOTE]
   > Сведения о том, как быстро загрузить данные карт, чтобы проверить элемент **Карта фигур** в действии, см. в разделе **Получение карт** ниже.
   > 
   > 

   ![](media/desktop-shape-map/shape-map_3a.png)
2. В области параметров **Формат** разверните раздел **Фигура** и выберите вариант из раскрывающегося списка **Стандартные карты**, чтобы отобразить данные. На этом этапе появится изображение карты, как показано на рисунке ниже.

   ![](media/desktop-shape-map/shape-map_3b.png)

   > [!NOTE]
   > В разделе **Ключи регионов** в конце этой статьи перечислены таблицы с ключами регионов карт, которые можно использовать для проверки визуального элемента **Карта фигур**.
   > 
   > 
3. После этого в области параметров **Формат** вы можете настраивать параметры проекции и масштабирования карты, а также цвета точек данных. Кроме того, можно менять настройки масштаба. В частности, здесь можно настраивать цвета, задавать минимальные и максимальные значения и т. д.

   ![](media/desktop-shape-map/shape-map_3d.png)
4. Вы также можете добавить столбец категории данных в контейнер **Условные обозначения** и распределить регионы карты по категориям.

## <a name="use-custom-maps"></a>Использование настраиваемых карт
Вы можете использовать с **картой фигур** пользовательские карты в формате **TopoJSON**. Если ваша карта в другом формате, вы можете воспользоваться онлайн-инструментами, такими как [**Map Shaper**](http://mapshaper.org/), для преобразования *файлов фигур* или карт *GeoJSON* в формат **TopoJSON**.

Чтобы использовать файл карты **TopoJSON**, добавьте в отчет визуальный элемент ShapeMap, а также добавьте данные в контейнеры *Расположение* и *Насыщенность цвета*. Затем в области **Визуализации** выберите раздел **Формат** (на который указывает стрелка (1) на следующем рисунке), разверните раздел **Фигура** и выберите **+ Добавить карту**.

![](media/desktop-shape-map/shape-map_6.png)

## <a name="sample-custom-map"></a>Пример настраиваемой карты
*Федеральная прокуратура США* выпускает годовой финансовый отчет о судебных разбирательствах и количестве рассматриваемых дел.  Все эти отчеты можно найти по следующей ссылке:

https://www.justice.gov/usao/resources/annual-statistical-reports

Так как штаты могут делиться на несколько округов, нужно использовать настраиваемую карту фигур.  Импортировав карту **TopoJSON** с судебными округами США в **Power BI Desktop**, можно визуализировать финансовые данные прокуратуры по округам за год.  На рисунке ниже показан пример такой карты.

![](media/desktop-shape-map/shape-map_7a.png)

Вы можете выполнять нужные действия с картами отдельного штата, а также отображать подробные сведения с учетом находящихся в нем округов. 

![](media/desktop-shape-map/shape-map_7b.png)

Если вы хотите поэкспериментировать с этим набором данных и визуализацией, можете скачать исходный PBIX-файл, использовавшийся для создания этого отчета, по приведенной ниже ссылке.

* [Демонстрационный PBIX-файл настраиваемой карты фигур](http://download.microsoft.com/download/1/2/8/128943FB-9231-42BD-8A5D-5E2362C9D589/DistrictAttorneyFiscalReport.pbix)

## <a name="getting-map-data"></a>Получение карт
Чтобы быстро загрузить в модель данные и протестировать визуальный элемент **Карта фигур**, скопируйте одну из таблиц, приведенных в конце этой статьи, и нажмите кнопку **Ввести данные** на ленте **Главная**.

![](media/desktop-shape-map/shape-map_4.png)

При наличии нескольких столбцов вам потребуется вставить данные с помощью редактора, например Excel, и скопировать каждый столбец данных отдельно. Затем вставьте данные в приложение Power BI Desktop. Верхняя строка будет автоматически назначена заголовком.

![](media/desktop-shape-map/shape-map_5.png)

Чтобы добавить новый столбец, просто введите его название (в пустом столбце справа), а затем добавьте значение в каждую ячейку (так же, как в Excel). Завершив подготовку, нажмите кнопку **Загрузить**, и столбец будет добавлен в модель данных в Power BI Desktop.

> [!NOTE]
> Указывая страны или регионы, используйте трехбуквенное сокращение для правильной работы геокодирования в визуализации карт. *Не* используйте двухбуквенные сокращения, так как некоторые страны или регионы могут не распознаваться правильно.
> 
> Если у вас есть только двухбуквенные сокращения, в [этой внешней записи блога](https://blog.ailon.org/how-to-display-2-letter-country-data-on-a-power-bi-map-85fc738497d6#.yudauacxp) вы найдете инструкции о том, как связать двухбуквенные сокращения для обозначения стран и регионов с трехбуквенными.
> 
> 

## <a name="preview-behavior-and-requirements"></a>Особенности работы и требования предварительной версии
С этим предварительным выпуском **карты фигур** связан ряд моментов и требований.

* Визуальный элемент **Карта фигур** представляет собой предварительную версию, поэтому его необходимо сначала включить в Power BI Desktop. Чтобы включить **карту фигур**, выберите **Файл > Параметры и настройки > Параметры > Предварительная версия функций** и установите флажок **Визуальный элемент "Карта фигур"**.
* Сейчас для корректной классификации по **условным обозначениям** нужно также настроить контейнер **Насыщенность цвета**.
* В окончательном выпуске **карты фигур** в пользовательском интерфейсе будут отображаться ключи текущей карты (дата окончательного выпуска пока не определена, и **карта фигур** еще находится на этапе предварительной версии). В этой предварительной версии вы можете использовать ключи регионов карт, приведенные в таблицах раздела **Ключи регионов** в этой статье.
* Визуализация **Карта фигур** будет отображать до 1000 точек данных.

## <a name="region-keys"></a>Ключи регионов
Для тестирования **карты фигур** в этой предварительной версии используйте приведенные ниже **ключи регионов**.

### <a name="australia-states"></a>Australia: States

| id | abbr | iso | name | postal |
| --- | --- | --- | --- | --- |
| au-wa |WA |AU-WA |Western Australia |WA |
| au-vic |Vic |AU-VIC |Victoria |VIC |
| au-tas |Tas |AU-TAS |Tasmania |TAS |
| au-sa |SA |AU-SA |South Australia |SA |
| au-qld |Qld |AU-QLD |Queensland |QLD |
| au-nt |NT |AU-NT |Northern Territory |NT |
| au-nsw |NSW |AU-NSW |New South Wales |NSW |
| au-act |ACT |AU-ACT |Australian Capital Territory |ACT |

### <a name="austria-states"></a>Austria: States

| id | iso | name | name-en | postal |
| --- | --- | --- | --- | --- |
| at-wi |AT-9 |Wien |Vienna |WI |
| at-vo |AT-8 |Vorarlberg |Vorarlberg |VO |
| at-tr |AT-7 |Tirol |Tyrol |TR |
| at-st |AT-6 |Steiermark |Styria |ST |
| at-sz |AT-5 |Salzburg |Salzburg |SZ |
| at-oo |AT-4 |Oberösterreich |Upper Austria |OO |
| at-no |AT-3 |Niederösterreich |Lower Austria |NO |
| at-ka |AT-2 |Kärnten |Carinthia |KA |
| at-bu |AT-1 |Burgenland |Burgenland |BU |

### <a name="brazil-states"></a>Brazil: States

| id |
| --- |
| Tocantins |
| Pernambuco |
| Goias |
| Sergipe |
| Sao Paulo |
| Santa Catarina |
| Roraima |
| Rondonia |
| Rio Grande do Sul |
| Rio Grande do Norte |
| Rio de Janeiro |
| Piaui |
| Parana |
| Paraiba |
| Para |
| Minas Gerais |
| Mato Grosso |
| Maranhao |
| Mato Grosso do Sul |
| Distrito Federal |
| Ceara |
| Espirito Santo |
| Bahia |
| Amazonas |
| Amapa |
| Alagoas |
| Acre |
| Litigated Zone 1 |
| Litigated Zone 2 |
| Litigated Zone 3 |
| Litigated Zone 4 |

### <a name="canada-provinces"></a>Canada: Provinces

| id | iso | name | postal |
| --- | --- | --- | --- |
| ca-nu |CA-NU |Nunavut |NU |
| ca-nt |CA-NT |Northwest Territories |NT |
| ca-yt |CA-YT |Yukon |YT |
| ca-sk |CA-SK |Saskatchewan |SK |
| ca-qc |CA-QC |Quebec |QC |
| ca-pe |CA-PE |Prince Edward Island |PE |
| ca-on |CA-ON |Ontario |ON |
| ca-ns |CA-NS |Nova Scotia |NS |
| ca-nl |CA-NL |Newfoundland and Labrador |NL |
| ca-nb |CA-NB |New Brunswick |NB |
| ca-mb |CA-MB |Manitoba |MB |
| ca-bc |CA-BC |British Columbia |BC |
| ca-ab |CA-AB |Alberta |AB |

### <a name="france-regions"></a>France: Regions

| id | name | name-en |
| --- | --- | --- |
| Alsace |Alsace |Alsace |
| Rhone-Alpes |Rhône-Alpes |Rhone-Alpes |
| Provence-Alpes-Cote d'Azur |Provence-Alpes-Côte d'Azur |Provence-Alpes-Cote d'Azur |
| Poitou-Charentes |Poitou-Charentes |Poitou-Charentes |
| Picardie |Picardie |Picardy |
| Pays de la Loire |Pays de la Loire |Pays de la Loire |
| Nord-Pas-de-Calais |Nord-Pas-de-Calais |Nord-Pas-de-Calais |
| Midi-Pyrenees |Midi-Pyrénées |Midi-Pyrenees |
| Lorraine |Lorraine |Lorraine |
| Limousin |Limousin |Limousin |
| Languedoc-Roussillon |Languedoc-Roussillon |Languedoc-Roussillon |
| Ile-del-France |Île-de-France |Ile-de-France |
| Haute-Normandie |Haute-Normandie |Upper Normandy |
| Franche-Comte |Franche-Comté |Franche-Comte |
| Corse |Corse |Corsica |
| Champagne-Ardenne |Champagne-Ardenne |Champagne-Ardenne |
| Centre-Val de Loire |Centre-Val de Loire |Centre-Val de Loire |
| Bretagne |Bretagne |Brittany |
| Bourgogne |Bourgogne |Burgundy |
| Basse-Normandie |Basse-Normandie |Lower Normandy |
| Auvergne |Auvergne |Auvergne |
| Aquitaine |Aquitaine |Aquitaine |

### <a name="germany-states"></a>Germany: States

| id | iso | name | name-en | postal |
| --- | --- | --- | --- | --- |
| de-be |DE-BE |Berlin |Berlin |BE |
| de-th |DE-TH |Thüringen |Thuringia |TH |
| de-st |DE-ST |Sachsen-Anhalt |Saxony-Anhalt |ST |
| de-sn |DE-SN |Sachsen |Saxony |SN |
| de-mv |DE-MV |Mecklenburg-Vorpommern |Mecklenburg-Vorpommern |MV |
| de-bb |DE-BB |Brandenburg |Brandenburg |BB |
| de-sh |DE-SH |Schleswig-Holstein |Schleswig-Holstein |SH |
| de-sl |DE-SL |Saarland |Saarland |SL |
| de-rp |DE-RP |Rheinland-Pfalz |Rhineland-Palatinate |RP |
| de-nw |DE-NW |Nordrhein-Westfalen |North Rhine-Westphalia |NW |
| de-ni |DE-NI |Niedersachsen |Lower Saxony |NI |
| de-he |DE-HE |Hessen |Hesse |HE |
| de-hh |DE-HH |Hamburg |Hamburg |HH |
| de-hb |DE-HB |Bremen |Bremen |HB |
| de-by |DE-BY |Bayern |Bavaria |BY |
| de-bw |DE-BW |Baden-Württemberg |Baden-Wurttemberg |BW |

### <a name="ireland-counties"></a>Ireland: Counties

| id |
| --- |
| Wicklow |
| Wexford |
| Westmeath |
| Waterford |
| Sligo |
| Tipperary |
| Roscommon |
| Offaly |
| Monaghan |
| Meath |
| Mayo |
| Louth |
| Longford |
| Limerick |
| Leitrim |
| Laoighis |
| Kilkenny |
| Kildare |
| Kerry |
| Galway |
| Dublin |
| Donegal |
| Cork |
| Clare |
| Cavan |
| Carlow |

### <a name="italy-regions"></a>Italy: Regions

| id | iso | name | name-en | postal |
| --- | --- | --- | --- | --- |
| it-vn |IT-34 |Veneto |Veneto |VN |
| it-vd |IT-23 |Valle d'Aosta |Aosta Valley |VD |
| it-um |IT-55 |Umbria |Umbria |UM |
| it-tt |IT-32 |Trentino-Alto Adige |Trentino-South Tyrol |TT |
| it-tc |IT-52 |Toscana |Tuscany |TC |
| it-sc |IT-82 |Sicilia |Sicily |SC |
| it-sd |IT-88 |Sardegna |Sardinia |SD |
| it-pm |IT-21 |Piemonte |Piedmont |PM |
| it-ml |IT-67 |Molise |Molise |ML |
| it-mh |IT-57 |Marche |Marche |MH |
| it-lm |IT-25 |Lombardia |Lombardy |LM |
| it-lg |IT-42 |Liguria |Liguria |LG |
| it-lz |IT-62 |Lazio |Lazio |LZ |
| it-fv |IT-36 |Friuli-Venezia Giulia |Friuli-Venezia Giulia |FV |
| it-er |IT-45 |Emilia-Romagna |Emilia-Romagna |ER |
| it-cm |IT-72 |Campania |Campania |CM |
| it-lb |IT-78 |Calabria |Calabria |LB |
| it-bc |IT-77 |Basilicata |Basilicata |BC |
| it-pu |IT-75 |Apulia |Puglia |PU |
| it-ab |IT-65 |Abruzzo |Abruzzo |AB |

### <a name="mexico-states"></a>Mexico: States

| id | abreviatura | iso | name | name-en | postal |
| --- | --- | --- | --- | --- | --- |
| mx-zac |Zac. |MX-ZAC |Zacatecas |Zacatecas |ZA |
| mx-yuc |Yuc. |MX-YUC |Yucatán |Yucatan |YU |
| mx-ver |Ver. |MX-VER |Veracruz |Veracruz |VE |
| mx-tla |Tlax. |MX-TLA |Tlaxcala |Tlaxcala |TL |
| mx-tam |Tamps. |MX-TAM |Tamaulipas |Tamaulipas |TM |
| mx-tab |Tab. |MX-TAB |Tabasco |Tabasco |TB |
| mx-son |Son. |MX-SON |Sonora |Sonora |SO |
| mx-sin |Sin. |MX-SIN |Sinaloa |Sinaloa |SI |
| mx-slp |S.L.P. |MX-SLP |San Luis Potosí |San Luis Potosi |SL |
| mx-roo |Q.R. |MX-ROO |Quintana Roo |Quintana Roo |QR |
| mx-que |Qro. |MX-QUE |Querétaro |Queretaro |QE |
| mx-pue |Pue. |MX-PUE |Puebla |Puebla |PU |
| mx-oax |Oax. |MX-OAX |Oaxaca |Oaxaca |OA |
| mx-nle |N.L. |MX-NLE |Nuevo León |Nuevo Leon |NL |
| mx-nay |Nay. |MX-NAY |Nayarit |Nayarit |NA |
| mx-mor |Mor. |MX-MOR |Morelos |Morelos |MR |
| mx-mic |Mich. |MX-MIC |Michoacán |Michoacan |MC |
| mx-mex |Méx. |MX-MEX |Estado de México |Mexico State |MX |
| mx-jal |Jal. |MX-JAL |Jalisco |Jalisco |JA |
| mx-hid |Hgo. |MX-HID |Hidalgo |Hidalgo |HI |
| mx-gro |Gro. |MX-GRO |Guerrero |Guerrero |GR |
| mx-gua |Gto. |MX-GUA |Guanajuato |Guanajuato |GT |
| mx-dur |Dgo. |MX-DUR |Durango |Durango |DU |
| mx-dif |Col. |MX-DIF |Ciudad de México |Mexico City |DF |
| mx-col |Coah. |MX-COL |Colima |Colima |CL |
| mx-coa |Chis. |MX-COA |Coahuila |Coahuila |CA |
| mx-chh |Chih. |MX-CHH |Chihuahua |Chihuahua |CH |
| mx-chp |CDMX. |MX-CHP |Chiapas |Chiapas |CP |
| mx-cam |Camp. |MX-CAM |Campeche |Campeche |CM |
| mx-bcs |B.C.S. |MX-BCS |Baja California Sur |Baja California Sur |BS |
| mx-bcn |B.C. |MX-BCN |Baja California |Baja California |BN |
| mx-agu |Ags. |MX-AGU |Aguascalientes |Aguascalientes |AG |

### <a name="netherlands-provinces"></a>Netherlands: Provinces

| id | iso | name | name-en |
| --- | --- | --- | --- |
| nl-zh |NL-ZH |Zuid-Holland |South Holland |
| nl-ze |NL-ZE |Zeeland |Zeeland |
| nl-ut |NL-UT |Utrecht |Utrecht |
| nl-ov |NL-OV |Overijssel |Overijssel |
| nl-nh |NL-NH |Noord-Holland |North Holland |
| nl-nb |NL-NB |Noord-Brabant |North Brabant |
| nl-li |NL-LI |Limburg |Limburg |
| nl-gr |NL-GR |Groningen |Groningen |
| nl-ge |NL-GE |Gelderland |Gelderland |
| nl-fr |NL-FR |Fryslân |Friesland |
| nl-fl |NL-FL |Flevoland |Flevoland |
| nl-dr |NL-DR |Drenthe |Drenthe |

### <a name="uk-countries"></a>UK: Countries

| id | iso | name |
| --- | --- | --- |
| gb-wls |GB-WLS |Wales |
| gb-sct |GB-SCT |Scotland |
| gb-nir |GB-NIR |Northern Ireland |
| gb-eng |GB-ENG |England |

### <a name="usa-states"></a>USA: States

| id | name | postal |
| --- | --- | --- |
| us-mi |Michigan |MI |
| us-ak |Alaska |AK |
| us-hi |Hawaii |HI |
| us-fl |Florida |FL |
| us-la |Louisiana |LA |
| us-ar |Arkansas |AR |
| us-sc |South Carolina |SC |
| us-ga |Georgia |GA |
| us-ms |Mississippi |MS |
| us-al |Alabama |AL |
| us-nm |New Mexico |NM |
| us-tx |Texas |TX |
| us-tn |Tennessee |TN |
| us-nc |North Carolina |NC |
| us-ok |Oklahoma |OK |
| us-az |Arizona |AZ |
| us-mo |Missouri |MO |
| us-va |Virginia |VA |
| us-ks |Kansas |KS |
| us-ky |Kentucky |KY |
| us-co |Colorado |CO |
| us-md |Maryland |MD |
| us-wv |West Virginia |WV |
| us-de |Delaware |DE |
| us-dc |District of Columbia |DC |
| us-il |Illinois |IL |
| us-oh |Ohio |OH |
| us-ca |California |CA |
| us-ut |Utah |UT |
| us-nv |Nevada |NV |
| us-in |Indiana |IN |
| us-nj |New Jersey |NJ |
| us-ri |Rhode Island |RI |
| us-ct |Connecticut |CT |
| us-pa |Pennsylvania |PA |
| us-ny |New York |NY |
| us-ne |Nebraska |NE |
| us-ma |Massachusetts |MA |
| us-ia |Iowa |IA |
| us-nh |New Hampshire |NH |
| us-or |Oregon |OR |
| us-mn |Minnesota |MN |
| us-vt |Vermont |VT |
| us-id |Idaho |ID |
| us-wi |Wisconsin |WI |
| us-wy |Wyoming |WY |
| us-sd |South Dakota |SD |
| us-nd |North Dakota |ND |
| us-me |Maine |ME |
| us-mt |Montana |MT |
| us-wa |Washington |WA |

