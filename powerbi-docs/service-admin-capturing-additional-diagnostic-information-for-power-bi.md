---
title: Запись дополнительных диагностических сведений
description: Эти инструкции предоставляют два возможных варианта ручного сбора дополнительных диагностических сведений из веб-клиента Power BI.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 710fb4cdcf9efb051434966d47c2eaced17ac9ba
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100212"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>Запись дополнительных диагностических сведений для Power BI

В этой статье инструкции ручного сбора дополнительных диагностических сведений из веб-клиента Power BI.

1. Перейдите к [Power BI](https://app.powerbi.com) с Microsoft Edge или Internet Explorer.

1. Нажмите клавишу **F12** открытие средств разработчика Microsoft Edge.

   ![Снимок экрана из Microsoft Edge Developer вкладки "Сервис элементы".](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. Откройте вкладку **Сеть**. Здесь указан уже зафиксированный трафик.

   ![Снимок экрана из Microsoft Edge Developer tools вкладка «сеть».](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    Вы можете выбрать один из следующих вариантов.

    * Перейдите в окно и воспроизвести все проблемы, которые вы можете столкнуться.

    * Скрыть и Показать разработчика, окно "средства" в любое время, во время сеанса, нажав клавишу F12.

1. Чтобы остановить сеанс профилирования, выберите красный квадрат на **сети** вкладку разработчика средств области.

   ![Снимок экрана из Microsoft Edge Developer tools вкладка «сеть» с помощью вызова за пределы "Остановить".](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. Выберите значок дискеты, чтобы экспортировать данные в виде файла архива HTTP (HAR).

   ![Снимок экрана из Microsoft Edge Developer tools вкладка «сеть» в выноске значок дискеты.](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. Укажите имя HAR-файла и сохраните его.

    HAR-файл будет содержать все сведения о сетевых запросах между окном браузера и включая Power BI:

    * Идентификаторы действий для каждого запроса.

    * Точные метки времени для каждого запроса.

    * Информация об ошибках, возвращаемых клиенту.

    Эта трассировка также будет содержать данные, используемые для заполнения визуальных элементов, отображаемых на экране.

1. HAR-файл можно передать на анализ службе поддержки.

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)
