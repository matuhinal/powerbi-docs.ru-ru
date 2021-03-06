---
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 01/31/2020
ms.author: davidi
ms.openlocfilehash: 912b0213c328c623e7881f7f30fe7d67f6d889b3
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83274651"
---
## <a name="limitations"></a>Ограничения

Ниже приведен список текущих ограничений для безопасности на уровне строк в облачных моделях.

* Если вы уже задавали роли и правила в службе Power BI, их необходимо повторно создать в Power BI Desktop.

* Безопасность на уровне строк (RLS) можно определить только в наборах данных, созданных в Power BI Desktop. Если вы хотите включить RLS для наборов данных, созданных в Excel, нужно сначала преобразовать файлы в формат Power BI Desktop (PBIX). [Дополнительные сведения](../connect-data/desktop-import-excel-workbooks.md).

* Поддерживаются только импорт и подключения DirectQuery. Активные подключения к службам Analysis Services обрабатываются в локальной модели.

## <a name="known-issues"></a>Известные проблемы

Существует известная проблема, когда при попытке опубликовать из Power BI Desktop уже опубликованный отчет выдается сообщение об ошибке. Ниже описана последовательность действий, которая к этому приводит.

1. Предположим, у Анны есть набор данных, который опубликован в службе Power BI, и для него настроена безопасность на уровне строк.

1. Анна обновляет отчет в Power BI Desktop и публикует его заново.

1. У Анны возникает ошибка.

**Временное решение.** Пока эта проблема не решена, вы можете повторно публиковать файлы Power BI Desktop из службы Power BI. Для этого выберите **Получить данные** > **Файлы**.

