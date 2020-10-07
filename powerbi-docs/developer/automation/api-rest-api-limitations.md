---
title: Ограничения REST API Power BI
description: REST API Power BI имеет перечисленные ниже ограничения
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: de9fd241959b679a0da7926cd6b2254689afbfd2
ms.sourcegitcommit: 6bc66f9c0fac132e004d096cfdcc191a04549683
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91747282"
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
* Максимум 5 000 000 сохраняемых строк для каждой таблицы в наборе данных "без политики хранения"  
* 4 000 символов на значение для столбца строки в операции POST со строками
  
## <a name="see-also"></a>См. также

* [Лимиты и ограничения службы Azure AD](/azure/active-directory/active-directory-service-limits-restrictions)   
* [Обзор интерфейса REST API Power BI](/rest/api/power-bi/)