---
title: Использование SAP HANA в Power BI Desktop
description: Использование SAP HANA в Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c2a2069eb5f4d056db5840a08ecb1a871bf587c8
ms.sourcegitcommit: f01a88e583889bd77b712f11da4a379c88a22b76
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2018
ms.locfileid: "39329875"
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>Использование SAP HANA в Power BI Desktop
Теперь с помощью Power BI Desktop вы можете получить доступ к базе данных **SAP HANA** . Для использования **SAP HANA**на локальном клиентском компьютере нужно установить драйвер ODBC SAP HANA, чтобы подключение к данным **SAP HANA** в Power BI Desktop работало правильно. Драйвер ODBC SAP HANA можно скачать в [Центре скачивания программного обеспечения SAP](https://support.sap.com/swdc). В нем следует найти клиент SAP HANA CLIENT для компьютеров Windows. В связи с частым изменением структуры **Центра скачивания программного обеспечения SAP** более конкретные рекомендации по навигации по этому сайту недоступны.

Для подключения к базе данных **SAP HANA** последовательно выберите пункты **Получить данные > База данных > База данных SAP HANA**, как показано на следующем рисунке:

![](media/desktop-sap-hana/sap-hana-1.png)

При подключении к базе данных SAP HANA укажите имя сервера и порт в формате *сервер:порт*. На рисунке ниже показан пример, в котором используется имя сервера *ServerXYZ* и порт *30015*.

![](media/desktop-sap-hana/sap-hana-2.png)

В этом выпуске **SAP HANA** в режиме [DirectQuery](desktop-directquery-sap-hana.md) поддерживается в Power BI Desktop и службе Power BI, и вы можете публиковать и отправлять отчеты, использующие **SAP HANA** в режиме DirectQuery, в службу Power BI. Когда **SAP HANA** не используется в режиме DirectQuery, вы также можете публиковать и отправлять отчеты в службу Power BI.

### <a name="supported-features-for-sap-hana"></a>Поддерживаемые компоненты SAP HANA
Этот выпуск содержит множество возможностей для работы с **SAP HANA**, перечисленных в списке ниже.

* Для удобства пользователей соединитель Power BI для **SAP HANA** использует драйвер SAP ODBC.
* **SAP HANA** поддерживает DirectQuery и функцию импорта
* Power BI поддерживает информационные модели HANA (например, представления аналитики и вычислений) и отличается оптимизированной навигацией.
* **SAP HANA** позволяет использовать функцию прямого SQL для подключения к строкам и столбцам таблиц.
* Включает оптимизированную навигацию для моделей HANA
* Power BI поддерживает переменные и входные параметры **SAP HANA**

### <a name="installing-the-sap-hana-odbc-driver"></a>Установка драйвера ODBC SAP HANA
### <a name="limitations-of-sap-hana"></a>Ограничения SAP HANA
Использование **SAP HANA**связано с рядом описанных ниже ограничений.

* Строки NVARCHAR усекаются максимум до 4000 символов Юникод
* SMALLDECIMAL не поддерживается
* VARBINARY не поддерживается
* Допустимый диапазон дат — с 30.12.1899 до 31.12.9999.


## <a name="next-steps"></a>Дальнейшие действия
Дополнительные сведения о DirectQuery см. в следующих статьях:

* [DirectQuery и SAP HANA](desktop-directquery-sap-hana.md)
* [Power BI и DirectQuery](desktop-directquery-about.md)
* [Источники данных, поддерживаемые DirectQuery](desktop-directquery-data-sources.md)

