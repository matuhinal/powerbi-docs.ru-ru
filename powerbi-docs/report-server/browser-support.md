---
title: "Поддержка браузера для сервера отчетов Power BI"
description: "Узнайте о том, какие версии браузера поддерживаются для просмотра и администрирования сервера отчетов Power BI и элементов управления средства просмотра отчетов."
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
ms.author: asaxton
ms.openlocfilehash: 3e146417c78c7c95221c37051eda08a7b8497012
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="browser-support-for-power-bi-report-server"></a>Поддержка браузера для сервера отчетов Power BI
Узнайте о том, какие версии браузера поддерживаются для просмотра и администрирования сервера отчетов Power BI и элементов управления средства просмотра отчетов.

## <a name="browser-requirements-for-the-web-portal"></a>Требования к браузеру для веб-портала
Ниже приведен актуальный список браузеров, поддерживаемых для веб-портала.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple OS X**  
*OS X 10.9–10.11*

* Apple Safari (+)
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple iOS**  
*iPhone и iPad с iOS 9*

* Apple Safari (+)

**Google Android**  
*Смартфоны и планшеты с Android 4.4 (KitKat) или более поздней версии*

* Google Chrome (+)
  
  **(+)** — последняя общедоступная версия

## <a name="browser-requirements-for-the-report-viewer-web-control-2015"></a>Требования к браузеру для веб-элемента управления средством просмотра отчетов (2015 г.)
Ниже приведен актуальный список браузеров, поддерживаемых для веб-элемента управления средством просмотра отчетов. Средство просмотра отчетов поддерживает просмотр отчетов на веб-портале.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)

**Apple OS X**  
*OS X 10.9–10.11*

* Apple Safari (+)
  
  **(+)** — последняя общедоступная версия

### <a name="authentication-requirements"></a>Требования к аутентификации
Браузеры поддерживают определенные схемы аутентификации, которые должны обрабатываться сервером отчетов для успешного выполнения запросов клиента. В таблице ниже приведены стандартные типы аутентификации, поддерживаемые каждым браузером в операционной системе Windows.

| **Тип браузера** | **Поддержка** | **Браузер по умолчанию** | **Сервер по умолчанию** |
| --- | --- | --- | --- |
| **Microsoft Edge** (+) |Negotiate, Kerberos, NTLM, Basic |Согласование |Да. Стандартные параметры аутентификации поддерживают Edge. |
| **Microsoft Internet Explorer** |Negotiate, Kerberos, NTLM, Basic |Согласование |Да. Стандартные параметры аутентификации поддерживают Internet Explorer. |
| **Google Chrome**(+) |Negotiate, NTLM, Basic |Согласование |Да. Стандартные параметры аутентификации поддерживают Chrome. |
| **Mozilla Firefox**(+) |NTLM, Basic |NTLM |Да. Стандартные параметры аутентификации поддерживают Firefox. |
| **Apple Safari**(+) |NTLM, Basic |Обычная |Да. Стандартные параметры аутентификации поддерживают Safari. |

 **(+)** — последняя общедоступная версия

### <a name="script-requirements-for-viewing-reports"></a>Требования к скриптам для просмотра отчетов
Чтобы использовать средство просмотра отчетов, настройте браузер для выполнения скриптов.

Если поддержка скриптов отключена, появится такое же сообщение об ошибке, как и при открытии отчета:

```
Your browser does not support scripts or has been configured to not allow scripts to run. Click here to view this report without scripts
```

 Если выбрать просмотр отчета без поддержки скриптов, отчет преображается в формат HTML. В этом случае некоторые возможности средства просмотра отчетов (например, панель инструментов отчетов и схема документа) будут недоступны.

> [!NOTE]
> Панель инструментов отчета включена в средство просмотра HTML. По умолчанию панель инструментов отображается в верхней части каждого отчета, отображаемого в окне браузера. Средство просмотра отчетов позволяет искать данные в отчете, прокручивать страницы и настраивать размер страниц для просмотра. См. дополнительные сведения о [панели инструментов отчетов и средстве просмотра HTML](https://docs.microsoft.com/sql/reporting-services/html-viewer-and-the-report-toolbar).
> 
> 

## <a name="browser-support-for-report-viewer-web-server-controls-in-visual-studio"></a>Поддержка браузеров для элементов управления веб-сервера средства просмотра отчетов в Visual Studio
Элементы управления веб-сервера средства просмотра отчетов используются для внедрения функций отчета в веб-приложение ASP.NET. См. дополнительные сведения о том, как получить элемент управления средства просмотра отчетов в ходе [интеграции служб Reporting Services с помощью элементов управления средства просмотра отчетов](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started).

Используйте браузер, в котором включена поддержка скриптов. Если браузер не может выполнять скрипты, просмотр отчета невозможен.

**Microsoft Windows**  
*Windows 7, 8.1, 10; Windows Server 2008 R2, 2012, 2012 R2*

* Microsoft Edge (+)
* Microsoft Internet Explorer 11
* Google Chrome (+)
* Mozilla Firefox (+)
  
  **(+)** — последняя общедоступная версия

## <a name="next-steps"></a>Дальнейшие действия
[Руководство администратора](admin-handbook-overview.md)  
[Краткое руководство по установке сервера отчетов Power BI](quickstart-install-report-server.md)  
[Install Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder) (Установка построителя отчетов)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714) (Скачивание SQL Server Data Tools (SSDT))

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

