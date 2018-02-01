---
title: "Устранение неполадок при запуске Power BI Desktop"
description: "Устранение неполадок при запуске Power BI Desktop"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 515832b9e6b737a942b08b491b78337d78398ee3
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/25/2018
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>Устранение проблем в случае, если Power BI Desktop не запускается
В **Power BI Desktop** пользователям, установившим и использующим предыдущие версии **локального шлюза данных Power BI**, может быть запрещен запуск Power BI Desktop из-за ограничений политики администрирования, которую локальный шлюз Power BI налагает на именованные каналы на локальном компьютере. 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>Устранение проблем с локальным шлюзом данных и Power BI Desktop
Существует три варианта устранения проблемы, связанной с локальным шлюзом данных, и обеспечения запуска Power BI Desktop:

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>Решение 1. Установите последнюю версию локального шлюза данных Power BI
Последняя версия локального шлюза данных Power BI не налагает ограничения на именованные каналы на локальном компьютере и разрешает запускать Power BI Desktop должным образом. Если вам нужно и дальше использовать локальных шлюз данных Power BI, это рекомендуемое решение. Последнюю версию локального шлюза данных Power BI можно скачать в [этом расположении](https://go.microsoft.com/fwlink/?LinkId=698863). Обратите внимание, что ссылка является прямой ссылкой для скачивания исполняемого файла установки.

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>Решение 2. Удалите или остановите службу Windows локального шлюза данных Power BI
Если вам больше не нужен локальный шлюз данных Power BI, вы можете удалить его или остановить службу Windows локального шлюза данных Power BI. Это приводит к удалению ограничения политики и позволяет запустить Power BI Desktop.

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>Решение 3. Запустите Power BI Desktop с правами администратора
Кроме того, вы можете запустить Power BI Desktop от имени администратора, что также позволит успешно запустить Power BI Desktop. По-прежнему рекомендуется установить последнюю версию локального шлюза данных Power BI, как описано ранее в этой статье.

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>Справка по другим проблемам при запуске Power BI Desktop
Мы стараемся описать как можно больше проблем, связанных с использованием **Power BI Desktop**. Мы регулярно просматриваем описание проблем, которые возникают у многих наших клиентов, и включаем их в наши статьи.

Если проблема с запуском **Power BI Desktop** не связана с локальным шлюзом данных или если предыдущие решения не помогли, вы можете обратиться в службу поддержки [Power BI](https://support.powerbi.com) (https://support.powerbi.com). Вам помогут определить и устранить проблему.

Чтобы оптимизировать изоляцию и выявление проблем с **Power BI Desktop**, которые могут возникнуть в будущем (мы надеемся, что их не будет или будет мало), необходимо включить трассировку и сбор файлов журналов. Чтобы включить трассировку, выберите **Файл > Параметры и настройки > Параметры**, щелкните **Диагностика** и установите флажок **Включить трассировку** в разделе *Параметры диагностики*. Мы понимаем, что необходимо запустить **Power BI Desktop**, чтобы задать этот параметр, который больше полезен для будущих проблем, связанных с запуском **Power BI Desktop**.

