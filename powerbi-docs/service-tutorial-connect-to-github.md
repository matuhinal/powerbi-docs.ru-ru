---
title: Руководство. Соединиться с репозиторием GitHub с помощью Power BI
description: В этом учебнике вы подключитесь к реальным данным в службе GitHub с помощью Power BI, после чего служба Power BI автоматически создаст панели мониторинга и отчеты.
author: maggiesMSFT
manager: kfile
ms.reviewer: SarinaJoan
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 04/19/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 3aeb1fc16ae200399125a2366a8993d45aad34c4
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578626"
---
# <a name="tutorial-connect-to-a-github-repo-with-power-bi"></a>Руководство. Соединиться с репозиторием GitHub с помощью Power BI
В этом учебнике вы подключитесь к реальным данным в службе GitHub с помощью Power BI, после чего служба Power BI автоматически создаст панели мониторинга и отчеты. Подключение к Power BI на общедоступный репозиторий содержимого (также называется *репозитория*) и просмотреть ответы на следующие вопросы: сколько людей участвует в создании общедоступного содержимого Power BI; кто вносит наибольший вклад; в какой день недели содержимое добавляется наиболее активно; И другие вопросы. 

![Отчет GitHub в Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-punch-card.png)

В этом учебнике вы выполните следующие действия:

> [!div class="checklist"]
> * зарегистрируете учетную запись GitHub, если у вас ее еще нет; 
> * войдете в учетную запись Power BI или зарегистрируете ее, если у вас ее еще нет;
> * откроете службу Power BI;
> * найдете приложение GitHub;
> * введете сведения для общедоступного репозитория Power BI в GitHub;
> * просмотрите панель мониторинга и отчет с данными GitHub;
> * очистите ресурсы, удалив приложение.

Если вы не зарегистрированы в Power BI, перед началом работы [пройдите бесплатную регистрацию](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="prerequisites"></a>Предварительные требования

Для прохождения этого учебника требуется учетная запись GitHub. 

- Зарегистрируйтесь в службе [учетной записи GitHub](https://docs.microsoft.com/contribute/get-started-setup-github).


## <a name="how-to-connect"></a>Способы подключения
1. Войдите в службу Power BI (https://app.powerbi.com). 
2. В области навигации слева выберите пункт **Приложения** и нажмите кнопку **Получить приложения**.
   
   ![Кнопка "Получить приложения" в Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial.png) 

3. Выберите **приложений**, тип **GitHub** в поле поиска > **получить сейчас**.
   
   ![Кнопка "Получить" в Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-app-source.png) 

4. В **установить это приложение Power BI?** выберите **установить**.
5. В **нового приложения готов**выберите **перейдите к приложению**.
6. В **приступить к работе с нового приложения**выберите **подключайте данные из**.

    ![Начало работы с новым приложением](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

7. Введите имя и владельца репозитория. URL-адрес этого репозитория — https://github.com/MicrosoftDocs/powerbi-docs, поэтому в поле **Владелец репозитория** укажите **MicrosoftDocs**, а в поле **Репозиторий** — **powerbi-docs**. 
   
    ![Имя репозитория Power BI в GitHub](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect.png)

5. Введите созданные учетные данные GitHub. Power BI может пропустить этот шаг, если вы уже вошли в GitHub в браузере. 

6. Для **метод проверки подлинности**, Сохранить **oAuth2** выбранного \> **Sign In**.

7. Следуйте инструкциям на экране. Предоставьте Power BI разрешение на доступ к данным GitHub.
   
   Теперь Power BI может подключаться к данным в GitHub.  Данные обновляются раз в день.

8. После импорта данных в Power BI вы увидите содержимое новой рабочей областью GitHub. 
9. Щелкните стрелку рядом с именем рабочей области в панели навигации слева. Видно, что рабочая область содержит панель мониторинга и отчета. 

    ![Приложения в области навигации слева](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav-expanded.png)

10. Нажмите кнопку с многоточием (...) рядом с именем панели мониторинга > **Переименовать** > тип **информационная панель GitHub**.
 
    ![Плитка GitHub в Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav.png) 

8. Щелкните значок глобальной навигации, чтобы свернуть область навигации и освободить место на экране.

    ![Значок глобальной навигации](media/service-tutorial-connect-to-github/power-bi-global-navigation-icon.png)

10. Выбор информационной панели GitHub.
    
    Информационная панель GitHub содержит реальные данные, поэтому значения, которые вы видите может отличаться.

    ![Панель мониторинга GitHub в Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-new-dashboard.png)

    

## <a name="ask-a-question"></a>Задать вопрос

1. Поместите курсор в **задать вопрос о данных**. Power BI предлагает **вопросы, чтобы приступить к работе**. 

1. Выберите **числа пользователей существуют**.
 
    ![Существуют ли количество пользователей](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-qna-how-many-users.png)

13. В диапазоне от **сколько** и **существуют ли пользователи**, тип **на запросы на включение внесенных изменений**. 

     Power BI создает Гистограмма, показывающая количество запросов на включение внесенных изменений на человека.

    ![Существуют ли количество запросов на включение внесенных изменений на пользователя](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-qna-how-many-prs.png)


13. Щелкните значок закрепления, чтобы закрепить ее на панель мониторинга, затем **Exit Q & A**.

## <a name="view-the-github-report"></a>Просмотр отчета GitHub 

1. В панели GitHub, выделите гистограмму **запросов на Вытягивание по месяцам** для открытия соответствующего отчета.

    ![Запросы на Вытягивание по месяц Гистограмма](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-column-chart.png)

2. Выберите имя пользователя в **всего запросов на Вытягивание пользователем** диаграммы. В этом примере мы видим, что большая часть свои часы в феврале.

    ![Отчет GitHub в Power BI с выделенными данными по пользователю](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-cross-filter-total-prs.png)

3. Выберите вкладку **Перфокарта**, чтобы перейти к следующей странице отчета. 
 
    ![Страница "Перфокарта" отчета GitHub в Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tues-3pm.png)

    Как видно во вторник в 15: 00 — это наиболее общее время и день недели для *фиксирует*, когда люди проверять свою работу.

## <a name="clean-up-resources"></a>Очистка ресурсов

Завершив работу с учебником, вы можете удалить приложение GitHub. 

1. На панели навигации слева выберите пункт **Приложения**.
2. Наведите указатель на плитку GitHub и щелкните значок **Удалить** в виде корзины.

    ![Удаление приложения GitHub](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-delete.png)

## <a name="next-steps"></a>Дальнейшие действия

В этом учебнике вы подключились к общедоступному репозиторию GitHub и получили данные, которые служба Power BI отформатировала в панели мониторинга и отчете. Вы получили ответы на некоторые вопросы, изучив панель мониторинга и отчет. Теперь вы можете узнать, как подключаться к другим службами, таким как Salesforce, Microsoft Dynamics и Google Analytics. 
 
> [!div class="nextstepaction"]
> [Подключение к используемым веб-службам](service-connect-to-services.md)


