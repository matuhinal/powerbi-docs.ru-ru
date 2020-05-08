---
title: Управление своим источником данных — Oracle
description: Сведения об управлении локальным шлюзом данных и источниками, которые к нему относятся.
author: arthiriyer
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: arthii
LocalizationGroup: Gateways
ms.openlocfilehash: 5641e42d380458bd1ddcdb316c56e17fafe2d71f
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "79207282"
---
# <a name="manage-your-data-source---oracle"></a>Управление своим источником данных — Oracle

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

После [установки локального шлюза данных](/data-integration/gateway/service-gateway-install) нужно [добавить источники данных](service-gateway-data-sources.md#add-a-data-source), которые можно будет с ним использовать. В этой статье рассмотрены способы работы со шлюзами и источниками данных Oracle, которые используются для запланированного обновления или DirectQuery.

## <a name="install-the-oracle-client"></a>Установка клиента Oracle

Чтобы установить подключение между шлюзом и сервером Oracle, установите и настройте поставщик данных Oracle для .NET (ODP.NET). ODP.NET — это часть Oracle Data Access Components (ODAC).

Для 32-разрядной версии Power BI Desktop используйте следующую ссылку, чтобы скачать и установить 32-разрядный клиент Oracle:

* [32-разрядная версия Oracle Data Access Components (ODAC) с Oracle Developer Tools для Visual Studio (12.1.0.2.4)](https://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

Если вы используете 64-разрядную версию Power BI Desktop или локальный шлюз данных, перейдите по следующей ссылке, чтобы скачать и установить 64-разрядный клиент Oracle:

* [64-разрядная версия ODAC 12.2c, выпуск 1 (12.2.0.1.0) для 64-разрядных версий Windows](https://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

После установки клиента укажите в файле tnsnames.ora нужную информацию для своей базы данных. При настройке подключения для Power BI Desktop и шлюза используется имя net_service_name, которое задано в файле tnsnames.ora. Если net_service_name не настроен, подключиться не удастся. По умолчанию используется такой путь к файлу tnsnames.ora: `[Oracle Home Directory]\Network\Admin\tnsnames.ora`. Дополнительные сведения о том, как настраивать файлы tnsnames.ora, см. в статье [Local Локальные параметры именования (tnsnames.ora)](https://docs.oracle.com/cd/B28359_01/network.111/b28317/tnsnames.htm).

### <a name="example-tnsnamesora-file-entry"></a>Пример записи в файле tnsnames.ora

Ниже приведен основной формат записи в файле tnsname.ora:

```
net_service_name=
 (DESCRIPTION=
   (ADDRESS=(protocol_address_information))
   (CONNECT_DATA=
     (SERVICE_NAME=service_name)))
```

Ниже приведен пример с введенными данными о порте и сервере:

```
CONTOSO =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = oracleserver.contoso.com)(PORT = 1521))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = CONTOSO)
    )
  )
```

## <a name="add-a-data-source"></a>Добавление источника данных

Дополнительные сведения о том, как добавить источник данных, см. в статье [Добавление источника данных](service-gateway-data-sources.md#add-a-data-source). В разделе **Тип источника данных** выберите **Oracle**.

![Добавление источника данных Oracle](media/service-gateway-onprem-manage-oracle/data-source-oracle.png)

Выбрав тип источника данных Oracle, укажите для него параметры, включая **Сервер** и **База данных**. 

В разделе **Метод проверки подлинности** выберите **Windows** или **Базовый**. Если планируется использовать учетную запись, созданную в Oracle, а проверку подлинности Windows, выберите вариант **Базовый**. Затем введите учетные данные, которые будут использоваться для этого источника данных.

> [!NOTE]
> Все запросы к источнику данных будут выполняться с использованием этих учетных данных. Дополнительные сведения о хранении учетных данных см. в статье [Хранение зашифрованных учетных данных в облаке](service-gateway-data-sources.md#store-encrypted-credentials-in-the-cloud).

![Задание параметров источников данных](media/service-gateway-onprem-manage-oracle/data-source-oracle2.png)

После заполнения всех полей нажмите кнопку **Добавить**. Теперь этот источник данных можно использовать для запланированного обновления или для DirectQuery на сервере Oracle, расположенном на локальном компьютере. В случае успеха появится сообщение *Подключение установлено*.

![Отображение состояния подключения](media/service-gateway-onprem-manage-oracle/datasourcesettings4.png)

### <a name="advanced-settings"></a>Дополнительные параметры

Для источника данных также можно настроить уровень конфиденциальности. Этот параметр определяет, каким образом можно комбинировать данные. Он используется только для запланированного обновления. Параметр уровня конфиденциальности не применяется к DirectQuery. Дополнительные сведения об уровнях конфиденциальности для источника данных см. в статье [Уровни конфиденциальности (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540).

![Настройка уровня конфиденциальности](media/service-gateway-onprem-manage-oracle/datasourcesettings9.png)

## <a name="use-the-data-source"></a>Использование источника данных

После создания источника данных он будет доступен для использования с подключениями DirectQuery или через функцию запланированного обновления.

> [!WARNING]
> Имена сервера и базы данных в Power BI Desktop и источнике данных в конфигурации локального шлюза должны совпадать.

Связь между набором и источником данных в пределах шлюза основана на именах сервера и базы данных. Эти имена должны совпадать. Например, если вы указали IP-адрес в качестве имени сервера в Power BI Desktop, необходимо будет использовать такой IP-адрес и для источника данных в конфигурации шлюза. Кроме того, это имя должно совпадать с псевдонимом, который указан в файле tnsnames.ora. Дополнительные сведения о файле tnsnames.ora см. в разделе [Установка клиента Oracle](#install-the-oracle-client).

Это требование справедливо и для DirectQuery, и для запланированного обновления.

### <a name="use-the-data-source-with-directquery-connections"></a>Использование источника данных с подключениями DirectQuery

Убедитесь, что имена сервера и базы данных совпадают в Power BI Desktop и источнике данных для шлюза. Кроме того, для публикации наборов данных DirectQuery ваша учетная запись должна быть указана на вкладке **Пользователи** источника данных. Выбор для DirectQuery выполняется в Power BI Desktop при импорте данных. Дополнительные сведения об использовании DirectQuery см. в статье [Использование DirectQuery в Power BI Desktop](desktop-use-directquery.md).

После публикации (из Power BI Desktop или окна **Получить данные**) ваши отчеты должны начать работать. Установление подключения после создания источника данных в рамках шлюза может занять несколько минут.

### <a name="use-the-data-source-with-scheduled-refresh"></a>Использование источника данных с запланированным обновлением

Если вы указаны на вкладке **Пользователи** источника данных, настроенного в шлюзе, а имена сервера и базы данных совпадают, вы увидите шлюз в списке вариантов, доступных для использования с запланированным обновлением.

![Отображение пользователей](media/service-gateway-onprem-manage-oracle/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="troubleshooting"></a>Устранение неполадок

В Oracle может возникнуть несколько ошибок, если синтаксис именования содержит ошибку или неправильно настроен:

* ORA-12154: TNS: не удалось разрешить указанный идентификатор подключения.
* ORA-12514: прослушивателю TNS неизвестна служба, запрошенная в дескрипторе подключения.
* ORA-12541: TNS: нет прослушивателя.
* ORA-12170: TNS: время ожидания подключения истекло.
* ORA-12504: TNS: прослушиватель не получил имя SERVICE_NAME в параметре CONNECT_DATA.

Эти ошибки могут произойти, если клиент Oracle не установлен или неправильно настроен. Если он установлен, нужно проверить, правильно ли настроен файл tnsnames.ora и используется ли нужное имя net_service_name. Кроме того, нужно задать одно и то же имя net_service_name на компьютере, на котором выполняется Power BI Desktop, и компьютере, на котором запущен шлюз. Дополнительные сведения см. в статье [Установка клиента Oracle](#install-the-oracle-client).

> [!NOTE]
> Ошибка может также возникать из-за несовместимости между версиями сервера и клиента Oracle. Как правило, версии должны совпадать.

См. дополнительные сведения об [устранении неполадок локального шлюза данных](/data-integration/gateway/service-gateway-tshoot).

## <a name="next-steps"></a>Дальнейшие действия

* [Устранение неполадок со шлюзами — Power BI](service-gateway-onprem-tshoot.md)
* [Power BI Premium](service-premium.md)

Появились дополнительные вопросы? Попробуйте задать вопрос в [сообществе Power BI](https://community.powerbi.com/).

