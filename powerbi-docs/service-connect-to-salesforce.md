---
title: Подключение к Salesforce с помощью Power BI
description: SalesForce для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/30/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: b351ba2151937b62002dc0cfca849cff58985581
ms.sourcegitcommit: d441d350504f8c6d9e100d229757add6237f0bef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73060813"
---
# <a name="connect-to-salesforce-with-power-bi"></a>Подключение к Salesforce с помощью Power BI
С помощью Power BI вы легко можете подключаться к учетной записи Salesforce.com. Это подключение позволяет извлечь данные Salesforce и обеспечить автоматическое предоставление панели мониторинга и отчетов.

См. дополнительные сведения об [интеграции Salesforce](https://powerbi.microsoft.com/integrations/salesforce) с Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. В Power BI нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
   ![](media/service-connect-to-salesforce/pbi_getdata.png) 
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-salesforce/pbi_getservices.png) 
3. Выберите **Аналитика для Salesforce** и **Получить**.  
   
   ![](media/service-connect-to-salesforce/salesforce.png)
4. Выберите **Вход** для запуска потока входа в систему.
   
    ![](media/service-connect-to-salesforce/dialog.png)
5. При появлении запроса введите учетные данные Salesforce. Выберите **Разрешить**, чтобы служба Power BI получила доступ к базовым сведениям и данным Salesforce.
   
   ![](media/service-connect-to-salesforce/sf_authorize.png)
6. Выберите данные, которые вы хотите импортировать в Power BI, в раскрывающемся списке:
   
   * **Панель мониторинга**
     
     Выберите стандартную панель мониторинга в зависимости от пользователя (например, **Менеджер по продажам**). Эти панели мониторинга извлекают определенный набор из стандартных данных Salesforce, который не содержит настраиваемые поля.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcechooserole.png)
   * **Отчеты**
     
     Выберите один или несколько пользовательских отчетов из вашей учетной записи Salesforce. Эти отчеты соответствуют вашим представлениям в Salesforce и могут содержать данные из пользовательских полей или объектов.
     
     ![](media/service-connect-to-salesforce/pbi_salesforcereports.png)
     
     Если вы не видите все отчеты, добавьте или создайте их в вашей учетной записи Salesforce и повторите попытку подключения.

7. Выберите **Подключить**, чтобы начать импорт. Во время операции появится уведомление о том, что выполняется импорт. После завершения импорта вы увидите панель мониторинга, отчет и набор данных Salesforce на левой панели навигации.
   
   ![](media/service-connect-to-salesforce/pbi_getdatasalesforcedash.png)

Вы можете изменить эту панель мониторинга для отображения данных любым нужным образом. Вы можете задавать вопросы в поле "Вопросы и ответы" или [выбрать плитку](consumer/end-user-tiles.md), чтобы открыть соответствующий отчет и [изменить или удалить плитки на панели мониторинга](service-dashboard-edit-tile.md).

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Изменение и удаление плитки](service-dashboard-edit-tile.md) на панели мониторинга
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных ежедневно обновляется по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="system-requirements-and-considerations"></a>Системные требования и рекомендации

- Подключение к рабочей учетной записи Salesforce, для которой включен доступ к API

- Разрешения, предоставляемые приложению Power BI во время входа

- Учетная запись предоставляет достаточно вызовов API для извлечения и обновления данных.

- Для обновления необходим маркер аутентификации. Убедитесь, что вы импортировали не более пяти наборов данных Salesforce, так как Salesforce разрешает использовать не более пяти токенов проверки подлинности для каждого приложения.

- В API отчетов Salesforce есть ограничение на количество строк данных: не более 2000 строк.


## <a name="troubleshooting"></a>Устранение неполадок

При возникновении ошибок ознакомьтесь с требованиями выше. 

Возможность входа в личный домен или домен песочницы сейчас не поддерживается.

### <a name="unable-to-connect-to-the-remote-server-message"></a>Сообщение "Не удалось подключиться к удаленному серверу"

Если при попытке подключиться к учетной записи Salesforce появляется сообщение "Не удалось подключиться к удаленному серверу", см. описание решения на следующем форуме: [Сообщение об ошибке входа в соединитель Salesforce: "Не удалось подключиться к удаленному серверу"](https://www.outsystems.com/forums/Forum_TopicView.aspx?TopicId=17674&TopicName=log-in-error-message-unable-to-connect-to-the-remote-server&).


## <a name="next-steps"></a>Дальнейшие действия
[Что такое Power BI?](fundamentals/power-bi-overview.md)

[Источники данных для службы Power BI](service-get-data.md)

