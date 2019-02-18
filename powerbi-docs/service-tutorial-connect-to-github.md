---
title: Руководство. Подключение к примеру в GitHub с помощью Power BI
description: В этом учебнике вы подключитесь к реальным данным в службе GitHub с помощью Power BI, после чего служба Power BI автоматически создаст панели мониторинга и отчеты.
author: maggiesMSFT
manager: kfile
ms.reviewer: SarinaJoan
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 05/17/2018
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 8f44356f79b8a77ef06fe464671dbbaaaa4187e9
ms.sourcegitcommit: 5e83fa6c93a0bc6599f76cc070fb0e5c1fce0082
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56215593"
---
# <a name="tutorial-connect-to-a-github-sample-with-power-bi"></a>Руководство. Подключение к примеру в GitHub с помощью Power BI
В этом учебнике вы подключитесь к реальным данным в службе GitHub с помощью Power BI, после чего служба Power BI автоматически создаст панели мониторинга и отчеты. Подключившись к общедоступному *репозиторию* содержимого Power BI, можно следующее: сколько людей участвует в создании общедоступного содержимого Power BI; кто вносит наибольший вклад; в какой день недели содержимое добавляется наиболее активно; а также получить ответы на другие вопросы. 

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

- [Зарегистрируйте учетную запись GitHub](https://docs.microsoft.com/contribute/get-started-setup-github), если у вас ее еще нет.


## <a name="how-to-connect"></a>Способы подключения
1. Войдите в службу Power BI (http://powerbi.com). 
2. В области навигации слева выберите пункт **Приложения** и нажмите кнопку **Получить приложения**.
   
   ![Кнопка "Получить приложения" в Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial.png) 

3. Выберите **Приложения**, в поле поиска введите **github** и нажмите кнопку **Получить**.
   
   ![Кнопка "Получить" в Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-get-it-now.png) 

4. Введите имя и владельца репозитория. URL-адрес этого репозитория — https://github.com/MicrosoftDocs/powerbi-docs, поэтому в поле **Владелец репозитория** укажите **MicrosoftDocs**, а в поле **Репозиторий** — **powerbi-docs**. 
   
    ![Имя репозитория Power BI в GitHub](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-repo-name.png)

5. Введите созданные учетные данные GitHub. Power BI может пропустить этот шаг, если вы уже вошли в GitHub в браузере. 

6. В качестве **метода проверки подлинности** выберите **oAuth2** \> **Войти**.

7. Следуйте инструкциям на экране. Предоставьте Power BI разрешение на доступ к данным GitHub.
   
   Теперь Power BI может подключаться к данным в GitHub.  Данные обновляются раз в день.

8. После импорта данных в Power BI появится новая плитка GitHub. 
 
   ![Плитка GitHub в Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tile.png) 

8. Щелкните значок глобальной навигации, чтобы свернуть область навигации и освободить место на экране.

    ![Значок глобальной навигации](media/service-tutorial-connect-to-github/power-bi-global-navigation-icon.png)

10. Щелкните плитку GitHub, которая появилась в шаге 8. 
    
    Откроется панель мониторинга GitHub. Данные меняются динамически, поэтому в вашем случае значения могут быть другими.

    ![Панель мониторинга GitHub в Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-dashboard.png)

    

## <a name="ask-a-question"></a>Задать вопрос

11. Установите курсор в поле **Задать вопрос о своих данных** и выберите **запросы на вытягивание**. 

    ![Поле "Задать вопрос о своих данных" в Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-ask-question.png)

12. Введите **по месяцам**.
 
    ![Запросы на вытягивание по месяцам](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-ask-question-by-month.png)

     Power BI создаст линейчатую диаграмму с числом запросов на вытягивание по месяцам.

13. Нажмите кнопку **Выйти из раздела вопросов и ответов**.

## <a name="view-the-github-report"></a>Просмотр отчета GitHub 

1. На панели мониторинга GitHub выберите комбинированную диаграмму (гистограмму и график) **Запросы на вытягивание по месяцам**, чтобы открыть связанный отчет.

    ![Комбинированная диаграмма "Запросы на вытягивание по месяцам"](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-pull-requests-combo-chart.png)

2. Выберите имя пользователя на диаграмме **Всего запросов на вытягивание по пользователям** и посмотрите, не превышает ли среднее число часов для него общее среднее значение за март, как в этом примере.

    ![Отчет GitHub в Power BI с выделенными данными по пользователю](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-report-highlight.png)

3. Выберите вкладку **Перфокарта**, чтобы перейти к следующей странице отчета. 
 
    ![Страница "Перфокарта" отчета GitHub в Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tues-3pm.png)

    Очевидно, что больше всего *фиксаций* приходится на 15:00 во вторник.

## <a name="clean-up-resources"></a>Очистка ресурсов

Завершив работу с учебником, вы можете удалить приложение GitHub. 

1. На панели навигации слева выберите пункт **Приложения**.
2. Наведите указатель на плитку GitHub и щелкните значок **Удалить** в виде корзины.

    ![Удаление приложения GitHub](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-delete.png)

## <a name="next-steps"></a>Дальнейшие действия

В этом учебнике вы подключились к общедоступному репозиторию GitHub и получили данные, которые служба Power BI отформатировала в панели мониторинга и отчете. Вы получили ответы на некоторые вопросы, изучив панель мониторинга и отчет. Теперь вы можете узнать, как подключаться к другим службами, таким как Salesforce, Microsoft Dynamics и Google Analytics. 
 
> [!div class="nextstepaction"]
> [Подключение к используемым веб-службам](service-connect-to-services.md)


