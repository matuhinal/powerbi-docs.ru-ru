---
title: Настройка оповещений о данных в мобильных приложениях Power BI
description: Узнайте, как в мобильных приложениях Power BI настроить оповещения, уведомляющие вас о том, что данные на панелях мониторинга выходят за установленные пределы.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 12/18/2017
ms.author: maggies
ms.openlocfilehash: aa4aac1b0628fb0670a4265095ba2abcae3c1dcf
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="set-data-alerts-in-the-power-bi-mobile-apps"></a>Настройка оповещений о данных в мобильных приложениях Power BI
Область применения:

| ![iPhone](media/mobile-set-data-alerts-in-the-mobile-apps/iphone-logo-50-px.png) | ![iPad](media/mobile-set-data-alerts-in-the-mobile-apps/ipad-logo-50-px.png) | ![Телефон Android](media/mobile-set-data-alerts-in-the-mobile-apps/android-phone-logo-50-px.png) | ![Планшет Android](media/mobile-set-data-alerts-in-the-mobile-apps/android-tablet-logo-50-px.png) | ![Планшет Android](media/mobile-set-data-alerts-in-the-mobile-apps/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone |iPad |Телефоны под управлением Android |Планшеты Android |Устройства под управлением Windows 10 |

Оповещения можно настраивать на панели мониторинга в службе Power BI и мобильных приложениях Power BI. Оповещения уведомляют о том, что данные на плитке выходят за пределы заданного порога. Оповещения используются с плитками, которые сдержат отдельные элементы (например, карточки и датчики), но не данные потоковой передачи. Оповещения о данных можно настраивать на мобильном устройстве и просматривать в службе Power BI, и наоборот. Видеть настраиваемые оповещения о данных можете только вы, даже если панель мониторинга или моментальный снимок плитки находятся в общем доступе.

Настроить оповещения для плиток можно при наличии лицензии Power BI Pro или бесплатной лицензии Power BI, а также если для общей панели мониторинга доступна емкость Premium. 

> [!WARNING]
> Уведомления на основе данных содержат сведения о данных. Если ваше устройство украдено, рекомендуем отключить все правила генерации оповещений на основе данных в службе Power BI. 
> 
> Дополнительные сведения об [управлении оповещениями о данных в службе Power BI](service-set-data-alerts.md).
> 
> 

## <a name="data-alerts-on-an-iphone-or-ipad"></a>Оповещения о данных на устройстве iPhone или iPad
### <a name="set-an-alert-on-an-iphone-or-ipad"></a>Настройка оповещений на устройстве iPhone или iPad
1. Коснитесь плитки или датчика с числом на панели мониторинга, чтобы открыть ее в режиме фокусировки.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-card-visual.png)
2. Коснитесь значка колокольчика ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-alert-icon.png), чтобы добавить оповещение.  
3. Нажмите **Добавить правило оповещения**.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-add-alert-rule.png)
4. Укажите тип оповещений (текущее значение становится больше или меньше заданного порога), которые хотите получать, и введите число.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-set-alert-threshold.png)
5. Укажите, хотите ли вы получать ежечасные или ежедневные уведомления, а также сообщения электронной почты.
   
   > [!NOTE]
   > Вы не будете получать уведомления каждый час или каждый день, если данные не были обновлены за соответствующий период.
   > 
   > 
6. Вы также можете изменить название оповещения.
7. Коснитесь элемента **Сохранить**.
8. Для одной плитки можно настроить оповещения как для превышения порога, так и для падения ниже его. В разделе **Управление оповещениями** нажмите **Добавить правило оповещения**.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-add-another-alert-rule.png)

### <a name="manage-alerts-on-your-iphone-or-ipad"></a>Управление оповещениями на устройствах iPhone и iPad
На мобильном устройстве можно управлять отдельными оповещениями. [Всеми оповещениями можно управлять в службе Power BI](service-set-data-alerts.md).

1. На панели мониторинга нажмите на плитку числа или датчика, на которой есть оповещение.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-card-visual.png)
2. Нажмите на значок звонка ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-has-alert-icon.png).  
3. Коснитесь имени оповещения, чтобы изменить его, коснитесь ползунка, чтобы отключить оповещения по электронной почте, или коснитесь значка корзины для удаления оповещения.
   
    ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-edit-delete-alert.png)

## <a name="data-alerts-on-an-android-device"></a>Оповещения о данных на устройстве Android
### <a name="set-an-alert-on-an-android-device"></a>Настройка оповещений на устройстве Android
1. На панели мониторинга в Power BI коснитесь плитки с датчиком или числом, чтобы открыть ее.  
2. Коснитесь значка колокольчика ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-alert-icon.png), чтобы добавить оповещение.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-tap-alert.png)
3. Нажмите на значок плюса (+).
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-plus-alert.png)
4. Укажите тип оповещений (текущее значение становится больше или меньше заданного порога), которые хотите получать, и введите число.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-tablet-set-alert-condition.png)
5. Коснитесь элемента **Готово**.
6. Укажите, хотите ли вы получать ежечасные или ежедневные уведомления, а также сообщения электронной почты.
   
   > [!NOTE]
   > Вы не будете получать уведомления каждый час или каждый день, если данные не были обновлены за соответствующий период.
   > 
   > 
