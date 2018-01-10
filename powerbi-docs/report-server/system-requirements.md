---
title: "Требования к оборудованию и программному обеспечению для установки сервера отчетов Power BI"
description: "В этой статье изложены минимальные требования к оборудованию и программному обеспечению для установки и запуска сервера отчетов Power BI."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: d6daa5625037729df6aa7908a43c0e068efbfb8b
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2018
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>Требования к оборудованию и программному обеспечению для установки сервера отчетов Power BI
В этой статье изложены минимальные требования к оборудованию и программному обеспечению для установки и запуска сервера отчетов Power BI.

## <a name="processor-memory-and-operating-system-requirements"></a>Требования к процессору, памяти и операционной системе
| Компонент | Требование |
| --- | --- |
| .NET Framework |4.6<br><br>Можно вручную установить платформу .NET Framework со страницы [Платформа .NET Framework Microsoft 4.6 (веб-установщик) для Windows](http://support.microsoft.com/kb/3045560).<br/><br/> Дополнительные сведения, рекомендации и инструкции по .NET Framework 4.6 см. в [руководстве по развертыванию .NET Framework для разработчиков](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx).<br/><br/>Перед установкой .NET Framework 4.6 для Windows 8.1 и Windows Server 2012 R2 требуется установить обновление [KB2919355](http://support.microsoft.com/kb/2919355). |
| Жесткий диск |Для сервера отчетов Power BI требуется не менее 1 ГБ свободного места на жестком диске.<br><br>Дополнительное место потребуется на сервере базы данных, на котором размещена база данных сервера отчетов. |
| Память |**Минимум:** 1 ГБ<br/><br/> **Рекомендуется:** не менее 4 ГБ |
| Скорость процессора |**Минимум:** процессор x64 с тактовой частотой 1,4 ГГц<br/><br/> **Рекомендуется:** 2,0 ГГц или выше |
| Тип процессора |Процессор x64: AMD Opteron, AMD Athlon 64, Intel Xeon с поддержкой технологии Intel EM64T, Intel Pentium IV с поддержкой технологии EM64T |
| Операционная система |Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows Server 2012 R2 Datacenter<br><br>Windows Server 2012 R2 Standard<br><br>Windows Server 2012 R2 Essentials<br><br>Windows Server 2012 R2 Foundation<br><br>Windows Server 2012 Datacenter<br><br>Windows Server 2012 Standard<br><br>Windows Server 2012 Essentials<br><br>Windows Server 2012 Foundation<br><br>Windows 10 Домашняя<br><br>Windows 10 Профессиональная<br><br>Windows 10 Корпоративная<br><br>Windows 8.1<br><br>Windows 8.1 Профессиональная<br><br>Windows 8.1 Корпоративная<br><br>Windows 8<br><br>Windows 8 Профессиональная<br><br>Windows 8 Корпоративная |

> [!NOTE]
> Установка сервера отчетов Power BI поддерживается только на процессорах x64.
> 
> 

## <a name="database-server-version-requirements"></a>Требования к версии сервера базы данных
Для размещения базы данных сервера отчетов используется SQL Server. Экземпляр ядра СУБД SQL Server может быть локальным или удаленным. Вот поддерживаемые версии ядра СУБД SQL Server, которые могут использоваться для размещения баз данных сервера отчетов:

* SQL Server 2017;
* SQL Server 2016;
* SQL Server 2014;
* SQL Server 2012;
* SQL Server 2008 R2;
* SQL Server 2008.

Для создания базы данных сервера отчетов на удаленном компьютере необходимо настроить подключение для использования учетной записи пользователя домена или учетную запись службы с сетевым доступом. Если вы решите использовать удаленный экземпляр SQL Server, хорошо подумайте, какие учетные данные сервера отчетов следует использовать для подключения к экземпляру SQL Server. Дополнительные сведения см. в статье [Настройка соединения с базой данных сервера отчетов (собственный режим)](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager).

## <a name="considerations"></a>Примечания
При настройке основных параметров, необходимых для приведения сервера отчетов в рабочее состояние, сервер отчетов Power BI установит значения по умолчанию. Должны выполняться следующие требования.

* Ядро СУБД SQL Server должно быть доступным после установки и до настройки базы данных сервера отчетов. На экземпляре ядра СУБД должна размещаться база данных сервера отчетов, которую создаст диспетчер конфигурации Services. Для самой установки ядро СУБД не требуется.
* Учетная запись пользователя для запуска программы установки должна входить в локальную группу администраторов.
* Учетная запись пользователя, используемая для диспетчера конфигурации Reporting Services, должна иметь разрешение на доступ к базам данных (и их создание) на экземпляре ядра СУБД, на котором размещены базы данных сервера отчетов.
* В процессе установки должны использоваться значения по умолчанию для резервирования URL-адресов, которые обеспечивают доступ к серверу отчетов и веб-порталу. К этим значениям относятся порт 80, строгий подстановочный знак и имена виртуальных каталогов в формате **ReportServer** и **Reports**.

## <a name="read-only-domain-controller-rodc"></a>Контроллер домена только для чтения (RODC)
 Несмотря на то что сервер отчетов можно установить в среде, имеющей контроллер домена только для чтения (RODC), для правильной работы служб Reporting Services необходим доступ к контроллеру домена для чтения и записи. Если службы Reporting Services имеют доступ только к контроллеру домена только для чтения, при попытке администрирования службы могут возникнуть ошибки.

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>Отчеты Power BI и динамические подключения к службам Analysis Services
С помощью динамического подключения можно работать с табличными и с многомерными экземплярами. Для правильной работы сервера служб Analysis Services должны быть соблюдены требования в отношении его версии и выпуска.

| **Версия сервера** | **Требуемый номер SKU** |
| --- | --- |
| 2012 SP1 CU4 или более поздняя версия |Бизнес-аналитика и SKU категории "корпоративный" |
| 2014 |Бизнес-аналитика и SKU категории "корпоративный" |
| 2016 и более поздние версии |SKU категории "стандартный" или старшая версия |

## <a name="next-steps"></a>Дальнейшие действия
[Руководство пользователя](user-handbook-overview.md)  
[Руководство администратора](admin-handbook-overview.md)  
[Краткое руководство по установке сервера отчетов Power BI](quickstart-install-report-server.md)  
[Install Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder) (Установка построителя отчетов)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714) (Скачивание SQL Server Data Tools (SSDT))

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

