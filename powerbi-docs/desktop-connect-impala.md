---
title: Подключение к базе данных Impala в Power BI Desktop
description: Простое и удобное подключение к базе данных Impala в Power BI Desktop и ее использование
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 3be28f80e12954941f81b749fb934b1a53b6130d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54284479"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>Подключение к базе данных Impala в Power BI Desktop
В Power BI Desktop вы можете подключиться к базе данных **Impala** и использовать ее так же, как и любой другой источник данных в Power BI Desktop.

## <a name="connect-to-an-impala-database"></a>Подключение к базе данных Impala
Для подключения к базе данных **Impala**, сделайте следующее: 

1. В Power BI Desktop на вкладке ленты **Главная** выберите **Получить данные**. 

2. В области слева выберите категорию **База данных**. Отобразится **Impala**.

    ![Получить данные](media/desktop-connect-impala/connect_impala_2.png)

3. В появившемся окне **Impala** введите или вставьте в поле имя сервера Impala. Нажмите кнопку **ОК**. Вы можете **импортировать** данные непосредственно в Power BI или использовать **DirectQuery**. См. дополнительные сведения об [использовании DirectQuery](desktop-use-directquery.md).

    ![Окно Impala](media/desktop-connect-impala/connect_impala_3a.png)

4. При появлении запроса введите учетные данные или подключитесь анонимно. Соединитель Impala поддерживает анонимную проверку подлинности, обычную проверку подлинности (имя пользователя и пароль) и проверку подлинности Windows.

    ![Соединитель Impala](media/desktop-connect-impala/connect_impala_4.png)

    > [!NOTE]
    > Когда будут указаны имя пользователя и пароль для определенного сервера **Impala**, Power BI Desktop запомнит эти учетные данные для последующих попыток подключения. Эти учетные данные можно изменить, последовательно выбрав элементы **Файл > Параметры и настройки > Параметры источника данных**.


5. После подключения появится окно **Навигатор**, которое отображает данные, доступные на сервере. Выберите нужные элементы для импорта и использования в **Power BI Desktop**.

    ![Окно "Навигатор"](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>Рекомендации и ограничения
Существуют определенные ограничения и рекомендации, которые следует учитывать при работе с соединителем **Impala**.

* Соединитель Impala поддерживается в локальном шлюзе данных с помощью любого из трех механизмов проверки подлинности.

## <a name="next-steps"></a>Дальнейшие действия
Power BI Desktop поддерживает возможность подключения к разным источникам данных. Дополнительные сведения об источниках данных см. в следующих статьях:

* [Что такое Power BI Desktop?](desktop-what-is-desktop.md)
* [Источники данных в Power BI Desktop](desktop-data-sources.md)
* [Формирование и объединение данных в Power BI Desktop](desktop-shape-and-combine-data.md)
* [Подключение к данным Excel в Power BI Desktop](desktop-connect-excel.md)   
* [Ввод данных непосредственно в Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   

