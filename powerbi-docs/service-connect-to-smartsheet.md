---
title: Подключение к Smartsheet с помощью Power BI
description: Smartsheet для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: b30e9934c6a1779538aeb5fe82db59e018fdb880
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34249466"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Подключение к Smartsheet с помощью Power BI
Smartsheet — это удобная платформа для совместной работы и обмена файлами. Пакет содержимого Smartsheet для Power BI включает панель мониторинга, отчеты и набор данных с обзором вашей учетной записи Smartsheet. Вы можете также использовать [Power BI Desktop](desktop-connect-to-data.md) для подключения напрямую к отдельным листам в учетной записи. 

Подключитесь к [пакету содержимого Smartsheet](https://app.powerbi.com/groups/me/getdata/services/smartsheet) для Power BI.

>[!NOTE]
>Для подключения и загрузки пакета содержимого для Power BI рекомендуется использовать учетную запись администратора Smartsheet, так как она обеспечивает доступ к дополнительным возможностям.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
   ![](media/service-connect-to-smartsheet/pbi_getdata.png)
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-smartsheet/pbi_getservices.png) 
3. Выберите **Smartsheet \> Получить**.
   
   ![](media/service-connect-to-smartsheet/smartsheet.png)
4. В качестве метода проверки подлинности выберите **oAuth2 \> Войти**.
   
   При появлении запроса введите учетные данные Smartsheet и пройдите проверку подлинности.
   
   ![](media/service-connect-to-smartsheet/creds.png)
   
   ![](media/service-connect-to-smartsheet/creds2.png)
5. После импорта данных в Power BI в области навигации слева появятся новая панель мониторинга, отчеты и набора данных. Новые элементы будут отмечены желтой звездочкой (\*). Выберите Smartsheet.
   
   ![](media/service-connect-to-smartsheet/dashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="whats-included"></a>Содержимое
Пакет содержимого Smartsheet для Power BI содержит общие сведения о вашей учетной записи Smartsheet, например число рабочих областей, отчеты и листы, в которые вносятся изменения, и т. д. Пользователи с правами администратора смогут также видеть некоторые сведения о пользователях в системе, например создателей верхних листов.  

Вы можете использовать соединитель Smartsheet в [Power BI Desktop](desktop-connect-to-data.md) для подключения напрямую к отдельным листам в учетной записи.  

## <a name="next-steps"></a>Дальнейшие действия:

[Приступая к работе с Power BI](service-get-started.md)

[Получение данных для Power BI](service-get-data.md)