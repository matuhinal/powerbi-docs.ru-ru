---
title: Публикация отчета с разбивкой на страницы в службе Power BI
description: Из этого руководства вы узнаете, как опубликовать отчет с разбивкой на страницы в службе Power BI, передав его с локального компьютера.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 05/04/2020
ms.openlocfilehash: 39609d0bf3681de2b01f433143556ac102ee0662
ms.sourcegitcommit: a72567f26c1653c25f7730fab6210cd011343707
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83565490"
---
# <a name="publish-a-paginated-report-to-the-power-bi-service"></a>Публикация отчета с разбивкой на страницы в службе Power BI

Из этой статьи вы узнаете, как опубликовать отчет с разбивкой на страницы в службе Power BI, передав его с локального компьютера. Отчеты с разбивкой на страницы можно передавать в личную рабочую область или в любую другую рабочую область, размещенную в емкости Premium. Найдите значок в виде бриллианта ![Значок емкости Power BI Premium в виде бриллианта](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) рядом с именем рабочей области. 

Если источник данных отчета находится на локальном компьютере, после отправки отчета необходимо создать шлюз. См. раздел [Создание шлюза](#create-a-gateway) далее в этой статье.

## <a name="add-a-workspace-to-a-premium-capacity"></a>Добавление рабочей области в емкость Premium

Если рабочая область не имеет значка с бриллиантом ![Значок емкости Power BI Premium в виде бриллианта](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) рядом с именем, ее следует добавить в емкость Premium. 

1. Выберите **Рабочие области**, щелкните многоточие ( **...** ) рядом с именем рабочей области и выберите **Изменить рабочую область**.

    ![Выбор действия "Изменить рабочую область"](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace.png)

1. В диалоговом окне **Изменение рабочей области** разверните узел **Дополнительно**, затем переместите ползунок **Dedicated capacity** (Выделенная емкость) в положение **Вкл.**

    ![Выбор выделенной емкости](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace-dialog.png)

   Возможно, вы не сможете внести такое изменение. В этом случае обратитесь к администратору емкости Power BI Premium, чтобы он предоставил вам права назначения для добавления рабочей области в емкость Premium.

## <a name="from-report-builder-publish-a-paginated-report"></a>В построителе отчетов опубликуйте отчет с разбивкой на страницы

1. Создайте отчет с разбивкой на страницы в построителе отчетов и сохраните этот отчет на локальный компьютер.

1. В построителе отчетов в меню **Файл** выберите **Сохранить как**.

    ![Меню "Файл" > "Сохранить" > "Сохранить как"](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-save-as.png)

    Если вы еще не вошли в Power BI, войдите в систему или создайте учетную запись. В правом верхнем углу построителя отчетов выберите **Вход** и выполните требуемые действия.

2. В списке рабочих областей слева выберите рабочую область со значком ромба ![значок ромба Power BI Premium](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) рядом с именем. Заполните поле **Имя файла** и нажмите **Сохранить**. 

    ![Выбор рабочей области Premium](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-workspace.png)

4. Откройте службу Power BI в браузере и перейдите к рабочей области Premium, где требуется опубликовать отчет с разбивкой на страницы. Отчет будет представлен на вкладке **Отчеты**.

    ![Отчет с разбивкой на страницы в списке отчетов](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

5. Выберите отчет с разбивкой на страницы, чтобы открыть его в службе Power BI. Если отчет имеет параметры, выберите их, чтобы перейти к просмотру отчета.

    ![Выбор параметров](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

6. Если источник данных для отчета находится на локальном компьютере, узнайте из этой статьи о том, как [создать шлюз](#create-a-gateway) для доступа к источнику данных.

## <a name="from-the-power-bi-service-upload-a-paginated-report"></a>Отправка отчета с разбивкой на страницы в службе Power BI

Можно также перейти в службу Power BI и отправить отчет с разбивкой на страницы.

1. Создайте отчет с разбивкой на страницы в построителе отчетов и сохраните этот отчет на локальный компьютер.

1. Откройте службу Power BI в браузере и перейдите к рабочей области Premium, где вы намерены опубликовать отчет. Теперь здесь есть значок бриллианта ![Значок емкости Power BI Premium в виде бриллианта](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) рядом с именем рабочей области. 

1. Выберите **Получить данные**.

    ![Элемент "Получить данные" в Power BI](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-get-data.png)

1. В поле **Файлы** выберите **Получить**.

    ![Элемент "Получить файлы" в Power BI](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-files-get.png)

1. Выберите **Локальный файл**, перейдите к отчету с разбивкой на страницы и щелкните **Открыть**.

    ![Выбор элемента "Локальный файл"](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-local-file.png)

1. Щелкните **Продолжить** > **Изменить учетные данные**.

    ![Выбор элемента "Изменить учетные данные"](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-edit-credentials.png)

1. Введите учетные данные и щелкните **Вход**.

    ![Изменить учетные данные](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-credentials.png)

   Отчет будет представлен на вкладке **Отчеты**.

    ![Отчет с разбивкой на страницы в списке отчетов](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

1. Выберите отчет, чтобы открыть его в службе Power BI. Если отчет имеет параметры, выберите их, чтобы перейти к просмотру отчета.
 
    ![Выбор параметров](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

6. Если источник данных для отчета находится на локальном компьютере, узнайте из этой статьи о том, как [создать шлюз](#create-a-gateway) для доступа к источнику данных.

## <a name="create-a-gateway"></a>Создание шлюза

Как и с любым другим отчете Power BI, если источник данных размещен на локальном компьютере, для доступа к этим данным следует создать или выбрать существующий шлюз.

1. Щелкните **Управление** рядом с именем отчета.

   ![Управление отчетом с разбивкой на страницы](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-manage.png)

1. Подробное описание процесса и дальнейшие действия см. в статье [Что такое локальный шлюз данных](../connect-data/service-gateway-onprem.md).



## <a name="next-steps"></a>Дальнейшие действия

- [Просмотр отчета с разбивкой на страницы в службе Power BI](../consumer/paginated-reports-view-power-bi-service.md)
- [Сведения об отчетах с разбивкой на страницы в Power BI Premium](paginated-reports-report-builder-power-bi.md)
- [Руководство. Внедрение отчетов Power BI с разбивкой на страницы в приложение для клиентов](../developer/embedded/embed-paginated-reports-customers.md)
