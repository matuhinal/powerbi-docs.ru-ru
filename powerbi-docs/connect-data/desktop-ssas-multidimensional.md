---
title: Многомерные данные Analysis Services в Power BI Desktop
description: Многомерные данные SQL Server Analysis Services (SSAS) в Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 7b96e9707e9c91c6403047091bed00afbff3789d
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85222524"
---
# <a name="connect-to-ssas-multidimensional-models-in-power-bi-desktop"></a>Подключение к многомерным моделям SSAS в Power BI Desktop

С помощью Power BI Desktop вы можете получить доступ к *многомерным моделям SSAS*, которые обычно называются *SSAS MD*.

Для подключения к базе данных SSAS MD выберите **Получить данные**, **База данных** > **База данных SQL Server Analysis Services**, а затем **Подключиться**:

![База данных SQL Server Analysis Services (SSAS), диалоговое окно "Получить данные", Power BI Desktop](media/desktop-ssas-multidimensional/ssas-multidimensional-2.png)

Служба Power BI и Power BI Desktop поддерживают многомерные модели SSAS в режиме активного подключения. Вы можете опубликовать и отправить в службу Power BI отчеты, использующие **многомерные модели SSAS** в режиме активного подключения.

## <a name="capabilities-and-features-of-ssas-md"></a>Функции и возможности многомерных моделей SSAS

В следующих разделах описаны функции и возможности Power BI и подключений к многомерным моделям SSAS.

### <a name="tabular-metadata-of-multidimensional-models"></a>Табличные метаданные многомерных моделей

В таблице ниже продемонстрировано соответствие между многомерными объектами и табличными метаданными, возвращаемыми приложением Power BI Desktop. Power BI запрашивает табличные метаданные у моделей. Он использует полученную информацию при отправке соответствующих запросов DAX в службы SSAS, когда вы создаете визуализации (например, таблицы, матрицы, диаграммы или срезы).

| Многомерный объект BISM | Табличные метаданные |
| --- | --- |
| Куб |Модель |
| Измерение куба |Таблица |
| Атрибуты измерения (ключи), имя |Столбцы |
| Группа мер |Таблица |
| Мера |Мера |
| Меры без связи с группами мер |В таблице *Меры* |
| Связь между группой мер и измерением куба |Связь |
| Перспектива |Перспектива |
| КПЭ |КПЭ |
| Пользовательские иерархии и иерархии "родители-потомки" |Иерархии |

### <a name="measures-measure-groups-and-kpis"></a>Меры, группы мер и КПЭ

Группы мер в многомерном кубе доступны как таблицы с ведущим знаком ∑ в области **Поля**. Вычисляемые меры, с которыми не связаны группы мер, собраны в специальной таблице под названием *Меры* в табличных метаданных.

Чтобы упростить сложные модели в многомерной модели, можно задать набор мер или КПЭ в кубе в *папке отображения*. Power BI распознает папки отображения в табличных метаданных и показывает меры и КПЭ в таких папках. КПЭ в многомерных базах данных поддерживают *значения*, *цели*, *изображения состояния* и *изображения тренда*.

### <a name="dimension-attribute-type"></a>Тип атрибутов измерения

Многомерные модели также поддерживают возможность связывания атрибутов измерений с определенными типами атрибутов. Например, в табличных метаданных доступно измерение **География**, в котором атрибуты *Город*, *Область или край*, *Страна* и *Почтовый индекс* связаны с соответствующими географическими типами. Power BI распознает метаданные, что позволяет создавать визуализации в виде карт. Соответствующие связи помечены значком *карта* рядом с элементом в области **Поле** в Power BI.

Power BI также может выводить изображения при наличии поля, содержащего их URL-адреса. Эти поля можно указать как типы *ImageURL* в SQL Server Data Tools (или затем в Power BI). Этот тип информации затем предоставляется Power BI в табличных метаданных. Power BI может загружать такие изображения по URL-адресу и выводить их в визуальных элементах.

### <a name="parent-child-hierarchies"></a>Иерархии «родители-потомки»

Многомерные модели поддерживают иерархии "родители-потомки", которые представлены как *иерархия* в табличных метаданных. Каждый уровень иерархии "родители-потомки" представлен в табличных метаданных в виде скрытого столбца. Ключевой атрибут измерения типа "родители-потомки" в табличных метаданных недоступен.

