---
title: Функция supportsKeyboardFocus
description: В этой статье описывается, как использовать функцию supportsKeyboardFocus в визуальных элементах Power BI, а также требования к ее использованию.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 04/30/2020
ms.openlocfilehash: 1e5a4cf8c80d8123d39fd2ab76898abc0c439ad9
ms.sourcegitcommit: 50b21718a167c2b131313b4135c8034c6f027597
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/14/2020
ms.locfileid: "92049391"
---
# <a name="use-the-supportskeyboardfocus-feature"></a>Использование функции supportsKeyboardFocus

В этой статье описывается, как использовать функцию `supportsKeyboardFocus` в визуальных элементах Power BI.
Функция `supportsKeyboardFocus` позволяет перемещаться по точкам данных визуального элемента с помощью клавиатуры.

Дополнительные сведения о навигации по визуальных элементах с помощью клавиатуры см. в разделе [Навигация с помощью клавиатуры](../../create-reports/desktop-accessibility-consuming-tools.md#keyboard-navigation).

## <a name="example"></a>Пример

Откройте визуальный элемент, использующий функцию `supportsKeyboardFocus`. Выберите любую точку данных в визуальном элементе и перейдите на вкладку. Фокус перемещается к следующей точке данных при каждом переходе на вкладку. Нажмите клавишу "ВВОД", чтобы выбрать выделенную точку данных.

![Поддерживает пример фокуса клавиатуры](./media/supportskeyboardfocus-feature/supports-keyboard-focus-example.png)

## <a name="requirements"></a>Требования

Для этой функции требуется API версии 2.1.0 или более поздней версии.

Эту функцию можно применить ко всем визуальным элементам, за исключением визуальных элементов изображения.

## <a name="usage"></a>Использование

Чтобы использовать функцию `supportsKeyboardFocus`, добавьте следующий код в файл *capabilities.json* визуального элемента.
Эта возможность позволяет визуальному элементу получать фокус с помощью навигации по клавишам.

```json
    {   
            ...
        "supportsKeyboardFocus": true
            ...
    }

```

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения о специальных возможностях см. в статье [Создание отчетов со специальными возможностями Power BI](../../create-reports/desktop-accessibility-creating-reports.md).

Чтобы испытать разработку в Power BI, см. руководство [Разработка визуализации "Круговая карточка" в Power BI](develop-circle-card.md).
