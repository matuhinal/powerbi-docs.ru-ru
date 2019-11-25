---
title: Использование политики автоматического хранения данных в режиме реального времени в API Power BI
description: Сведения об использовании политики автоматического хранения в службе Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: cdbf50ee5078eaade7794242b3ed522e043cab22
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74265847"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>Политика автоматического хранения данных в режиме реального времени

Автоматическая политика хранения в службе Power BI является параметром строки запроса, который включает политику хранения по умолчанию для автоматической очистки старых данных, сохраняя постоянный поток новых данных на панель мониторинга. Первая политика хранения называется *В порядке поступления (FIFO)* . Если она включена, данные будут собираться в таблицу, пока в ней не заполнится 200 000 строк. После превышения 200 000 строк самые старые строки удаляются из набора данных. Таким образом, в наличии постоянно будет от 200 000 до 210 000 строк с новейшими данными.  
  
<center>

![политика хранения](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

Политики хранения включаются при создании наборов данных. Вам нужно всего лишь добавить параметр запроса default retention policy в операцию POST с наборами данных и присвоить ему значение *basicFIFO*.  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}