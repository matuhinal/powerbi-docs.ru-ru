---
title: Подключение к SweetIQ с помощью Power BI
description: SweetIQ для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6592405de2d76c14334c8c31e4af84cd5a090ed9
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34247557"
---
# <a name="connect-to-sweetiq-with-power-bi"></a>Подключение к SweetIQ с помощью Power BI
Пакет контента Power BI извлекает данные из учетной записи SweetIQ и создает набор готового содержимого, что позволяет легко изучать данные. Воспользуйтесь пакетом контента SweetIQ, чтобы проанализировать данные о местоположениях, списках, оценках и проверках. Данные обновляются ежедневно, так что вам всегда доступны последние сведения.

Подключите [пакет содержимого SweetIQ](https://app.powerbi.com/groups/me/getdata/services/sweetiq) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. На панели навигации слева щелкните **Получить данные**.
   
    ![](media/service-connect-to-sweetiq/getdata.png)
2. Выберите **SweetIQ** и щелкните **Получить**.
   
    ![](media/service-connect-to-sweetiq/sweetiq.png)
3. Укажите идентификатор клиента SweetIQ. Обычно это буквенно-цифровое значение. Дополнительные сведения о поиске этого значения см. ниже.
   
    ![](media/service-connect-to-sweetiq/parameter.png)
4. Выберите тип проверки подлинности **Ключ** и укажите свой API-ключ Sweet IQ. Обычно это буквенно-цифровое значение. Дополнительные сведения о поиске этого значения см. ниже.
   
    ![](media/service-connect-to-sweetiq/credentials.png)
5. Power BI начинает загрузку ваших данных, что может занять некоторое время в зависимости от размера данных вашей учетной записи. По окончании загрузки вы увидите новую панель мониторинга, отчет и набор данных в левой области навигации.
   
    ![](media/service-connect-to-sweetiq/dashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="finding-parameters"></a>Поиск параметров
ИД клиента и ключ API для этого пакета контента отличается от вашего имени пользователя и пароля SweetIQ.

Выберите ИД клиента для одного из клиентов, к которому у вашей учетной записи имеется доступ. Список клиентов доступен в разделе "Управление клиентами" вашей учетной записи SweetIQ.

Обратитесь к администратору, чтобы получить свой ключ API и, соответственно, доступ к данным для конкретного клиента.

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Получение данных для Power BI](service-get-data.md)

