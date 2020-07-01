---
title: Подключение к хранилищу Snowflake Computing в Power BI Desktop
description: 'Хранилище вычислительных ресурсов Snowflake в Power BI Desktop: простое подключение и использование'
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b343136acb22d213c0e2ad2dfcf83fbda805e88a
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85224140"
---
# <a name="connect-to-a-snowflake-computing-warehouse-in-power-bi-desktop"></a>Подключение к хранилищу данных Snowflake Computing из Power BI Desktop
В Power BI Desktop вы можете подключиться к хранилищу вычислительных ресурсов **Snowflake**, чтобы использовать его так же, как и любой другой источник данных в Power BI Desktop. 

## <a name="connect-to-a-snowflake-computing-warehouse"></a>Подключение к хранилищу вычислительных ресурсов Snowflake
Для подключения к хранилищу вычислительных ресурсов **Snowflake** на вкладке **Главная** на ленте в Power BI Desktop выберите **Получить данные**. В области слева выберите категорию **База данных**. Отобразится пункт **Snowflake**.

![](media/desktop-connect-snowflake/connect-snowflake-2b.png)

В появившемся окне **Snowflake** введите или вставьте в поле имя хранилища вычислительных ресурсов Snowflake и нажмите кнопку **ОК**. Обратите внимание, что можно **импортировать** данные непосредственно в Power BI или использовать **DirectQuery**. Вы можете ознакомиться с дополнительными сведениями об [использовании DirectQuery](desktop-use-directquery.md). Обратите внимание на то, что единый вход AAD поддерживает только DirectQuery.

![](media/desktop-connect-snowflake/connect-snowflake-3.png)

При появлении запроса укажите имя пользователя и пароль.

![](media/desktop-connect-snowflake/connect-snowflake-4.png)

> [!NOTE]
> Если указаны имя пользователя и пароль для определенного сервера **Snowflake**, Power BI Desktop будет использовать те же учетные данные при последующих попытках подключения. Эти учетные данные можно изменить, последовательно выбрав элементы **Файл > Параметры и настройки > Параметры источника данных**.
> 
> 

Чтобы использовать учетную запись Майкрософт, необходимо настроить интеграцию Snowflake с AAD на стороне Snowflake. Для этого ознакомьтесь с разделом Getting Started (Начало работы) в [документации Snowflake по этой теме](https://docs.snowflake.net/manuals/user-guide/oauth-powerbi.html#power-bi-sso-to-snowflake).

![Тип проверки подлинности учетной записи Майкрософт в соединителе Snowflake.](media/desktop-connect-snowflake/connect-snowflake-6.png)


После успешного подключения откроется окно **Навигатор**, содержащее данные, доступные на сервере. Из них вы можете выбрать один или несколько элементов для импорта и использования в **Power BI Desktop**.

![Ошибка ODBC 28000, приводящая к сбою подключения.](media/desktop-connect-snowflake/connect-snowflake-5.png)

Вы можете **загрузить** выбранную таблицу, после чего таблица будет целиком перемещена в **Power BI Desktop**. Или же можно **изменить** запрос — в таком случае откроется **редактор запросов**, с помощью которого можно отфильтровать и уточнить набор нужных вам данных, а затем загрузить уточненный набор данных в **Power BI Desktop**.

## <a name="next-steps"></a>Дальнейшие действия
В Power BI Desktop можно подключаться к данным самых разных видов. Дополнительные сведения об источниках данных см. в перечисленных ниже статьях.

* [Что такое Power BI Desktop?](../fundamentals/desktop-what-is-desktop.md)
* [Источники данных в Power BI Desktop](desktop-data-sources.md)
* [Формирование и объединение данных в Power BI Desktop](desktop-shape-and-combine-data.md)
* [Подключение к данным Excel в Power BI Desktop](desktop-connect-excel.md)   
* [Ввод данных непосредственно в Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   
