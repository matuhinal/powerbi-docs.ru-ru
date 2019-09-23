---
title: Программная настройка учетных данных для Power BI
description: Порядок программной настройки учетных данных для Power BI в целях автоматизации
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/25/2019
ms.openlocfilehash: f93119a621330d673fd2cf6035e0416646bd5e6a
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "61380189"
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

3. Зашифруйте строку учетных данных с помощью открытого ключа шлюза, используя алгоритм шифрования RSA.

    Используйте для шифрования следующий вспомогательный класс:

    ```csharp
        public static class AsymmetricKeyEncryptionHelper
        {
            private const int SegmentLength = 85;
            private const int EncryptedLength = 128;

            /// <summary>

            /// Encrypts credentials using the RSA algorithm

            /// </summary>

            public static string EncodeCredentials(string credentialData, string publicKeyExponent, string publicKeyModulus)
            {
                using (RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(EncryptedLength * 8))
                {
                    var parameters = rsa.ExportParameters(false);

                    parameters.Exponent = Convert.FromBase64String(publicKeyExponent);

                    parameters.Modulus = Convert.FromBase64String(publicKeyModulus);

                    rsa.ImportParameters(parameters);

                    return Encrypt(credentialData, rsa);
                }
            }

             private static string Encrypt(string plainText, RSACryptoServiceProvider rsa)
            {

                byte[] plainTextArray = Encoding.UTF8.GetBytes(plainText);

                // Split the message into different segments, each segment's length is 85. So, the result may be 85,85,85,20. 

                bool hasIncompleteSegment = plainTextArray.Length % SegmentLength != 0; 

                int segmentNumber = (!hasIncompleteSegment) ? (plainTextArray.Length / SegmentLength) : ((plainTextArray.Length SegmentLength) + 1);

                byte[] encryptedData = new byte[segmentNumber * EncryptedLength];

                int encryptedDataPosition = 0;

                for (var i = 0; i < segmentNumber; i++)
                {
                    int lengthToCopy;

                    if (i == segmentNumber - 1 && hasIncompleteSegment)

                        lengthToCopy = plainTextArray.Length % SegmentLength;

                    else

                        lengthToCopy = SegmentLength;

                    var segment = new byte[lengthToCopy];

                    Array.Copy(plainTextArray, i * SegmentLength, segment, 0, lengthToCopy);

                    var segmentEncryptedResult = rsa.Encrypt(segment, true);

                    Array.Copy(segmentEncryptedResult, 0, encryptedData, encryptedDataPosition, segmentEncryptedResult.Length);

                    encryptedDataPosition += segmentEncryptedResult.Length;

                }

                return Convert.ToBase64String(encryptedData);

            }

        }

        var encryptedCredentials = AsymmetricKeyEncryptionHelper.EncodeCredentials(credentials);
    ```

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
