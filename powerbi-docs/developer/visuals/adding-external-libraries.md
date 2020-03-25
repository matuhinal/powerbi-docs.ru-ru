---
title: Добавление внешних библиотек в визуальные элементы Power BI
description: В этой статье описывается, как использовать внешние библиотеки в визуальных элементах Power BI.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 02/24/2020
ms.openlocfilehash: 9df111e7545c43fe9b75784b1a95df4f37fd01e7
ms.sourcegitcommit: 2c798b97fdb02b4bf4e74cf05442a4b01dc5cbab
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80114136"
---
# <a name="adding-external-libraries"></a>Добавление внешних библиотек

В этой статье описывается, как использовать внешние библиотеки в визуальных элементах Power BI. Она содержит сведения об установке, импорте и вызове внешних библиотек из кода визуального элемента Power BI.

## <a name="javascript-libraries"></a>Библиотеки JavaScript

1. Установите внешнюю библиотеку JavaScript с помощью любого диспетчера пакетов, например *npm* или *yarn*.
2. Импортируйте необходимые модули в файлы исходного кода с помощью внешней библиотеки.

>[!NOTE]
>Если вы хотите добавить в библиотеку JavaScript вводимые элементы, а также обеспечить функции IntelliSense и безопасность во время компиляции, убедитесь, что установлен соответствующий пакет.

### <a name="installing-the-d3-library"></a>Установка библиотеки d3

Это пример установки [библиотеки d3](https://www.npmjs.com/package/d3) и пакета [@types/d3](https://www.npmjs.com/package/@types/d3) с помощью [npm](https://www.npmjs.com/).

Полный пример приведен в коде [визуальных элементов Power BI](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/src/gantt.ts#L29).

1. Установите пакет *d3* и пакет *типов d3*.

    ```powershell
    npm install d3@5 --save
    npm install @types/d3@5 --save
    ```

2. Импортируйте библиотеку *d3* в файлы, которые ее используют, например `visual.ts`.

    ```typescript
    import * as d3 from "d3";
    ```

## <a name="css-framework"></a>Платформа CSS

1. Установите внешнюю платформу CSS с помощью любого диспетчера пакетов, например *npm* или *yarn*.
2. В файл с расширением `.less` визуального элемента добавьте оператор `import`.

### <a name="installing-bootstrap"></a>Установка начальной загрузки

Это пример установки [начальной загрузки](https://www.npmjs.com/package/bootstrap) с помощью [npm](https://www.npmjs.com/).

Полный пример приведен в коде [визуальных элементов Power BI](https://github.com/Microsoft/powerbi-visuals-sankey/blob/c8200da56913cd8b253be949a35fad0f4472b6de/style/visual.less#L32).

1. Установите пакет *bootstrap*.

    ```powershell
    npm install bootstrap --save
    ```

2. Добавьте оператор `import` в `visual.less`.

    ```less
    @import (less) "node_modules/bootstrap/dist/css/bootstrap.css";
    ```
