---
title: "Подключение к AT Internet Bridge с помощью Power BI"
description: "AT Internet Bridge для Power BI"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: a96e4b0f20eaea1a9f9e9fc71ea2724952f61fc3
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-at-internet-bridge-with-power-bi"></a>Подключение к AT Internet Bridge с помощью Power BI
AT Internet помогает извлекать пользу из данных с помощью унифицированной платформы цифровой аналитики — Analytics Suite. Пакет содержимого AT Internet Bridge для Power BI содержит данные, связанные с посещениями, источниками, локализацией и устройствами для вашего сайта.

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

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](service-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="whats-included"></a>Содержимое
Пакет содержимого включает данные за последние 45 дней в следующих таблицах:  

    - "Преобразование";  
    - "Устройства";  
    - "Локализация";  
    - "Источники";  
    - "Глобальные посещения".  

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Power BI — основные понятия](service-basic-concepts.md)

