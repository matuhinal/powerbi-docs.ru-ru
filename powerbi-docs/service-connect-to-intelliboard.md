---
title: Подключение к IntelliBoard с помощью Power BI
description: IntelliBoard для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e912c47c58c96de8d2875b83a530468135e93ef2
ms.sourcegitcommit: b53a6f5575f5f8bc443ecdca9c72525ce123518f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2019
ms.locfileid: "70185924"
---
# <a name="connect-to-intelliboard-with-power-bi"></a>Подключение к IntelliBoard с помощью Power BI
IntelliBoard предлагает упрощенный доступ к данным системы управления обучением Moodle через Reporting Services. Пакет содержимого IntelliBoard для Power BI предоставляет дополнительную аналитику, включая метрики ваших курсов, списки зарегистрированных пользователей, общую производительность и ваши действия в системе управления обучением.

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

Подключитесь к [пакету содержимого IntelliBoard](https://app.powerbi.com/getdata/services/intelliboard) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.  
   
    ![](media/service-connect-to-intelliboard/getdata.png)
2. В поле **Службы** выберите **Получить**.  
   
    ![](media/service-connect-to-intelliboard/services.png)
3. Выберите **IntelliBoard**, а затем нажмите **Получить**.  
   
    ![](media/service-connect-to-intelliboard/intelliboard.png)
4. Выберите **OAuth 2**, и затем нажмите **Войти**. При появлении запроса введите учетные данные IntelliBoard.
   
    ![](media/service-connect-to-intelliboard/creds.png)
   
    ![](media/service-connect-to-intelliboard/creds2.png)
5. После подключения автоматически загрузятся информационная панель, отчет и набор данных. После завершения плитки обновятся в соответствии с данными из вашей учетной записи IntelliBoard.
   
    ![](media/service-connect-to-intelliboard/dashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="whats-included"></a>Содержимое
Пакет содержимого включает в себя данные из следующих таблиц.  

    - Действие  
    - "Агенты"  
    - "Авторизация"  
    - Страны  
    - "Прогресс обучения"  
    - "Зачисление"
    - "Язык"  
    - "Платформа"  
    - "Итоги"  
    - "Прогресс пользователя"    

## <a name="system-requirements"></a>Требования к системе
Чтобы создать этот пакет содержимого, требуется учетная запись IntelliBoard с разрешениями для вышеперечисленных таблиц.

## <a name="next-steps"></a>Дальнейшие действия
[Что такое Power BI?](power-bi-overview.md)

[Основные понятия для разработчиков в службе Power BI](service-basic-concepts.md)

