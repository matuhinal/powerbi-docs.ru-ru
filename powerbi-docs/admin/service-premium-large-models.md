---
title: Большие модели в Power BI Premium (Предварительная версия)
description: Функция больших моделей позволяет размерам наборов данных в Power BI Premium превышать 10 ГБ.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 03/03/2020
LocalizationGroup: Premium
ms.openlocfilehash: 93d24ca00ee33733a461bb553dd7e344a1a8b6f8
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83274335"
---
# <a name="large-models-in-power-bi-premium-preview"></a>Большие модели в Power BI Premium (Предварительная версия)

Наборы данных Power BI могут хранить данные в кэше в памяти с высоким уровнем сжатия для оптимизации производительности запросов, что позволяет поддерживать быстрое взаимодействие с пользователем даже при больших наборах данных. Функция больших моделей позволяет размерам наборов данных в Power BI Premium превышать 10 ГБ. Но зато размер набора данных ограничивается размером емкости Power BI Premium, что похоже на ограничения размера модели в Azure Analysis Services. Дополнительные сведения о размерах емкости в Power BI Premium см. в разделе "Узлы емкости". Вы можете настроить большие модели для всех номеров SKU P Premium и Внедренных номеров SKU A, однако они работают только с [новых рабочих областей](../collaborate-share/service-create-the-new-workspaces.md).

Большие модели не влияют на размер передачи PBIX, который по-прежнему ограничен 10 ГБ. Вместо этого при обновлении службы наборы данных выходят за пределы 10 ГБ. Чтобы настроить набор данных, превышающий 10 ГБ, можно использовать добавочное обновление.

## <a name="enable-large-models"></a>Включение больших моделей

Чтобы создать набор данных, превышающий 10 ГБ, выполните следующие действия.

1. Создайте набор данных в Power BI Desktop и настройте [добавочное обновление](service-premium-incremental-refresh.md).

1. Опубликуйте набор данных в службе Power BI Premium.

1. Включите набор данных для больших моделей, выполнив приведенные ниже командлеты PowerShell. Эти командлеты приводят к тому, что Power BI хранит набор данных в файлах Azure Premium, а ограничение в 10 ГБ не применяется.

1. Вызов обновления для загрузки исторических данных на основе политики добавочного обновления. Для загрузки журнала первому обновлению может понадобится некоторое время. Последующие обновления должны выполняться быстрее, так как они являются добавочными.

### <a name="powershell-cmdlets"></a>Командлеты PowerShell

Включите набор данных для хранилища файлов класса Premium с помощью командлетов PowerShell в текущей версии больших моделей. Для запуска командлетов PowerShell требуются права администратора емкости и администратора рабочей области.

1. Найдите идентификатор набора данных (GUID). Идентификатор можно увидеть в URL-адресе, на вкладке **Наборы данных** для рабочей области в разделе параметров набора данных.

    ![GUID набора данных](media/service-premium-large-models/dataset-guid.png)

1. В командной строке администратора PowerShell установите модуль [MicrosoftPowerBIMgmt](/powershell/module/microsoftpowerbimgmt.data/).

    ```powershell
    Install-Module -Name MicrosoftPowerBIMgmt
    ```

1. Выполните следующие командлеты, чтобы войти и проверить режим хранения набора данных.

    ```powershell
    Login-PowerBIServiceAccount

    (Get-PowerBIDataset -Scope Organization -Id <Dataset ID> -Include actualStorage).ActualStorage
    ```

    Ответ должен выглядеть следующим образом. Режим хранения — ABF (файл резервной копии Analysis Services), который используется по умолчанию.

    ```
    Id                   StorageMode

    --                   -----------

    <Dataset ID>         Abf
    ```

1. Выполните следующие командлеты, чтобы настроить режим хранения для файлов Premium и проверить его. Преобразование в файлы Premium может занять несколько секунд.

    ```powershell
    Set-PowerBIDataset -Id <Dataset ID> -TargetStorageMode PremiumFiles

    (Get-PowerBIDataset -Scope Organization -Id <Dataset ID> -Include actualStorage).ActualStorage
    ```

    Ответ должен выглядеть следующим образом. Теперь для режима хранения заданы файлы Premium.

    ```
    Id                   StorageMode
    
    --                   -----------
    
    <Dataset ID>         PremiumFiles
    ```

Состояние преобразований наборов данных в файлы Premium и из них можно проверить с помощью командлета [Get-PowerBIWorkspaceMigrationStatus](/powershell/module/microsoftpowerbimgmt.workspaces/get-powerbiworkspacemigrationstatus).

## <a name="dataset-eviction"></a>Исключение наборов данных

