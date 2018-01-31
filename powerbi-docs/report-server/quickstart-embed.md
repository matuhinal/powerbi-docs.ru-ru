---
title: "Внедрение отчета с использованием iFrame"
description: "Сама по себе установка сервера отчетов Power BI выполняется очень быстро. Скачивание и установка с последующей настройкой занимают всего нескольких минут."
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/09/2017
ms.author: maghan
ms.openlocfilehash: 56835bfb25c8c930099fadf710137f69fa89fc2e
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2018
---
# <a name="quickstart-embed-a-power-bi-report-using-an-iframe-and-url-parameters"></a>Краткое руководство по внедрению отчета Power BI с использованием параметров iFrame и URL-адреса

Вы можете внедрить любой отчет, используя iFrame в приложении. 

## <a name="url-parameter"></a>Параметр URL-адреса

В любой URL-адрес отчета можно добавить параметр строки запроса `?rs:Embed=true`.

Например:

```
http://myserver/reports/powerbi/Sales?rs:embed=true
```

Это будет работать со всеми типами отчетов в пределах сервера отчетов Power BI.

## <a name="iframe"></a>iFrame

Получив URL-адрес, можно создать iFrame на веб-странице для размещения отчета.

Например:

```
<iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
```

## <a name="url-filter"></a>Фильтр URL-адресов

Вы можете добавить параметр строки запроса к URL-адресу для фильтрации данных, которые возвращаются в отчете Power BI.

Синтаксис прост: начните с URL-адреса отчета, добавьте знак вопроса, а затем синтаксис этого фильтра.

URL?filter=***Таблица***/***Поле*** eq '***значение***'

Придерживайтесь следующих рекомендаций:

- Имена переменных **Таблица** и **Поле** чувствительны к регистру, а **значение** — нет.
- Отчет можно отфильтровать по полям, скрытым для просмотра.
- **Значение** должно быть заключено в одинарные кавычки.
- Тип поля должен быть строкой.
- Имена таблицы и поля не должны содержать пробелов.

###  <a name="example-filter-on-a-field"></a>Пример: фильтрация по полю

Например, [Анализ розничной торговли — образец](../sample-datasets.md). Этот URL-адрес отчета на сервере отчетов в папке power-bi:

```
https://report-server/reports/power-bi/Retail-Analysis-Sample
```

На визуализации карты в примере "Анализ розничной торговли" показаны магазины в Северной Каролине и других штатах.

![Визуализация карты примера "Анализ розничной торговли"](media/quickstart-embed/report-server-retail-analysis-sample-map.png)

*NC* — это значение для штата Северная Каролина, которое хранится в поле **Territory** в таблице **Store**. Чтобы отфильтровать отчет для отображения данных, связанных только с магазинами в Северной Каролине, добавьте следующий текст в URL-адрес:

?filter=Store/Territory eq 'NC'

Теперь, когда отчет отфильтрован по Северной Каролине, все визуализации на странице отчета показывают данные только по Северной Каролине.

![Отфильтрованная визуализация примера "Анализ розничной торговли"](media/quickstart-embed/report-server-retail-analysis-sample-filtered-map.png)

### <a name="create-a-dax-formula-to-filter-on-multiple-values"></a>Создание формулы DAX для фильтрации по нескольким значениям

Еще один способ фильтрации по нескольким полям заключается в следующем: можно создать вычисляемый столбец в Power BI Desktop, который сцепляет два поля в одно значение. Затем можно выполнить фильтрацию по этому значению.

Например, образец "Анализ розничной торговли" содержит два поля: Territory и Chain. В Power BI Desktop можно [создать вычисляемый столбец](../desktop-tutorial-create-calculated-columns.md) (поле), который называется TerritoryChain. Помните, что имя **поля** не может содержать пробелы. Вот формула DAX для этого столбца:

TerritoryChain = [Territory] & " - " & [Chain]

Опубликуйте отчет на Сервере отчетов Power BI, а затем используйте строку запроса в URL-адресе для фильтрации и отображения данных, связанных только с магазинами Lindseys в Северной Каролине.

```
https://report-server/reports/power-bi/Retail-Analysis-Sample?filter=Store/TerritoryChain eq 'NC-Lindseys'

```

## <a name="next-steps"></a>Дальнейшие действия

[Краткое руководство по созданию отчета Power BI для сервера отчетов Power BI](quickstart-create-powerbi-report.md)  
[Краткое руководство по созданию отчета c разбивкой на страницы Power BI для сервера отчетов Power BI](quickstart-create-paginated-report.md)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)