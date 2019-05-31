---
title: Подключение к Troux с помощью Power BI
description: Troux для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 9152538204089ed9c75b69b79a08dc7496a8cca9
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "61156157"
---
# <a name="connect-to-troux-for-power-bi"></a>Подключение к Troux для Power BI
С помощью пакета содержимого Troux вы можете визуализировать репозиторий корпоративной архитектуры совершенно новыми способами непосредственно в Power BI. В пакет содержимого входит набор средств анализа бизнес-возможностей, приложения, которые предоставляют эти возможности, и технологии, которые поддерживают эти приложения, полностью настраиваемые с помощью Power BI.

Подключите [пакет содержимого Troux](https://app.powerbi.com/getdata/services/troux) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
   ![](media/service-connect-to-troux/getdata.png)
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-troux/services.png)
3. Выберите **Troux** \> **Получить**.
   
   ![](media/service-connect-to-troux/troux.png)
4. Укажите URL-адрес Troux OData. Сведения о том, как [найти эти параметры](#FindingParams), см. ниже.
   
   ![](media/service-connect-to-troux/params.png)
5. В качестве значения параметра **Проверка подлинности**выберите **Обычная** , укажите имя пользователя и пароль (регистр учитывается), а затем щелкните **Вход**.
   
    ![](media/service-connect-to-troux/creds.png)
6. После утверждения процесс импорта начнется автоматически. После завершения в области навигации появятся новая панель мониторинга, отчет и модель. Выберите панель мониторинга, чтобы просмотреть импортированные данные.
   
     ![](media/service-connect-to-troux/dashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="system-requirements"></a>Требования к системе
Требуется доступ к веб-каналу Troux OData и Troux 9.5.1 или более поздняя версия.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Поиск параметров
Уникальный URL-адрес веб-канала Troux OData можно получить в службе по работе с клиентами.

## <a name="troubleshooting"></a>Устранение неполадок
Если после ввода учетных данных возникает ошибка, связанная со временем ожидания, повторите попытку подключения.

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Получение данных в Power BI](service-get-data.md)

