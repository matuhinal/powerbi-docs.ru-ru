---
ms.openlocfilehash: f22c12ec0ad5bd413f3658704132143c878df1aa
ms.sourcegitcommit: a5853ef44ed52e80eabee3757bb6887fa400b75b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73800097"
---
Использование **переменных** — исключительно полезная возможность, связанная с выражениями DAX.

![](media/7-4-dax-expressions/dax-variables_1.png)

Вы можете определить переменную в любом месте выражения DAX, используя следующий синтаксис:

    VARNAME = RETURNEDVALUE

Переменные могут быть любого типа данных, включая таблицы.

Помните, что каждый раз, когда вы ссылаетесь на переменную в выражении DAX, Power BI приходится повторно вычислять ее значение в соответствии с определением. По этой причине рекомендуется не повторять переменные в функции.

> Видео от [Альберто Феррари (Alberto Ferrari), SQLBI](https://www.sqlbi.com/learning-dax)
> 
> 

