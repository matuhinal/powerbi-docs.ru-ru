---
title: "Подключение к базе данных Oracle"
description: "Процедура и загружаемые файлы, необходимые для подключения Oracle к Power BI Desktop"
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
ms.openlocfilehash: 6308b2e201b669bf17ee636677232b365d62e332
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-an-oracle-database"></a>Подключение к базе данных Oracle
Для подключения к базе данных Oracle с помощью **Power BI Desktop** необходимо установить правильное программное обеспечение клиента Oracle на компьютере, где выполняется Power BI Desktop. Используемое клиентское программное обеспечение Oracle зависит от того, какую версию Power BI Desktop вы установили — **32-разрядную** или **64-разрядную**.

**Поддерживаемые версии**: Oracle 9 и более поздних версий; клиентское программное обеспечение Oracle 8.1.7 и более поздних версий.

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Определение установленной версии Power BI Desktop
Чтобы определить, какая версия Power BI Desktop установлена, выберите **Файл > О программе** и проверьте строку **Версия:**. На следующем рисунке показано, что установлена 64-разрядная версия Power BI Desktop:

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Установка клиента Oracle
Для **32-разрядной** версии Power BI Desktop используйте следующую ссылку, чтобы скачать и установить **32-разрядный** клиент Oracle:

* [32-разрядная версия Oracle Data Access Components (ODAC) с Oracle Developer Tools для Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

Для **64-разрядной** версии Power BI Desktop используйте следующую ссылку, чтобы скачать и установить **64-разрядный** клиент Oracle:

* [64-разрядная версия ODAC 12c, выпуск 4 (12.1.0.2.4), для 64-разрядных версий Windows](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>Подключение к базе данных Oracle
После установки соответствующего драйвера клиента Oracle можно подключиться к базе данных Oracle. Выполните следующие действия для подключения.

1. В окне "Получить данные" выберите **База данных > База данных Oracle**.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. В появившемся диалоговом окне **База данных Oracle** укажите имя сервера и выберите **Подключить**. Если необходим идентификатор безопасности (SID), можно указать его в формате *ИмяСервера/SID*.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. Если вы хотите импортировать данные с помощью собственного запроса к базе данных, запрос можно поместить в поле **Инструкция SQL**, которое доступно при развертывании раздела **Дополнительные параметры** диалогового окна **База данных Oracle**.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. После ввода сведений о базе данных Oracle в диалоговом окне "База данных Oracle" (включая любую дополнительную информацию, например идентификатор безопасности или собственный запрос к базе данных) нажмите кнопку **ОК** для подключения.
5. Если базе данных Oracle требуются учетные данные пользователя базы данных, введите эти учетные данные в диалоговом окне при появлении запроса.

