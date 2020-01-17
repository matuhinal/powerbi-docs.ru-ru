---
title: Шифрование учетных данных
description: Пошаговое руководство. Шифрование учетных данных для источников данных локального шлюза
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/08/2020
ms.openlocfilehash: b1fc4a505aa993c606743eefb6e8fb8c0379317d
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2020
ms.locfileid: "75836605"
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

Зашифруйте значение учетных данных с помощью открытого ключа шлюза. У разных версий шлюза могут иметься разные размеры открытого ключа.

См. пример в коде пакета SDK, доступном в репозитории PowerBI-CSharp GitHub, [PowerBI-CSharp/SDK/PowerBI.API/Extensions/v2/](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions/V2).

- [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricKeyEncryptor.cs)
- [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/Asymmetric1024KeyEncryptionHelper.cs)
- [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricHigherKeyEncryptionHelper.cs)
- [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AuthenticatedEncryption.cs)