---
title: Источники данных для отчетов с разбивкой на страницы в решении "Сервер отчетов Power BI"
description: Сведения о том, к каким источникам данных могут подключаться отчеты с разбивкой на страницы (RDL) в решении "Сервер отчетов Power BI".
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: maggies
ms.openlocfilehash: 7cb5772e6ccdc1e4036d70f65a3a28210a4f6df1
ms.sourcegitcommit: d55d3089fcb3e78930326975957c9940becf2e76
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260722"
---
# <a name="paginated-report-data-sources--in-power-bi-report-server"></a>Источники данных для отчетов с разбивкой на страницы в решении "Сервер отчетов Power BI"
Отчеты Reporting Services с разбивкой на страницы в решении "Сервер отчетов Power BI" поддерживают те же источники данных, которые используются в SQL Server Reporting Services. См. дополнительные сведения об [источниках данных, поддерживаемых службами Reporting Services](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

## <a name="connect-to-oracle-data-sources-with-useinstalleduiculture"></a>Подключение к источникам данных Oracle с помощью UseInstalledUICulture

Для подключения к источникам данных Oracle Сервер отчетов Power BI использует поставщик данных Oracle для .NET (ODP.NET), который не зависит от NLS.

По умолчанию для загрузки ODP.NET сервер отчетов использует язык и региональные параметры пользовательского интерфейса первого клиента.  В результате до перезапуска службы все последующие подключения с сервера отчетов к Oracle будут использовать первоначальные язык и региональные параметры пользовательского интерфейса.  Такой подход может вызвать проблемы при преобразовании отчета для просмотра из-за несовпадений в форматировании языка и региональных параметров пользовательского интерфейса.

Чтобы обеспечить лучшую работу в Сервере отчетов Power BI, мы предоставили параметр конфигурации с именем UseInstalledUICulture. Если для UseInstalledUICulture задано значение true, сервер отчетов всегда будет загружать ODP.NET, используя язык и региональные параметры пользовательского интерфейса сервера, а не первого клиента.
Этот параметр доступен в Сервере отчетов Power BI, начиная с февральского выпуска службы

Чтобы включить эту функцию, измените запись расширения ORACLE в файле rsreportserver.config, как показано ниже.
```xml
<Extension Name="ORACLE" Type="Microsoft.ReportingServices.DataExtensions.OracleClientConnectionWrapper,Microsoft.ReportingServices.DataExtensions">
    <Configuration>
        <UseInstalledUICulture>true</UseInstalledUICulture>
    </Configuration>
</Extension>
```

## <a name="next-steps"></a>Дальнейшие действия
Подключившись к источнику данных, [создайте отчет с разбивкой на страницы](quickstart-create-paginated-report.md).  


Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
