---
title: Программная настройка учетных данных для Power BI
description: Порядок программной настройки учетных данных для Power BI в целях автоматизации
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/08/2020
ms.openlocfilehash: 222edd901409fa71d98308f27407838d54564834
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75836591"
---
# <a name="configure-credentials-programmatically-for-power-bi"></a>Программная настройка учетных данных для Power BI

Выполните указанные ниже действия, чтобы программно настроить учетные данные для Power BI.

## <a name="configure-a-credential-flow-for-data-sources"></a>Настройка потока учетных данных для источников данных

1. Вызовите интерфейс [получения источников данных](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasourcesingroup), чтобы обнаружить источники данных для набора данных. Текст ответа для каждого источника данных содержит тип, сведения о подключении, шлюз и идентификатор источника данных.

    ```csharp
    var datasources = pbiClient.Datasets.GetDatasources(datasetId).Value;
    var datasource = datasources.First(); // select a datasource
    ```

2. Создайте строку учетных данных в соответствии с [примерами обновления источника данных](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) в зависимости от типа учетных данных.

    ```csharp
    var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
    ```

3. Создайте сведения об учетных данных.

    ```csharp
    var credentialDetails = new CredentialDetails(
                    credentials,
                    CredentialTypeEnum.Basic,
                    EncryptedConnectionEnum.Encrypted,
                    EncryptionAlgorithmEnum.None,
                    PrivacyLevelEnum.Private);
    ```

4. Вызовите интерфейс [обновления источника данных](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource), чтобы задать учетные данные, используя идентификатор шлюза и источника данных из шага 1 и сведения об учетных данных из шага 4.

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

### <a name="expired-on-premises-data-source-credentials-flow"></a>Поток учетных данных для локального источника данных с истекшим сроком действия

1. [Выполните шаги 1 и 2 из предыдущего сценария](#configure-a-credential-flow-for-data-sources).

2. Вызовите интерфейс [получения шлюза](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways) для извлечения открытого ключа шлюза.

    ```csharp
    var gateway = pbiClient.Gateways.GetGatewayById(datasource.GatewayId);
    ```

3. Зашифруйте строку учетных данных с помощью открытого ключа шлюза. У разных версий шлюза могут иметься разные размеры открытого ключа.
    
    См. пример в коде пакета SDK, доступном в репозитории PowerBI-CSharp GitHub, [PowerBI-CSharp/SDK/PowerBI.API/Extensions/v2/](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions/V2).
    * [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricKeyEncryptor.cs)
    * [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/Asymmetric1024KeyEncryptionHelper.cs)
    * [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricHigherKeyEncryptionHelper.cs)
    * [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AuthenticatedEncryption.cs)

4. Создавайте сведения об учетных данных с зашифрованными учетными данными.

    ```csharp
    var credentialDetails = new CredentialDetails(
                    encryptedCredentials,
                    CredentialTypeEnum.Basic,
                    EncryptedConnectionEnum.Encrypted,
                    EncryptionAlgorithmEnum.RSA-OAEP,
                    PrivacyLevelEnum.Private);
    ```

5. Вызовите интерфейс [обновления источника данных](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) для задания учетных данных.

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

## <a name="configure-a-new-data-source-for-a-data-gateway"></a>Настройка нового источника данных для шлюза данных

1. Установите [локальный шлюз данных](https://powerbi.microsoft.com/gateway/) на своем компьютере.

2. Вызовите интерфейс [получения шлюза](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways) для извлечения открытого ключа и идентификатора шлюза.

    ```csharp
    var gateways = pbiClient.Gateways.GetGateways().Value;
    var gateway = gateways.First(); // select a gateway
    ```

3. Создайте сведения об учетных данных, как в предыдущем сценарии, с помощью открытого ключа шлюза, полученного на шаге [Поток учетных данных для локального источника данных с истекшим сроком действия](#expired-on-premises-data source-credentials-flow-on-premises-data-gateway).

4. Создайте текст запроса.

    ```csharp
    var request = new PublishDatasourceToGatewayRequest(
    dataSourceType: "SQL",
    connectionDetails: "{\"server\":\"myServer\",\"database\":\"myDatabase\"}",
    credentialDetails: credentialDetails,
    dataSourceName: "my sql datasource");
    ```

5. Вызовите API [создания источника данных](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource).

    ```csharp
    pbiClient.Gateways.CreateDatasource(gateway.Id, request);
    ```

## <a name="troubleshooting"></a>Устранение неполадок

### <a name="no-gateway-and-data-source-id-found-when-calling-get-data-sources"></a>Отсутствие идентификатора источника данных и шлюза при вызове интерфейса для получения источников данных

Эта проблема означает, что набор данных не привязан к шлюзу. При создании набора данных для каждого облачного подключения в облачном шлюзе пользователя автоматически создается источник данных без учетных данных. Этот шлюз используется для хранения учетных данных для облачных подключений.

После создания набора данных выполняется автоматическая привязка между ним и подходящим шлюзом, содержащим соответствующие источники данных для всех подключений. Если подходящие шлюзы отсутствуют или их несколько, автоматическая привязка завершается сбоем.

Создайте отсутствующие локальные источники данных и привяжите набор данных к шлюзу вручную с помощью интерфейса [привязки к шлюзу](https://docs.microsoft.com/rest/api/power-bi/datasets/bindtogateway).

Чтобы обнаружить доступные для привязки шлюзы, используйте интерфейс [обнаружения шлюзов](https://docs.microsoft.com/rest/api/power-bi/datasets/discovergateways).