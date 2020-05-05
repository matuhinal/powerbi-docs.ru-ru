---
title: Подключение к базе данных Oracle
description: Процедура и загружаемые файлы, необходимые для подключения Oracle к Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/24/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a118cd0874410e538ca8329e0b8c0ed1bdb430b7
ms.sourcegitcommit: 834cad24901f7fd966c4010e36a7904bc120e57f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "82149594"
---
# <a name="connect-to-an-oracle-database"></a>Подключение к базе данных Oracle
Для подключения к базе данных Oracle с помощью Power BI Desktop необходимо установить правильное программное обеспечение клиента Oracle на компьютере, где выполняется Power BI Desktop. Используемое клиентское программное обеспечение Oracle зависит от того, какую версию Power BI Desktop вы установили: 32-разрядную или 64-разрядную.

Поддерживаемые версии Oracle: 
- Oracle 9 и более поздней версии
- Клиентское программное обеспечение Oracle 8.1.7 и более поздней версии

> [!NOTE]
> Если вы настраиваете базу данных Oracle для Сервера отчетов Power BI, см. сведения о [типе соединения Oracle](https://docs.microsoft.com/sql/reporting-services/report-data/oracle-connection-type-ssrs?view=sql-server-ver15). 


## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>Определение установленной версии Power BI Desktop
Чтобы определить, какая версия Power BI Desktop установлена, выберите **Файл** > **Справка** > **О программе** и проверьте строку **Версия**. На следующем рисунке показано, что установлена 64-разрядная версия Power BI Desktop:

![Версия Power BI Desktop](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>Установка клиента Oracle
- Для 32-разрядной версии Power BI Desktop [скачайте и установите 32-разрядный клиент Oracle](https://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html).

- Для 64-разрядной версии Power BI Desktop [скачайте и установите 64-разрядный клиент Oracle](https://www.oracle.com/technetwork/database/windows/downloads/index-090165.html).

## <a name="connect-to-an-oracle-database"></a>Подключение к базе данных Oracle
После установки соответствующего драйвера клиента Oracle можно подключиться к базе данных Oracle. Чтобы установить соединение, сделайте следующее:

1. На вкладке **Главная** выберите пункт **Получить данные**. 

2. В открывшемся окне **Получить данные** при необходимости выберите **Дополнительно** и затем выберите **База данных** > **База данных Oracle**, после чего нажмите кнопку **Подключиться**.
   
   ![Подключение к базе данных Oracle](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. В появившемся диалоговом окне **База данных Oracle** укажите имя в поле **Сервер** и нажмите кнопку **ОК**. Если требуется идентификатор безопасности (SID), можно указать его в следующем формате: *имя_сервера/SID*, где *SID* — это уникальное имя базы данных. Если формат *имя_сервера/SID* не подходит, попробуйте использовать формат *имя_сервера/имя_службы*, где *имя_службы* — это псевдоним, используемый при подключении.


   ![Ввод имени сервера Oracle](media/desktop-connect-oracle-database/connect-oracle-database_3.png)

   > [!TIP]
   > При возникновении проблем с подключением на этом шаге используйте следующий формат в поле **Сервер**: *(DESCRIPTION=(ADDRESS=(PROTOCOL=TCP)(HOST=имя_узла)(PORT=номер_порта))(CONNECT_DATA=(SERVICE_NAME=имя_службы)))*
   
3. Если вы хотите импортировать данные с помощью собственного запроса к базе данных, запрос можно поместить в поле **Инструкция SQL**, которое появляется при развертывании раздела **Дополнительные параметры** диалогового окна **База данных Oracle**.
   
   ![Развертывание раздела "Дополнительные параметры"](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. После ввода сведений о базе данных Oracle в диалоговом окне **База данных Oracle** (включая любую дополнительную информацию, например идентификатор безопасности или собственный запрос к базе данных) нажмите кнопку **ОК** для подключения.
5. Если базе данных Oracle требуются учетные данные пользователя базы данных, введите эти учетные данные в диалоговом окне при появлении запроса.


## <a name="troubleshooting"></a>Устранение неполадок

Если вы скачали Power BI Desktop из Microsoft Store, может возникнуть проблема с подключением к базам данных Oracle из-за проблемы с драйвером Oracle. Если вы столкнетесь с этой проблемой, появится следующее сообщение об ошибке: *Ссылка на объект не задана*. Чтобы устранить эту проблему, выполните одно из следующих действий:

* Скачайте Power BI Desktop из [Центра загрузки](https://www.microsoft.com/download/details.aspx?id=58494) вместо магазина Microsoft Store.

* Если вы хотите использовать версию из Microsoft Store: на локальном компьютере скопируйте файл oraons.dll из папки _12.X.X\client_X_ в папку _12.X.X\client_X\bin_, где _X_ представляет номера версии и каталога.

Если при подключении к базе данных Oracle в Power BI Gateway отображается сообщение об ошибке *Ссылка на объект не задана*, выполните инструкции в разделе [Управление своим источником данных — Oracle](service-gateway-onprem-manage-oracle.md).

Если вы используете Сервер отчетов Power BI, см. сведения о [типе соединения Oracle](https://docs.microsoft.com/sql/reporting-services/report-data/oracle-connection-type-ssrs?view=sql-server-ver15).