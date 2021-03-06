---
title: Создание приложений-шаблонов в Power BI
description: Сведения о создании приложений-шаблонов, которые можно распространять между любыми клиентами Power BI.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 09/15/2020
ms.author: painbar
ms.openlocfilehash: 2f663c8e47e9a66ec3f4ee3eb70646239be6126a
ms.sourcegitcommit: 02b5d031d92ea5d7ffa70d5098ed15e4ef764f2a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "91375012"
---
# <a name="create-a-template-app-in-power-bi"></a>Создание приложений-шаблонов в Power BI

*Приложения-шаблоны* Power BI позволяют партнерам создавать приложения Power BI с минимальным количеством кода или вообще без него и развертывать их для любых клиентов.  В этой статье приводятся пошаговые инструкции по созданию приложения-шаблона Power BI.

Если вы создаете отчеты и панели мониторинга Power BI, то можете стать *автором приложений-шаблонов*, который создает и упаковывает в *приложение* различное аналитическое содержимое. Затем готовое приложение можно развернуть в других клиентах Power BI с помощью любой доступной платформы, например AppSource, или используя его в вашей собственной веб-службе. Кроме того, будучи автором, вы можете создавать распространяемый защищенный пакет аналитики.

Правами пользователей на создание или установку приложений-шаблонов управляют администраторы Power BI. Пользователи, у которых есть соответствующие права, могут устанавливать приложение-шаблон, а затем изменять его и распространять среди пользователей Power BI в своей организации.

## <a name="prerequisites"></a>Предварительные требования

Ниже приведены требования к созданию приложения-шаблона:  

