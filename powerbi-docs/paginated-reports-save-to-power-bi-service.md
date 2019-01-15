---
title: Публикация отчета с разбивкой на страницы в службе Power BI (предварительная версия)
description: Из этого руководства вы узнаете, как опубликовать отчет с разбивкой на страницы в службе Power BI, передав его с локального компьютера.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 11/05/2018
ms.author: maggies
ms.openlocfilehash: 76ec5c140fc90dcf71a76bc6ca13a860e3474c37
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280956"
---
# <a name="publish-a-paginated-report-to-the-power-bi-service-preview"></a>Публикация отчета с разбивкой на страницы в службе Power BI (предварительная версия)

Из этой статьи вы узнаете, как опубликовать отчет с разбивкой на страницы в службе Power BI, передав его с локального компьютера. Отчеты с разбивкой на страницы можно передавать в личную рабочую область или в любую другую рабочую область, размещенную в емкости Premium. Найдите значок в виде бриллианта ![Значок емкости Power BI Premium в виде бриллианта](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) рядом с именем рабочей области. 

Если источник данных отчета находится на локальном компьютере, после отправки отчета необходимо [создать шлюз](#create-a-gateway-to-an-on-premises-data-source).

## <a name="add-a-workspace-to-a-premium-capacity"></a>Добавление рабочей области в емкость Premium

Если рабочая область не имеет значка с бриллиантом ![Значок емкости Power BI Premium в виде бриллианта](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) рядом с именем, ее следует добавить в емкость Premium. 

1. Выберите **Рабочие области**, щелкните многоточие (**...**) рядом с именем рабочей области и выберите **Изменить рабочую область**.

    ![Выбор действия "Изменить рабочую область"](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace.png)

1. В диалоговом окне **Изменение рабочей области** разверните узел **Дополнительно**, затем переместите ползунок **Dedicated capacity** (Выделенная емкость) в положение **Вкл.**

    ![Выбор выделенной емкости](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace-dialog.png)

   Возможно, вы не сможете внести такое изменение. В этом случае обратитесь к администратору емкости Power BI Premium, чтобы он предоставил вам права назначения для добавления рабочей области в емкость Premium.


## <a name="upload-a-paginated-report"></a>Отправка отчета с разбивкой на страницы

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

   Вы увидите новый отчет в списке отчетов.

    ![Отчет с разбивкой на страницы в списке отчетов](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

1. Выберите отчет, чтобы открыть его в службе Power BI. Если отчет имеет параметры, выберите их, чтобы перейти к просмотру отчета.
 
    ![Выбор параметров](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

## <a name="create-a-gateway"></a>Создание шлюза

Как и с любым другим отчете Power BI, если источник данных размещен на локальном компьютере, для доступа к этим данным следует создать или выбрать существующий шлюз.

1. Щелкните **Управление** рядом с именем отчета.

   ![Управление отчетом с разбивкой на страницы](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-manage.png)

1. Подробное описание процесса и дальнейшие действия вы найдете в статье [об установке шлюза](service-gateway-install.md).

### <a name="gateway-limitations"></a>Ограничения шлюза

Сейчас шлюзы не поддерживают многозначные параметры.


## <a name="next-steps"></a>Дальнейшие действия

- [Просмотр отчета с разбивкой на страницы в службе Power BI](paginated-reports-view-power-bi-service.md)
- [Сведения об отчетах с разбивкой на страницы в Power BI Premium (предварительная версия)](paginated-reports-report-builder-power-bi.md)

