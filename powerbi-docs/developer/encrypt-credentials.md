---
title: Шифрование учетных данных
description: Пошаговое руководство. Шифрование учетных данных для источников данных локального шлюза
author: mahirdiab
ms.author: mahirdiab
manager: eligr
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/04/2019
ms.openlocfilehash: 6229d65e7ef28d0c9b6013166cb504cfb976f46d
ms.sourcegitcommit: 76772a361e6cd4dd88824b2e4b32af30656e69db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2019
ms.locfileid: "56892236"
---
# <a name="encrypt-credentials"></a>Шифрование учетных данных

При отправке запроса на [создание источника данных](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) или [обновление источника данных](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) для **корпоративного локального шлюза** с помощью [REST API Power BI](https://docs.microsoft.com/rest/api/power-bi/) учетные данные должны шифроваться с использованием открытого ключа шлюза.

Ниже приведен пример кода, демонстрирующий шифрование учетных данных в .NET.

Учетные данные, передаваемые в метод EncodeCredentials ниже, должны иметь один из следующих форматов в зависимости от их типа:

**Базовые учетные данные или учетные данные Windows**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
```

**Учетные данные в виде ключей**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"key\", \"value\":\"ec....LA=\"}]}";
```

**Учетные данные OAuth2**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"accessToken\", \"value\":\"eyJ0....fwtQ\"}]}";
```

**Анонимные учетные данные**

```csharp
var credentials = "{\"credentialData\":\"\"}";
```

**Шифрование учетных данных**

```csharp
public static class AsymmetricKeyEncryptionHelper
{

    private const int SegmentLength = 85;
    private const int EncryptedLength = 128;

    public static string EncodeCredentials(string credentials, string publicKeyExponent, string publicKeyModulus)
    {
        using (RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(EncryptedLength * 8))
        {
            var parameters = rsa.ExportParameters(false);
            parameters.Exponent = Convert.FromBase64String(publicKeyExponent);
            parameters.Modulus = Convert.FromBase64String(publicKeyModulus);
            rsa.ImportParameters(parameters);
            return Encrypt(credentials, rsa);
        }
    }

    private static string Encrypt(string plainText, RSACryptoServiceProvider rsa)
    {
        byte[] plainTextArray = Encoding.UTF8.GetBytes(plainText);

        // Split the message into different segments, each segment's length is 85. So the result may be 85,85,85,20.
        bool hasIncompleteSegment = plainTextArray.Length % SegmentLength != 0;

        int segmentNumber = (!hasIncompleteSegment) ? (plainTextArray.Length / SegmentLength) : ((plainTextArray.Length / SegmentLength) + 1);

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
```