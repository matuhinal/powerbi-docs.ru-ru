---
title: Изменение строк подключения к источникам данных с помощью PowerShell
description: Изменение строк подключения к источникам данных с помощью API в PowerShell — сервер отчетов Microsoft Power BI
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 10/24/2019
ms.author: maggies
ms.openlocfilehash: 5cdf29c71ef3e5f8dc02799945cf76ccc518dabe
ms.sourcegitcommit: df8bcc65f0df69bf1fc1d47eb06575742eac1622
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75953753"
---
# <a name="change-data-source-connection-strings-in-power-bi-reports-with-powershell---power-bi-report-server"></a>Изменение строк подключения к источникам данных в отчетах Power BI с помощью PowerShell — сервер отчетов Microsoft Power BI


Строки подключения к источникам данных в отчетах Power BI на сервере отчетов Power BI можно изменять с помощью интерфейсов API в PowerShell. 

> [!NOTE]
> Сейчас эта функция работает только для DirectQuery. Поддержка импорта и обновления данных ожидается в ближайшее время.

1. Установите командлеты PowerShell для сервера отчетов Power BI. Командлеты и инструкции по установке см. на странице [https://github.com/Microsoft/ReportingServicesTools](https://github.com/Microsoft/ReportingServicesTools). 

2. Получите сведения о существующем источнике данных для файла Power BI с помощью командлетов PowerShell:

    ```powershell
    Get-RsRestItemDataSource -RsItem '/MyPbixReport'
    ```

    Чтобы просмотреть сведения о первом источнике данных, который содержится в отчете Power BI, используйте следующую строку: 

    ```powershell
    $dataSources[0]
    ```

3. Измените сведения о подключении и учетные данные требуемым образом. Если вы изменяете строку подключения и источник данных использует сохраненные учетные данные, необходимо указать пароль к учетной записи. 

    Чтобы изменить строку подключения к источнику данных, используйте следующую строку:

    ```powershell
    $dataSources[0].ConnectionString = 'data source=myCatalogServer;initial catalog=ReportServer;persist security info=False' 
    ```

    Чтобы изменить тип учетных данных для источника данных, используйте следующую строку:

    ```powershell
    $dataSources[0].DataModelDataSource.AuthType = 'Integrated'
    ```

    Чтобы изменить имя пользователя и пароль для источника данных, используйте следующую строку:

    ```powershell
    $dataSources[0].DataModelDataSource.Username = 'domain\user
    ```
    ```powershell
    $dataSources[0].DataModelDataSource.Secret = 'password'
    ```

4. Сохраните измененные учетные данные на сервере.

    ```powershell
    Set-RsRestItemDataSource -RsItem '/MyPbixReport' -RsItemType 'PowerBIReport' -DataSources $dataSources
    ```

## <a name="next-steps"></a>Дальнейшие действия

[Источники данных для отчетов с разбивкой на страницы в решении "Сервер отчетов Power BI"](connect-data-sources.md) 

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)
