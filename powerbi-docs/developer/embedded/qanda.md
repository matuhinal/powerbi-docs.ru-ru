---
title: Вопросы и ответы в Power BI Embedded
description: Power BI Embedded позволяет интегрировать функцию "Вопросы и ответы" в приложение, с помощью которого пользователи могут задавать вопросы на естественном языке.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: how-to
ms.date: 11/20/2017
ms.openlocfilehash: 0106cc9ddb0e82a7b40e362342fce5196ef655c5
ms.sourcegitcommit: 6bc66f9c0fac132e004d096cfdcc191a04549683
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91749283"
---
# <a name="qa-in-power-bi-embedded"></a>Вопросы и ответы в Power BI Embedded

Power BI Embedded позволяет встроить функцию "Вопросы и ответы" в приложение, с помощью которого пользователи могут задавать вопросы на естественном языке и сразу же получать ответы в виде таких визуальных элементов, как диаграммы и графики.

![Вопросы и ответы: интерактивный вопрос во внедренном окне](media/qanda/embedded-qanda.gif)

Вы можете внедрить в приложение функцию "Вопросы и ответы" в **интерактивном** режиме и режиме **вывода результатов**. В **интерактивном** режиме вы вводите вопросы, и они отображаются в визуальном элементе. Если у вас есть сохраненный или заданный вопрос для отображения, используйте режим **вывода результатов**, введя вопрос во внедренную конфигурацию.

Код JavaScript будет выглядеть примерно так:

```javascript
// Embed configuration used to describe the what and how to embed.
// This object is used when calling powerbi.embed within the JavaScript API.
// You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
var config= {
    type: 'qna',
    tokenType:   models.TokenType.Embed | models.TokenType.Aad,
    accessToken: access token value,
    embedUrl:    https://app.powerbi.com/qnaEmbed (groupId to be appended as query parameter if required),
    datasetIds:  array of requested data set ids (at the moment we support only one dataset),
    viewMode:    models.QnaMode.Interactive | models.QnaMode.ResultOnly,
    question:    optional parameter for Explore mode (QnaMode.Interactive) and mandatory for Render Result mode (QnaMode.ResultOnly)
};

// Get a reference to the embedded QNA HTML element
var qnaContainer = $('#qnaContainer')[0];

// Embed the QNA and display it within the div container.
var qna = powerbi.embed(qnaContainer, config);
```

## <a name="set-question"></a>Заданный вопрос

При использовании с заданным вопросом режима **вывода результатов** вы можете вводить дополнительные вопросы в окно и сразу же получать ответы, которые замещают предыдущий результат. На экране появится новый визуальный элемент с ответом на вопрос.

Примером этого может быть список вопросов и ответов. Пользователь может переходить между вопросами и получать ответы в той же внедренной части.

**Фрагмент кода с примером использования пакета SDK для JS:**  

```javascript
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

qna.setQuestion("This year sales")
    .then(function (result) {
        …….
    })
    .catch(function (errors) {
        …….
    });
```

## <a name="visual-rendered-event"></a>Событие отображенного визуального элемента

В **интерактивном** режиме приложение может получать уведомления о событии изменения данных каждый раз, когда отображаемый визуальный элемент меняется в соответствии с вводимым обновленным входящим запросом.

Прослушивание события *visualRendered* позволяет сохранять вопросы для последующего использования. 

**Фрагмент кода с примером использования пакета SDK для JS:**  

```javascript
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

// qna.off removes a given event listener if it exists.
qna.off("visualRendered");

// qna.on will add an event listener.
qna.on("visualRendered", function(event) {
     …….
});
```

## <a name="embed-token"></a>Токен внедрения

Создайте токен внедрения набора данных для запуска функции "Вопросы и ответы". Дополнительные сведения см. в статье [Создание токена](/rest/api/power-bi/embedtoken).

## <a name="next-steps"></a>Дальнейшие действия

Чтобы попробовать внедрить компонент "Вопросы и ответы", воспользуйтесь [примером внедрения на JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/).

У вас имеются и другие вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)