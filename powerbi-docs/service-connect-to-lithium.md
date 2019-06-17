---
title: Подключение к Lithium с помощью Power BI
description: Lithium для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6fa16cf59ece7f701fc50f1914138b9ca5362c45
ms.sourcegitcommit: 762857c8ca09ce222cc3f8b006fa1b65d11e4ace
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66720460"
---
# <a name="connect-to-lithium-with-power-bi"></a>Подключение к Lithium с помощью Power BI
Lithium помогает строить доверительные отношения между лучшими торговыми марками и клиентами, находить ответы и обмениваться опытом. Подключив пакет содержимого Lithium для Power BI, вы сможете оценивать основные метрики, связанные с интернет-сообществом, для повышения объемов продаж, снижения затрат на обслуживание и повышения уровня доверия со стороны клиентов. 

Подключитесь к [пакету содержимого Lithium](https://app.powerbi.com/getdata/services/lithium) для Power BI.

>[!NOTE]
>Пакет содержимого Power BI использует API-интерфейс Lithium. Большое число вызовов API может повлечь за собой взимание дополнительных платежей за использование Lithium. Уточните этот момент у администратора Lithium.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. Выберите **Lithium** \> **Получить**.
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. Укажите URL-адрес вашего сообщества Lithium. Он будет иметь формат *https://community.yoursite.com* .
   
   ![](media/service-connect-to-lithium/params.png)
5. При появлении запроса введите учетные данные Lithium. Выберите **oAuth 2** в качестве механизма проверки подлинности, нажмите кнопку **Вход** и следуйте потоку операций проверки подлинности Lithium.
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. После завершения процедуры входа в систему начнется процесс импорта. После завершения в области навигации появятся новая панель мониторинга, отчет и модель. Выберите панель мониторинга, чтобы просмотреть импортированные данные.
   
    ![](media/service-connect-to-lithium/lithium.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="system-requirements"></a>Требования к системе
Для пакета содержимого Lithium требуется Lithium community версии 15.9 или более поздней. Для подтверждения обратитесь к администратору Lithium.

## <a name="next-steps"></a>Дальнейшие действия
[Что такое Power BI?](power-bi-overview.md)

[Основные понятия для разработчиков в службе Power BI](service-basic-concepts.md)

