---
title: Запись дополнительных диагностических сведений
description: Эти инструкции предоставляют два возможных варианта ручного сбора дополнительных диагностических сведений из веб-клиента Power BI.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/17/2019
ms.author: kfollis
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 49e0b85cb42b008f8d5e3e38296172e24b868fa8
ms.sourcegitcommit: c18130ea61e67ba111be870ddb971c6413a4b632
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86161222"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>Запись дополнительных диагностических сведений для Power BI

В этой статье представлены инструкции по ручному сбору дополнительных диагностических сведений из веб-клиента Power BI.

1. Перейдите к [Power BI](https://app.powerbi.com) с помощью браузера Microsoft Edge или Internet Explorer.

1. Нажмите клавишу **F12**, чтобы открыть средства разработчика Microsoft Edge.

   ![Снимок экрана: вкладка "Элементы" в средствах разработчика Microsoft Edge](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. Откройте вкладку **Сеть**. Здесь указан уже зафиксированный трафик.

   ![Снимок экрана: вкладка "Сеть" в средствах разработчика Microsoft Edge](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    Вы можете выбрать один из следующих вариантов.

    * Перемещайтесь по этому окну и воспроизводите возникшие проблемы.

    * Чтобы скрыть или показать окно средств разработчика в любой момент во время работы, нажмите клавишу F12.

1. Чтобы остановить профилирование сеанса, щелкните красный квадрат на вкладке **Сеть** в области средств разработчика.

   ![Снимок экрана: вкладка "Сеть" в средствах разработчика Microsoft Edge с выделенным значком остановки](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. Выберите значок дискеты, чтобы экспортировать данные в качестве архива HTTP (HAR-файла).

   ![Снимок экрана: вкладка "Сеть" в области средств разработчика Microsoft Edge с выделенным значком дискеты](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. Укажите имя HAR-файла и сохраните его.

    HAR-файл будет содержать все сведения о сетевых запросах между окном браузера и Power BI, в том числе:

    * идентификаторы действий для каждого запроса;

    * точную метку времени для каждого запроса;

    * все сведения об ошибках, возвращенные клиенту.

    Эта трассировка также будет содержать данные, используемые для заполнения визуальных элементов, отображаемых на экране.

1. HAR-файл можно передать на анализ службе поддержки.

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
