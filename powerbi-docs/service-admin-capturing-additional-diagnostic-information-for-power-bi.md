---
title: "Запись дополнительных диагностических сведений"
description: "Запись дополнительных диагностических сведений"
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.author: maghan
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 65954c19087e9c9968c549f610d4e36e942e3206
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2018
---
# <a name="capturing-additional-diagnostic-information"></a>Запись дополнительных диагностических сведений
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Запись дополнительных диагностических сведений для Power BI
Эти инструкции предоставляют два возможных варианта ручного сбора дополнительных диагностических сведений из веб-клиента Power BI.  Необходимо следовать только одному из этих вариантов.

## <a name="network-capture---edge--internet-explorer"></a>Сбор по сети — Edge и Internet Explorer
1. Откройте [Power BI](https://app.powerbi.com) в браузере Edge или Internet Explorer.
2. Запустите средства разработчика Edge, нажав клавиши F12.
3. Откроется окно средств разработчика: 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. Откройте вкладку "Сеть". Здесь указан уже зафиксированный трафик. 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. Вы можете перемещаться по этому окну и пытаться воспроизвести возникшие у вас проблемы. Чтобы скрыть или восстановить окно средств разработчика в любой момент во время работы, нажмите клавишу F12.
6. Чтобы остановить сбор данных, нажмите на значок красного квадрата на вкладке "Сеть" в области средств разработчика.
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. Выберите значок дискеты, чтобы **экспортировать данные в формате HAR**.
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. Укажите имя HAR-файла и сохраните его.
   
    HAR-файл будет содержать все сведения о сетевых запросах между окном браузера и Power BI.  Эти сведения будут включать идентификаторы действий для каждого запроса, точные метки времени для каждого запроса, а также сведения об ошибках, возвращенных клиенту.  Эта трассировка также будет содержать данные, используемые для заполнения визуальных элементов, отображаемых на экране.
9. HAR-файл можно передать на анализ службе поддержки.

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

