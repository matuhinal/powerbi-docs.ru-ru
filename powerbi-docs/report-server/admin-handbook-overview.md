---
title: "Общие сведения о руководстве для администратора сервера отчетов Power BI"
description: "Это — руководство для администратора сервера отчетов Power BI, локального расположения для хранения и администрирования ваших отчетов Power BI, мобильных отчетов и отчетов с разбивкой на страницы."
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 6434084ab59cf842544dbcf9e373a8f6985a9ee3
ms.sourcegitcommit: eec6b47970bf69ed30638d1a20051f961ba792f2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2018
---
# <a name="administrator-handbook-overview-power-bi-report-server"></a>Общие сведения о руководстве для администратора сервера отчетов Power BI
Это — руководство для администратора сервера отчетов Power BI, локального расположения для хранения и администрирования ваших отчетов Power BI, мобильных отчетов и отчетов с разбивкой на страницы.

![](media/admin-handbook-overview/admin-handbook.png)

Это руководство поможет вам разобраться в основных понятиях, связанных с планированием, развертыванием и администрированием сервера отчетов Power BI.

## <a name="installing-and-migration"></a>Установка и миграция
Чтобы начать использовать сервер отчетов Power BI, его сначала нужно установить. Ниже описано, как это можно сделать.

Перед началом установки, обновления или миграции на сервер отчетов Power BI просмотрите [требования к системе](system-requirements.md) для сервера отчетов.

### <a name="installing"></a>Установка
Развертывая новый сервер отчетов Power BI, ознакомьтесь со следующими материалами. Быстро приступить к работе вам поможет краткое руководство. А подробные сведения представлены в руководстве по установке.

* [Краткое руководство по установке сервера отчетов Power BI](quickstart-install-report-server.md)
* [Установка сервера отчетов Power BI](install-report-server.md)

### <a name="migration"></a>Миграция
Для SQL Server Reporting Services обновления отсутствуют. Если у вас есть экземпляр SQL Server Reporting Services, который нужно сделать сервером отчетов Power BI, необходимо выполнить перенос. Есть и другие причины, из-за которых может потребоваться выполнить миграцию. Дополнительные сведения см. в документации по миграции.

[Миграция установки сервера отчетов](migrate-report-server.md)

## <a name="configuring-your-report-server"></a>Настройка сервера отчетов
Настройка сервера отчетов предусматривает разные возможности. Будет ли использоваться SSL? Будет ли настроен почтовый сервер? Нужно ли выполнить интеграцию со службой Power BI, чтобы закреплять визуализации?

Настройка преимущественно будет выполняться в диспетчере конфигурации сервера отчетов. Дополнительные сведения см. в документации по [диспетчеру настройки](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode).

## <a name="security"></a>Безопасность
Любая организация стремится обезопасить свои данные. Дополнительные сведения об аутентификации, авторизации, ролях и разрешениях см. в документации по [обеспечению безопасности](https://docs.microsoft.com/sql/reporting-services/security/reporting-services-security-and-protection).

## <a name="next-steps"></a>Дальнейшие действия
[Краткое руководство по установке сервера отчетов Power BI](quickstart-install-report-server.md)  
[Как найти ключ продукта сервера отчетов](find-product-key.md)  
[Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI](install-powerbi-desktop.md)  
[Install Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder) (Установка построителя отчетов)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714) (Скачивание SQL Server Data Tools (SSDT))

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

