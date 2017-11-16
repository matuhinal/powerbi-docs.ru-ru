---
title: "Сторонняя служба: соединитель Google Analytics для Power BI Desktop"
description: "Сторонняя служба: соединитель Google Analytics для Power BI Desktop"
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
ms.date: 07/20/2017
ms.author: davidi
ms.openlocfilehash: 3c1c5ede054c129aad06e7047d8e03e5dfc307b8
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="google-analytics-connector-for-power-bi-desktop"></a>Соединитель Google Analytics для Power BI Desktop
> [!NOTE]
> Пакет содержимого и соединитель Google Analytics в Power BI Desktop основаны на API-интерфейсе Core Reporting для Google Analytics. Таким образом, наличие функций и доступность со временем могут меняться.
> 
> 

Подключиться к данным Google Analytics можно при помощи соединителя **Google Analytics**. Чтобы подключиться, выполните следующие действия.

1. В **Power BI Desktop** выберите **Получить данные** на вкладке ленты **Главная**.
2. В окне **Получение данных** в списке категорий в левой области выберите **Прочее** .
3. В списке в области справа выберите **Google Analytics** .
4. В нижней части окна выберите **Подключить**.  
   ![](media/service-google-analytics-connector/tps_googleanalytics_1.png)

Откроется диалоговое окно, в котором сообщается, что соединитель является сторонней службой, и предупреждается о возможности изменения функций и доступности с течением времени, а также содержатся другие уточнения.  
![](media/service-google-analytics-connector/tps_googleanalytics_2.png)

После нажатия кнопки **Продолжить** вам будет предложено войти в службу Google Analytics.  
![](media/service-google-analytics-connector/tps_googleanalytics_3.png)

При вводе учетных данных вам будет предложено выбрать доступ к Power BI в автономном режиме. Таким образом **Power BI Desktop** используется для доступа к данным Google Analytics.  

После принятия предложения в **Power BI Desktop** будет отображено уведомление о том, что вход выполнен.  
![](media/service-google-analytics-connector/tps_googleanalytics_5.png)

Выберите **Подключить**, после чего данные Google Analytics будут подключены к **Power BI Desktop** и загружены.  
![](media/service-google-analytics-connector/tps_googleanalytics_6.png)

## <a name="changes-to-the-api"></a>Изменения API-интерфейса
Несмотря на попытки выпуска обновлений в соответствии с любыми изменениями, API-интерфейс может измениться так, что изменения повлияют на результаты формируемых запросов. В некоторых случаях поддержка определенных запросов может отсутствовать. В связи с этой зависимостью мы не гарантируем наличие и правильность результатов запросов при использовании этого соединителя.

Дополнительные сведения об изменениях API-интерфейса Google Analytics см. в [журнале изменений](https://developers.google.com/analytics/devguides/changelog).

