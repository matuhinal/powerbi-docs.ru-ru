---
title: Ограничения REST API Power BI
description: REST API Power BI имеет перечисленные ниже ограничения
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: df17563d384359fe33123ed87743754bb33bf04d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277992"
---
# <a name="power-bi-rest-api-limitations"></a>Ограничения REST API Power BI  
  
**Операции POST со строками**  
  
* Максимум 75 столбцов
* Максимум 75 таблиц
* Максимум 10 000 строк на один запрос строк POST  
* 1 000 000 добавляемых строк в час на набор данных  
* Максимум 5 ожидающих запросов на операции POST со строками в наборе данных  
* 120 запросов операций POST со строками в минуту на набор данных
* Если в таблице 250 000 или более строк, 120 запросов строк POST в час на набор данных    
* Максимум 200 000 сохраняемых строк для каждой таблицы в наборе данных FIFO  
* Максимум 5 000 000 сохраняемых строк для каждой таблицы в наборе данных «без политики хранения»  
* 4 000 символов на значение для столбца строки в операции POST со строками
  
## <a name="see-also"></a>См. также:

[Ограничения службы Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-service-limits-restrictions)   
[Обзор интерфейса REST API Power BI](https://docs.microsoft.com/rest/api/power-bi/)