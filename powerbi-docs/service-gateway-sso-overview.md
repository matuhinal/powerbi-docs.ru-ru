---
title: Использование единого входа в локальные источники данных
description: Настройте шлюз, чтобы включить единый вход (SSO) из Power BI в локальные источники данных.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 10/15/2018
LocalizationGroup: Gateways
ms.openlocfilehash: b728ba6ebaab81ea475f51b9134de34c37d4149b
ms.sourcegitcommit: 3b1a1f55465e5dca88783046c6b4c073e4e22e4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "51580501"
---
# <a name="overview-of-single-sign-on-sso-for-gateways-in-power-bi"></a>Общие сведения о едином входе (SSO) для шлюзов в Power BI

Вы можете быстро установить подключение с единым входом, включив обновление отчетов и панели мониторинга Power BI с помощью данных из локальной среды. Для этого настройте локальный шлюз данных либо с ограниченным делегированием Kerberos, либо с SAML. Локальный шлюз данных упрощает единый вход (SSO) с помощью функции DirectQuery, которая используется для подключения к локальным источникам данных.

В настоящее время поддерживаются следующие источники данных:

* SQL Server ([Kerberos](service-gateway-sso-kerberos.md))
* SAP HANA ([Kerberos](service-gateway-sso-kerberos.md) и [SAML](service-gateway-sso-saml.md))
* SAP BW ([Kerberos](service-gateway-sso-kerberos.md)
* Teradata ([Kerberos](service-gateway-sso-kerberos.md))
* Spark ([Kerberos](service-gateway-sso-kerberos.md))
* Impala ([Kerberos](service-gateway-sso-kerberos.md))

Когда пользователь работает с отчетом DirectQuery в службе Power BI, каждая операция перекрестной фильтрации, среза, сортировки и редактирования отчета генерирует запросы, которые в режиме реального времени отправляются в основной источник данных в локальной среде.  Если для источника данных настроен единый вход, запросы выполняются с идентификатором пользователя, работающего в Power BI (то есть через веб-интерфейс или мобильные приложения Power BI). Таким образом, каждый пользователь может просмотреть данные, доступ к которым ему разрешен в основном источнике данных. Если настроен единый вход, общее кэширование данных разных пользователей не выполняется.

## <a name="query-steps-when-running-sso"></a>Действия запроса при выполнении единого входа

Запрос, который выполняется с единым входом, состоит из трех этапов, которые представлены на следующей схеме:

![Шаги запроса, выполняемого с единым входом](media/service-gateway-sso-overview/sso-query-steps.png)

> [!NOTE]
> Единый вход для Oracle еще не предусмотрен, но находится в разработке и ожидается в ближайшее время.

Ниже приведены дополнительные сведения об этих действиях:

1. При отправке каждого запроса в настроенный шлюз **служба Power BI** включает *имя субъекта-пользователя*.

2. Шлюз должен сопоставить имя субъекта-пользователя Azure с локальным идентификатором Active Directory.

   а.  Если решение Azure AD DirSync (также известное как *AAD Connect*) настроено, то сопоставление выполнится на этом шлюзе автоматически.

   б.  В противном случае шлюз может выполнить поиск и сопоставить имя участника-пользователя Azure AD с локальным пользователем, выполнив поиск в домене локальной версии Active Directory.

3. После сопоставления процесс службы шлюза олицетворяет локального пользователя, устанавливает подключение к базе данных и отправляет запрос. Шлюз не обязательно устанавливать на том же компьютере, что и базу данных.

## <a name="next-steps"></a>Дальнейшие действия

Теперь, когда вы знакомы с основами единого входа, более подробно изучите Kerberos и SAML:

* [Единый вход (SSO) с помощью Kerberos](service-gateway-sso-kerberos.md)
* [Единый вход (SSO) с помощью SAML](service-gateway-sso-saml.md)