---
title: Настройка запланированного обновления
description: Здесь описано, как выбрать шлюз и настроить запланированное обновление.
author: davidiseminger
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/06/2019
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: cc0527d093118fdb585800d0038f824223098119
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83323627"
---
# <a name="configure-scheduled-refresh"></a>Настройка запланированного обновления

>[!NOTE]
>После двух месяцев бездействия запланированное обновление набора данных будет приостановлено. Дополнительные сведения см. в разделе [*Запланированное обновление*](#scheduled-refresh) этой статьи.

В этой статье описываются параметры, доступные для обновления [локального шлюза данных (персональный режим)](service-gateway-personal-mode.md) и [локального шлюза данных](service-gateway-onprem.md) по расписанию. Параметры обновления настраиваются в следующих областях службы Power BI: **Подключение шлюза**, **Учетные данные источников данных** и **Запланированное обновление**. Мы рассмотрим каждую из них по очереди. Дополнительные сведения об обновлении данных, в том числе об ограничениях обновления по расписанию, см. в статье [Обновление данных](refresh-data.md#data-refresh).

Чтобы перейти к экрану **Запланированное обновление**, выполните указанные ниже действия.

1. В области навигации в разделе **Наборы данных** щелкните **Дополнительные параметры** (…) рядом с набором данных в списке.
2. Щелкните **Расписание обновлений**.

    ![Расписание обновлений](media/refresh-scheduled-refresh/dataset-menu.png)

## <a name="gateway-connection"></a>Подключение шлюза

Вы увидите различные параметры в зависимости от того, имеется личный или корпоративный шлюз, а также доступен ли он в сети.

Если шлюз недоступен, раздел **Подключение шлюза** неактивен. Кроме того, вы увидите сообщение о том, как установить личный шлюз.

![Шлюз не настроен](media/refresh-scheduled-refresh/gateway-not-configured.png)

Если личный шлюз настроен и находится в сети, его можно выбрать. Если он недоступен, то отображается как не в сети.

![Подключение шлюза](media/refresh-scheduled-refresh/gateway-connection.png)

Можно выбрать корпоративный шлюз, если он доступен. Вы увидите корпоративный шлюз, только если ваша учетная запись указана на вкладке **Пользователи** источника данных, настроенного для данного шлюза.

## <a name="data-source-credentials"></a>Учетные данные источников данных

### <a name="power-bi-gateway---personal"></a>Шлюз Power BI — персональный

Если вы используете персональный шлюз для обновления данных, нужно указать учетные данные для подключения к внутреннему источнику данных. Если используется подключение к пакету содержимого из веб-службы, то введенные учетные данные подключения используются и для запланированного обновления.

![Учетные данные источников данных](media/refresh-scheduled-refresh/data-source-credentials-pgw.png)

Входить в источник данных нужно лишь при первом использовании обновления для этого набора данных. После первого ввода эти учетные данные сохраняются вместе с набором данных.

> [!NOTE]
> В случае с некоторыми методами проверки подлинности нужно помнить, что, если истекает срок действия пароля, используемого для входа в источник данных, или же изменяется сам пароль, его также нужно изменить в разделе **Учетные данные источника данных**.

Обычно возникающие проблемы вызваны следующими причинами: шлюз находится в автономном режиме, так как не может выполнить вход в Windows и запустить службу, либо Power BI не удается войти в источники данных для запроса обновленных данных. Если обновление завершается со сбоем, проверьте параметры набора данных. Если служба шлюза находится в автономном режиме, ошибка отображается в поле **Состояние**. Если Power BI не удается войти в источники данных, ошибка отображается в учетных данных источника данных.

### <a name="on-premises-data-gateway"></a>Локальный шлюз данных

При использовании локального шлюза данных для обновления нет необходимости предоставлять учетные данные, так как они определены для источника данных администратором шлюза.

![Команда "Расписание обновлений"](media/refresh-scheduled-refresh/data-source-credentials-egw.png)

> [!NOTE]
> При подключении к локальным источникам данных SharePoint для обновления данных Power BI поддерживает только следующие механизмы аутентификации: *анонимный доступ*, *обычная проверка подлинности* и *аутентификация Windows (NTLM/Kerberos)* . Power BI не поддерживает *ADFS* или механизмы *проверки подлинности на основе форм* для обновления данных из локальных источников данных SharePoint.

## <a name="scheduled-refresh"></a>Запланированное обновление

В разделе **Запланированное обновление** можно определить частоту и периоды времени для обновления набора данных. Некоторым источникам данных для настройки для обновления шлюз нужен, а некоторым — нет.

Чтобы настроить параметры, установите для параметра **Поддерживать актуальность данных** значение **Включено**.

> [!NOTE]
> Цель заключается в запуске обновления в пределах 15 минут от запланированного периода времени, однако может иметь место задержка до одного часа, если службе не удается выделить требуемые ресурсы быстрее.

![Диалоговое окно "Запланированное обновление"](media/refresh-scheduled-refresh/scheduled-refresh.png)

> [!NOTE]
> После двух месяцев бездействия запланированное обновление набора данных будет приостановлено. Набор данных считается неактивным, если пользователи не открывали панели мониторинга или отчеты, созданные на основе этого набора данных. В этом случае владельцу набора данных отправляется электронное сообщение о том, что обновление по расписанию приостановлено. Расписание обновления для набора данных отображается как **отключенное**. Чтобы возобновить запланированное обновление, просто повторно откройте любую панель мониторинга или отчет, созданные на основе набора данных.

## <a name="whats-supported"></a>Поддерживаемые функции


> [!NOTE]
> Запланированное обновление также будет отключено автоматически после четырех ошибок подряд.

Запланированное обновление поддерживается для определенных наборов данных с использованием разных шлюзов. Ниже приведен справочник, позволяющий понять, что доступно, а что — нет.

### <a name="power-bi-gateway---personal"></a>Шлюз Power BI — персональный

**Power BI Desktop**

* Все источники данных в сети, отображаемые в редакторе запросов и разделе **Получение данных** в Power BI Desktop.
* Все локальные источники данных, отображаемые в редакторе запросов и разделе **Получение данных** в Power BI Desktop, кроме файла Hadoop (HDFS) и Microsoft Exchange.

**Excel**

* Все источники данных в сети, отображаемые в Power Query.
* Все локальные источники данных, отображаемые в Power Query, кроме файла Hadoop (HDFS) и Microsoft Exchange.
* Все источники данных в сети, отображаемые в Power Pivot.
* Все локальные источники данных, отображаемые в Power Pivot, кроме файла Hadoop (HDFS) и Microsoft Exchange.

> [!NOTE]
> В Excel 2016 и более поздних версиях функция Power Query доступна в разделе **Данные** на вкладке **Get & Transform Data** (Получить и преобразовать данные) ленты.

### <a name="power-bi-gateway"></a>Power BI Gateway

Сведения о поддерживаемых источниках данных см. в статье [Источники данных Power BI](power-bi-data-sources.md).

## <a name="troubleshooting"></a>Устранение неполадок
Иногда обновление данных может завершиться неправильно. Как правило, проблема связана со шлюзом. Ознакомьтесь со статьями об устранении неполадок со шлюзом и узнайте о соответствующих средствах и известных проблемах.

- [Устранение неполадок локального шлюза данных](service-gateway-onprem-tshoot.md)
- [Устранение неполадок с Power BI Gateway — Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)

## <a name="next-steps"></a>Дальнейшие действия

- [Обновление данных в Power BI](refresh-data.md)  
- [Шлюз Power BI Gateway — Personal](service-gateway-personal-mode.md)  
- [Локальный шлюз данных (персональный режим)](service-gateway-onprem.md)  
- [Устранение неполадок локального шлюза данных](service-gateway-onprem-tshoot.md)  
- [Устранение неполадок с Power BI Gateway — Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)