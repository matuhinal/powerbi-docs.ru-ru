---
title: "Краткое руководство по установке сервера отчетов Power BI"
description: "Сама по себе установка сервера отчетов Power BI выполняется очень быстро. Скачивание и установка с последующей настройкой занимают всего нескольких минут."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 06/28/2017
ms.author: asaxton
ms.openlocfilehash: 2e616369333d3bb2747ec20eb2072b69d5b9f9d5
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2017
---
# <a name="quickstart-install-power-bi-report-server"></a>Краткое руководство по установке сервера отчетов Power BI
Сама по себе установка сервера отчетов Power BI выполняется очень быстро. Скачивание и установка с последующей настройкой занимают всего нескольких минут.

Это — краткое писание процедуры быстрой установки сервера отчетов в ситуации, когда вам нужно просто запустить новый сервер. См. дополнительные сведения об [установке сервера отчетов Power BI](install-report-server.md).

 **Скачать** ![скачать](media/quickstart-install-report-server/download.png "скачать")

Чтобы скачать сервер отчетов Power BI, перейдите к разделу [Локальная работа с отчетами с использованием сервера Power BI Report Server](https://powerbi.microsoft.com/report-server/). Чтобы скачать версию Power BI Desktop, оптимизированную для сервера отчетов Power BI, перейдите в [Центр загрузки Майкрософт](https://go.microsoft.com/fwlink/?linkid=837581).

![Совет](media/quickstart-install-report-server/fyi-tip.png "Совет"). См. [заметки о текущем выпуске сервера отчетов Power BI](release-notes.md).

<iframe width="640" height="360" src="https://www.youtube.com/embed/zacaEb9A4F0?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="before-you-begin"></a>Подготовка
Прежде чем устанавливать сервер отчетов Power BI, рекомендуем ознакомиться с [требованиями к оборудованию и программному обеспечению для установки сервера отчетов Power BI](system-requirements.md).

## <a name="step-1-download"></a>Шаг 1. Скачивание
Скачайте файлы установки для сервера отчетов Power BI в локальное расположение. Чтобы скачать сервер отчетов Power BI, перейдите в [центр загрузки Майкрософт](https://go.microsoft.com/fwlink/?linkid=839351).

![Скачивание сервера отчетов Power BI](media/quickstart-install-report-server/download-pbireportserver.png)

## <a name="step-2-run-installer"></a>Шаг 2. Запуск установщика
Запустите скачанный исполняемый файл PowerBIReportServer.exe и выполните пошаговые инструкции на экранах установки. Вы можете выбрать путь установки, а также выпуск, который необходимо установить. Можно выбрать ознакомительную версию, срок действия которой истекает через 180 дней, или выпуск для разработчиков. Также вы можете ввести ключ продукта.

![Установка сервера отчетов Power BI](media/quickstart-install-report-server/pbireportserver-install.png)

## <a name="step-3-configure-the-server"></a>Шаг 3. Настройка сервера
Завершив установку, запустите диспетчер настройки, чтобы настроить параметры сервера. Вам нужно будет создать базу данных каталога ReportServer, а также подтвердить URL-адреса веб-портала и веб-службы.

![Настройка сервера отчетов Power BI](media/quickstart-install-report-server/pbireportserver-configure.png)

## <a name="step-4-browse-to-web-portal"></a>Шаг 4. Переход на веб-портал
Завершив настройку, вы сможете открыть в браузере веб-портал сервера. Адрес по умолчанию: `http://localhost/reports`. При отсутствии блокировки брандмауэрами вы сможете использовать для просмотра имя компьютера вместо стандартного имени localhost.

![Веб-портал сервера отчетов Power BI](media/quickstart-install-report-server/web-portal.png)

## <a name="next-steps"></a>Дальнейшие действия
[Руководство администратора](admin-handbook-overview.md)  
[Как найти ключ продукта сервера отчетов](find-product-key.md)  
[Установка сервера отчетов Power BI](install-report-server.md)  
[Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI](install-powerbi-desktop.md)  
[Поддержка браузера для сервера отчетов Power BI](browser-support.md)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

