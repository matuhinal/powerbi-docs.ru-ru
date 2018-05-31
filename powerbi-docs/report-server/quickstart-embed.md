---
title: Внедрение отчета с использованием iFrame
description: Внедрение отчета решения "Сервер отчетов Power BI" в iFrame сервера SharePoint Server
services: powerbi
author: markingmyname
ms.author: maghan
ms.date: 05/04/2018
ms.topic: quickstart
ms.service: powerbi
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 0639ea11fd09bd7cfe81328e8bee6112d61937aa
ms.sourcegitcommit: c29525cbac2e747edb4dd3a1841084bb0ce42582
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33867538"
---
# <a name="quickstart-embed-a-power-bi-report-server-report-using-an-iframe-in-sharepoint-server"></a>Краткое руководство по внедрению отчета решения "Сервер отчетов Power BI" с помощью iFrame в SharePoint Server

Из этого краткого руководства вы узнаете, как внедрить отчет решения "Сервер отчетов Power BI" с помощью iFrame на страницу SharePoint. Если вы используете SharePoint Online, решение "Сервер отчетов Power BI" должно быть общедоступным. В SharePoint Online веб-часть Power BI, которая работает со службой Power BI, не совместима с решением "Сервер отчетов Power BI". 

![Пример iFrame](media/quickstart-embed/quickstart_embed_01.png)
## <a name="prerequisites"></a>Предварительные требования
* Требуется установленное и настроенное решение [Сервер отчетов Power BI](https://powerbi.microsoft.com/en-us/report-server/).
* Должен быть установлено [приложение Power BI Desktop, оптимизированное для решения "Сервер отчетов Power BI"](install-powerbi-desktop.md).
* Требуется установленная и настроенная среда [SharePoint](https://docs.microsoft.com/en-us/sharepoint/install/install).

## <a name="creating-the-power-bi-report-server-report-url"></a>Создание URL-адреса для отчета решения "Сервер отчетов Power BI"

1. Скачайте из GitHub пример [Демонстрационный блог](https://github.com/Microsoft/powerbi-desktop-samples).

    ![Скачивание примера PBIX-файла](media/quickstart-embed/quickstart_embed_14.png)

2. Отройте пример PBIX-файла, размещенный на GitHub в разделе **приложения Power BI Desktop, оптимизированного для решения "Сервер отчетов Power BI"**.

    ![Средство сервера отчетов для Power BI Desktop](media/quickstart-embed/quickstart_embed_02.png)

3. Сохраните отчет в решении **Сервер отчетов Power BI**. 

    ![Сохранение в решении "Сервер отчетов Power BI"](media/quickstart-embed/quickstart_embed_03.png)

4. Просмотрите отчет на **веб-портале**.

    ![Веб-портал](media/quickstart-embed/quickstart_embed_04.png)

### <a name="capturing-the-url-parameter"></a>Запись параметра URL-адреса

Получив URL-адрес, вы можете создать iFrame для размещения отчета на веб-странице SharePoint. Вы можете добавить параметр строки запроса `?rs:embed=true` к любому URL-адресу отчета решения "Сервер отчетов Power BI", чтобы внедрить этот отчет в iFrame. 

   Например:
    ``` 
    http://myserver/reports/powerbi/Sales?rs:embed=true
    ```
## <a name="embedding-a-power-bi-report-server-report-in-a-sharepoint-iframe"></a>Внедрение отчета решения "Сервер отчетов Power BI" в SharePoint iFrame

1. Перейдите к странице **Содержимое сайта** в SharePoint.

    ![Страница "Содержимое сайта"](media/quickstart-embed/quickstart_embed_05.png)

2. Выберите страницу, на которую нужно добавить отчет.

    ![Приложение страницы "Содержимое сайта"](media/quickstart-embed/quickstart_embed_06.png)

3. Щелкните значок шестеренки в верхней правой части страницы и выберите **Изменить страницу**.

    ![Действие "Изменить страницу"](media/quickstart-embed/quickstart_embed_07.png)

4. Выберите **Добавить веб-часть**.

    ![Добавление веб-части](media/quickstart-embed/quickstart_embed_08.png)

5. В разделе **Категории** выберите **Среда и контент**, затем в разделе **Части** выберите **Редактор содержимого** и щелкните **Добавить**.

    ![Выбор веб-части редактора содержимого](media/quickstart-embed/quickstart_embed_09.png) и ![нажатие кнопки "Добавить"](media/quickstart-embed/quickstart_embed_091.png)

6. Выберите **Click here to add new content** (Щелкните здесь, чтобы добавить новое содержимое).

    ![Добавление содержимого](media/quickstart-embed/quickstart_embed_10.png)

7. На ленте выберите вкладку **Форматирование текста**, а затем щелкните **Изменить источник**.

     ![Изменение источника](media/quickstart-embed/quickstart_embed_11.png)

8. В окне изменения источника вставьте код для iFrame и нажмите кнопку "ОК".

    ![Код iFrame](media/quickstart-embed/quickstart_embed_12.png)

     Например:
     ```
     <iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
     ```

9. На ленте выберите вкладку **Страница**, затем щелкните **Остановить изменение**.

    ![Кнопка "Остановить изменение"](media/quickstart-embed/quickstart_embed_13.png)

10. Теперь вы увидите отчет на странице.

    ![Пример iFrame](media/quickstart-embed/quickstart_embed_01.png)

## <a name="next-steps"></a>Дальнейшие действия

[Краткое руководство по созданию отчета Power BI для сервера отчетов Power BI](quickstart-create-powerbi-report.md)  
[Краткое руководство по созданию отчета c разбивкой на страницы Power BI для сервера отчетов Power BI](quickstart-create-paginated-report.md)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/) 