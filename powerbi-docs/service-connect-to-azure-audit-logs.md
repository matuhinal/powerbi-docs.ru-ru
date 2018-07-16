---
title: Подключение к журналам аудита Azure с помощью Power BI
description: Журналы аудита Azure для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/06/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 903f2a345ba4d87cb217ececa459a3cca14d72fa
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37134646"
---
# <a name="connect-to-azure-audit-logs-with-power-bi"></a>Подключение к журналам аудита Azure с помощью Power BI
Пакет контента "Журналы аудита Azure" для Power BI позволяет анализировать и визуализировать информацию, хранящуюся в журналах аудита. Power BI извлекает данные, создает стандартную панель мониторинга и строит на основе этих данных отчеты.

[Подключитесь к пакету содержимого журналов аудита Azure](https://app.powerbi.com/getdata/services/azure-audit-logs) или прочтите дополнительные сведения об [интеграции журналов аудита Azure](https://powerbi.microsoft.com/integrations/azure-audit-logs) с Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.  
   
    ![](media/service-connect-to-azure-audit-logs/getdata.png)
2. В поле **Службы** выберите **Получить**.  
   
    ![](media/service-connect-to-azure-audit-logs/services.png) 
3. Выберите пункты **Журналы аудита Azure** > **Получить**.  
   
   ![](media/service-connect-to-azure-audit-logs/azureauditlogs.png)
4. При появлении запроса введите **идентификатор подписки Azure**. Сведения о том, как узнать свой [идентификатор подписки](#FindingParams), см. ниже.   
   
    ![](media/service-connect-to-azure-audit-logs/parameters.png)
5. В качестве **метода проверки подлинности** выберите **oAuth2** \> **Войти**.
   
    ![](media/service-connect-to-azure-audit-logs/creds.png)
6. Введите данные своей учетной записи для входа в систему.
   
    ![](media/service-connect-to-azure-audit-logs/login.png)
7. Power BI извлечет данные журналов аудита Azure и создаст информационную панель и отчет, готовые к использованию. 
   
    ![](media/service-connect-to-azure-audit-logs/dashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="system-requirements"></a>Требования к системе
Для пакета содержимого журналов аудита требуется доступ к журналам аудита на портале Azure. Дополнительные сведения см. [здесь](https://azure.microsoft.com/documentation/articles/insights-debugging-with-events/).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Поиск параметров
Вы можете определить свой идентификатор подписки одним из двух простых способов.

1. На сайте https://portal.azure.com -&gt; "Обзор" —&gt; "Подписки" —&gt; "Идентификатор подписки"
2. На сайте https://manage.windowsazure.com -&gt; "Параметры" —&gt; "Идентификатор подписки"

Идентификатор подписки представляет собой длинную последовательность цифр и букв, как в шаге \# 4 приведенного выше примера. 

## <a name="troubleshooting"></a>Устранение неполадок
Если происходит ошибка из-за недопустимых учетных данных или при попытке выполнить обновление, попробуйте удалить все экземпляры пакета содержимого журналов аудита Azure и повторите попытку подключения.

## <a name="next-steps"></a>Дальнейшие действия
[Что такое Power BI?](power-bi-overview.md)  
[Power BI — основные понятия](service-basic-concepts.md)  

