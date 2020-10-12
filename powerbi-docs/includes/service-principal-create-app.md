---
title: Создание приложения субъекта-службы
description: Создание приложения субъекта-службы
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 05/20/2020
ms.custom: include file
ms.openlocfilehash: 80886eab6de6c125d0361b326f5d31d2b3bb35e5
ms.sourcegitcommit: d153cfc0ce559480c53ec48153a7e131b7a31542
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91524536"
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

    ![Снимок экрана: получение ИД приложения на вкладке "Обзор".](media/embedded-service-principal/application-id.png)