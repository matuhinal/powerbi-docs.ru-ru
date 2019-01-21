---
title: Устранение неполадок при запуске Power BI Desktop
description: Устранение неполадок при запуске Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: f527fa17ab242f6835ca99a3ff3ef3e2525a001f
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277142"
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>Устранение проблем в случае, если Power BI Desktop не запускается
В **Power BI Desktop** пользователям, установившим и использующим предыдущие версии **локального шлюза данных Power BI**, может быть запрещен запуск Power BI Desktop из-за ограничений политики администрирования, которую локальный шлюз Power BI налагает на именованные каналы на локальном компьютере. 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Устранение проблем с локальным шлюзом данных и Power BI Desktop
Существует три варианта устранения проблемы, связанной с локальным шлюзом данных, и обеспечения запуска Power BI Desktop:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>Решение 1. Установите последнюю версию локального шлюза данных Power BI
Последняя версия локального шлюза данных Power BI не налагает ограничения на именованные каналы на локальном компьютере и разрешает запускать Power BI Desktop должным образом. Если вам нужно продолжить использование локального шлюза данных Power BI, рекомендуется именно это решение. Вы можете скачать последнюю версию локального шлюза данных Power BI [здесь](https://go.microsoft.com/fwlink/?LinkId=698863). Обратите внимание, что ссылка является прямой ссылкой для скачивания исполняемого файла установки.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>Решение 2. Удалите или остановите службу Windows для локального шлюза данных Power BI
Если локальный шлюз данных Power BI больше не требуется, можно удалить его или остановить его службу Windows. При этом ограничения политики снимаются, и становится возможен запуск Power BI Desktop.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>Решение 3. Запустите Power BI Desktop с правами администратора
Кроме того, вы можете запустить Power BI Desktop от имени администратора, что также позволит успешно запустить Power BI Desktop. По-прежнему рекомендуется установить последнюю версию локального шлюза данных Power BI, как было описано ранее.

Важно отметить, что приложение Power BI Desktop разработано как многопроцессная архитектура, и некоторые из этих процессов обмениваются данными с помощью именованных каналов Windows. При этом некоторые процессы могут мешать использованию именованных каналов. Чаще всего это происходит в рамках обеспечения безопасности, например, когда антивирусная программа или брандмауэр могут блокировать каналы или перенаправлять трафик в определенный порт. Эту проблему может решить запуск Power BI Desktop с правами администратора. Если такой запуск невозможен, обратитесь к администратору, чтобы узнать о применяемых правилах безопасности, которые блокируют правильный обмен данными для именованных каналов, и включить и Power BI Desktop и соответствующие подпроцессы в список разрешенных.

## <a name="resolve-issues-when-connecting-to-sql-server"></a>Устранение проблем при подключении к SQL Server
Если при подключении к базе данных SQL Server появляется сообщение об ошибке наподобие приведенного ниже, проблему часто можно решить, запустив приложение **Power BI Desktop** от имени администратора, а затем установив подключение к SQL Server.

    "An error happened while reading data from the provider: 'Could not load file or assembly 'System.EnterpriseServices, Version=4.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxx' or one of its dependencies. Either a required impersonation level was not provided, or the provided impersonation level is invalid. (Exception from HRESULT: 0x80070542)'"

После запуска приложения от имени администратора и установки подключения необходимые библиотеки DLL регистрируются правильно. После этого запускать приложение Power BI Desktop от имени администратора не требуется.

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>Справка по другим проблемам при запуске Power BI Desktop
Мы стараемся описать как можно больше проблем, связанных с использованием **Power BI Desktop**. Мы регулярно просматриваем описание проблем, которые возникают у многих наших клиентов, и включаем их в наши статьи.

Если проблема с запуском **Power BI Desktop** не связана с локальным шлюзом данных или если предыдущие действия не помогли, обратитесь в службу поддержки [Power BI](https://support.powerbi.com) (https://support.powerbi.com). Вам помогут определить и устранить проблему.

Чтобы оптимизировать изоляцию и выявление проблем с **Power BI Desktop**, которые могут возникнуть в будущем (мы надеемся, что их не будет или будет мало), необходимо включить трассировку и сбор файлов журналов. Чтобы включить трассировку, выберите **Файл > Параметры и настройки > Параметры**, щелкните **Диагностика** и установите флажок **Включить трассировку** в разделе *Параметры диагностики*. Мы понимаем, что необходимо запустить **Power BI Desktop**, чтобы задать этот параметр, который больше полезен для будущих проблем, связанных с запуском **Power BI Desktop**.

