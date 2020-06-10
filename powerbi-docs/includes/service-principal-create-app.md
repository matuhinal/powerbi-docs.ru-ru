---
title: Создание приложения субъекта-службы
description: Создание приложения субъекта-службы
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 05/20/2020
ms.custom: include file
ms.openlocfilehash: 0fe3e1743cb8853d6626b59b748d70bfcc292dbd
ms.sourcegitcommit: cd64ddd3a6888253dca3b2e3fe24ed8bb9b66bc6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "84315842"
---
1. Выполните вход в [Microsoft Azure](https://ms.portal.azure.com/#allservices).

2. В строке поиска найдите **Регистрация приложений** и щелкните ссылку **Регистрация приложений**.

    ![регистрация приложения azure](media/embedded-service-principal/azure-app-registration.png)

3. Щелкните **Новая регистрация**.

    ![новая регистрация](media/embedded-service-principal/new-registration.png)

4. Заполните необходимые сведения:
    * **Имя** — введите имя для своего приложения.
    * **Поддерживаемые типы учетных записей** — выберите поддерживаемые типы учетных записей.
    * (Необязательно) **URI перенаправления** — при необходимости введите универсальный код ресурса (URI).

5. Щелкните **Зарегистрировать**.

6. После регистрации на вкладке **Обзор** доступен *Идентификатор приложения*. Скопируйте и сохраните *Идентификатор приложения* для последующего использования.

    ![идентификатор приложения](media/embedded-service-principal/application-id.png)