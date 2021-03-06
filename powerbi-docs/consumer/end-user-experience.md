---
title: Навигация в службе Power BI
description: Обзор навигации в Power BI
author: mihart
ms.reviewer: mihart
featuredvideoid: G26dr2PsEpk
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: quickstart
ms.date: 10/12/2020
ms.author: mihart
LocalizationGroup: Get started
ms.openlocfilehash: 1c67ce91ce625bec3bb3be978bc553f2ff5a3eef
ms.sourcegitcommit: 02484b2d7a352e96213353702d60c21e8c07c6c0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "91982525"
---
# <a name="quickstart---getting-around-in-power-bi-service"></a>Краткое руководство. Навигация в службе Power BI

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Теперь, когда вы изучили [основы Power BI](end-user-basic-concepts.md), давайте ознакомимся с интерфейсом **службы Power BI** . Как упоминалось в предыдущей статье, участники вашей команды могут работать только в **Power BI Desktop** , формируя данные и создавая отчеты, панели мониторинга и приложения для других пользователей. Это *конструкторы* . Вы же можете проводить все время в службе Power BI, просматривая и используя содержимое, созданное другими ( **потребляя** его). Вы являетесь *бизнес-пользователем* . Это краткое руководство предназначено для *бизнес-пользователей* . 


   
 
## <a name="prerequisites"></a>Обязательные условия

