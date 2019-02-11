---
title: Общие сведения о руководстве для разработчика сервера отчетов Power BI
description: Это — руководство для разработчика сервера отчетов Power BI, локального расположения для хранения и администрирования ваших отчетов Power BI, мобильных отчетов и отчетов с разбивкой на страницы.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 9b1357d2e10214cdf578bff4d2aa7fca8fc19033
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794703"
---
# <a name="developer-handbook-overview-power-bi-report-server"></a>Общие сведения о руководстве для разработчика сервера отчетов Power BI
Это — руководство для разработчика сервера отчетов Power BI, локального расположения для хранения и администрирования ваших отчетов Power BI, мобильных отчетов и отчетов с разбивкой на страницы.

![](media/developer-handbook-overview/admin-handbook.png)

В этом руководстве описаны возможности работы с сервером отчетов Power BI, доступные разработчику.

## <a name="embedding"></a>Внедрение
Любой отчет на сервере Power BI можно внедрить в iFrame, добавив параметр строки запроса `?rs:Embed=true` в URL-адрес. Эта возможность доступна для отчетов Power BI и отчетов других типов.

### <a name="report-viewer-control"></a>Управление средством просмотра отчетов
Работая с отчетами с разбивкой на страницы, можно использовать элемент управления средства просмотра отчетов. Этот элемент управления можно поместить в приложение .NET для Windows или веб-приложение. См. дополнительные сведения об [элементе управления средства просмотра](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started).

## <a name="apis"></a>API-интерфейсы
Существует несколько вариантов взаимодействия API с сервером отчетов Power BI, а именно:

* [REST API](rest-api.md);
* [Доступ к URL-адресу](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)
* [Поставщик WMI](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

Для управления сервером отчетов можно также использовать [служебные программы PowerShell](https://github.com/Microsoft/ReportingServicesTools) с открытым исходным кодом.

> [!NOTE]
> Служебные программы PowerShell в настоящее время не поддерживают файлы Power BI Desktop (PBIX).
> 
> 

## <a name="custom-extensions"></a>Пользовательские расширения
Библиотека расширений — это набор классов, интерфейсов и типов значений, доступных на сервере отчетов Power BI. Эта библиотека обеспечивает доступ к функциональным возможностям системы. Она предназначена для использования приложений Microsoft .NET Framework для расширения компонентов сервера отчетов Power BI.

Вы можете создавать расширения нескольких типов.

* Расширения обработки данных
* Расширения доставки
* Расширения подготовки отчетов для отчетов с разбивкой на страницы
* Расширения безопасности

См. дополнительные сведения о [библиотеке расширений](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library).

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с элементом управления средства просмотра отчетов](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started)  
[Создание приложений с помощью веб-службы и платформы .NET Framework](https://docs.microsoft.com/sql/reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework)  
[Доступ к URL-адресу](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)  
[Библиотека расширений](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library)  
[Поставщик WMI](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