- [Лицензия Power BI Pro](../fundamentals/service-self-service-signup-for-power-bi.md).
- [Установка Power BI Desktop](../fundamentals/desktop-get-the-desktop.md) (необязательно).
- Знание [основных принципов Power BI](../fundamentals/service-basic-concepts.md).
- Разрешения на предоставление общего доступа к приложению шаблона (дополнительные сведения см. в разделе Power BI, посвященном [порталу администрирования и параметрам приложения шаблона](../admin/service-admin-portal.md#template-apps-settings)

## <a name="create-the-template-workspace"></a>Создание рабочей области приложения

Приложение-шаблон, которое можно распространять в других клиентах Power BI, необходимо создать в одной из новых рабочих областей.

1. В службе Power BI выберите **Рабочие области** > **Создать рабочую область**.

    ![Создание рабочей области](media/service-template-apps-create/power-bi-new-workspace.png)

2. В разделе **Создание рабочей области** введите имя, описание (необязательно) и изображение логотипа (необязательно) для рабочей области.

    ![Использование новых рабочих областей](media/service-template-apps-create/power-bi-upgrade-new.png)

4. Разверните раздел **Дополнительно** и выберите **Разработка приложения-шаблона**.

    ![Разработка приложения-шаблона](media/service-template-apps-create/power-bi-template-app-develop.png)

5. Щелкните **Сохранить**.
>[!NOTE]
>Вам нужно иметь разрешение от администратора Power BI для повышения уровня приложений-шаблонов.

## <a name="add-content-to-the-template-app-workspace"></a>Добавление содержимого в рабочую область приложения-шаблона

Как и при использовании обычной рабочей области Power BI, следующим шагом является добавление в него содержимого.  

- [Создайте содержимое Power BI](index.yml) в рабочей области.

Если вы используете параметры в Power Query, убедитесь, что они имеют четко определенный тип (например, Text). Типы Any и Binary не поддерживаются.

Рекомендации по созданию отчетов и панелей мониторинга для приложения-шаблона см. в статье [Советы по созданию приложений-шаблонов в Power BI](service-template-apps-tips.md).

## <a name="define-the-properties-of-the-template-app"></a>Определение свойств приложения-шаблона

Теперь, когда в рабочей области есть содержимое, вы можете упаковать его в приложение-шаблон. Первым шагом является создание тестового приложения-шаблона, доступного только в вашем клиенте организации.

1. В рабочей области приложения-шаблона выберите **Создать приложение**.

    ![Создание приложения](media/service-template-apps-create/power-bi-create-app.png)

    Здесь нужно указать дополнительные параметры сборки для приложения-шаблона на шести вкладках:

    **Фирменная символика**

    ![Фирменная символика](media/service-template-apps-create/power-bi-create-branding.png)
    - Имя приложения.
    - Описание
    - Сайт поддержки (ссылка отображается под сведениями о приложении после повторного распространения приложения-шаблона или приложения организации)
    - Логотип приложения (файл размером не более 45 КБ, с соотношением сторон 1:1 и в формате JPEG, PNG или JPG)
    - Цвет темы приложения

    **Навигация**

    Активируйте **Новый построитель навигации**, в котором можно настроить область навигации приложения (дополнительные сведения см. в разделе [Проектирование навигации](../collaborate-share/service-create-distribute-apps.md#design-the-navigation-experience) в этой статье).

   ![Выбор целевой страницы приложения](media/service-template-apps-create/power-bi-install-app-content.png)
    
    **Целевая страница приложения**: Если вы решили отказаться от построителя навигации, то можете выбрать целевую страницу приложения. задайте отчет или панель мониторинга в качестве целевой страницы своего приложения. Используйте целевую страницу, которая обеспечивает правильное впечатление.

    **Управление**

    Здесь можно задать ограничения, которые будут распространяться на пользователей для содержимого приложения. Используйте для защиты интеллектуальной собственности в приложении.

    ![Control](media/service-template-apps-create/power-bi-create-control.png)

    >[!NOTE]
    >Экспорт в формат PBIX всегда заблокирован для пользователей, устанавливающих приложение.

    **Параметры**

    Параметры создаются в исходном файле PBIX (узнайте подробнее о [создании параметров запроса](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/)). Используйте возможности на этой вкладке, чтобы помочь установщику приложения настроить приложение после установки при подключении к их данным.

    На этой вкладке можно также указать ссылку на документацию по приложению.

    ![Параметры](media/service-template-apps-create/power-bi-create-parameters.png)

    У каждого параметра есть имя и описание, которые берутся из запроса, а также поле значения. Существует три варианта получения значения для параметра во время установки.

    * Можно потребовать от установщика ввести значение. В этом случае необходимо указать пример, который будет заменен. Чтобы настроить параметр таким образом, установите флажок **Обязательно**, а затем присвойте пример в текстовом поле, указывающем, какой тип значения ожидается. Пример:

       ![Снимок экрана: значение требуемого параметра.](media/service-template-apps-create/power-bi-create-parameters-require-user.png)

    * Вы можете указать предварительно заполненное значение, которое пользователь, устанавливающий приложение, не может изменить. Параметр, настроенный таким образом, скрыт от пользователя, устанавливающего приложение. Этот метод следует использовать только в том случае, если вы уверены, что предварительно заполненное значение допустимо для всех пользователей. В противном случае используйте первый метод, упомянутый выше, для которого требуется ввод данных пользователем.

       Чтобы настроить параметр таким образом, введите значение в текстовое поле **Значение** и щелкните значок замка. После этого изменить значение не удастся. Пример:

       ![Снимок экрана: абсолютное значение параметра.](media/service-template-apps-create/power-bi-create-parameters-absolute.png)

    * Можно указать значение по умолчанию, которое пользователь может изменить во время установки. Чтобы настроить параметр таким образом, введите нужное значение по умолчанию в поле **Значение** и оставьте значок замка без блокировки. Пример:

      ![Снимок экрана: изменяемое значение параметра по умолчанию.](media/service-template-apps-create/power-bi-create-parameters-default.png)

    **Аутентификация**
    
    На этой вкладке можно выбрать метод проверки подлинности, который будет использоваться. Доступные параметры зависят от используемых типов источников данных.

    ![Снимок экрана: выбора метода проверки подлинности.](media/service-template-apps-create/power-bi-create-authentication.png)

    Уровень конфиденциальности настраивается автоматически:
   * Один источник данных: автоматически настроен как частный.
   * Множественный анонимный источник данных: автоматически настроен как общедоступный.

    **Доступ**
    
    На этапе тестирования решите, кто еще в организации может устанавливать и тестировать приложение. Не беспокойтесь — вы всегда можете вернуться и изменить эти параметры позже. Этот параметр не влияет на доступ к распространенному приложению-шаблону.

    ![Снимок экрана: вкладка доступа.](media/service-template-apps-create/power-bi-create-access.png)

2. Выберите **Создать приложение**.

    Появится сообщение, информирующее о готовности тестового приложения и содержащее ссылку, которую можно скопировать и отправить его тестировщикам.

    ![Тестовое приложение готово.](media/service-template-apps-create/power-bi-template-app-test-ready.png)

    Вы также выполнили первый шаг процесса управления выпусками, представленного далее.

## <a name="manage-the-template-app-release"></a>Управление выпуском приложения-шаблона

Перед выпуском общедоступной версии приложения-шаблона необходимо убедиться, что оно готово. Power BI создает панель управления выпусками, где можно изучать и контролировать всю процедуру выпуска приложения. Вы также можете активировать переход с одного этапа на другой. Ниже приведены основные этапы.

- Создание тестового приложения: для тестирования только в вашей организации.
- Повышение уровня тестового пакета до подготовительного: тестирование за пределами вашей организации.
- Повышение уровня подготовительного пакета до рабочей версии: рабочая версия.
- Удаление любого пакета или возврат к началу предыдущего этапа.

URL-адрес не изменяется при перемещении между этапами выпуска. Повышение уровня не затрагивает сам URL-адрес.

Давайте рассмотрим эти этапы:

1. В рабочей области шаблона щелкните **Управление выпусками**.

    ![Значок "Управление выпусками"](media/service-template-apps-create/power-bi-release-management-icon.png)

2. Если вы создали тестовое приложение в разделе **Определение свойств приложения-шаблона** выше, выберите **Получить ссылку** (рядом с пунктом **Тестирование** уже будет отображаться желтая точка).

    Если вы еще не создали приложение, выберите **Создать приложение**. Вы вернетесь к процессу создания приложения-шаблона.

    !["Создать приложение", "Получить ссылку"](media/service-template-apps-create/power-bi-dev-template-create-app-get-link.png)

4. Чтобы протестировать процедуру установки приложения, скопируйте ссылку в окне уведомления и вставьте ее в новое окно браузера.

    Далее вы будете выполнять те же действия, которые будут выполнять ваши клиенты. См. [Установка и распространение приложений-шаблонов в организации](service-template-apps-install-distribute.md)

5. В диалоговом окне выберите **Установить**.

    После установки появится уведомление о готовности нового приложения.

6. Выберите **Перейти к приложению**.
7. На экране **Начало работы с новым приложением** приложение будет отображаться так, как его увидят ваши клиенты.

    ![Начало работы с приложением](media/service-template-apps-create/power-bi-template-app-get-started.png)
8. Выберите **Исследовать приложение**, чтобы проверить тестовое приложение с использованием образца данных.
9. Чтобы внести изменения, вернитесь к приложению в исходной рабочей области. Изменяйте тестовое приложение, пока вас не будет все устраивать.
10. Когда вы будете готовы повысить уровень приложения до предварительного для дальнейшего тестирования вне клиента, вернитесь в область **Управление выпусками** и щелкните **Повысить уровень приложения**.

    ![Повышение уровня приложения до предварительного](media/service-template-apps-create/power-bi-template-app-promote.png)
    >[!NOTE]
    > При повышении уровня приложение становится общедоступным за пределами вашей организации.

    Если этот параметр не отображается, попросите у своего администратора Power BI предоставить вам [разрешения для разработки приложений-шаблонов](../admin/service-admin-portal.md#template-apps-settings) на портале администрирования.
11. Выберите **Повысить уровень**, чтобы подтвердить выбор.
12. Скопируйте новый URL-адрес для доступа к тестированию приложения вне вашего клиента. Эта ссылка также отправляется, чтобы начать распространение приложения в AppSource, для чего создается [предложение в центре для партнеров](/azure/marketplace/partner-center-portal/create-power-bi-app-offer). Отправляйте в центр для партнеров только ссылки предварительного уровня. Только после того, как приложение будет утверждено и вы получите уведомление о его публикации в AppSource, можно повысить уровень этого пакета до рабочего уровня в Power BI.
13. Когда приложение будет готово для использования в рабочей среде или публикации в AppSource, вернитесь в область **Управление выпусками** и щелкните **Повысить уровень приложения** рядом с пунктом **Предварительный этап**.
14. Выберите **Повысить уровень**, чтобы подтвердить выбор.

    Теперь приложение является рабочим и готово к распространению.

    ![Приложение в рабочей среде](media/service-template-apps-create/power-bi-template-app-production.png)

Чтобы сделать приложение общедоступным для тысяч пользователей Power BI, рекомендуем опубликовать его в AppSource. Дополнительные сведения: [Предложение приложения Power BI](/azure/marketplace/partner-center-portal/create-power-bi-app-offer).

## <a name="next-steps"></a>Дальнейшие действия

Сведения о том, как с вашим приложением-шаблоном взаимодействуют пользователи, см. в разделе [Установка, настройка и распространение приложений-шаблонов в организации](service-template-apps-install-distribute.md).

Дополнительные сведения о распространении приложения: [Предложение приложения Power BI](/azure/marketplace/partner-center-portal/create-power-bi-app-offer).