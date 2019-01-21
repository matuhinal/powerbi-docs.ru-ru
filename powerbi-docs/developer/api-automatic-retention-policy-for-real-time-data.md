---
title: Использование политики автоматического хранения данных в режиме реального времени в API Power BI
description: Сведения об использовании политики автоматического хранения в службе Power BI
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 9b5923c7bd92b1fe53ebb7ab9416aca8cece3cfa
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54294387"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>Политика автоматического хранения данных в режиме реального времени

Автоматическая политика хранения в службе Power BI является параметром строки запроса, который включает политику хранения по умолчанию для автоматической очистки старых данных, сохраняя постоянный поток новых данных, поступающих на информационную панель. Первая политика хранения называется *базовой с очисткой в порядке поступления (FIFO)*. Если она включена, данные будут собираться в таблицу, пока в ней не заполнится 200 000 строк. После превышения 200 000 строк самые старые строки удаляются из набора данных. Таким образом, в наличии постоянно будет от 200 000 до 210 000 строк с новейшими данными.  
  
<center>

![политика хранения](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

Политики хранения включаются при создании наборов данных. Вам нужно всего лишь добавить параметр запроса defaultRetentionPolicy в операцию POST с наборами данных и присвоить ему значение *basicFIFO*.  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}