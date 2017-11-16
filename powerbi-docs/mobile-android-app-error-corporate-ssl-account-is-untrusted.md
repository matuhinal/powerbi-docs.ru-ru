---
title: "Ошибка "
corporate: 
ssl: 
certificate: 
is: 
untrusted": 
'-': 
power: 
bi": 
description: "При входе в приложение Power BI для Android может появиться сообщение \"Не удалось выполнить проверку подлинности, так как SSL-сертификат вашей организации не является доверенным\""
.": 
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 4ef29c0cab96e21045f30805d7445aa34d37697a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="error-corporate-ssl-certificate-is-untrusted---power-bi"></a>Ошибка "Корпоративный SSL-сертификат не является доверенным" — Power BI
При входе в мобильное приложение Microsoft Power BI для Android может появиться сообщение "Не удалось выполнить проверку подлинности, так как SSL-сертификат вашей организации не является доверенным для этого устройства. Обратитесь к ИТ-администратору организации". 

Действия по устранению этой неполадки обычно зависят от операционной системы на устройстве Android, но эта ошибка может быть связана и с другими проблемами.

## <a name="on-android-7-or-later"></a>Android 7 или более поздней версии
Найдите обновление для приложения **Chrome** и установите это обновление.

## <a name="on-android-6-and-earlier"></a>Android 6 и более ранних версий
Возможно, вашему устройству требуется обновленная версия приложения System WebView. Приложение может быть установлено на устройстве — достаточно просто нажать кнопку **обновления**.

Если приложение System WebView не установлено на устройстве, сделайте следующее.

1. Закройте Power BI на устройстве Android.
2. Откройте магазин Google Play и найдите приложение **System WebView** от Google Inc.
3. Установите это приложение.
4. Перезапустите приложение Power BI и войдите в него.

## <a name="time-zone-settings"></a>Настройки часовых поясов
Настройки часовых поясов на вашем устройстве могут быть неправильными. 

Чтобы проверить их, последовательно выберите **Параметры** > **Система** > **Дата и время**.

## <a name="custom-authentication-server"></a>Пользовательский сервер проверки подлинности
Если вы используете пользовательский сервер проверки подлинности, SSL-сертификат на корпоративном сервере проверки подлинности может быть недействительным. Обратитесь за помощью к ИТ-администратору вашей организации.

## <a name="next-steps"></a>Дальнейшие действия
* [Скачивание приложения Android](http://go.microsoft.com/fwlink/?LinkID=544867) из магазина приложений Android.
* У вас появились вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

