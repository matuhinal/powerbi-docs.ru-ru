---
title: Устранение неполадок с источником данных, не поддерживающим обновление
description: Устранение неполадок с источником данных, не поддерживающим обновление
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 32c42f21eafa7118ed3977340517aeebe8c4219b
ms.sourcegitcommit: e5cf19e16112c7dad1591c3b38d232267ffb3ae1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72542897"
---
# <a name="troubleshooting-unsupported-data-source-for-refresh"></a>Устранение неполадок с источником данных, не поддерживающим обновление
При попытке настроить запланированное обновление набора данных может появиться сообщение об ошибке.

        You cannot schedule refresh for this dataset because it gets data from sources that currently don’t support refresh.

Это происходит, когда обновление источника данных, используемого в Power BI Desktop, не поддерживается. Необходимо найти используемый источник данных и сравнить его со списком поддерживаемых источников данных в разделе [Обновление данных в Power BI](refresh-data.md). 

## <a name="find-the-data-source"></a>Поиск источника данных
Если неизвестно, какой источник данных был использован, его можно найти, выполнив следующие действия в Power BI Desktop.  

1. В Power BI Desktop перейдите в область **Отчет** .  
   ![Область "Отчет" в Power BI Desktop](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-report-pane.png)
2. Щелкните **Изменить запросы** на ленте.  
   ![Изменение запросов](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-edit-queries.png)
3. Щелкните **Расширенный редактор**.  
   ![Расширенный редактор](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-advanced-editor.png)
4. Запишите название поставщика, указанного для источника.  В этом примере поставщиком является ActiveDirectory.  
   ![Поставщик источника данных](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-provider.png)
5. Сравните поставщик со списком поддерживаемых источников данных, приведенным в разделе [Обновление данных в Power BI](refresh-data.md).  Вы увидите, что обновление источника данных Active Directory не поддерживается.  

## <a name="next-steps"></a>Дальнейшие действия
[Обновление данных](refresh-data.md)  
[Шлюз Power BI Gateway — Personal](service-gateway-personal-mode.md)  
[On-premises data gateway (Локальный шлюз данных)](service-gateway-onprem.md)  
[Устранение неполадок локального шлюза данных](service-gateway-onprem-tshoot.md)  
[Устранение неполадок с Power BI Gateway — Personal](service-admin-troubleshooting-power-bi-personal-gateway.md)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

