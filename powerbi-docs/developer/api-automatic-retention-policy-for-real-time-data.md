---
title: Использование политики автоматического хранения данных в режиме реального времени в API Power BI
description: Сведения об использовании политики автоматического хранения в службе Power BI
author: rkarlin
ms.author: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: e2d81ac67ea5c070f31315a381b42e3a1379a49b
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2019
ms.locfileid: "73865065"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>Политика автоматического хранения данных в режиме реального времени

Автоматическая политика хранения в службе Power BI является параметром строки запроса, который включает политику хранения по умолчанию для автоматической очистки старых данных, сохраняя постоянный поток новых данных на панель мониторинга. Первая политика хранения называется *В порядке поступления (FIFO)* . Если она включена, данные будут собираться в таблицу, пока в ней не заполнится 200 000 строк. После превышения 200 000 строк самые старые строки удаляются из набора данных. Таким образом, в наличии постоянно будет от 200 000 до 210 000 строк с новейшими данными.  
  
<center>

![политика хранения](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

Политики хранения включаются при создании наборов данных. Вам нужно всего лишь добавить параметр запроса default retention policy в операцию POST с наборами данных и присвоить ему значение *basicFIFO*.  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}