- Если вы не зарегистрированы в Power BI, перед началом работы [пройдите бесплатную регистрацию](https://app.powerbi.com/signupredirect?pbi_source=web).

- Прочитайте статью [Power BI — основные понятия](end-user-basic-concepts.md).

- Для просмотра содержимого Power BI (отчеты, панели мониторинга, приложения), созданного *конструкторами* , необходимо соблюдение одного из двух условий:
    - наличие лицензии Power BI Pro;
    - ваша организация должна иметь подписку Power BI Premium и содержимое, к которому вам предоставлен доступ из емкости Premium.    
    [Сведения о лицензиях и подписках](end-user-license.md).     

    Для работы с этим кратким руководством не требуется соблюдение ни одного из этих условий. Корпорация Майкрософт предоставила доступ к примеру содержимого непосредственно из интерфейса службы Power BI. Мы будем использовать этот пример содержимого для изучения службы Power BI. 

## <a name="open-the-power-bi-service"></a>откроете службу Power BI;


Для начала откройте службу Power BI (app.powerbi.com). 
1. Если левая область навигации свернута, щелкните значок области навигации. ![Значок с тремя горизонтальными линиями](./media/end-user-experience/power-bi-burger.png) чтобы развернуть его. 


1. В левом нижнем углу выберите **Получить данные** . Давайте получим образец данных для ознакомления со службой Power BI. Мы подготовили для вас самые разные образцы данных, и в этот раз мы используем данные по маркетингу и продажам. 

   ![Снимок экрана с кнопкой "Получить данные".](./media/end-user-experience/power-bi-get-data.png)

1. После открытия окна **получения данных** щелкните **Примеры** .

   ![Снимок экрана с окном получения данных с красной рамкой вокруг элемента "Примеры".](./media/end-user-experience/power-bi-sample.png)

1. Последовательно выберите **Продажи и маркетинг** > **Подключить** . 

   ![Снимок экрана с выбранным примером "Продажи и маркетинг".](./media/end-user-experience/power-bi-sales.png)


5. Служба Power BI устанавливает пример в разделе **Моя рабочая область** .  **Моя рабочая область**  — частная песочница для обучения и экспериментов.  Содержимое можно просмотреть только в области **Моя рабочая область** . Пример включает панель мониторинга, один отчет и один набор данных. Как правило, *бизнес-пользователи* не получают наборы данных, но этот пример предназначен для всех пользователей, поэтому он содержит набор.

    ![Снимок экрана: экран приложений Power BI с приложением "Продажи и маркетинг — пример".](./media/end-user-experience/power-bi-new-sample.png)




    Большая часть совместно используемого содержимого не поддерживает прямой доступ к базовым наборам данных для *бизнес-пользователей* . Поскольку примеры для Power BI ориентированы на всех клиентов Power BI, они включают в себя необходимые наборы данных.   

    Дополнительные сведения о примерах см. в статье [Получить примеры для Power BI](../create-reports/sample-datasets.md).

## <a name="view-content-dashboards-and-reports"></a>Просмотр содержимого (панели мониторинга и отчеты)
Содержимое упорядочено в контексте рабочей области. Каждому бизнес-пользователю предоставляется как минимум одна рабочая область, которая называется **Моя рабочая область** . Когда *коллеги-конструктора* предоставят вам общий доступ к содержимому, вы сможете получить дополнительные рабочие области.  Например, если *конструктор* назначает вам разрешения на доступ к одной из рабочих областей, эта рабочая область будет отображаться на сайте Power BI.  

**Моя рабочая область** хранит все содержимое, которое вы создали и которое принадлежит вам. Это своего рода личная песочница или рабочая область для хранения личного содержимого. У многих *бизнес-пользователей* службы Power BI **Моя рабочая область** остается пустой, поскольку выполняемые ими задачи не предусматривают создание нового содержимого.  *Бизнес-пользователи* используют создаваемые другими данные для принятия бизнес-решений. Если вам предстоит самостоятельно создавать содержимое, мы рекомендуем ознакомиться со [статьями по службе Power BI для *конструкторов отчетов*](../index.yml).

И все же, рабочая область — это не просто список содержимого. На этой странице вы узнаете много полезного о панелях мониторинга и отчетах в рабочей области. Например, это может быть информация о владельце содержимого, дате его последнего обновления, конфиденциальных данных и подтверждениях. Выберите **More actions (...)** (Дополнительные действия (...)), чтобы отобразить список действий для панели мониторинга и отчета.   

Дополнительные сведения см. в статье [Совместная работа в рабочих областях](end-user-workspaces.md).

![Экран "Рабочая область приложения" с меню "Дополнительные действия" в разделе отчета](./media/end-user-experience/power-bi-more-actions.png)

Кроме того, рабочая область — это один из способов получить доступ к данным. В рабочей области можно открыть панель мониторинга или отчет, выбрав нужный элемент из списка.  Чтобы добавить панель мониторинга или отчет в избранное, наведите указатель мыши на нужный элемент и щелкните значок звездочки. Если *конструктор* предоставил вам [разрешения на общий доступ](end-user-shared-with-me.md), вы также можете поделиться содержимым из этой рабочей области. 

![Меню, открывающееся при наведении указателя мыши](./media/end-user-experience/power-bi-dashboard.png)

1. Выберите имя панели мониторинга, чтобы открыть ее. Наличие панелей мониторинга отличает службу Power BI от средства Power BI Desktop. [Ознакомьтесь со сведениями о панелях мониторинга](end-user-dashboards.md)

    ![Открытая панель мониторинга](./media/end-user-experience/power-bi-dashboard-open.png)

2. Действия, которые можно выполнить на панели мониторинга, отображаются в верхней строке меню.    

    ![Снимок экрана верхней части службы Power BI.](./media/end-user-experience/power-bi-top-menu.png)

3. Наведите указатель мыши на фрагмент панели мониторинга и щелкните **More options (...)** (Дополнительные параметры (...)), чтобы просмотреть параметры, необходимые для взаимодействия с этим фрагменту.

    ![Снимок экрана с раскрывающимся меню фрагмента панели мониторинга.](./media/end-user-experience/power-bi-tile-menu.png)

4. Выберите фрагмент панели мониторинга, чтобы открыть отчет, который использовался для создания этого фрагмента. Отчет откроется на странице, содержащей визуальный элемент, расположенный на фрагменте. Здесь выбрана Фрагмент панели мониторинга с диаграммой дерева. Служба Power BI открывает страницу отчета **YTD Category** .

    ![Открывается отчет.](./media/end-user-experience/power-bi-report.png)

    В отчетах есть несколько разделов. Слева находится список страниц отчета, доступных для щелчка. В верхней части находится строка меню, содержащая действия, которые можно выполнить с отчетом.  Доступные параметры будут зависеть от роли и разрешений, назначенных *конструктором отчетов* . Справа находится панель **Фильтры** . Центральный холст содержит сам отчет. Как и на панели мониторинга, здесь существуют действия, которые можно выполнить для всего отчета, для отдельных визуальных элементов, а также для одной страницы отчета. 

    См. дополнительные сведения об отчетах [Power BI](end-user-reports.md).

## <a name="using-the-left-navigation-pane"></a>Использование левой панели навигации
Панель навигации станет более эффективной, так как коллеги совместно используют содержимое. В этом разделе краткого руководства мы отложим пример *Продажи и маркетинга* и рассмотрим панель мониторинга и отчет, который используется *бизнес-пользователями* Power BI, работающими с большим объемом общего содержимого.

1. **Главная страница**  — это целевая страница по умолчанию при входе в службу Power BI. Главная страница — это отличная стартовая точка и альтернативный способ навигации по содержимому. Содержимое на главной странице организовано по избранным, последним, частым и популярным запросам. На этой странице также отображаются последние рабочие области и приложения. Просто выберите элемент, чтобы открыть его.

    На ней представлены все средства поиска и сортировки, область навигации и холст с *картами* , выбирая которые можно открывать панели мониторинга, отчеты и приложения. Поначалу на холсте главной страницы может быть не слишком много карт, но все изменится, когда вы начнете использовать Power BI совместно с коллегами. На вашем холсте главной страницы также будут обновляться сведения о рекомендованном содержимом и обучающих ресурсах.

   ![Снимок экрана главной страницы.](./media/end-user-experience/power-bi-full-home.png)

    Дополнительные сведения см. в статье [Поиск панелей мониторинга, отчетов и приложений](end-user-home.md).

2. На вкладках **Избранное** и **Недавние** есть стрелки. Щелкните стрелку, чтобы быстро просмотреть пять первых избранных или пять недавно открытых элементов. Во всплывающем элементе выберите содержимое, чтобы открыть его. 

   ![Всплывающий список с недавно открытым содержимым.](./media/end-user-experience/power-bi-recent.png)

    Чтобы просмотреть полный список избранных или недавно открытых элементов, выберите слово или значок. Эти списки содержимого содержат дополнительные сведения об отчетах, приложениях и панелях мониторинга.

    ![Список содержимого для избранных элементов.](./media/end-user-experience/power-bi-favorites.png)


    Дополнительные сведения см. в разделах [Недавнее содержимое в службе Power BI](end-user-recent.md) и [Избранное содержимое в службе Power BI](end-user-recent.md).

4. Выберите пункт **Приложения** , чтобы отобразить все приложения, к которым вам предоставили доступ или которые были установлены. Щелкните пункт **Мне предоставлен доступ** для просмотра панелей мониторинга и отчетов, к которым вам предоставлен доступ. Так как вы только начинаете работать со службой Power BI, эти области содержимого будут пустыми. 

    Дополнительные сведения см. в статьях [Приложения в Power BI](end-user-apps.md) и [Отображение панелей мониторинга и отчетов, к которым мне предоставлен доступ](end-user-shared-with-me.md).

### <a name="search-and-sort-content"></a>Поиск и сортировка содержимого
Если вы работаете со службой Power BI недавно, содержимого у вас может быть не так много. Однако по мере загрузки новых приложений и работы с предоставляемым вашими коллегами содержимым его объем может значительно увеличиваться. В таких случаях вам пригодятся функции поиска и сортировки.

Поиск можно выполнять практически из любого места службы Power BI. Для этого вам потребуется поле поиска или значок лупы.    
![значок лупы](./media/end-user-experience/power-bi-search-icon.png)

Начните вводить название панели мониторинга, отчета, книги, приложения или имя владельца в поле поиска. Поиск нужного содержимого в службе Power BI будет выполняться автоматически.

![Поиск отчета](./media/end-user-experience/power-bi-search-field.png)

Также предусмотрено множество способов сортировки содержимого. Если навести указатель мыши на заголовок столбца, могут появиться стрелки, указывающие на возможность его сортировки. Не все столбцы могут быть отсортированы. 

![Стрелка рядом с заголовком столбца "Тип"](./media/end-user-experience/power-bi-sort-icon.png)

Кроме того, вы можете воспользоваться фильтрами **поиска** , которые представлены в верхнем правом углу списка содержимого. Здесь можно выполнить быстрый поиск содержимого, выбрав тип содержимого, имя владельца или любое другое доступное поле.

![сортировка содержимого](./media/end-user-experience/power-bi-sort-date.png)


Дополнительные сведения см. в статье [Поиск и сортировка: навигация в Power BI](end-user-search-sort.md).

## <a name="find-the-owner"></a>Поиск имени владельца
Завершим работу с этим кратким руководством полезным советом. Если у вас есть вопросы о панели мониторинга, отчете или приложении, вы можете найти имя владельца. Открыв содержимое, щелкните раскрывающееся меню заголовка, чтобы отобразить имя владельца. Владельцем может быть пользователь или группа.

![Холст главной страницы](./media/end-user-experience/power-bi-owner.png)


## <a name="clean-up-resources"></a>Очистка ресурсов
Завершив работу с этим кратким руководством, вы можете при необходимости удалить примеры панели мониторинга, отчета и набора данных.

1. Откройте службу Power BI (app.powerbi.com) и войдите в нее.    
2. Откройте главную страницу Power BI, прокрутите вниз и выберите элемент **Моя рабочая область** .      

3. Наведите указатель мыши на панель мониторинга, отчет или набор данных и выберите **Дополнительные параметры (...)**  > **Удалить** . Повторите эти действия, чтобы удалить все необходимое.

    ![Удаление панели мониторинга](./media/end-user-experience/power-bi-cleanup.png)



## <a name="next-steps"></a>Дальнейшие действия

> [!div class="nextstepaction"]
> [Представление чтения в службе Power BI](end-user-reading-view.md)