### <a name="dimension-calculated-members"></a>Вычисляемые элементы измерения

Многомерные модели поддерживают возможность создания *вычисляемых элементов*различных типов. Ниже указаны два самых распространенных типа таких элементов.

* Вычисляемые элементы иерархий атрибутов, не имеющих общего родителя с элементом *Все*
* Вычисляемые элементы пользовательских иерархий

*Вычисляемые элементы иерархий атрибутов* доступны в многомерных моделях в качестве значений столбца. Для вычисляемых элементов такого типа существует еще несколько ограничений и параметров.

* У атрибута измерения может быть необязательный неизвестный элемент *UnknownMember*.

* Атрибут, содержащий вычисляемые элементы, не может быть ключевым атрибутом измерения, если не является его единственным атрибутом.

* Атрибут, содержащий вычисляемые элементы, не может быть атрибутом иерархии "родители-потомки".

Вычисляемые элементы пользовательских иерархий не видны в Power BI. Вместо этого можно подключиться к кубу, содержащему вычисляемые элементы в пользовательских иерархиях. Однако вы не сможете увидеть вычисляемые элементы, если они не соответствуют ограничениям, упомянутым в предыдущем списке.

### <a name="security"></a>Безопасность

В многомерных моделях безопасность на уровне измерений и ячеек реализована с помощью *ролей*. При подключении к кубу с помощью Power BI выполняется проверка подлинности и наличия необходимых разрешений. Если для пользователя действует *безопасность измерения*, элементы соответствующего измерения не видны ему в Power BI. Однако когда для пользователя определено разрешение *безопасности ячейки*, в соответствии с которым ограничен доступ к определенным ячейкам, этот пользователь не может подключиться к кубу с помощью Power BI.

## <a name="considerations-and-limitations"></a>Рекомендации и ограничения

На использование SSAS MD налагаются некоторые ограничения.

* Активные подключения поддерживаются только выпусками Enterprise и BI для SQL Server 2014. Для активных подключений требуется стандартная версия SQL Server 2016 или более поздние версии.

* Из Power BI недоступны *действия* и *именованные наборы*. Тем не менее вы можете подключаться к многомерным кубам, которые их содержат, чтобы создавать визуальные элементы и отчеты.

* Когда Power BI отображает метаданные для модели SSAS, иногда невозможно получить данные из модели. Такая ситуация может возникнуть, если вы установили 32-разрядную версию поставщика MSOLAP, а не 64-разрядную версию. Установка 64-разрядной версии поможет решить данную проблему.

* Вы не можете создавать меры *уровня отчета* при создании отчета с динамическим подключением к многомерной модели службы SSAS. Доступны только меры, определенные в модели MD.

## <a name="supported-features-of-ssas-md-in-power-bi-desktop"></a>Поддерживаемые возможности для работы с многомерными моделями SSAS в Power BI Desktop

В этом выпуске SSAS MD поддерживается использование следующих элементов. Дополнительные сведения об этих возможностях см. в разделе [Основные сведения о Power View для многомерных моделей](/sql/analysis-services/multidimensional-models/understanding-power-view-for-multidimensional-models?view=sql-server-2014).

* элементы по умолчанию;
* Атрибуты измерения
* Типы атрибутов измерения
* Вычисляемые элементы измерения, которые:
  * должны быть единственным действительным элементом, если измерение имеет несколько атрибутов;
  * не могут быть ключевым атрибутом измерения, если только это не единственный атрибут;
  * не могут быть атрибутом типа "родители-потомки".
* безопасность измерения.
* папки отображения;
* Иерархии
* URL-адреса изображений;
* Ключевые показатели эффективности
* тенденции изменения ключевых индикаторов производительности;
* меры (с группами мер или без них);
* меры как данные Variant.

## <a name="troubleshooting"></a>Устранение неполадок

Ниже перечислены все известные проблемы при подключении к службам SQL Server Analysis Services (SSAS).

* **Ошибка. Не удалось загрузить схему модели**. Эта ошибка обычно возникает, когда у подключающегося к службам Analysis Services пользователя нет доступа к кубу или базе данных.
