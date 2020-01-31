---
title: Функция Always Encrypted на Сервере отчетов Power BI
description: В этой статье описывается поддержка функции Always Encrypted на Сервере отчетов Power BI при использовании Microsoft SQL Server и Базы данных SQL Microsoft Azure в качестве источников данных.
author: maggiesMSFT
ms.reviewer: cfinlan
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/22/2020
ms.author: maggies
ms.openlocfilehash: f8d711bba8dc7570f2d470554fd1d971639bbb7b
ms.sourcegitcommit: a1409030a1616027b138128695b80f6843258168
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76710213"
---
# <a name="always-encrypted-in-power-bi-report-server"></a>Функция Always Encrypted на Сервере отчетов Power BI

В этой статье описывается поддержка функции Always Encrypted на Сервере отчетов Power BI при использовании Microsoft SQL Server и Базы данных SQL Microsoft Azure в качестве источников данных. Дополнительные сведения о возможностях Always Encrypted в SQL Server см. в статье [Always Encrypted](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine).

## <a name="always-encrypted-user-isolation"></a>Изоляция пользователей Always Encrypted

В настоящее время Сервер отчетов Power BI не ограничивает доступ к столбцам Always Encrypted в отчете, если у пользователя есть доступ к отчету.  Поэтому если серверу предоставлен доступ к ключам шифрования столбцов через главный ключ столбца, то пользователям доступны все столбцы отчетов, к которым у них есть доступ.

## <a name="always-encrypted-column-usage"></a>Использование столбцов Always Encrypted

### <a name="key-storage-strategies"></a>Стратегии хранения ключей

|Запоминающие устройства  |Поддерживается  |
|---------|---------|
|Хранилище сертификатов Windows | Да |
|Azure Key Vault | Нет |
| Криптография следующего поколения (CNG) | Нет |

### <a name="certificate-storage-and-access"></a>Хранилище сертификатов и доступ к нему

Доступ к сертификату требуется учетной записи службы. Сертификат должен храниться в хранилище сертификатов на локальном компьютере. Для получения дополнительной информации см.

- [Настройка учетной записи службы сервера отчетов](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager) (диспетчер конфигурации)
- Раздел [Предоставление приложениям и пользователям доступа к сертификатам](https://docs.microsoft.com/sql/relational-databases/security/encryption/create-and-store-column-master-keys-always-encrypted#making-certificates-available-to-applications-and-users) в статье по SQL Server "Создание и хранение главных ключей столбцов для Always Encrypted".

### <a name="column-encryption-strategy"></a>Стратегия шифрования столбцов

На Сервере отчетов Power BI стратегия шифрования столбцов может быть *детерминированной* или *случайной*. В таблице ниже представлены различия между этими стратегиями.

|Использование  |Детерминированное  |случайное шифрование;  |
|---------|---------|---------|
|Может считываться "как есть" в результатах запроса, например инструкции SELECT. | Да  | Да  |
|Может использоваться в качестве сущности Group By в запросе. | Да | Нет |
|Может использоваться как статистическое поле, кроме функций COUNT и DISTINCT. | Нет, кроме функций COUNT и DISTINCT | Нет |
|Может использоваться как параметр отчета | Да | Нет |

См. дополнительные сведения о [детерминированном и случайном шифровании](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine#selecting--deterministic-or-randomized-encryption).

### <a name="parameter-usage"></a>Использование параметров

Параметры можно использовать только с детерминированным шифрованием.

**Параметр с одним значением**.  Параметр с одним значением можно использовать для столбца Always Encrypted.

**Параметр с несколькими значениями**. Параметр более чем с одним значением нельзя использовать для столбца Always Encrypted.

**Каскадные параметры**. Каскадные параметры можно использовать с Always Encrypted, если выполняются *все* перечисленные ниже условия.

- Все столбцы Always Encrypted должны шифроваться с использованием детерминированной стратегии.
- Все параметры, используемые для столбцов Always Encrypted, являются параметрами с одним значением.
- Во всех сравнениях SQL используется оператор "равно" (=).

## <a name="datatype-support"></a>Поддержка типов данных

| Тип данных SQL | Поддерживает чтение поля | Поддерживает использование в качестве элемента Group By | Поддерживает агрегаты (COUNT, DISTINCT, MAX, MIN, SUM и т. д.) | Поддерживает фильтрацию через равенство с использованием параметров | Примечания |
| --- | --- | --- | --- | --- | --- |
| int | Да | Да | COUNT, DISTINCT | Да, как Integer |   |
| FLOAT | Да | Да | COUNT, DISTINCT | Да, как Float |   |
| nvarchar | Да | Да | COUNT, DISTINCT | Да, как Text | При использовании детерминированного шифрования необходимо указать порядок сортировки binary2 в параметрах сортировки для символьных столбцов. Подробные сведения см. в статье по SQL Server [Always Encrypted](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine#selecting--deterministic-or-randomized-encryption).  |
| varchar | Да | Да | COUNT, DISTINCT | Нет |   |
| Decimal | Да | Да | COUNT, DISTINCT | Нет |   |
| NUMERIC | Да | Да | COUNT, DISTINCT | Нет |   |
| значение datetime | Да | Да | COUNT, DISTINCT | Нет |   |
| datetime2 | Да | Да | COUNT, DISTINCT | Да, как Date/Time | Поддерживается, если столбец не имеет точности в миллисекундах (иными словами, не имеет тип datetime2(0)) |

## <a name="aggregation-alternatives"></a>Альтернативные агрегаты

В настоящее время для детерминированных столбцов Always Encrypted поддерживаются только агрегаты, которые напрямую используют оператор "равно" (=). Это ограничение в SQL Server связано с особенностями столбцов Always Encrypted. Пользователи должны выполнять агрегирование в отчете, а не в базе данных.

## <a name="always-encrypted-in-connection-strings"></a>Always Encrypted в строках подключения

Функцию Always Encrypted необходимо включить в строке подключения к источнику данных SQL Server. См. дополнительные сведения о включении [Always Encrypted для запросов приложений](https://docs.microsoft.com/sql/relational-databases/security/encryption/develop-using-always-encrypted-with-net-framework-data-provider#enabling-always-encrypted-for-application-queries).

## <a name="next-steps"></a>Дальнейшие действия

[Always Encrypted](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine) в SQL Server и Базе данных SQL Azure

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