Power BI использует управление динамической памятью для исключения неактивных наборов данных из памяти. Power BI исключает наборы данных, чтобы они могли загружать другие наборы данных для устранения запросов пользователей. Управление динамической памятью позволяет значительно увеличить сумму размеров набора данных по сравнению с объемом доступной памяти, но один набор данных должен помещаться в памяти. Дополнительные сведения об управлении динамической памятью см. в разделе [Принцип функционирования емкостей](service-premium-what-is.md#how-capacities-function).

Следует учитывать влияние вытеснений на большие модели. Несмотря на относительно быстрое время загрузки набора данных, для пользователей может быть заметной задержка, если они ожидают повторной загрузки больших наборов данных. По этой причине в текущей форме функция больших моделей рекомендуется в первую очередь для производственных мощностей, выделенных для корпоративных требований бизнес-аналитики, а не в сочетании с требованиями самостоятельной бизнес-аналитики. Менее вероятно, что емкость, выделенная для корпоративных требований бизнес-аналитики, будет часто вызывать выгрузку и требовать перезагрузки наборов данных. С другой стороны, емкости для самостоятельной бизнес-аналитики могут иметь небольшие наборы данных, которые чаще всего загружаются в память и выгружаются из нее.

## <a name="checking-dataset-size"></a>Проверка размера набора данных

После загрузки исторических данных вы можете использовать [SSMS](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) с помощью [конечной точки XML для аналитики](service-premium-connect-tools.md), чтобы проверить оценочный размер набора данных в окне "Свойства модели".

![Примерный размер набора данных](media/service-premium-large-models/estimated-dataset-size.png)

Вы также можете проверить размер набора данных, выполнив следующие запросы динамического административного представления из SSMS. Суммируйте столбцы DICTIONARY\_SIZE и USED\_SIZE на выходе, чтобы увидеть размер набора данных в байтах.

```sql
SELECT * FROM SYSTEMRESTRICTSCHEMA
($System.DISCOVER_STORAGE_TABLE_COLUMNS,
 [DATABASE_NAME] = '<Dataset Name>') //Sum DICTIONARY_SIZE (bytes)

SELECT * FROM SYSTEMRESTRICTSCHEMA
($System.DISCOVER_STORAGE_TABLE_COLUMN_SEGMENTS,
 [DATABASE_NAME] = '<Dataset Name>') //Sum USED_SIZE (bytes)
```

## <a name="limitations-and-considerations"></a>Рекомендации и ограничения

При использовании больших моделей учитывайте следующие ограничения.

- **Перенос собственного ключа шифрования BYOK.** Наборы данных, включенные для файлов уровня "Премиум", не шифруются [BYOK](service-encryption-byok.md).
- **Поддержка нескольких регионов.** Для наборов данных, включенных для файлов уровня "Премиум", не будет работать емкость, в которой также включен пункт [несколько регионов](service-admin-premium-multi-geo.md).

- **Скачивание Power BI Desktop.** Если набор данных хранится в файлах уровня "Премиум", [скачивание в виде PBIX-файла](../create-reports/service-export-to-pbix.md) завершится сбоем.
- **Поддерживаемые регионы**: Большие модели поддерживаются во всех регионах Azure, в которых поддерживается хранилище файлов класса Premium. Дополнительные сведения см. в списке [доступности продуктов по регионам](https://azure.microsoft.com/global-infrastructure/services/?products=storage), а также в таблице в разделе ниже.


## <a name="availability-in-regions"></a>Доступность по регионам

Большие модели в Power BI доступны только в тех регионах Azure, в которых поддерживается [хранилище файлов Azure класса "Премиум"](https://docs.microsoft.com/azure/storage/files/storage-files-planning#storage-tiers).

В следующем списке перечислены регионы, в которых доступны большие модели Power BI. В регионах, которые не вошли в этот список, большие модели не поддерживаются.


|Регион Azure  |Сокращенное название региона Azure  |
|---------|---------|
|Восточная Австралия     | australiaeast        |
|Юго-Восточная Австралия     | australiasoutheast        |
|Центральная часть США     | centralus        |
|Восточная Азия     | eastasia        |
|Восточная часть США     | eastus        |
|Восточная часть США 2     | eastus2        |
|Восточная Япония     | japaneast        |
|Западная Япония     | japanwest        |
|Центральная Корея, центральный регион     | koreacentral        |
|Республика Корея, южный регион     | koreasouth        |
|Центрально-северная часть США     | northcentralus        |
|Северная Европа     | northeurope        |
|Центрально-южная часть США     | southcentralus        |
|Юго-Восточная Азия     | southeastasia        |
|Южная часть Соединенного Королевства     | uksouth        |
|Западная часть Соединенного Королевства     | ukwest        |
|Западная Европа     | westeurope        |
|Западная часть США     | westus        |
|Западная часть США 2     | westus2        |



## <a name="next-steps"></a>Дальнейшие действия

Следующие ссылки дадут вам полезную информацию для работы с большими моделями.

* [Хранилище файлов Azure класса "Премиум"](https://docs.microsoft.com/azure/storage/files/storage-files-planning#storage-tiers)
* [Настройка поддержки нескольких регионов для Power BI Premium](service-admin-premium-multi-geo.md)
* [Использование собственных ключей шифрования для Power BI](service-encryption-byok.md)
* [Принцип функционирования емкостей](service-premium-what-is.md#how-capacities-function)
* [Добавочное обновление](service-premium-incremental-refresh.md)