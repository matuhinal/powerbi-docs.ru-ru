---
title: Как обновить учетные данные для пакета содержимого Xero
description: Если вы используете пакет содержимого Xero Power BI, то у вас могли возникнуть проблемы с ежедневным обновлением пакета содержимого из-за недавнего инцидента со службой Power BI.
author: SarinaJoan
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 0a7268c041976a3cab3316c91470c1378a3685f5
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83327744"
---
# <a name="how-to-refresh-your-xero-content-pack-credentials-if-refresh-failed"></a>Как обновить учетные данные для пакета содержимого Xero в случае сбоя обновления
Если вы используете пакет содержимого Xero Power BI, то у вас могли возникнуть некоторые проблемы с ежедневным обновлением пакета содержимого из-за недавнего инцидента со службой Power BI.

Чтобы увидеть, удалось ли выполнить обновление пакета содержимого, можно проверить состояние последнего обновления для набора данных Xero, как показано на снимке экрана ниже.

![](media/service-refresh-xero-credentials/powerbi-xero-refresh-failed.png)

Если вы видите, что обновление завершилось сбоем, как показано выше, то выполните следующие действия, чтобы обновить учетные данные пакета содержимого.

1. Нажмите **Дополнительные параметры** (...) рядом с набором данных Xero, а затем выберите команду **Запланировать обновление**. Откроется страница параметров пакета содержимого Xero.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-schedule-refresh.png)
2. На странице **Settings for Xero** (Параметры Xero) выберите **Учетные данные источников данных** > **Изменить учетные данные**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-settings-page.png)
3. Введите название организации > **Далее**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-configure.png)
4. Войдите, используя учетную запись Xero.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-welcome.png)
5. Теперь, когда учетные данные обновлены, давайте убедимся, что запланированное обновление будет запускаться ежедневно. Для этого нажмите кнопку **Дополнительные параметры** (...) рядом с набором данных Xero, а затем снова выберите команду **Запланировать обновление**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-refresh-schedule.png)
6. Также можно обновить набор данных немедленно. Нажмите **Дополнительные параметры** (...) рядом с набором данных Xero, а затем выберите команду **Обновить**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-refresh-now.png)

Если у вас по-прежнему возникают проблемы с обновлением, свяжитесь с нами через сайт [https://support.powerbi.com](https://support.powerbi.com) 

Чтобы ознакомиться с дополнительными сведениями о пакете содержимого Xero для Power BI, посетите страницу справки [Пакет содержимого Xero для Power BI](service-connect-to-xero.md).

### <a name="next-steps"></a>Дальнейшие действия
* У вас имеются и другие вопросы? [Ответы на них см. в сообществе Power BI.](https://community.powerbi.com/)

