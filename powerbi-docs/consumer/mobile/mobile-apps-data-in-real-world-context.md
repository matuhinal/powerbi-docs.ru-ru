---
title: Получение реальных данных с помощью мобильных приложений Power BI
description: Мобильные приложения Power BI могут связывать объекты физического мира непосредственно с соответствующей информацией BI без дополнительного поиска.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 03/11/2020
ms.author: painbar
ms.openlocfilehash: 512d9f5662a87b3819b7151eb0fc3a4d6a540dd6
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83278521"
---
# <a name="get-data-from-the-real-world-with-the-power-bi-mobile-apps"></a>Получение данных из реального мира с помощью мобильных приложений Power BI
Мобильные приложения Power BI могут связывать объекты физического мира непосредственно с соответствующей информацией BI несколькими способами. 

## <a name="qr-codes-for-tiles"></a>QR-коды для плиток
Создайте QR-код для отчета или плитки на панели мониторинга и поместите его в нужное вам место. Когда ваши коллеги отсканируют его с помощью iPhone, телефона Android или приложения Power BI для смешанной реальности, они увидят связанную с ним плитку. На iPhone эта плитка отображается в режиме дополненной реальности.

![QR-код](./media/mobile-apps-data-in-real-world-context/power-bi-ios-qr-ar-scanner-small.png)

Дополнительные сведения:

* [Создание QR-кода для плитки в Power BI](../../create-reports/service-create-qr-code-for-tile.md)
* [Сканирование QR-кода Power BI на мобильном устройстве](mobile-apps-qr-code.md)
* [Сканирование QR-кода с помощью приложения Power BI для смешанной реальности](mobile-mixed-reality-app.md#scan-a-report-qr-code-in-holographic-view)

## <a name="qr-codes-for-reports"></a>QR-коды для отчетов
Вы можете создать QR-код для отчета.  Отсканировав его с помощью устройства iPhone (поддержка для телефонов с Android будет добавлена в ближайшем будущем), ваши коллеги смогут увидеть связанный с этим кодом отчет. 

Дополнительные сведения о [создании QR-кода для отчета в Power BI](../../create-reports/service-create-qr-code-for-report.md)

## <a name="barcodes"></a>Штрихкоды
В отчеты можно добавлять теги для штрихкодов, и пользователь, который отсканирует код на изделии, сможет перейти непосредственно к этому отчету, данные в котором будут отфильтрованы по соответствующему изделию.

![Штрихкод](./media/mobile-apps-data-in-real-world-context/power-bi-barcode-scanner.png)

Дополнительные сведения:

* [Пометка данных штрихкодов в отчетах](../../transform-model/desktop-mobile-barcodes.md)
* [Сканирование штрихкода из приложения Power BI на iPhone](mobile-apps-scan-barcode-iphone.md)

## <a name="filter-by-location"></a>Фильтрация по местоположению
В приложении Power BI Desktop данным можно присваивать географическую категорию. После этого при просмотре соответствующего отчета мобильное приложение Power BI для iOS автоматически предлагает фильтры с учетом местоположения пользователя.

Ознакомьтесь с дополнительными сведениями о [фильтрации по местоположению](mobile-apps-geographic-filtering.md).

## <a name="next-steps"></a>Дальнейшие действия
* [Создание QR-кода для плитки в Power BI](../../create-reports/service-create-qr-code-for-tile.md)
* [Создание QR-кода для отчета в Power BI](../../create-reports/service-create-qr-code-for-report.md)
