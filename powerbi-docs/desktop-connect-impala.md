---
title: "Подключение к базе данных Impala в Power BI Desktop"
description: "Простое и удобное подключение к базе данных Impala в Power BI Desktop и ее использование"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 196974bedcace4fbe51b7e7ac551bd0923f7a891
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Подключение к базе данных Impala в Power BI Desktop
В Power BI Desktop вы можете подключиться к базе данных **Impala** и использовать ее так же, как и любой другой источник данных в Power BI Desktop.

## <a name="connect-to-an-impala-database"></a>Подключение к базе данных Impala
Для подключения к базе данных **Impala** на вкладке **Главная** на ленте в Power BI Desktop выберите **Получение данных**. В области слева выберите категорию **База данных**. Отобразится пункт **Impala**.

![](media/desktop-connect-impala/connect_impala_2.png)

В появившемся окне **Impala** введите или вставьте в поле имя сервера Impala и нажмите кнопку **ОК**. Обратите внимание, что можно **импортировать** данные непосредственно в Power BI или использовать **DirectQuery**. Вы можете ознакомиться с дополнительными сведениями об [использовании DirectQuery](desktop-use-directquery.md).

![](media/desktop-connect-impala/connect_impala_3a.png)

При появлении запроса введите имя пользователя и пароль или подключитесь анонимно (поддерживаются оба варианта).

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> Если указаны имя пользователя и пароль для определенного сервера **Impala**, Power BI Desktop использует те же учетные данные при последующих попытках подключения. Эти учетные данные можно изменить, последовательно выбрав элементы **Файл > Параметры и настройки > Параметры источника данных**.
> 
> 

После успешного подключения откроется окно **Навигатор**, содержащее данные, доступные на сервере. Из них вы можете выбрать один или несколько элементов для импорта и использования в **Power BI Desktop**.

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Рекомендации и ограничения
Существуют определенные ограничения и рекомендации, которые следует учитывать в соединителе **Impala**.

* Будущие планы включают поддержку обновлений с использованием **Power BI Gateway**.

## <a name="next-steps"></a>Дальнейшие действия
В Power BI Desktop можно подключаться к данным самых разных видов. Дополнительные сведения об источниках данных см. в перечисленных ниже статьях.

* [Начало работы с Power BI Desktop](desktop-getting-started.md)
* [Источники данных в Power BI Desktop](desktop-data-sources.md)
* [Формирование и объединение данных в Power BI Desktop](desktop-shape-and-combine-data.md)
* [Подключение к данным Excel в Power BI Desktop](desktop-connect-excel.md)   
* [Ввод данных непосредственно в Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

