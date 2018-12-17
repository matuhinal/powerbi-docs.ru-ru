---
title: Двунаправленная перекрестная фильтрация в Power BI Desktop
description: Включение перекрестной фильтрации при работе с DirectQuery в Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 89ee11efab495d55457e265e654972aac941d50c
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "53025334"
---
# <a name="bidirectional-cross-filtering-using-directquery-in-power-bi-desktop"></a>Двунаправленная перекрестная фильтрация при работе с DirectQuery в Power BI Desktop

При фильтрации таблиц для создания требуемого представления данных авторы отчетов (и архитекторы данных) сталкиваются с проблемой, пытаясь понять, как именно фильтрация применяется к отчету: контекст фильтра таблицы находится только на одной стороне связи, и часто для получения нужных результатов приходится прибегать к сложным формулам DAX.

Двунаправленная перекрестная фильтрация позволяет авторам отчетов и архитекторам данных лучше контролировать работу фильтров на связанных таблицах, применяя их на *обеих* сторонах связи между ними. Для этого контекст фильтра распространяется на вторую связанную таблицу на другой стороне связи.

## <a name="detailed-whitepaper-for-bidirectional-cross-filtering"></a>Подробный технический документ о двунаправленной перекрестной фильтрации
В [подробном техническом документе](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx) объясняются принципы работы двунаправленной перекрестной фильтрации в Power BI Desktop (в нем также рассматриваются службы SQL Server Analysis Services 2016, так как особенности их работы аналогичны).

* Скачать технический документ, посвященный [двунаправленной перекрестной фильтрации в Power BI Desktop](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx)

## <a name="enabling-bidirectional-cross-filtering-for-directquery"></a>Включение двунаправленной перекрестной фильтрации для DirectQuery

Для включения перекрестной фильтрации в диалоговом окне **Изменение связи** для соответствующей связи должны быть настроены следующие параметры:

* Для параметра **Направление кроссфильтрации** должно быть выбрано значение **Оба**.
* Должен быть установлен флажок **Применить фильтр безопасности в обоих направлениях**.

  ![](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

> [!NOTE]
> При создании формул DAX с перекрестной фильтрацией в Power BI Desktop используйте вместо параметра *UserName* параметр *UserPrincipalName* (который часто совпадает с именем пользователя для входа, например <em>joe@contoso.com</em>). При этом вам может потребоваться создать связанную таблицу *UserName* (или, например, EmployeeID), сопоставив ее с *UserPrincipalName*.

Дополнительные сведения и примеры работы двунаправленной перекрестной фильтрации см. в [техническом документе](http://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx), упомянутом выше в этой статье.

