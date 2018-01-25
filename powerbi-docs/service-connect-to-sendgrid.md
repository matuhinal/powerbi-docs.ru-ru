---
title: "Подключение к SendGrid с помощью Power BI"
description: "SendGrid для Power BI"
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
ms.openlocfilehash: d077bedcc1faa10af79cf3eba258b1dac969ae10
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
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

