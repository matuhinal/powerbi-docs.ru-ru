---
title: Требования к оборудованию и программному обеспечению для установки сервера отчетов Power BI
description: В этой статье изложены минимальные требования к оборудованию и программному обеспечению для установки и запуска Сервера отчетов Power BI.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 07/23/2019
ms.openlocfilehash: fea28cd1c6541ae9255acd4be14cc85c2c2c5bed
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68415370"
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>Требования к оборудованию и программному обеспечению для установки сервера отчетов Power BI

В этой статье изложены минимальные требования к оборудованию и программному обеспечению для установки и запуска Сервера отчетов Power BI.

## <a name="processor-memory-and-operating-system-requirements"></a>Требования к процессору, памяти и операционной системе

| Компонент | Требование |
| --- | --- |
| .NET Framework |4.6<br><br>Можно вручную установить платформу .NET Framework со страницы [Платформа .NET Framework Microsoft 4.6 (веб-установщик) для Windows](http://support.microsoft.com/kb/3045560).<br/><br/> Дополнительные сведения, рекомендации и инструкции по .NET Framework 4.6 см. в [руководстве по развертыванию .NET Framework для разработчиков](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx).<br/><br/>Перед установкой .NET Framework 4.6 для Windows 8.1 и Windows Server 2012 R2 требуется установить обновление [KB2919355](http://support.microsoft.com/kb/2919355). |
| Жесткий диск |Для сервера отчетов Power BI требуется не менее 1 ГБ свободного места на жестком диске.<br><br>Дополнительное место потребуется на сервере базы данных, на котором размещена база данных сервера отчетов. |
| Память |**Минимальные требования** 1 ГБ<br/><br/> **Рекомендуемые требования** Не менее 4 ГБ |
| Скорость процессора |**Минимум:** 64-битный процессор с тактовой частотой 1,4 ГГц<br/><br/> **Рекомендуемые требования** 2,0 ГГц или выше |
| Тип процессора |64-битный процессор: AMD Opteron, AMD Athlon 64, Intel Xeon с поддержкой технологии Intel EM64T, Intel Pentium IV с поддержкой технологии EM64T |
| Операционная система |Windows Server 2019 Datacenter<br><br>Windows Server 2019 Standard<br><br>Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows Server 2012 R2 Datacenter<br><br>Windows Server 2012 R2 Standard<br><br>Windows Server 2012 R2 Essentials<br><br>Windows Server 2012 R2 Foundation<br><br>Windows Server 2012 Datacenter<br><br>Windows Server 2012 Standard<br><br>Windows Server 2012 Essentials<br><br>Windows Server 2012 Foundation<br><br>Windows 10 Домашняя<br><br>Windows 10 Профессиональная<br><br>Windows 10 Корпоративная<br><br>Windows 8.1<br><br>Windows 8.1 Профессиональная<br><br>Windows 8.1 Корпоративная<br><br>Windows 8<br><br>Windows 8 Профессиональная<br><br>Windows 8 Корпоративная |

> [!NOTE]
> Установка сервера отчетов Power BI поддерживается только на процессорах x64.


## <a name="database-server-version-requirements"></a>Требования к версии сервера базы данных

Для размещения базы данных сервера отчетов используется SQL Server. Экземпляр ядра СУБД SQL Server может быть локальным или удаленным. Вот поддерживаемые версии ядра СУБД SQL Server, которые могут использоваться для размещения баз данных сервера отчетов:

* SQL Server 2017;
* SQL Server 2016;
* SQL Server 2014;
* SQL Server 2012;

Когда вы создаете базу данных сервера отчетов на удаленном компьютере, следует настроить для подключения учетную запись пользователя домена или учетную запись службы с сетевым доступом. Если вы решите использовать удаленный экземпляр SQL Server, хорошо подумайте, какие учетные данные сервера отчетов следует использовать для подключения к экземпляру SQL Server. Дополнительные сведения см. в статье [Настройка соединения с базой данных сервера отчетов (собственный режим)](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager).

## <a name="considerations"></a>Примечания

При настройке основных параметров, необходимых для приведения сервера отчетов в рабочее состояние, сервер отчетов Power BI установит значения по умолчанию. Должны выполняться следующие требования.

* Поддерживаемые языки для сервера отчетов Power BI: английский, немецкий, испанский, японский, итальянский, французский, русский, китайский (упрощенное письмо), китайский (традиционное письмо), португальский (Бразилия), корейский
* Ядро СУБД SQL Server должно быть доступным после установки и до настройки базы данных сервера отчетов. На экземпляре ядра СУБД должна размещаться база данных сервера отчетов, которую создаст диспетчер конфигурации Services. Для самой установки ядро СУБД не требуется.
* В статье [Возможности служб Reporting Services, поддерживаемые различными выпусками SQL Server 2016](https://docs.microsoft.com/sql/reporting-services/reporting-services-features-supported-by-the-editions-of-sql-server-2016) описаны различия между выпусками SQL Server.
* Учетная запись пользователя, от имени которой выполняется программа установки, должна входить в локальную группу администраторов.
* Учетная запись пользователя, от имени которой выполняется диспетчер конфигурации служб Reporting Services, должна иметь разрешение на доступ к базам данных (и их создание) на экземпляре ядра СУБД, на котором размещены базы данных сервера отчетов.
* В процессе установки должны использоваться значения по умолчанию для резервирования URL-адресов, которые обеспечивают доступ к серверу отчетов и веб-порталу. К этим значениям относятся порт 80, строгий подстановочный знак и имена виртуальных каталогов в формате **ReportServer** и **Reports**.

## <a name="read-only-domain-controller-rodc"></a>Контроллер домена только для чтения (RODC)

 Сервер отчетов можно установить в среде с контроллером домена только для чтения (RODC). Но для правильной работы службам Reporting Services нужен доступ к контроллеру домена чтения и записи. Если службы Reporting Services имеют доступ только к контроллеру домена только для чтения, при попытке администрирования службы могут возникнуть ошибки.

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>Отчеты Power BI и динамические подключения к службам Analysis Services

С помощью динамического подключения можно работать с табличными и с многомерными экземплярами. Для правильной работы сервера служб Analysis Services должны быть соблюдены требования в отношении его версии и выпуска.

| **Версия сервера** | **Требуемый номер SKU** |
| --- | --- |
| 2012 SP1 CU4 или более поздняя версия |Бизнес-аналитика и SKU категории "корпоративный" |
| 2014 |Бизнес-аналитика и SKU категории "корпоративный" |
| 2016 и более поздние версии |SKU категории "стандартный" или старшая версия |

## <a name="next-steps"></a>Дальнейшие действия

[Что такое Сервер отчетов Power BI?](get-started.md)  
[Обзор функций администратора](admin-handbook-overview.md)  
[Установка сервера отчетов Power BI](install-report-server.md)  
[Загрузка построителя отчетов](https://www.microsoft.com/download/details.aspx?id=53613)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714) (Скачивание SQL Server Data Tools (SSDT))

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
