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
ms.openlocfilehash: 60ca8d828d3bb33dced97213e2f135db364c35e5
ms.sourcegitcommit: ba447d7cc94418d7d3cf6fdcb686ec1a859258a8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37145145"
---
# <a name="connect-to-project-online-with-power-bi"></a>Подключение к Project Online с помощью Power BI
Microsoft Project Online — это гибкое решение для управления портфелем проекта (PPM) и повседневной работы. Project Online позволяет организациям приступить к работе, расставить приоритеты по инвестициям в портфель проектов, а также добиться запланированного уровня ценности для бизнеса. Пакет содержимого Project Online для Power BI позволяет использовать функции аналитики Project Online для управления проектами, портфолио и ресурсами.

Подключитесь к [пакету содержимого Project Online](https://app.powerbi.com/getdata/services/project-online) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
    ![](media/service-connect-to-project-online/getdata.png)
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-project-online/services.png)
3. Выберите **Microsoft Project Online** \> **Получить**.
   
   ![](media/service-connect-to-project-online/mproject.png)
4. В текстовом поле **URL-адрес Project Web App** введите URL-адрес для Project Web App (PWA), к которому требуется подключиться, и нажмите кнопку **Далее**. Обратите внимание, что в личном домене ситуация может отличаться от приведенной в примере. В текстовом поле **Язык сайта PWA** введите номер, который соответствует нужному языку сайта PWA. Введите одну цифру "1" для английского языка, "2" для французского языка, "3" для немецкого языка, "4" для португальского (Бразилия), "5" для португальского (Португалия) и "6" для испанского языка. 
   
    ![](media/service-connect-to-project-online/params.png)
5. В качестве метода проверки подлинности выберите **oAuth2** \> **Войти**. При появлении запроса введите учетные данные Project Online и пройдите процесс проверки подлинности.
   
    ![](media/service-connect-to-project-online/creds.png)
    
Обратите внимание, что вам нужно использовать разрешения на уровне средства просмотра портфеля, диспетчера портфелей или администратора для Project Web App, к которому вы подключаетесь.

6. Вы увидите уведомление, указывающее на загрузку данных. В зависимости от размера вашей учетной записи это может занять некоторое время. После импорта данных в Power BI в области навигации слева появятся новая панель мониторинга, 13 отчетов и набор данных. Это панель мониторинга по умолчанию, которую Power BI создает для отображения данных. Вы можете изменить эту панель мониторинга для отображения данных любым нужным образом.

   ![](media/service-connect-to-project-online/dashboard2.png)

7. После подготовки панели мониторинга и отчетов вы можете приступить к изучению данных Project Online. Пакет содержимого включает 13 удобных и подробных отчетов по обзору портфеля (6 страниц отчетов), обзору ресурсов (5 страниц отчетов) и состоянию проекта (2 страницы отчетов). 

   ![](media/service-connect-to-project-online/report1.png)
   
   ![](media/service-connect-to-project-online/report3.png)
   
   ![](media/service-connect-to-project-online/report2.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

**Расширение пакета содержимого**

Загрузка [PBIT-файла в GitHub](https://github.com/OfficeDev/Project-Power-BI-Content-Packs) для дальнейшей настройки и обновления пакета содержимого

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Получение данных в Power BI](service-get-data.md)

