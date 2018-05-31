---
title: Общие сведения об администрировании Сервера отчетов Power BI
description: В этой статье описано, как администрировать Сервер отчетов Power BI — локальное расположение для хранения и администрирования ваших отчетов Power BI, мобильных отчетов и отчетов с разбивкой на страницы.
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/07/2018
ms.author: maghan
ms.openlocfilehash: 52b2c9cac7fd07564480fdbf3a6a91e04e72db11
ms.sourcegitcommit: c29525cbac2e747edb4dd3a1841084bb0ce42582
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883096"
---
# <a name="admin-overview-power-bi-report-server"></a>Общие сведения об администрировании Сервера отчетов Power BI
В этой статье описано, как администрировать Сервер отчетов Power BI — локальное расположение для хранения и администрирования ваших отчетов Power BI, мобильных отчетов и отчетов с разбивкой на страницы. В этом руководстве описано, как планировать, развертывать и администрировать Сервер отчетов Power BI, и приведены ссылки на связанные материалы.

![](media/admin-handbook-overview/admin-handbook.png)



## <a name="installing-and-migration"></a>Установка и миграция
Чтобы начать использовать сервер отчетов Power BI, его сначала нужно установить. Ниже описано, как это можно сделать.

Перед началом установки, обновления или миграции на сервер отчетов Power BI просмотрите [требования к системе](system-requirements.md) для сервера отчетов.

### <a name="installing"></a>Установка
Развертывая новый сервер отчетов Power BI, ознакомьтесь со следующими материалами. 

[Установка сервера отчетов Power BI](install-report-server.md)

### <a name="migration"></a>Миграция
Для SQL Server Reporting Services обновления отсутствуют. Если у вас есть экземпляр SQL Server Reporting Services, который нужно сделать сервером отчетов Power BI, необходимо выполнить перенос. Есть и другие причины, из-за которых может потребоваться выполнить миграцию. Дополнительные сведения см. в документации по миграции.

[Миграция установки сервера отчетов](migrate-report-server.md)

## <a name="configuring-your-report-server"></a>Настройка сервера отчетов
Настройка сервера отчетов предусматривает разные возможности. Будет ли использоваться SSL? Будет ли настроен почтовый сервер? Нужно ли выполнить интеграцию со службой Power BI, чтобы закреплять визуализации?

Настройка преимущественно будет выполняться в диспетчере конфигурации сервера отчетов. Дополнительные сведения см. в документации по [диспетчеру настройки](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode).

## <a name="security"></a>Безопасность
Любая организация стремится обезопасить свои данные. Дополнительные сведения об аутентификации, авторизации, ролях и разрешениях см. в документации по [обеспечению безопасности](https://docs.microsoft.com/sql/reporting-services/security/reporting-services-security-and-protection).

## <a name="next-steps"></a>Дальнейшие действия
[Установка сервера отчетов Power BI](install-report-server.md)  
[Поиск ключа продукта сервера отчетов](find-product-key.md)  
[Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI](install-powerbi-desktop.md)  
[Install Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder) (Установка построителя отчетов)  
[Download SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714) (Скачивание SQL Server Data Tools (SSDT))

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

