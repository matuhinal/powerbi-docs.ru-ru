---
title: Подключение отчета к набору данных с помощью динамической привязки
description: Сведения о внедрении отчета с использованием динамической привязки.
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 11/07/2019
ms.openlocfilehash: f797dd55202ff4cba87cc3a15601d85091e94823
ms.sourcegitcommit: c839ef7437bc8fb8f7eeda23e59d05c7192a7fe8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2019
ms.locfileid: "74164060"
---
# <a name="connect-a-report-to-a-dataset-using-dynamic-binding"></a>Подключение отчета к набору данных с помощью динамической привязки 

Использование динамической привязки уместно, когда отчет подключен к набору данных. Соединение между отчетом и набором данных называется *привязкой*. Если привязка определяется не заранее, а в точке внедрения, то привязка называется [динамической](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FLate_binding&data=02%7C01%7CKesem.Sharabi%40microsoft.com%7C5d5b0d2d62cf4818f0c108d7635b151e%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637087115150775585&sdata=AbEtdJvgy4ivi4v4ziuui%2Bw2ibTQQXBQNYRKbXn5scA%3D&reserved=0).
 
При внедрении отчета Power BI с помощью *динамической привязки*можно подключить тот же отчет к разным наборам данных в зависимости от учетных данных пользователя.
 
Это означает, что в зависимости от набора данных, к которому подключен отчет, его можно использовать для вывода различных сведений. Например, отчет, показывающий значения розничной продажи, можно подключить к разным наборам данных розничной торговли и выдавать различные результаты, основываясь на наборе данных розничного продавца, к которому он подключен.
 
Отчет и набор данных не обязательно должны размещаться в одной рабочей области. При этом обе рабочие области, содержащие отчет и набор данных, должны быть назначены [емкости](azure-pbie-create-capacity.md).

В рамках процесса внедрения убедитесь, что вы *создали маркер с достаточными разрешениями*и *настроили объект конфигурации*.


## <a name="generating-a-token-with-sufficient-permissions"></a>Создание маркера с достаточными разрешениями

Динамическая привязка поддерживается для двух сценариев: *внедрения в организацию* и *внедрения для клиентов*. В следующей таблице приводятся рекомендации для каждого сценария.


|Сценарий  |Владение данными  |Маркер  |Требования  |
|---------|---------|---------|---------|
|*Внедрение для организации*    |Пользовательские данные         |Маркер доступа для пользователей Power BI         |Пользователь, маркер Azure AD которого используется, должен иметь необходимые разрешения для всех артефактов.         |
|*Внедрение для клиентов*     |Данные приложения         |Маркер доступа для пользователей, не работающих с Power BI         |Должен включать разрешения как для отчета, так и для динамически привязанного набора данных. Используйте [API для создания токена внедрения для нескольких элементов](embed-sample-for-customers.md#multiEmbedToken), чтобы создать токен внедрения, поддерживающий несколько артефактов.         |

## <a name="adjusting-the-config-object"></a>Настройка объекта конфигурации
Добавьте `datasetBinding` к объекту конфигурации. Используйте приведенный ниже пример в качестве справки.

```javascript
var config = {
    type: 'report',
    tokenType: models.TokenType.Embed,
    accessToken: accessToken,
    embedUrl: embedUrl,
    id: "reportId", // The wanted report id
    permissions: permissions,

    // -----  Adjustment required for dynamic binding ---- //
    datasetBinding: {
        datasetId: "notOriginalDatasetId",  // </The wanted dataset id
    }
    // ---- End of dynamic binding adjustment ---- //
};

// Get a reference to the embedded report HTML element
var embedContainer = $('#embedContainer')[0];

// Embed the report and display it within the div container
var report = powerbi.embed(embedContainer, config);
```

## <a name="next-steps"></a>Дальнейшие действия

Если вы еще не знакомы с принципами внедрения содержимого в Power BI, обратитесь к представленным ниже руководствам:
* [Руководство. Внедрение содержимого Power BI в приложение для клиентов](embed-sample-for-customers.md)
* [Руководство. Внедрение содержимого Power BI в приложение для организации](embed-sample-for-your-organization.md)