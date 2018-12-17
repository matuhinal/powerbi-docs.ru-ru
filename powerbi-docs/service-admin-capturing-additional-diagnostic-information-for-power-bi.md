---
title: Запись дополнительных диагностических сведений
description: Запись дополнительных диагностических сведений
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 8a8ec433a6ebb620593648cdb222df0f60b2f21e
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "53025173"
---
# <a name="capturing-additional-diagnostic-information"></a>Запись дополнительных диагностических сведений
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>Запись дополнительных диагностических сведений для Power BI
Эти инструкции предоставляют два возможных варианта ручного сбора дополнительных диагностических сведений из веб-клиента Power BI.  Необходимо следовать только одному из этих вариантов.

## <a name="network-capture---edge--internet-explorer"></a>Сбор по сети — Microsoft Edge и Internet Explorer
1. Откройте [Power BI](https://app.powerbi.com) в браузере Microsoft Edge или Internet Explorer.
2. Запустите средства разработчика Microsoft Edge, нажав клавишу F12.
3. Откроется окно средств разработчика: 
   
   ![Инструменты разработчиков](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. Откройте вкладку "Сеть". Здесь указан уже зафиксированный трафик. 
   
   ![Вкладка "Сеть" в Edge](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. Вы можете перемещаться по этому окну и пытаться воспроизвести возникшие у вас проблемы. Чтобы скрыть или восстановить окно средств разработчика в любой момент во время работы, нажмите клавишу F12.
6. Чтобы остановить сбор данных, нажмите на значок красного квадрата на вкладке "Сеть" в области средств разработчика.
   
   ![Остановка сбора данных](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. Выберите значок дискеты, чтобы **экспортировать данные в формате HAR**.
   
   ![Экспорт файла](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. Укажите имя HAR-файла и сохраните его.
   
    HAR-файл будет содержать все сведения о сетевых запросах между окном браузера и Power BI.  Эти сведения будут включать идентификаторы действий для каждого запроса, точные метки времени для каждого запроса, а также сведения об ошибках, возвращенных клиенту.  Эта трассировка также будет содержать данные, используемые для заполнения визуальных элементов, отображаемых на экране.
9. HAR-файл можно передать на анализ службе поддержки.

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](http://community.powerbi.com/)

