---
title: "Подключение к SendGrid с помощью Power BI"
description: "SendGrid для Power BI"
services: powerbi
documentationcenter: 
author: SarinaJoan
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
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: b2484e579cf3a5e428566e8fc3aead151552eff6
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2018
---
# <a name="connect-to-sendgrid-with-power-bi"></a>Подключение к SendGrid с помощью Power BI
Пакет контента Power BI для SendGrid позволяет извлекать информацию и статистику из вашей учетной записи SendGrid. С помощью пакета контента SendGrid можно визуализировать статистику SendGrid на панели мониторинга.

Подключите [пакет содержимого SendGrid](https://app.powerbi.com/getdata/services/sendgrid) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
   ![](media/service-connect-to-sendgrid/pbi_getdata.png) 
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-sendgrid/pbi_getservices.png) 
3. Выберите пакет содержимого **SendGrid** и нажмите кнопку **Получить**.
   
   ![](media/service-connect-to-sendgrid/sendgrid.png) 
4. При появлении запроса введите имя пользователя и пароль SendGrid. Выберите **Войти**.
   
   ![](media/service-connect-to-sendgrid/pbi_sendgridsignin.png)
5. После импорта данных в Power BI в области навигации слева появятся новая панель мониторинга, отчет и набор данных, заполненные статистикой по электронной почте за последние 90 дней. Новые элементы отмечены желтой звездочкой \*.
   
   ![](media/service-connect-to-sendgrid/pbi_sendgriddash.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="whats-included"></a>Содержимое
На панели мониторинга SendGrid доступны следующие метрики:

* Общая статистика по электронной почте — запрошено, доставлено, отклонен, заблокировано как нежелательная почта, отчет о нежелательной почте и т. д.
* Статистика по электронной почте по категориям
* Статистика по электронной почте по географии
* Статистика по электронной почте по ISP
* Статистика по электронной почте по устройствам, клиентам, браузерам

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Получение данных](service-get-data.md)

