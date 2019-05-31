---
ms.openlocfilehash: 5c2b254f20bd1eba97840a464a1b554cc4fe1238
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "61273600"
---
Использование **переменных** — исключительно полезная возможность, связанная с выражениями DAX.

![](media/7-4-dax-expressions/dax-variables_1.png)

Вы можете определить переменную в любом месте выражения DAX, используя следующий синтаксис:

    VARNAME = RETURNEDVALUE

Переменные могут быть любого типа данных, включая таблицы.

Помните, что каждый раз, когда вы ссылаетесь на переменную в выражении DAX, Power BI приходится повторно вычислять ее значение в соответствии с определением. По этой причине рекомендуется не повторять переменные в функции.

> Видео от [Альберто Феррари (Alberto Ferrari), SQLBI](http://www.sqlbi.com/learning-dax)
> 
> 

