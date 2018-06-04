---
title: Подключение к Project Online с помощью Power BI
description: Project Online для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 52bd4b5dc27ff127eadea49cb3e761d6cda4788d
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34249167"
---
# <a name="connect-to-project-online-with-power-bi"></a>Подключение к Project Online с помощью Power BI
Microsoft Project Online — это гибкое решение для управления портфелем проекта (PPM) и повседневной работы. Project Online позволяет организациям приступить к работе, расставить приоритеты по инвестициям в портфель проектов, а также добиться запланированного уровня ценности для бизнеса. Пакет содержимого Project Online для Power BI позволяет анализировать данные проекта с помощью готовых метрик, таких как состояние портфеля и соответствие проекта.

Подключитесь к [пакету содержимого Project Online](https://app.powerbi.com/getdata/services/project-online) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
    ![](media/service-connect-to-project-online/getdata.png)
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-project-online/services.png)
3. Выберите **Microsoft Project Online** \> **Получить**.
   
   ![](media/service-connect-to-project-online/mproject.png)
4. В текстовом поле **URL-адрес Project Web App** введите URL-адрес для Project Web App (PWA), к которому требуется подключиться, и нажмите кнопку **Далее**. Обратите внимание, что в личном домене ситуация может отличаться от приведенной в примере.
   
    ![](media/service-connect-to-project-online/params.png)
5. В качестве метода проверки подлинности выберите **oAuth2** \> **Войти**. При появлении запроса введите учетные данные Project Online и пройдите процесс проверки подлинности.
   
    ![](media/service-connect-to-project-online/creds.png)
    
Обратите внимание, что вам нужно использовать разрешения на уровне средства просмотра портфеля, диспетчера портфелей или администратора для Project Web App, к которому вы подключаетесь.

6. Вы увидите уведомление, указывающее на загрузку данных. В зависимости от размера вашей учетной записи это может занять некоторое время. После импорта данных в Power BI в области навигации слева появятся новая панель мониторинга, отчеты и набора данных. Это панель мониторинга по умолчанию, которую Power BI создает для отображения данных. Вы можете изменить эту панель мониторинга для отображения данных любым нужным образом.
   
   ![](media/service-connect-to-project-online/dashboard2.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Получение данных в Power BI](service-get-data.md)

