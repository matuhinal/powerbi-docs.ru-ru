---
title: Динамическая привязка
description: Сведения о внедрении отчета с использованием динамической привязки.
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 09/25/2019
ms.openlocfilehash: 8110023de4df28f65129bd53203cec9752acc1af
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2019
ms.locfileid: "73864446"
---
# <a name="dynamic-binding"></a>Динамическая привязка

Применение динамической привязки позволяет осуществлять динамический выбор набора данных при внедрении отчета. Отчет и набор данных не обязательно должны размещаться в одной рабочей области. В зависимости от выбранного набора данных конечные пользователи будут видеть разные результаты.

При этом обе рабочие области, содержащие отчет и набор данных, должны быть назначены емкости.

Внедрение отчета с использованием динамической привязки осуществляется в два этапа:
1. Создание маркера
2. Настройка объекта конфигурации

## <a name="generating-a-token"></a>Создание маркера
Используйте [API для создания и внедрения маркера для нескольких элементов](embed-sample-for-customers.md#multiEmbedToken).

Динамическая привязка поддерживается в сценариях внедрения и для *организации*, и для *клиентов*.

| Решение                   | Маркер                               | Требования                                                                                                                                                  |
|---------------------------------|-------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *Внедрение для организации* | Маркер доступа для пользователей Power BI     | Пользователь, маркер Azure AD которого используется, должен иметь необходимые разрешения для всех артефактов.                                                                    |
| *Внедрение для клиентов*    | Маркер доступа для пользователей, не работающих с Power BI | Должен включать разрешения как для отчета, так и для динамически привязанного набора данных. Используйте новый API для создания маркера внедрения, поддерживающего несколько артефактов. |

## <a name="adjusting-the-config-object"></a>Настройка объекта конфигурации
Добавьте `datasetBinding` к объекту конфигурации. В качестве справки используйте представленный внизу страницы пример.

Если вы еще не знакомы с принципами внедрения содержимого в Power BI, обратитесь к представленным ниже руководствам:
* [Внедрение содержимого Power BI в приложение для клиентов](embed-sample-for-customers.md)
* [Руководство. Внедрение содержимого Power BI в приложение для организации](embed-sample-for-your-organization.md)

 ### <a name="example"></a>Пример
```javascript
var config = {
    type: 'report',
    tokenType: models.TokenType.Embed,
    accessToken: accessToken,
    embedUrl: embedUrl,
    id: "reportId", // The wanted report id
    permissions: permissions,

    /////////////////////////////////////////////
    // Adjustment required for dynamic binding //
    datasetBinding: {
        datasetId: "notOriginalDatasetId",  // </The wanted dataset id
    }
    // End of dynamic binding adjustment            //
    /////////////////////////////////////////////
};

// Get a reference to the embedded report HTML element
var embedContainer = $('#embedContainer')[0];

// Embed the report and display it within the div container
var report = powerbi.embed(embedContainer, config);
```