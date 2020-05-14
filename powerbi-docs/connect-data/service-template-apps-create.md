---
title: Создание приложений-шаблонов в Power BI
description: Сведения о создании приложений-шаблонов, которые можно распространять между любыми клиентами Power BI.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/04/2020
ms.author: painbar
ms.openlocfilehash: a99ecc89679aa83f9da9a271c5e55d12a7df3dd4
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348489"
---
# <a name="create-a-template-app-in-power-bi"></a>Создание приложений-шаблонов в Power BI

Новые *приложения-шаблоны* Power BI позволяют партнерам создавать приложения Power BI с минимальным количеством кода или вообще без него и развертывать их для любых клиентов.  В этой статье приводятся пошаговые инструкции по созданию приложения-шаблона Power BI.

Если вы создаете отчеты и панели мониторинга Power BI, то можете стать *автором приложений-шаблонов*, который создает и упаковывает в *приложение* различное аналитическое содержимое. Затем готовое приложение можно развернуть в других клиентах Power BI с помощью любой доступной платформы, например AppSource, или используя его в вашей собственной веб-службе. Кроме того, будучи автором, вы можете создавать распространяемый защищенный пакет аналитики.

Правами пользователей на создание или установку приложений-шаблонов управляют администраторы клиента Power BI. Пользователи, у которых есть соответствующие права, могут устанавливать приложение-шаблон, а затем изменять его и распространять среди пользователей Power BI в своей организации.

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

2. В разделе **Создание рабочей области** выберите **Перейти на новую**.

    ![Использование новых рабочих областей](media/service-template-apps-create/power-bi-upgrade-new.png)

3. Введите имя, описание (необязательно) и изображение логотипа (необязательно) для рабочей области.

4. Разверните раздел **Дополнительно** и выберите **Разработка приложения-шаблона**.

    ![Разработка приложения-шаблона](media/service-template-apps-create/power-bi-template-app-develop.png)

5. Нажмите кнопку **Сохранить**.
>[!NOTE]
>Вам нужно иметь разрешение от администратора Power BI для повышения уровня приложений-шаблонов.

## <a name="create-the-content-in-your-template-app"></a>Создание содержимого в приложении-шаблоне

Как и при использовании обычной рабочей области Power BI, следующим шагом является создание в ней содержимого.  

- [Создайте содержимое Power BI](index.yml) в рабочей области.

Если вы используете параметры в Power Query, убедитесь, что они имеют четко определенный тип (например, Text). Типы Any и Binary не поддерживаются.

Рекомендации по созданию отчетов и панелей мониторинга для приложения-шаблона см. в статье [Советы по созданию приложений-шаблонов в Power BI](service-template-apps-tips.md).

## <a name="create-the-test-template-app"></a>Создание тестового приложения-шаблона

Теперь, когда в рабочей области есть содержимое, вы можете упаковать его в приложение-шаблон. Первым шагом является создание тестового приложения-шаблона, доступного только в вашем клиенте организации.

1. В рабочей области шаблона выберите **Создать приложение**.

    ![Создать приложение](media/service-template-apps-create/power-bi-create-app.png)

    Здесь нужно указать дополнительные параметры сборки для приложения-шаблона в пяти категориях:

    **Фирменная символика**

    ![Фирменная символика](media/service-template-apps-create/power-bi-create-branding.png)
    - Имя приложения
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

    ![Управление](media/service-template-apps-create/power-bi-create-control.png)

    >[!NOTE]
    >Экспорт в формат PBIX всегда заблокирован для пользователей, устанавливающих приложение.

    **Параметры**

    Используйте эту категорию для управления поведением параметров при подключении к источникам данных. Дополнительные сведения о [создании параметров запроса](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/).

    ![Параметры](media/service-template-apps-create/power-bi-create-parameters.png)
    - **Значение**: значение параметра по умолчанию.
    - **Требуется**: используйте, чтобы потребовать у установщика ввести параметр, определяемый пользователем.
    - **Блокировка**: не позволяет установщику изменить параметр.

    **Доступ**: на этапе тестирования решите, какие пользователи в организации могут устанавливать и тестировать приложение. Не беспокойтесь — вы всегда можете вернуться и изменить эти параметры позже. Этот параметр не влияет на доступ к распространенному приложению шаблона.

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

2. Выберите **Создать приложение**.

    Если вы создали тестовое приложение в разделе **Создание тестового приложения-шаблона** выше, рядом с пунктом **Тестирование** уже будет отображаться желтая точка и выбирать здесь **Создать приложение** не нужно. Если все же выбрать этот пункт, вы вернетесь к процессу создания приложения-шаблона.

3. Щелкните **Получить ссылку**.

    !["Создать приложение", "Получить ссылку"](media/service-template-apps-create/power-bi-dev-template-create-app-get-link.png)

4. Чтобы протестировать процедуру установки приложения, скопируйте ссылку в окне уведомления и вставьте ее в новое окно браузера.

    Далее вы будете выполнять те же действия, которые будут выполнять ваши клиенты. Изучить процесс с их стороны можно в статье [Установка и распространение приложений-шаблонов в организации](service-template-apps-install-distribute.md).

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
12. Скопируйте новый URL-адрес для доступа к тестированию приложения вне вашего клиента. Эта ссылка также отправляется, чтобы начать распространение приложения в AppSource, для чего создается [предложение в центре для партнеров](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-power-bi-app-offer). Отправляйте в центр для партнеров только ссылки предварительного уровня. Только после того, как приложение будет утверждено и вы получите уведомление о его публикации в AppSource, моно повысить уровень этого пакета до рабочего уровня в Power BI.
13. Когда приложение будет готово для использования в рабочей среде или публикации в AppSource, вернитесь в область **Управление выпусками** и щелкните **Повысить уровень приложения** рядом с пунктом **Предварительный этап**.
14. Выберите **Повысить уровень**, чтобы подтвердить выбор.

    Теперь приложение является рабочим и готово к распространению.

    ![Приложение в рабочей среде](media/service-template-apps-create/power-bi-template-app-production.png)

Чтобы сделать приложение общедоступным для тысяч пользователей Power BI, рекомендуем опубликовать его в AppSource. Дополнительные сведения: [Предложение приложения Power BI](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-power-bi-app-offer).

## <a name="next-steps"></a>Дальнейшие действия

Сведения о том, как с вашим приложением-шаблоном взаимодействуют пользователи, см. в разделе [Установка, настройка и распространение приложений-шаблонов в организации](service-template-apps-install-distribute.md).

Дополнительные сведения о распространении приложения: [Предложение приложения Power BI](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-power-bi-app-offer).