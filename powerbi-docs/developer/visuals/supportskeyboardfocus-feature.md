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
ms.openlocfilehash: c8cf0f4e896b8a44764d1c363c597182f55d30b3
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83276520"
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

Чтобы испытать разработку Power BI, см. статью [Руководство. Разработка визуального элемента Power BI](custom-visual-develop-tutorial.md).
