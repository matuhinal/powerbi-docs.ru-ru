---
title: Внедрение нового приложения Power App в отчет Power BI
description: Сведения о внедрении приложения, которое использует тот же источник данных и может фильтроваться так же, как другие элементы отчета
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 02/03/2020
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 99869740eb20b14625e66ff50cb48b08e5cb3e15
ms.sourcegitcommit: 75300b3f53f438ed7d3bd4edc93b9eb5925bf3af
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036683"
---
# <a name="tutorial-embed-a-power-apps-visual-in-a-power-bi-report"></a>Руководство. Внедрение визуального элемента Power Apps в отчет Power BI

В этом учебнике вы используете визуальный элемент Power Apps для создания приложения, внедряемого в пример отчета Power BI. Это приложение взаимодействует с другими визуальными элементами отчета.

Если у вас нет подписки на Power Apps, перед началом работы [создайте бесплатную учетную запись](https://web.powerapps.com/signup?redirect=marketing&email=).

Из этого руководства вы узнаете, как выполнять следующие задачи:
> [!div class="checklist"]
> * Добавление визуального элемента Power Apps в отчет Power BI
> * Взаимодействие с Power Apps для создания нового приложения, использующего данные из отчета Power BI
> * Просмотр визуального элемента Power Apps и работа с ним в отчете

## <a name="prerequisites"></a>Предварительные требования

* Браузер [Google Chrome](https://www.google.com/chrome/browser/) или [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge)
* [Подписка на Power BI](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi) с установленным [примером "Анализ возможностей"](https://docs.microsoft.com/power-bi/sample-opportunity-analysis#get-the-content-pack-for-this-sample)
* Умение [создавать приложения в Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/data-platform-create-app-scratch) и [изменять отчеты Power BI](https://docs.microsoft.com/power-bi/service-the-report-editor-take-a-tour)



## <a name="create-a-new-app"></a>Создание приложения
При добавлении визуального элемента Power Apps в отчет выполняется запуск Power Apps Studio с активным подключением данных между Power Apps и Power BI.

1. Откройте отчет "Анализ возможностей — пример" и выберите вкладку *Upcoming Opportunities* (Предстоящие возможные сделки). 


2. Переместите и измените размеры некоторых плиток в отчете, чтобы освободить место для нового визуального элемента.

    ![Перемещение и изменение размеров плиток в отчете](media/power-bi-visualization-powerapp/power-bi-report-page.jpg)

2. Щелкните значок Power Apps в области "Визуализации", после чего измените размер визуального элемента в соответствии с заданной областью.

    ![Область "Визуализации" с выбранным значком Power Apps](media/power-bi-visualization-powerapp/power-bi-powerapps-icon.jpg)

3. В области **Поля** выберите **Name** (Название), **Product Code** (Код продукта) и **Sales Stage** (Этап продаж). 

    ![Выбор полей](media/power-bi-visualization-powerapp/power-bi-fields.jpg)

4. На визуальном элементе Power Apps выберите среду Power Apps, в которой нужно создать приложение, а затем нажмите **Создать**.

    ![Создание приложения](media/power-bi-visualization-powerapp/power-bi-create-new-powerapp.png)

    В Power Apps Studio вы увидите созданное базовое приложение с *коллекцией*, в которой отображается одно из полей, выбранных в Power BI.

    ![Открытие Power Apps](media/power-bi-visualization-powerapp/power-bi-power-app.png)

5.  Измените размер коллекции так, чтобы она занимала только половину экрана. 

6. В левой области выберите элемент **Screen1**, а затем задайте для свойства **Fill** окна значение LightBlue (чтобы окно было лучше видно в отчете).

    ![цветовая палитра](media/power-bi-visualization-powerapp/power-bi-powerapps-fill.png)

6. Освободите место для элемента управления "метка". 

    ![изменение размеров коллекции](media/power-bi-visualization-powerapp/power-bi-powerapps-gallery.png)


8. Вставьте элемент управления "текстовая подпись" в разделе **Коллекция**.

   ![элемент управления "Метка"](media/power-bi-visualization-powerapp/power-bi-label.png)

7. Перетащите метку в нижнюю часть визуального элемента. Для свойства **Текст** задайте значение `"Opportunity Count: " & CountRows(Gallery1.AllItems)`. Теперь отображается общее число возможных сделок в наборе данных.

    ![Приложение с измененным размером коллекции](media/power-bi-visualization-powerapp/power-bi-power-app-label.png)

    ![Приложение с обновленной меткой](media/power-bi-visualization-powerapp/power-bi-label-live.png)

7. Сохраните приложение с именем "Приложения возможных сделок". 

    ![Сохранение приложения](media/power-bi-visualization-powerapp/power-bi-save-powerapp.png)


## <a name="view-the-app-in-the-report"></a>Просмотр приложения в отчете
Теперь приложение доступно в отчете Power BI. Оно взаимодействует с другими визуальными элементами, так как у них общий источник данных.

![Приложение в отчете Power BI](media/power-bi-visualization-powerapp/power-bi-powerapps-visual.png)

В отчете Power BI выберите на срезе пункт **Jan** (Янв). В результате будет отфильтрован весь отчет, включая данные в приложении.

![Отфильтрованный отчет](media/power-bi-visualization-powerapp/power-bi-last.png)

Обратите внимание на то, что число возможных сделок в приложении совпадает с числом в левом верхнем углу отчета. Вы можете выбирать другие элементы в отчете, и данные в приложении будут обновляться.


## <a name="clean-up-resources"></a>Очистка ресурсов
Если пример "Анализ возможностей" больше не нужен, можно удалить панель мониторинга, отчет и набор данных.


## <a name="next-steps"></a>Дальнейшие действия
["Вопросы и ответы": визуализация](power-bi-visualization-types-for-reports-and-q-and-a.md)