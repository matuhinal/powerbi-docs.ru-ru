---
title: Подключение к MailChimp с помощью Power BI
description: MailChimp для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: f54841b77d79854334ddb6d93ccdc9b5926201ac
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37136717"
---
# <a name="connect-to-mailchimp-with-power-bi"></a>Подключение к MailChimp с помощью Power BI
Пакет содержимого для Power BI извлекает данные из вашей учетной записи MailChimp и создает панель мониторинга, набор отчетов и набор данных, которые позволяют анализировать ваши данные. Используйте аналитику для создания [панелей мониторинга MailChimp](https://powerbi.microsoft.com/integrations/mailchimp), чтобы быстро определить тенденции по кампаниям, отчетам и отдельным подписчикам. Данные обновляются ежедневно, так что вам всегда доступны последние сведения.

Подключитесь к [пакету содержимого MailChimp](https://app.powerbi.com/getdata/services/mailchimp) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
    ![](media/service-connect-to-mailchimp/pbi_getdata.png)
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-mailchimp/pbi_getservices.png)
3. Выберите **MailChimp** \> **Получить**.
   
   ![](media/service-connect-to-mailchimp/mailchimp.png)
4. В качестве метода проверки подлинности выберите **oAuth2** \> **Войти**.
   
    При появлении запроса введите учетные данные MailChimp и пройдите процесс проверки подлинности.
   
    При первом подключении вам будет предложено разрешить Power BI доступ только для чтения к вашей учетной записи. Выберите **Разрешить**, чтобы начать импорт. Это может занять несколько минут в зависимости от объема данных в вашей учетной записи.
   
    ![](media/service-connect-to-mailchimp/allow.png)
5. После импорта данных в Power BI в области навигации слева появятся новая панель мониторинга, отчеты и набора данных. Это панель мониторинга по умолчанию, которую Power BI создает для отображения данных. Вы можете изменить эту панель мониторинга для отображения данных любым нужным образом.
   
   ![](media/service-connect-to-mailchimp/pbi_mailchimpnewdash.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="next-steps"></a>Дальнейшие действия
[Что такое Power BI?](power-bi-overview.md)

[Power BI — основные понятия](service-basic-concepts.md)

