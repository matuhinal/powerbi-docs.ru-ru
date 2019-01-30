---
title: Подключение к базе данных Oracle
description: Процедура и загружаемые файлы, необходимые для подключения Oracle к Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 826338a5e5524bb54c2ebb2207a3d438a8d428b1
ms.sourcegitcommit: 3c8196be5626a0f037599abb6ccbd294fb1249df
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2019
ms.locfileid: "54899234"
---
# <a name="connect-to-an-oracle-database"></a>Подключение к базе данных Oracle
Для подключения к базе данных Oracle с помощью **Power BI Desktop** необходимо установить правильное программное обеспечение клиента Oracle на компьютере, где выполняется Power BI Desktop. Используемое клиентское программное обеспечение Oracle зависит от того, какую версию Power BI Desktop вы установили — **32-разрядную** или **64-разрядную**.

**Поддерживаемые версии**: Oracle 9 и более поздних версий, клиентское программное обеспечение Oracle 8.1.7 и более поздних версий.

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Определение установленной версии Power BI Desktop
Чтобы определить, какая версия Power BI Desktop установлена, выберите **Файл > Справка > О программе** и проверьте строку **Версия:**. На следующем рисунке показано, что установлена 64-разрядная версия Power BI Desktop:

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Установка клиента Oracle
Для **32-разрядной** версии Power BI Desktop используйте следующую ссылку, чтобы скачать и установить **32-разрядный** клиент Oracle:

* [32-разрядная версия Oracle Data Access Components (ODAC) с Oracle Developer Tools для Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

Для **64-разрядной** версии Power BI Desktop используйте следующую ссылку, чтобы скачать и установить **64-разрядный** клиент Oracle:

* [64-разрядная версия ODAC 12c, выпуск 4 (12.1.0.2.4), для 64-разрядных версий Windows](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>Подключение к базе данных Oracle
После установки соответствующего драйвера клиента Oracle можно подключиться к базе данных Oracle. Чтобы установить соединение, сделайте следующее:

1. В окне "Получить данные" выберите **База данных > База данных Oracle**.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. В появившемся диалоговом окне **База данных Oracle** укажите имя сервера и выберите **Подключить**. Если требуется идентификатор безопасности (SID), можно указать его в формате *имя_сервера/SID*, где SID — это уникальное имя базы данных. Если формат *ИмяСервера/SID* не подходит, попробуйте использовать формат *ИмяСервера/ИмяСлужбы*, где ИмяСлужбы — это псевдоним, используемый при подключении.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. Если вы хотите импортировать данные с помощью собственного запроса к базе данных, запрос можно поместить в поле **Инструкция SQL**, которое доступно при развертывании раздела **Дополнительные параметры** диалогового окна **База данных Oracle**.
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. После ввода сведений о базе данных Oracle в диалоговом окне "База данных Oracle" (включая любую дополнительную информацию, например идентификатор безопасности или собственный запрос к базе данных) нажмите кнопку **ОК** для подключения.
5. Если базе данных Oracle требуются учетные данные пользователя базы данных, введите эти учетные данные в диалоговом окне при появлении запроса.


## <a name="troubleshooting"></a>Устранение неполадок

Если вы скачали Power BI Desktop из Microsoft Store, может возникнуть проблема с подключением к базам данных Oracle из-за проблемы с драйвером Oracle. Если вы столкнетесь с этой проблемой, появится сообщение об ошибке "Ссылка на объект не установлена". Чтобы устранить проблему, выполните одно из следующих действий:

* Скачайте Power BI Desktop с сайта https://powerbi.microsoft.com/desktop.

* Если вы хотите использовать версию из Microsoft Store: на локальном компьютере скопируйте файл oraons.dll из папки _12.X.X\client_X_ в папку _12.X.X\client_X\bin_. "X" означает версию и номера каталогов.