7. Вы также можете изменить название оповещения.
8. Коснитесь элемента **Сохранить**.

### <a name="manage-alerts-on-an-android-device"></a>Управление оповещениями на устройстве Android
Вы можете управлять отдельными оповещениями в мобильном приложении Power BI, а также [всеми своими оповещениями в службе Power BI](service-set-data-alerts.md).

1. На панели мониторинга нажмите на плитку карточки или датчика, на которой есть оповещение.  
2. Коснитесь значка колокольчика ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-filled-alert-bell.png).  
3. Нажмите на оповещение, чтобы изменить значение или отключить его.
   
    ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-manage-alerts.png)
4. Чтобы добавить еще одно оповещение на ту же плитку, коснитесь значка плюса (+).
5. Чтобы полностью удалить оповещение, коснитесь значка корзины ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-android-delete-alert-icon.png).

## <a name="data-alerts-on-a-windows-device"></a>Оповещения о данных на устройстве с Windows
### <a name="set-data-alerts-on-a-windows-device"></a>Настройка оповещений о данных на устройстве с Windows
1. Коснитесь плитки или датчика с числом на панели мониторинга, чтобы открыть ее.  
2. Коснитесь значка колокольчика ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-alert-bell-off.png), чтобы добавить оповещение.  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-tap-alert.png)
3. Нажмите на значок плюса (+).
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-no-alerts-yet.png)
4. Укажите тип оповещений (текущее значение становится больше или меньше заданного порога), которые хотите получать, и введите число.
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-set-alert.png)
5. Укажите, хотите ли вы получать ежечасные или ежедневные уведомления, а также сообщения электронной почты.
   
   > [!NOTE]
   > Вы не будете получать уведомления каждый час или каждый день, если данные не были обновлены за соответствующий период.
   > 
   > 
6. Вы также можете изменить название оповещения.
7. Нажмите на значок галочки.
8. Для одной плитки можно настроить оповещения как для превышения порога, так и для падения ниже его. В разделе **Управление оповещениями** нажмите на значок плюса (+).
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-add-another-alert.png)

### <a name="manage-alerts-on-a-windows-device"></a>Управление оповещениями на устройстве с Windows
Вы можете управлять отдельными оповещениями в мобильном приложении Power BI, а также [всеми своими оповещениями в службе Power BI](service-set-data-alerts.md).

1. На панели мониторинга нажмите на плитку карточки или датчика, на которой есть оповещение.  
2. Нажмите на значок звонка ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-alert-bell-on.png).  
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-has-alerts.png)
3. Нажмите на оповещение, чтобы изменить значение или отключить его.
   
    ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-windows-10-add-another-alert.png)
4. Чтобы полностью удалить оповещение, щелкните его правой кнопкой мыши или нажмите с удержанием и выберите команду **Удалить**.

## <a name="receiving-alerts"></a>Получение оповещений
Оповещения появляются в [центре уведомлений](mobile-apps-notification-center.md) Power BI на вашем мобильном устройстве или в службе Power BI вместе с оповещениями о новых панелях мониторинга, к которым вам предоставили доступ.

Источники данных часто настраиваются для ежедневного обновления, хотя некоторые источники обновляются чаще. Если при обновлении данных на панели выясняется, что отслеживаемые значения вышли за установленные пороги, может произойти несколько вещей.

1. Power BI проверяет, прошло ли больше часа или 24 часов (в зависимости от выбранного вами варианта) с момента отправки предыдущего оповещения.
   
   Пока значение находится за установленным порогом, вы будете получать оповещение каждый час или каждые 24 часа.
2. Если вы включили отправку оповещений на электронную почту, в ваш ящик придет примерно такое сообщение:
   
   ![](media/mobile-set-data-alerts-in-the-mobile-apps/powerbi-alerts-email.png)
3. Power BI добавляет сообщение в ваш **Центр уведомлений**, а также значок нового оповещения на соответствующую плитку ![](media/mobile-set-data-alerts-in-the-mobile-apps/powerbi-alert-tile-notification-icon.png).
4. Нажмите кнопку глобальной структуры навигации ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-alert-global-nav-button.png), чтобы [открыть **центр уведомлений**](mobile-apps-notification-center.md) и просмотреть сведения об оповещении.
   
     ![](media/mobile-set-data-alerts-in-the-mobile-apps/power-bi-iphone-notifications.png) 

> [!NOTE]
> Оповещения отправляются только при обновлении данных. При обновлении данных Power BI проверяет, настроены ли для них оповещения. Если значение достигает заданного порога, оповещение срабатывает.
> 
> 

## <a name="tips-and-troubleshooting"></a>Советы и устранение неполадок
* В настоящее время не поддерживаются оповещения для плиток Bing, а также для плиток карточек с мерами даты и времени.
* Оповещения работают только с числовыми данными.
* Оповещения отправляются только при обновлении данных. Они не работают со статическими данными.
* Оповещения не используются с плитками, которые содержат данные потоковой передачи.

## <a name="next-steps"></a>Дальнейшие действия
* [Управление оповещениями в службе Power BI](service-set-data-alerts.md)
* [Получение уведомлений в мобильных приложениях Power BI](mobile-apps-notification-center.md)
* У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

