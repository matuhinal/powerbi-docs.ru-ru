---
title: Подключение к AT Internet Bridge с помощью Power BI
description: AT Internet Bridge для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: c24a508652b147b6fc684039d2965f9935b624c0
ms.sourcegitcommit: b53a6f5575f5f8bc443ecdca9c72525ce123518f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2019
ms.locfileid: "70186038"
---
# <a name="connect-to-at-internet-bridge-with-power-bi"></a>Подключение к AT Internet Bridge с помощью Power BI
AT Internet помогает извлекать пользу из данных с помощью унифицированной платформы цифровой аналитики — Analytics Suite. Пакет содержимого AT Internet Bridge для Power BI содержит данные, связанные с посещениями, источниками, локализацией и устройствами для вашего сайта.

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

Подключитесь к [пакету содержимого AT Internet Bridge](https://app.powerbi.com/getdata/services/at-internet-bridge) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
   ![](media/service-connect-to-at-internet/pbi_getdata.png) 
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-at-internet/pbi_getservices.png) 
3. Выберите **AT Internet Bridge** \> **Получить**.
   
   ![](media/service-connect-to-at-internet/atinternet.png)
4. Укажите номер веб-сайта AT Internet, к которому вы хотите подключиться.
   
   ![](media/service-connect-to-at-internet/params.png)
5. Выберите **Обычная** в качестве механизма проверки подлинности, укажите имя пользователя и пароль AT Internet, а затем нажмите кнопку **Вход**.
   
   ![](media/service-connect-to-at-internet/creds.png)
6. Нажмите кнопку **Подключить** , чтобы начать импорт. После завершения в области навигации появятся новая панель мониторинга, отчет и модель. Выберите панель мониторинга, чтобы просмотреть импортированные данные.
   
    ![](media/service-connect-to-at-internet/atinternet.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="whats-included"></a>Содержимое
Пакет содержимого включает данные за последние 45 дней в следующих таблицах:  

    - "Преобразование";  
    - "Устройства";  
    - "Локализация";  
    - "Источники";  
    - "Глобальные посещения".  

## <a name="next-steps"></a>Дальнейшие действия
[Что такое Power BI?](power-bi-overview.md)

[Основные понятия для разработчиков в службе Power BI](service-basic-concepts.md)

