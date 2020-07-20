---
title: Отключение фонового обновления Power Query
description: Руководство по отключению фонового обновления Power Query.
author: peter-myers
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: v-pemyer
ms.openlocfilehash: 39eef27e746e636ddb331d28a930c1cd0dca0a5d
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2020
ms.locfileid: "86214928"
---
# <a name="disable-power-query-background-refresh"></a>Отключение фонового обновления Power Query

В этой статье описываются средства моделирования данных импорта, работающие с Power BI Desktop.

По умолчанию, когда надстройка Power Query импортирует данные, она также кэширует до 1000 строк предварительных данных для каждого запроса. Предварительные данные позволяют быстро выполнять предварительный просмотр исходных данных, а также результатов преобразования на каждом этапе запроса. Они хранятся на диске отдельно, а не в файле Power BI Desktop.

Однако если файл Power BI Desktop содержит много запросов, получение и хранение предварительных данных может замедлять обновление.

## <a name="recommendation"></a>Рекомендация

Чтобы ускорить обновление, можно настроить файл Power BI Desktop так, чтобы кэш предварительных данных обновлялся _в фоновом режиме_. В Power BI Desktop для этого нужно выбрать _Файл > Параметры и настройки > Параметры_, а затем перейти на страницу _Загрузка данных_. На ней можно включить параметр **Разрешить скачивание в фоновом режиме для предварительного просмотра данных**. Имейте в виду, что этот параметр можно задать только для текущего файла.

![Снимок экрана: Power BI Desktop с параметрами фоновых данных](media/power-query-background-refresh/power-query-options-background-data.png)

Если включено фоновое обновление, предварительные данные могут оказаться устаревшими. В этом случае Редактор Power Query выдаст следующее предупреждение:

![Снимок экрана: Power BI Desktop с Редактором Power Query, предупреждающим о старых предварительных данных](media/power-query-background-refresh/power-query-preview-data-old.png)

Кэш предварительных данных можно обновить в любой момент. Его можно обновить для отдельного запроса или для всех с помощью команды **Обновить просмотр**. Она находится на вкладке **Главная страница** ленты в окне Редактора Power Query.

![Снимок экрана: Power BI Desktop с командами Редактора Power Query для обновления предварительных данных](media/power-query-background-refresh/power-query-refresh-preview-data.png)

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения, связанные с темой этой статьи, см. в следующих ресурсах.

- [Документация по Power Query](/power-query/)
- У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
