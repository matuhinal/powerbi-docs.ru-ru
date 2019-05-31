---
title: Как обновить учетные данные для пакета содержимого Xero
description: Если вы используете пакет содержимого Xero Power BI, то у вас могли возникнуть проблемы с ежедневным обновлением пакета содержимого из-за недавнего инцидента со службой Power BI.
author: SarinaJoan
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 1d773f8c7509fa4bbf872ae62f03bbb4da815d84
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "61221268"
---
# <a name="how-to-refresh-your-xero-content-pack-credentials-if-refresh-failed"></a>Как обновить учетные данные для пакета содержимого Xero в случае сбоя обновления
Если вы используете пакет содержимого Xero Power BI, то у вас могли возникнуть некоторые проблемы с ежедневным обновлением пакета содержимого из-за недавнего инцидента со службой Power BI.

Чтобы увидеть, удалось ли выполнить обновление пакета содержимого, можно проверить состояние последнего обновления для набора данных Xero, как показано на снимке экрана ниже.

![](media/service-refresh-xero-credentials/powerbi-xero-refresh-failed.png)

Если вы видите, что обновление завершилось сбоем, как показано выше, то выполните следующие действия, чтобы обновить учетные данные пакета содержимого.

1. Нажмите кнопку с многоточием (...) рядом с набором данных Xero, а затем выберите **Запланировать обновление**. Откроется страница параметров пакета содержимого Xero.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-schedule-refresh.png)
2. На странице **Settings for Xero** (Параметры Xero) выберите **Учетные данные источников данных** > **Изменить учетные данные**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-settings-page.png)
3. Введите название организации > **Далее**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-configure.png)
4. Войдите, используя учетную запись Xero.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-welcome.png)
5. Теперь, когда учетные данные обновлены, давайте убедимся, что запланированное обновление будет запускаться ежедневно. Для этого нажмите кнопку с многоточием (...) рядом с набором данных Xero, а затем снова выберите **Запланировать обновление**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-refresh-schedule.png)
6. Также можно обновить набор данных немедленно. Нажмите кнопку с многоточием (...) рядом с набором данных Xero, а затем выберите **Обновить**.
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-refresh-now.png)

Если у вас по-прежнему возникают проблемы с обновлением, свяжитесь с нами через сайт [http://support.powerbi.com](http://support.powerbi.com) 

Чтобы ознакомиться с дополнительными сведениями о пакете содержимого Xero для Power BI, посетите страницу справки [Пакет содержимого Xero для Power BI](service-connect-to-xero.md).

### <a name="next-steps"></a>Дальнейшие действия
* Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)

