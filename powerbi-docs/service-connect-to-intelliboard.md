---
title: Подключение к IntelliBoard с помощью Power BI
description: IntelliBoard для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 0931dee6f9719a4a53c5ccf2c20aeb8f9170af42
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46549691"
---
# <a name="connect-to-intelliboard-with-power-bi"></a>Подключение к IntelliBoard с помощью Power BI
IntelliBoard предлагает упрощенный доступ к данным системы управления обучением Moodle через службы отчетов. Пакет содержимого IntelliBoard для Power BI предоставляет дополнительную аналитику, включая метрики ваших курсов, списки зарегистрированных пользователей, общую производительность и ваши действия в системе управления обучением.

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

[Power BI — основные понятия](consumer/end-user-basic-concepts.md)

