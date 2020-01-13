---
title: Структура проекта визуального элемента Power BI
description: В этой статье описывается структура проектов визуальных элементов.
author: zBritva
ms.author: v-ilgali
ms.reviewer: ''
ms.service: powerbi
ms.topic: tutorial
ms.subservice: powerbi-custom-visuals
ms.date: 03/15/2019
ms.openlocfilehash: 728aba749f80710fdc0bb1e180b3318e63caa88c
ms.sourcegitcommit: 331ebf6bcb4a5cdbdc82e81a538144a00ec935d4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/28/2019
ms.locfileid: "75542100"
---
# <a name="power-bi-visual-project-structure"></a>Структура проекта визуального элемента Power BI

После выполнения команды pbiviz new `<visual project name>` в папке `<visual project name>` создается базовая структура файлов и папок.

## <a name="visual-project-structure"></a>Структура проекта визуального элемента

![Структура проекта визуального элемента](./media/visual-project-structure.png)

* `.vscode` — содержит параметры проекта для VS Code. Чтобы настроить рабочую область, измените файл `.vscode/settings.json`. Дополнительные сведения о параметрах VS Code см. в [документации](https://code.visualstudio.com/docs/getstarted/settings).

* Папка `assets` содержит только файл `icon.png`. Он используется в качестве значка визуального элемента в области "Визуализации" Power BI.

    ![Область "Визуализации"](./media/visualization-pane-analytics-tab.png)

* Папка `node_modules` содержит все пакеты, [установленные диспетчером пакетов Node](https://docs.npmjs.com/files/folders.html).

* Папка `src` содержит исходный код визуального элемента. По умолчанию средство создает два файла:

  * `visual.ts` — основной исходный код визуального элемента;

  * `settings.ts` — код параметров для визуального элемента. Классы в этом файле упрощают [работу со свойствами визуального элемента](./objects-properties.md#properties).

* Папка `style` содержит файл `visual.less` со стилями для визуального элемента.

* Файл `capabilities.json` содержит основные свойства и параметры визуального элемента. Он позволяет объявлять поддерживаемые функции, объекты, свойства и сопоставление представлений данных для визуального элемента.

    Дополнительные сведения о возможностях см. в [документации](./capabilities.md).

* Файл `package-lock.json` создается автоматически для любой операции, которая предполагает изменение дерева `node_modules` или файла `package.json` средством npm.

    Дополнительные сведения о файле `package-lock.json` см. в [официальной документации по NPM](https://docs.npmjs.com/files/package-lock.json).

* Файл `package.json` описывает пакет проекта. Обычно он содержит сведения о проекте, его авторах, описание и зависимости проекта.

    Дополнительные сведения о файле `package.json` см. в [официальной документации по NPM](https://docs.npmjs.com/files/package.json.html).

* Файл `pbiviz.json` содержит метаданные визуального элемента. Задайте метаданные визуального элемента в нем.

    Типичное содержимое:

  ```json
    {
        "visual": {
            "name": "<visual project name>",
            "displayName": "<visual project name>",
            "guid": "<visual project name>23D8B823CF134D3AA7CC0A5D63B20B7F",
            "visualClassName": "Visual",
            "version": "1.0.0",
            "description": "",
            "supportUrl": "",
            "gitHubUrl": ""
        },
        "apiVersion": "2.6.0",
        "author": { "name": "", "email": "" },
        "assets": { "icon": "assets/icon.png" },
        "externalJS": null,
        "style": "style/visual.less",
        "capabilities": "capabilities.json",
        "dependencies": null,
        "stringResources": []
    }
  ```

    где

  * `name` — внутреннее имя визуального элемента.

  * `displayName` — имя визуального элемента в пользовательском интерфейсе Power BI.

  * `guid` — уникальный идентификатор визуального элемента.

  * `visualClassName` — имя основного класса визуального элемента. Power BI создает экземпляр этого класса, чтобы визуальный элемент можно было использовать в отчете Power BI.

  * `version` — номер версии визуального элемента.

  * `author` — содержит имя и контактный адрес электронной почты автора.

  * `icon` в `assets` — путь к файлу значка для визуального элемента.

  * `externalJS` содержит пути к библиотекам JS, используемым в визуальном элементе;

    > [!IMPORTANT]
    > В последних версиях средства (3.x.x и более поздних) `externalJS` больше не используется.

  * `style` — путь к файлам стилей.

  * `capabilities` — путь к файлу `capabilities.json`.

  * `dependencies` — путь к файлу `dependencies.json`. `dependencies.json` содержит сведения о пакетах R, используемых в визуальных элементах на языке R.

  * `stringResources` — массив путей к файлам с локализациями.

  Дополнительные сведения о локализации визуальных элементов см. в [документации](./localization.md).

* `tsconfig.json` — это файл конфигурации для TypeScript.

    Дополнительные сведения о конфигурации TypeScript см. в [официальной документации](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html).

    В разделе `files` файла `tsconfig.json` должен содержаться путь к файлу *.ts с основным классом визуального элемента, указанным в свойстве `visualClassName` в файле `pbiviz.json`.

* Файл `tslint.json` содержит конфигурацию TSLint.

    Дополнительные сведения о конфигурации TSLint см. в [официальной документации](https://palantir.github.io/tslint/usage/configuration/).

## <a name="next-steps"></a>Дальнейшие действия

* Более подробно ознакомьтесь с [понятием визуального элемента](./power-bi-visuals-concept.md), чтобы лучше понять, как визуальный элемент, пользователь и Power BI взаимодействуют друг с другом.

* Приступите к разработке собственных визуальных элементов Power BI с нуля с помощью [пошагового руководства](./custom-visual-develop-tutorial.md).
