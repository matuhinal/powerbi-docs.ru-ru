---
title: Образец модели DAX
description: Образец модели DAX для поддержки статей справки.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/25/2020
ms.author: v-pemyer
ms.openlocfilehash: 0efa26a6ef3e47272d1434fab453a17ad9823c8c
ms.sourcegitcommit: cff93e604e2c5f24e0f03d6dbdcd10c2332aa487
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90965438"
---
# <a name="dax-sample-model"></a>Образец модели DAX

Пример модели Power BI Desktop **Adventure Works DW 2020** предназначен для поддержки обучения DAX. Модель основана на [образце хранилища данных Adventure Works](/sql/samples/adventureworks-install-configure#data-warehouse-downloads) для AdventureWorksDW2017, однако данные были изменены в соответствии с целями образца модели.

## <a name="scenario"></a>Сценарий

:::image type="content" source="media/dax-sample-model/adventure-works-logo-150x150.png" alt-text="Изображение логотипа компании Adventure Works.":::

Компания Adventure Works представляет производителя велосипедов, который продает велосипеды и аксессуары на международных рынках. Данные компании хранятся в хранилище данных в Базе данных SQL Azure.

## <a name="model-structure"></a>Структура модели

Модель содержит семь таблиц:

|Таблица|Описание|
|-----|-------|
|**Customer**|Описание клиентов и их географических расположений. Клиенты приобретают продукты в Интернете (интернет-продажи).|
|**Date**|Существует три связи между таблицами **Дата** и **Продажи**: даты заказа, даты отгрузки и даты доставки. Связь "Дата заказа" активна. Отчеты компании содержат данные продаж за финансовый год, который начинается 1 июля каждого года. Таблица помечается как таблица дат с помощью столбца **Date**.|
|**Продукт**|Хранит только готовые продукты.|
|**Торговый посредник**|Описывает торговых посредников и их географические расположения. Торговый посредник занимается продажей продуктов своим клиентам.|
|**Sales**|Хранит строки из заказа на продажу. Все финансовые значения задаются в долларах США (USD). Наиболее ранняя дата заказа — 1 июля 2017 г., а последняя дата заказа — 15 июня 2020 г.|
|**Заказ на продажу**|Описывает заказы на продажу и номера строк заказов, а также канал продаж: **Reseller** или **Internet**. Эта таблица имеет связь "один к одному" с таблицей **Sales**.|
|**Территория продаж**|Территории продаж организованы в группы (Северная Америка, Европа и Тихоокеанский регион), страны и регионы. Только в США продукты продаются на уровне региона.|

Модель не содержит никаких вычислений DAX.

## <a name="download-sample"></a>Скачивание образца

Файл образца модели Power BI Desktop можно загрузить [здесь](https://aka.ms/dax-docs-sample-file).

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения по этим вопросам см. в следующих ресурсах.

- [Руководство по выражениям анализа данных (DAX)](/dax/)
- Схема обучения: [Использование DAX в Power BI Desktop](/learn/paths/dax-power-bi/)
- У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
- У вас есть предложения? [Идеи по улучшению Power BI](https://ideas.powerbi.com)