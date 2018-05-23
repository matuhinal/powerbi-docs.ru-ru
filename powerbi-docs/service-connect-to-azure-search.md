---
title: Подключение к службе "Поиск Azure" с помощью Power BI
description: Поиск Azure для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 5b7cee097aaecacc4bf9525e93fde51839c0a081
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="connect-to-azure-search-with-power-bi"></a>Подключение к службе "Поиск Azure" с помощью Power BI
Аналитика трафика службы поиска Azure позволяет отслеживать трафик и получать по нему подробные сведения в службе поиска Azure. Пакет содержимого службы поиска Azure для Power BI предоставляет подробные сведения по данным службы поиска, включая поиск, индексацию, статистику служб и задержки за последние 30 дней. Дополнительные сведения см. в [записи блога Azure](https://azure.microsoft.com/en-us/blog/analyzing-your-azure-search-traffic/).

Подключите [пакет содержимого службы поиска Azure](https://app.powerbi.com/getdata/services/azure-search) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
   ![](media/service-connect-to-azure-search/pbi_getdata.png) 
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-azure-search/pbi_getservices.png) 
3. Выберите **Поиск Azure** \> **Получить**.
   
   ![](media/service-connect-to-azure-search/azuresearch.png)
4. Укажите имя учетной записи хранилища таблиц, в которой хранится анализ службы поиска Azure.
   
   ![](media/service-connect-to-azure-search/params.png)
5. Выберите **Ключ** в качестве механизма проверки подлинности и укажите ключ учетной записи хранения. Щелкните **Войти** , чтобы начать процесс загрузки.
   
   ![](media/service-connect-to-azure-search/creds.png)
6. После завершения на панели навигации появятся новая панель мониторинга, отчет и модель. Выберите панель мониторинга, чтобы просмотреть импортированные данные.
   
    ![](media/service-connect-to-azure-search/dashboard2.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="system-requirements"></a>Требования к системе
Для пакета содержимого службы поиска Azure требуется включить аналитику трафика службы поиска Azure в учетной записи.

## <a name="troubleshooting"></a>Устранение неполадок
Убедитесь, что имя учетной записи хранения правильно указано вместе с полным ключом доступа. Имя учетной записи хранения должно соответствовать учетной записи, настроенной в аналитике трафика службы поиска Azure.

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Power BI — основные понятия](service-basic-concepts.md)

