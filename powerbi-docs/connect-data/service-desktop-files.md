---
title: Получение данных из файлов Power BI Desktop
description: Узнайте, как перенести данные и отчеты из Power BI Desktop в Power BI
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 5368370cc25e12fdeab333b42a064ec4db66c301
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83347385"
---
# <a name="get-data-from-power-bi-desktop-files"></a>Получение данных из файлов Power BI Desktop
![](media/service-desktop-files/pbid_file_icon.png)

**Power BI Desktop** упрощает проведение бизнес-аналитики и формирование отчетности. Вне зависимости от поставленных задач (подключение к различным источникам данных, запрос и преобразование данных, моделирование данных и формирование эффективных и динамических отчетов) **Power BI Desktop** обеспечивает интуитивно понятное и быстрое выполнение задач в области бизнес-аналитики. Если вы еще не знакомы с **Power BI Desktop**, прочтите статью [Начало работы с Power BI Desktop](../fundamentals/desktop-getting-started.md).

После того как в **Power BI Desktop** внесены данные и сформированы отчеты, вы уже можете перенести сохраненный файл в **службу Power BI**.

## <a name="where-your-file-is-saved-makes-a-difference"></a>Важно, где сохранен файл
**Локально**. В случае сохранения файла на локальный диск на компьютере или в другом расположении в вашей организации вы можете *импортировать* файл или выполнить *публикацию* из Power BI Desktop, чтобы перенести его данные и отчеты в Power BI. На самом деле файл останется на локальном диске, поэтому файл не переносится в Power BI целиком. На самом деле создается новый набор данных в Power BI, и в него загружаются данные и модель данных из файла Power BI Desktop. Если файл содержит отчеты, они будут отображаться на сайте Power BI в области "Отчеты".

**OneDrive — бизнес**. Если вы используете хранилище OneDrive для бизнеса и для входа в него используете ту же учетную запись, что и для Power BI, вне всяких сомнений, это самый эффективный способ синхронизировать вашу работу в Power BI Desktop с набором данных, отчетами и информационными панелями в Power BI. Так как Power BI и OneDrive находятся в облаке, Power BI *подключается* к вашему файлу в OneDrive примерно раз в час. При обнаружении каких-либо изменений ваш набор данных, отчеты и информационные панели в Power BI автоматически обновляются.

**OneDrive — персональный**. Если вы сохраняете файлы в свою учетную запись OneDrive, то получите многие преимущества, доступные для OneDrive для бизнеса. Главное отличие — при первом подключении к файлу (щелкнув "Получить данные" > "Файлы" > "OneDrive — персональный") необходимо войти в OneDrive с учетной записью Майкрософт, которая обычно отличается от учетной записи, используемой для входа в Power BI. При входе в OneDrive с учетной записью Майкрософт убедитесь, что установлен флажок "Оставаться в системе". Тогда Power BI сможет примерно раз в час подключаться к вашему файлу и синхронизировать его с набором данных в Power BI.

**Сайты рабочих групп SharePoint**. Сохранение файлов Power BI Desktop на сайтах рабочих групп SharePoint очень похоже на сохранение файлов в OneDrive для бизнеса. Главное отличие состоит в подключении к файлу из Power BI. Можно указать URL-адрес или подключаться к корневой папке.

## <a name="import-or-connect-to-a-power-bi-desktop-file-from-power-bi"></a>Импорт или подключение к файлу Power BI Desktop из Power BI
>[!IMPORTANT]
>Максимальный размер файла, импортируемого в Power BI, составляет 1 ГБ.

1. В Power BI на панели навигации щелкните **Получить данные**.
   
   ![](media/service-desktop-files/pbid_get_data_button.png)
2. В разделе **Файлы** щелкните **Получить**.
   
   ![](media/service-desktop-files/pbid_files_get.png)
3. Найдите свой файл. Файлы Power BI Desktop имеют расширение PBIX.
   
   ![](media/service-desktop-files/pbid_find_your_file.png)

## <a name="publish-a-file-from-power-bi-desktop-to-your-power-bi-site"></a>Публикация файла из Power BI Desktop на сайт Power BI
Функция публикации из Power BI Desktop фактически аналогична получению данных в Power BI и позволяет импортировать файла с локального диска или подключиться к нему в OneDrive.  Это краткое описание, но вы можно получить дополнительные сведения в разделе [Публикация из Power BI Desktop](../create-reports/desktop-upload-desktop-files.md).

1. В Power BI Desktop последовательно выберите **Файл** > **Опубликовать** > **Опубликовать в Power BI** или щелкните **Опубликовать** на ленте.
   
   ![](media/service-desktop-files/pbid_publish.png)
2. Войдите в Power BI. Это необходимо будет сделать только при первом входе.
   
   По завершении вы получите ссылку, с помощью которой сможете открыть отчет на сайте Power BI.
   
   ![](media/service-desktop-files/pbid_publishing.png)

## <a name="next-steps"></a>Дальнейшие действия
**Изучите данные**. После передачи данных и отчетов из файла в Power BI пришло время для их изучения. Если файл уже содержит отчеты, они отображаются на панели навигации в разделе **Отчеты**. Если файл содержит только данные, вы можете создавать новые отчеты. Просто щелкните правой кнопкой мыши новый набор данных и выберите команду **Просмотреть**.

**Обновите внешние источники данных**. Если файл Power BI Desktop подключается к внешним источникам данных, можно установить расписание обновлений, чтобы гарантировать актуальность набора данных. В большинстве случаев настроить расписание обновлений довольно просто, но подробное описание этой функции выходит за рамки данной статьи. Дополнительные сведения см. в разделе [Обновление данных в Power BI](refresh-data.md).