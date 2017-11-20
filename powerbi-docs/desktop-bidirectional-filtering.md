---
title: "Двунаправленная перекрестная фильтрация в Power BI Desktop (предварительная версия)"
description: "Включение перекрестной фильтрации при работе с DirectQuery в Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 7946a9389897c4401e581482c0630547a764616d
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="bidirectional-cross-filtering-using-directquery-in-power-bi-desktop-preview"></a>Двунаправленная перекрестная фильтрация при работе с DirectQuery в Power BI Desktop (предварительная версия)

При фильтрации таблиц для создания требуемого представления данных авторы отчетов (и архитекторы данных) сталкиваются с проблемой, пытаясь понять, как именно фильтрация применяется к отчету: контекст фильтра таблицы находится только на одной стороне связи, и часто для получения нужных результатов приходится прибегать к сложным формулам DAX.

Двунаправленная перекрестная фильтрация позволяет авторам отчетов и архитекторам данных лучше контролировать работу фильтров на связанных таблицах, применяя их на *обеих* сторонах связи между ними. Для этого контекст фильтра распространяется на вторую связанную таблицу на другой стороне связи.

В [подробном техническом документе](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) объясняются принципы работы двунаправленной перекрестной фильтрации в Power BI Desktop (в нем также рассматриваются службы SQL Server Analysis Services 2016, так как особенности их работы аналогичны).

* Скачать технический документ, посвященный [двунаправленной перекрестной фильтрации в Power BI Desktop](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx)

### <a name="enabling-bidirectional-cross-filtering-for-directquery"></a>Включение двунаправленной перекрестной фильтрации для DirectQuery
Для использования перекрестной фильтрации в DirectQuery необходимо сначала ее включить. Это предварительная версия функции, и ее доступность и особенности работы могут быть изменены в следующих выпусках Power BI Desktop.

Чтобы включить перекрестную фильтрацию для DirectQuery в Power BI Desktop, выберите **Файл > Параметры и настройки > Параметры**, а затем установите флажок **Включить кроссфильтрацию в обоих направлениях для DirectQuery**, как показано на изображении ниже.

![](media/desktop-bidirectional-filtering/bidirectional-filtering_1.png)

> [!NOTE]
> При создании формул DAX с перекрестной фильтрацией в Power BI Desktop используйте вместо параметра *UserName* параметр *UserPrincipalName* (который часто совпадает с именем пользователя для входа, например *joe@contoso.com*). При этом вам может потребоваться создать связанную таблицу *UserName* (или, например, EmployeeID), сопоставив ее с *UserPrincipleName*.
> 
> 

Для включения перекрестной фильтрации в диалоговом окне **Изменение связи** для соответствующей связи должны быть настроены следующие параметры:

* Для параметра **Направление кроссфильтрации** должно быть выбрано значение **Оба**.
* Должен быть установлен флажок **Применить фильтр безопасности в обоих направлениях**.
  
  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

Дополнительные сведения и примеры работы двунаправленной перекрестной фильтрации см. в [техническом документе](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx), упомянутом выше в этой статье.

