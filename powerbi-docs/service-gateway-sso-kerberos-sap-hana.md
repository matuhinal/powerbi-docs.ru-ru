---
title: Использование Kerberos для единого входа в SAP HANA
description: Настройка сервера SAP HANA для включения единого входа из службы Power BI
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 9c2eb554a4e3b3ec90d3fe17145e0ec277298e1b
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/06/2020
ms.locfileid: "74697504"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-hana"></a>Использование Kerberos для единого входа в SAP HANA

В этой статье описывается, как настроить источник данных SAP HANA для включения единого входа из службы Power BI.

> [!NOTE]
> Прежде чем пытаться обновить отчет на основе SAP HANA, в котором используется единый вход Kerberos, выполните действия, описанные в этой статье, а также инструкции в статье [Настройка единого входа на основе Kerberos](service-gateway-sso-kerberos.md).

## <a name="enable-sso-for-sap-hana"></a>Включение единого входа для SAP HANA

Чтобы включить единый вход для SAP HANA, выполните следующие действия:

1. Убедитесь, что для сервера SAP HANA используется минимально допустимая версия, которая зависит от уровня платформы сервера SAP HANA:
   - [HANA 2 SPS 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386)
   - [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324)
   - [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)

2. На компьютере шлюза установите последнюю версию драйвера ODBC для SAP HANA. Минимальная версия драйвера ODBC для HANA — 2.00.020.00, выпущенная в августе 2017 г.

3. Убедитесь, что сервер SAP HANA настроен для единого входа на основе Kerberos. Дополнительные сведения о настройке единого входа для SAP HANA с помощью Kerberos см. в разделе о [едином входе с использованием Kerberos](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.03/1885fad82df943c2a1974f5da0eed66d.html) руководства по безопасности SAP HANA. На этой странице приведены полезные ссылки, в частности примечание SAP 1837331 — HOWTO HANA DBSSO Kerberos/Active Directory.

Мы также рекомендуем указанные ниже дополнительные действия, которые позволят обеспечить небольшое повышение производительности.

1. В каталоге установки шлюза найдите и откройте этот файл конфигурации: Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config.

2. Найдите свойство `FullDomainResolutionEnabled` и измените его значение на `True`.

    ```xml
    <setting name=" FullDomainResolutionEnabled " serializeAs="String">
          <value>True</value>
    </setting>
    ```

Теперь [запустите отчет Power BI](service-gateway-sso-kerberos.md#run-a-power-bi-report).

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения о локальном шлюзе данных и DirectQuery см. в следующих ресурсах:

* [Что такое локальный шлюз данных?](/data-integration/gateway/service-gateway-onprem)
* [Power BI и DirectQuery](desktop-directquery-about.md)
* [Источники данных, поддерживаемые DirectQuery](desktop-directquery-data-sources.md)
* [Использование DirectQuery и SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md)
* [DirectQuery и SAP HANA](desktop-directquery-sap-hana.md)
