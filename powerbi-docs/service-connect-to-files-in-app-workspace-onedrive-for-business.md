---
title: Подключение к файлам в OneDrive для рабочей области приложения Power BI
description: Узнайте о хранении файлов Excel, CSV и Power BI Desktop в хранилище OneDrive для рабочей области приложения Power BI, а также о подключении к ним.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukasz
ms.service: powerbi
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 52b7748b6b634caf87de01ddc965576339a04b8b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "61175070"
---
# <a name="connect-to-files-stored-in-onedrive-for-your-power-bi-app-workspace"></a>Подключение к файлам, хранящимся в OneDrive, для рабочей области приложения Power BI
После [создания рабочей области приложения в Power BI](service-create-distribute-apps.md) вы можете хранить свои файлы Excel, CSV и Power BI Desktop в хранилище OneDrive для бизнеса для своей рабочей области приложения Power BI. Вы можете продолжить обновление файлов, хранящихся в OneDrive. Эти обновления автоматически отражаются в отчетах Power BI и панели мониторинга на основе файлов. 

> [!NOTE]
> Новые возможности рабочей области изменяется связь между рабочих областей Power BI и групп Office 365. Каждый раз при создании одной из новых рабочих областей нельзя автоматически создавать группу Office 365. Узнайте о [создание новых рабочих областей](service-create-the-new-workspaces.md)

Добавление файлов в рабочую область приложения состоит из двух этапов. 

1. Сначала вам необходимо [отправить файлы в хранилище OneDrive для бизнеса](service-connect-to-files-in-app-workspace-onedrive-for-business.md#1-upload-files-to-the-onedrive-for-business-for-your-app-workspace) для рабочей области приложения.
2. Затем вы [подключитесь к этим файлам из Power BI](service-connect-to-files-in-app-workspace-onedrive-for-business.md#2-import-excel-files-as-datasets-or-as-excel-online-workbooks).

> [!NOTE]
> Рабочие области приложений доступны только в [Power BI Pro](service-features-license-type.md).
> 

## <a name="1-upload-files-to-the-onedrive-for-business-for-your-app-workspace"></a>1. Отправка файлов в хранилище OneDrive для бизнеса для рабочей области приложения
1. В службе Power BI щелкните стрелку рядом с элементом "Рабочие области" и выберите кнопку с многоточием ( **…** ) рядом с именем рабочей области. 
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-ellipsis.png)
2. Выберите **Файлы**, чтобы открыть OneDrive для бизнеса для рабочей области приложения в Office 365.
   
   > [!NOTE]
   > Если в меню рабочей области приложения не отображается параметр **Файлы**, выберите **участников**, чтобы открыть хранилище OneDrive для бизнеса для рабочей области приложения. Затем выберите **Файлы**. Office 365 задает расположение хранилища OneDrive для файлов рабочей области группы приложения. Этот процесс может занять некоторое время. 
   > 
   > 
3. Теперь вы можете передать файлы в хранилище OneDrive для бизнеса для рабочей области приложения. Выберите команду **Отправить**и перейдите к своим файлам.
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grpfilesonedrive.png)

## <a name="2-import-excel-files-as-datasets-or-as-excel-online-workbooks"></a>2. Импорт файлов Excel в качестве наборов данных или книг Excel Online
Теперь, когда файлы находятся в хранилище OneDrive для бизнеса для рабочей области приложения, есть два варианта действий. Вы можете выбрать один из следующих вариантов. 

* [Импортировать данные из книги Excel в виде набора данных](service-get-data-from-files.md). Затем данные можно используйте для создания отчетов и панелей мониторинга, которые можно просмотреть в браузере и на мобильных устройствах.
* [Подключиться к целой книге Excel в Power BI](service-excel-workbook-files.md) и отобразить ее так же, как в Excel Online.

### <a name="import-or-connect-to-the-files-in-your-app-workspace"></a>Импорт файлов в рабочей области приложения или подключение к ним
1. В Power BI перейдите в рабочую область приложения, чтобы ее имя отобразилось в левом верхнем углу. 
2. Нажмите кнопку **Получить данные** в нижней части левой панели навигации. 
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-get-data-button.png)
3. В поле **Файлы** выберите **Получить**.
   
   ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_getfiles.png)
4. Выберите **OneDrive** - *имя вашей рабочей области приложения*.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grp_one_drive_shrpt.png)
5. Щелкните нужный файл, затем — **Подключиться**.
   
    На этом этапе можно решить, следует ли [импортировать данные из книги Excel](service-get-data-from-files.md), или [подключение к целым книгам Excel](service-excel-workbook-files.md).
6. Выберите команду **Импортировать** или **Подключиться**.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_importexceldataorwholecrop.png)
7. Если выбрать **Импортировать**, книга отобразится на вкладке **Наборы данных**. 
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-import.png)
   
    Если выбрать **Подключиться**, книга отобразится на вкладке **Книги**.
   
    ![](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-connect.png)

## <a name="next-steps"></a>Дальнейшие действия
* [Создание и распространение приложения в Power BI](service-create-distribute-apps.md)
* [Импорт данных из книг Excel](service-get-data-from-files.md)
* [Подключение к целым книгам Excel](service-excel-workbook-files.md)
* Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)
* Хотите оставить отзыв? Посетите [форум идей по улучшению Power BI](https://ideas.powerbi.com/forums/265200-power-bi).

