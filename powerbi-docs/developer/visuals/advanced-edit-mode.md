---
title: Режим расширенного редактирования
description: Визуальные элементы Power BI с расширенными элементами управления пользовательского интерфейса
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 625105aed773bce5cf70932f092faf60ea001c2c
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425558"
---
# <a name="advanced-edit-mode"></a>Режим расширенного редактирования

Визуальные элементы, требующие расширенных элементов управления пользовательского интерфейса, могут объявлять поддержку режима расширенного редактирования.
Если он поддерживается и активен, в меню визуального элемента отображается кнопка `Edit`.
При нажатии кнопки `Advanced` для EditMode задается значение `Edit`.
Визуальный элемент может использовать флаг EditMode, чтобы определить, нужно ли отображать такие элементы управления пользовательского интерфейса.

По умолчанию визуальный элемент не поддерживает режим расширенного редактирования.
Если требуется другое поведение, его нужно явно указать в файле `capabilities.json` визуального элемента, задав свойство `advancedEditModeSupport`.

Возможные значения:

- 0 — NotSupported

- 1 — SupportedNoAction

- 2 — SupportedInFocus

## <a name="entering-advanced-edit-mode"></a>Вход в режим расширенного редактирования

Кнопка `Edit` отображается при следующих условиях:

 1\. Для свойства `advancedEditModeSupport` в capabilities.json задано значение `SupportedNoAction` или `SupportedInFocus`.

 2\. Визуальный элемент открыт в режиме редактирования отчета.

Если свойство `advancedEditModeSupport` в файле capabilities.json отсутствует или имеет значение `NotSupported`, кнопка "Изменить" исчезает.

![Вход в режим редактирования](./media/edit-mode.png)

Когда пользователь нажимает кнопку `Edit`, визуальный элемент получит вызов update() с параметром EditMode, имеющим значение `Advanced`.
В соответствии со значением, заданным в возможностях, выполняются следующие действия:

* `SupportedNoAction` — не требуется никаких дальнейших действий со стороны узла.
* `SupportedInFocus` — узел развертывает визуальный элемент в режим фокусировки.

## <a name="exiting-advanced-edit-mode"></a>Выход из режима расширенного редактирования

Кнопка `Back to report` отображается при следующих условиях:

1\. Для свойства `advancedEditModeSupport` в capabilities.json задано значение `SupportedInFocus`.
