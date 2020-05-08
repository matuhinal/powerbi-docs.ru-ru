---
title: Устранение неполадок при запуске Power BI Desktop
description: Устранение неполадок при запуске Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/14/2020
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 67c83f2cc0eb81e90f447961ed178a04e97e050e
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "76160910"
---
# <a name="troubleshoot-opening-power-bi-desktop"></a>Устранение неполадок с открытием Power BI Desktop

В Power BI Desktop пользователям, установившим и использующим предыдущие версии *локального шлюза данных Power BI*, может быть запрещен запуск Power BI Desktop из-за ограничений политики администрирования, которую локальный шлюз Power BI налагает на именованные каналы на локальном компьютере.

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Устранение проблем с локальным шлюзом данных и Power BI Desktop

У вас есть три варианта устранения проблемы, связанной с локальным шлюзом данных, и обеспечения открытия Power BI Desktop:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>Решение 1. Установите последнюю версию локального шлюза данных Power BI

Последняя версия локального шлюза данных Power BI не налагает ограничения на именованные каналы на локальном компьютере и разрешает открыть Power BI Desktop должным образом. Если вам нужно продолжить использование локального шлюза данных Power BI, рекомендуется именно его обновление. Вы можете скачать [последнюю версию локального шлюза данных Power BI](https://go.microsoft.com/fwlink/?LinkId=698863). Ссылка является прямой ссылкой для скачивания исполняемого файла установки.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-microsoft-service"></a>Решение 2. Удалите или остановите службу Майкрософт для локального шлюза данных Power BI

Вы можете удалить локальный шлюз данных Power BI, если он больше не нужен. Или можно также отключить службу Майкрософт локального шлюза данных Power BI, которая удаляет ограничение политики и позволяет открывать Power BI Desktop.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>Решение 3. Запустите Power BI Desktop с правами администратора

Вместо этого Power BI Desktop можно запустить от имени администратора, что также позволит успешно открыть Power BI Desktop. По-прежнему рекомендуется установить последнюю версию локального шлюза данных Power BI, как было описано ранее.

Приложение Power BI Desktop разработано как многопроцессную архитектуру, и некоторые из этих процессов обмениваются данными с помощью именованных каналов Windows. При этом некоторые процессы могут мешать использованию именованных каналов. Чаще всего это происходит в рамках обеспечения безопасности, например, когда антивирусная программа или брандмауэр могут блокировать каналы или перенаправлять трафик в определенный порт. Эту проблему может решить открытие Power BI Desktop с правами администратора. Если выполнение с правами администратора не привело к открытию, попросите администратора определить, какие правила безопасности препятствуют правильной связи именованных каналов. Затем список разрешений Power BI Desktop и соответствующие ему подпроцессы.

## <a name="resolve-issues-when-connecting-to-sql-server"></a>Устранение проблем при подключении к SQL Server

При попытке подключения к базе данных SQL Server может появиться сообщение об ошибке следующего вида:

`"An error happened while reading data from the provider:`\
`'Could not load file or assembly 'System.EnterpriseServices, Version=4.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxx' or one of its dependencies.`\
`Either a required impersonation level was not provided, or the provided impersonation level is invalid. (Exception from HRESULT: 0x80070542)'"`

Часто проблему можно устранить, если открыть Power BI Desktop от имени администратора, прежде чем устанавливать подключение SQL Server.

После открытия Power BI Desktop от имени администратора и установки подключения необходимые библиотеки DLL регистрируются правильно. После этого открытие приложения Power BI Desktop от имени администратора не требуется.

## <a name="get-help-with-other-launch-issues"></a>Получение справки по другим проблемам при запуске

Мы стараемся описать как можно больше проблем, связанных с использованием Power BI Desktop. Мы регулярно просматриваем описание проблем, которые возникают у многих наших клиентов, и включаем их в наши статьи.

Если проблема с открытием Power BI Desktop не связана с локальным шлюзом данных или если предыдущие действия не помогли, обратитесь в службу поддержки *Power BI* (<https://support.powerbi.com>).Вам помогут определить и устранить проблему.

Если в будущем у вас возникнут другие проблемы с Power BI Desktop, полезным действием станет включение трассировки и сбор файлов журналов. Файлы журнала могут помочь изолировать и определить неполадку. Чтобы включить трассировку, нажмите **Файл** > **Параметры и настройки** > **Параметры**, выберите **Диагностика**, а затем **Включить трассировку**. Для установки этого параметра необходимо запустить Power BI Desktop, но это полезно для будущих проблем, связанных с открытием Power BI Desktop.
