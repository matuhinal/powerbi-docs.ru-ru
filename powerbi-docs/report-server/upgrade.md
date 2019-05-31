---
title: Обновление сервера отчетов Power BI
description: Узнайте, как обновлять сервер отчетов Power BI.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.custom: ''
ms.date: 09/05/2017
ms.openlocfilehash: 8cee670028da828e052d8fe30c594882555c5d53
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770161"
---
# <a name="upgrade-power-bi-report-server"></a>Обновление сервера отчетов Power BI

Узнайте, как обновлять сервер отчетов Power BI.

 **Скачать** ![скачать](media/upgrade/download.png "скачать")

Чтобы скачать сервер отчетов Power BI и службу Power BI Desktop, оптимизированную для сервера отчетов Power BI, перейдите на страницу [Локальная работа с отчетами с использованием сервера Power BI Report Server](https://powerbi.microsoft.com/report-server/).

## <a name="before-you-begin"></a>Подготовка

Перед обновлением сервера отчетов советуем выполнить следующие шаги, чтобы создать его резервную копию.

### <a name="backing-up-the-encryption-keys"></a>Архивация ключей шифрования

При настройке установки сервера отчетов в первый раз, следует создать резервные копии ключей шифрования. Каждый раз, когда вы измените удостоверение учетных записей служб или переименуйте компьютер следует создавать резервную копию ключей. Дополнительные сведения см. в статье [Ключи шифрования служб SSRS — резервное копирование и восстановление ключей шифрования](https://docs.microsoft.com/sql/reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys).

### <a name="backing-up-the-report-server-databases"></a>Архивация баз данных сервера отчетов

Так как сервер отчетов является сервером без отслеживания состояния, все данные приложений хранятся в базах данных **reportserver** и **reportservertempdb**, выполняющихся на экземпляре ядра СУБД SQL Server. Для резервного копирования можно **reportserver** и **reportservertempdb** баз данных с помощью одного из поддерживаемых методов резервного копирования баз данных SQL Server. Ниже приведены рекомендации для баз данных сервера отчетов.

* Использовать модель полного восстановления для резервного копирования **reportserver** базы данных.
* Использовать простую модель восстановления для резервного копирования **reportservertempdb** базы данных.
* Вы можете использовать разные расписания архивации для каждой базы данных. Единственная причина для резервного копирования **reportservertempdb** нужно, чтобы избежать необходимости ее повторного создания в случае сбоя оборудования. В случае сбоя оборудования вам не нужно восстанавливать данные в **reportservertempdb**, однако вам необходима структура таблицы. Если вы потеряете базу данных **reportservertempdb**, единственный способ вернуть ее — повторно создать базу данных сервера отчетов. Повторно созданная база данных **reportservertempdb** должна иметь такое же имя, что и имя основной базы данных сервера.

Дополнительные сведения об архивации и восстановлении реляционных баз данных SQL Server см. в [этой статье](https://docs.microsoft.com/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases).

### <a name="backing-up-the-configuration-files"></a>Архивация файлов конфигурации

Сервер отчетов Power BI использует файлы конфигурации для хранения настроек приложений. При первой настройке сервера, а также после развертывания любые пользовательские расширения, следует создать резервные копии файлов. Требуется архивировать следующие файлы:

* config.json;
* RSHostingService.exe.config;
* Rsreportserver.config;
* Rssvrpolicy.config;
* Reportingservicesservice.exe.config;
* Web.config для приложений ASP.NET сервера отчетов;
* Machine.config для ASP.NET.

## <a name="upgrade-the-report-server"></a>Обновление сервера отчетов

Само по себе обновление сервера отчетов Power BI выполняется очень легко. Чтобы установить его, нужно выполнить совсем немного действий.

1. Найдите папку с файлом PowerBIReportServer.exe и запустите установщик.

2. Щелкните **Обновить сервер отчетов Power BI**.

    ![Обновление сервера отчетов Power BI](media/upgrade/reportserver-upgrade1.png "обновить сервер отчетов Power BI")

3. Прочтите и примите условия лицензионного соглашения, а затем щелкните **Обновить**.

    ![Лицензионное соглашение](media/upgrade/reportserver-upgrade-eula.png "лицензионное соглашение")

4. После успешного обновления щелкните **Настроить сервер отчетов**, чтобы запустить диспетчер конфигурации служб Reporting Services, или щелкните **Закрыть**, чтобы выйти из установщика.

    ![Обновление конфигурации](media/upgrade/reportserver-upgrade-configure.png)

## <a name="upgrade-power-bi-desktop"></a>Обновление Power BI Desktop

После обновления сервера отчетов необходимо, чтобы все авторы отчетов Power BI обновились до версии Power BI Desktop, оптимизированной для сервера отчетов Power BI и соответствующей ему.

## <a name="next-steps"></a>Дальнейшие действия

* [Обзор функций администратора](admin-handbook-overview.md)  
* [Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI](install-powerbi-desktop.md)  
* [Verify a Reporting Services Installation](https://docs.microsoft.com/sql/reporting-services/install-windows/verify-a-reporting-services-installation) (Проверка установки служб Reporting Services)  
* [Configure the Report Server Service Account (SSRS Configuration Manager)](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager) (Настройка учетной записи службы сервера отчетов (System Center Configuration Manager))  
* [Configure Report Server URLs (SSRS Configuration Manager)](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager) (Настройка URL-адресов сервера отчетов (System Center Configuration Manager))  
* [Configure a Report Server Database Connection (SSRS Configuration Manager)](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager) (Настройка подключения к базе данных сервера отчетов (System Center Configuration Manager))  
* [SSRS Encryption Keys — Initialize a Report Server](https://docs.microsoft.com/sql/reporting-services/install-windows/ssrs-encryption-keys-initialize-a-report-server) (Ключи шифрования SSRS — инициализация сервера отчетов)  
* [Configure SSL Connections on a Native Mode Report Server](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server) (Настройка подключений SSL на сервере отчетов в основном режиме)  
* [Configure Windows Service Accounts and Permissions](https://docs.microsoft.com/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions) (Настройка учетных записей и разрешений службы Windows)  
* [Поддержка браузера для сервера отчетов Power BI](browser-support.md)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)