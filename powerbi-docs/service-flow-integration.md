---
title: Интеграция Power BI с Power Automate
description: Сведения о том, как создавать потоки Power Automate, которые активируются оповещениями о данных Power BI.
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: YhmNstC39Mw
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/25/2020
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: aafba825c5bd4ece3c8b97256d5943f91b456cd7
ms.sourcegitcommit: 032a77f2367ca937f45e7e751997d7b7d0e89ee2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77609694"
---
# <a name="power-automate-and-power-bi"></a>Power Automate и Power BI

[Power Automate](https://docs.microsoft.com/power-automate/getting-started) — это предложение SaaS для автоматизации рабочих процессов в различных приложениях и службах SaaS, которые используют бизнес-пользователи. Power Automate позволяет автоматизировать задачи путем интеграции избранных приложений и служб (включая Power BI) для получения уведомлений, синхронизации файлов, сбора данных и т. п. Выполнение повторяющихся задач существенно упрощается благодаря автоматизации рабочих процессов.

[Приступая к работе с Power Automate](https://docs.microsoft.com/power-automate/getting-started).

Посмотрите видео, где Power Automate создает поток, который отправляет подробное сообщение по электронной почте коллегам при активации оповещения Power BI. Затем сделайте то же самое, выполнив пошаговые инструкции, приведенные под видео.

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>Создание потока, который активируется оповещением о данных Power BI

### <a name="prerequisites"></a>Предварительные требования
В этом руководстве показано, как создать два разных потока — на основе шаблона и с нуля. Для дальнейшей работы [создайте оповещение о данных в Power BI](service-set-data-alerts.md), создайте бесплатную учетную запись Slack и [зарегистрируйтесь в Power Automate](https://flow.microsoft.com/#home-signup) (это бесплатно).

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>Создание потока, использующего Power BI, на основе шаблона
В этой задаче мы создаем на основе шаблона простой поток, который активируется с помощью оповещения о данных (уведомления) Power BI.

1. Войдите в Power Automate (flow.microsoft.com).
2. Выберите **Мои потоки**.
   
   ![Панель меню Power Automate](media/service-flow-integration/power-bi-my-flows.png)
3. Выберите **Создать из шаблона**.
   
    ![Панель меню "Мои потоки"](media/service-flow-integration/power-bi-template.png)
4. С помощью поля поиска найдите шаблоны Power BI и выберите **Отправка электронного письма кому угодно при активации оповещения о данных Power BI > Продолжить**.
   
    ![результаты поиска](media/service-flow-integration/power-bi-flow-alert.png)


### <a name="build-the-flow"></a>Создание потока
Этот шаблон содержит один триггер (оповещение о данных Power BI для новых олимпийских медалей сборной Ирландии) и одно действие (отправка сообщения электронной почты). При выборе поля Power Automate отобразит динамическое содержимое, которое можно использовать.  В этом примере мы включили в текст сообщения значение и URL-адрес плитки.

![Шаблон потока](media/service-flow-integration/power-bi-template1.png)

1. В раскрывающемся списке триггера выберите оповещение о данных Power BI. Выберите **New medal for Ireland** (Новая медаль для Ирландии). Чтобы узнать, как создать оповещение, см. статью [Оповещения о данных в службе Power BI](service-set-data-alerts.md).
   
   ![раскрывающийся список оповещений](media/service-flow-integration/power-bi-trigger-flow.png)
2. Введите один или несколько допустимых адресов электронной почты, а затем выберите **Изменить** (см. ниже) или **Добавить динамическое содержимое**. 
   
   ![Экран отправки электронных сообщений](media/service-flow-integration/power-bi-flow-email.png)

3. Power Automate создаст заголовок и сообщение, которые можно сохранить или изменить. Вы можете использовать все значения, заданные при создании оповещения в Power BI: просто поместите курсор и выберите нужный элемент в серой выделенной области. 

   ![Экран отправки электронных сообщений](media/service-flow-integration/power-bi-flow-email-default.png)

1.  Например, если в Power BI вы создали заголовок оповещения **We won another medal** (Мы получили еще одну медаль), можно выбрать **Заголовок оповещения**, чтобы добавить этот текст в поле темы своего сообщения электронной почты.

    ![создание текста электронного сообщения](media/service-flow-integration/power-bi-flow-message.png)

    Вы также можете использовать текст сообщения по умолчанию или создать собственный. В примере выше приводится несколько изменений в сообщении.

1. Когда все будет готово, выберите **Создать поток** или **Сохранить поток**.  Поток будет создан и проанализирован.  При обнаружении ошибок Power Automate отображает соответствующие сообщения.
2. Если будут обнаружены ошибки, выберите **Изменить поток** для их исправления. В противном случае выберите **Готово**, чтобы выполнить новую последовательность.
   
   ![сообщение об успехе](media/service-flow-integration/power-bi-flow-running.png)
5. Когда оповещение о данных активируется, на указанные вами адреса будут отправлены сообщения электронной почты.  
   
   ![оповещение по электронной почте](media/service-flow-integration/power-bi-flow-email2.png)

## <a name="create-a-power-automate-that-uses-power-bi---from-scratch-blank"></a>Создание пустого (с нуля) потока Power Automate, который использует Power BI
В этой задаче мы создаем с нуля простой поток, который активируется с помощью оповещения о данных (уведомления) Power BI.

1. Войдите в Power Automate.
2. Выберите **Мои потоки** > **Создать с нуля**.
   
   ![Верхняя панель меню Power Automate](media/service-flow-integration/power-bi-my-flows.png)
3. С помощью поля поиска найдите триггер Power BI и выберите **Power BI — When a data driven alert is triggered** (Power BI — при активации оповещения о данных).

### <a name="build-your-flow"></a>Создание потока
1. В раскрывающемся списке выберите имя оповещения.  Чтобы узнать, как создать оповещение, см. статью [Оповещения о данных в службе Power BI](service-set-data-alerts.md).
   
    ![выбор имени оповещения](media/service-flow-integration/power-bi-totalstores2.png)
2. Выберите **Новый шаг** > **Добавить действие**.
   
   ![добавление нового шага](media/service-flow-integration/power-bi-new-step.png)
3. С помощью поиска найдите **Outlook** и выберите **Создать событие**.
   
   ![Создание потока](media/service-flow-integration/power-bi-create-event.png)
4. Заполните поля в событии. При выборе поля Power Automate отобразит динамическое содержимое, которое можно использовать.
   
   ![Продолжение создания потока](media/service-flow-integration/power-bi-flow-event.png)
5. Когда все будет готово, выберите **Создать поток**.  Power Automate сохранит и проанализирует поток. Если ошибок нет, выберите **Готово**, чтобы запустить поток.  Новая последовательность будет добавлена на страницу **Мои потоки**.
   
   ![Завершение потока](media/service-flow-integration/power-bi-flow-running.png)
6. Если поток активируется с помощью оповещения о данных Power BI, вы получите в Outlook примерно следующее уведомление о событии.
   
    ![Power Automate запускает уведомление Outlook](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>Дальнейшие действия
* [Начало работы с Power Automate](https://docs.microsoft.com/power-automate/getting-started/)
* [Настройка оповещений о данных в службе Power BI](service-set-data-alerts.md)
* [Настройка оповещений о данных на устройстве iPhone](consumer/mobile/mobile-set-data-alerts-in-the-mobile-apps.md)
* [Настройка оповещений о данных в мобильном приложении Power BI для Windows 10](consumer/mobile/mobile-set-data-alerts-in-the-mobile-apps.md)
* Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](https://community.powerbi.com/)

