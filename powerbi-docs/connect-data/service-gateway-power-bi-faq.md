---
title: Вопросы и ответы о локальном шлюзе данных — Power BI
description: В этой статье приводятся вопросы и ответы о локальном шлюзе данных для Power BI. В этой статье собраны все часто задаваемые вопросы о шлюзе, используемом в Power BI.
author: arthiriyer
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: arthii
LocalizationGroup: Gateways
ms.openlocfilehash: f64fcd86d54c20e1318d38c2a73e9bca2174558a
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83302674"
---
# <a name="on-premises-data-gateway-faq---power-bi"></a>Вопросы и ответы о локальном шлюзе данных — Power BI

[!INCLUDE [gateway-rewrite](../includes/gateway-rewrite.md)]

## <a name="power-bi"></a>Power BI

**Вопрос.** Нужно ли обновлять локальный шлюз данных (персональный режим)?

**Ответ.** Нет, вы можете продолжать использовать шлюз (персональный режим) для работы с Power BI.

**Вопрос.** Требуются ли специальные разрешения для установки шлюза и управления им в службе Power BI?

**Ответ.** Специальные разрешения не требуются.

**Вопрос.** Можно ли отправлять книги Excel с моделями данных Power Pivot, которые подключаются к локальным источникам данных? Требуется ли для этого шлюз? 

**Ответ.** Да, такую книгу можно отправить. И нет, шлюз для этого не нужен. Но так как данные будут размещены в модели данных Excel, отчеты в Power BI на основе книги Excel не будут динамическими. Чтобы обновить отчеты в Power BI, вам придется каждый раз повторно загружать обновленную книгу. Вы также можете воспользоваться шлюзом с запланированным обновлением.

**Вопрос.** Когда пользователи совместно работают с панелями мониторинга, для которых настроено подключение DirectQuery, смогут ли они видеть данные, если у них разные разрешения? 

**Ответ.** На панели мониторинга, подключенной к службам Azure Analysis Services, пользователи видят только те данные, к которым у них есть доступ. Если пользователи имеют разные разрешения, они не смогут просматривать данные. Для других источников администратор задает для всех пользователей одинаковые учетные данные.

**Вопрос.** Почему я не могу подключиться к серверу Oracle? 

**Ответ.** Чтобы подключиться к серверу Oracle, может потребоваться установить клиент Oracle и указать в файле tnsnames.ora необходимую информацию о сервере. Эта установка выполняется отдельно за пределами шлюза. Дополнительные сведения см. в статье [Установка клиента Oracle](service-gateway-onprem-manage-oracle.md#install-the-oracle-client).

**Вопрос.** Я использую скрипты R. Он поддерживается?

**Ответ.** Скрипты R поддерживаются только в персональном режиме.

## <a name="analysis-services-in-power-bi"></a>Analysis Services в Power BI

**Вопрос.** Можно ли использовать библиотеку msdmpump.dll для создания настраиваемого сопоставления действующих имен пользователей для Analysis Services? 

**Ответ.** Нет. В настоящее время это не поддерживается.

**Вопрос.** Можно ли использовать шлюз для подключения к экземпляру многомерного OLAP? 

**Ответ.** Да. Локальный шлюз данных поддерживает активные подключения как к табличным, так и к многомерным моделям Analysis Services.

**Вопрос.** Что будет, если я установлю шлюз на компьютер в домене, отличном от домена моего локального сервера, который использует проверку подлинности Windows? 

**Ответ.** Здесь ничего нельзя гарантировать. Все зависит от отношений доверия между двумя доменами. Если два разных домена созданы в модели доверенных доменов, то шлюз может подключиться к серверу служб Analysis Services и разрешить доверенное имя пользователя. В противном случае может возникнуть ошибка входа.

**Вопрос.** Как узнать, какое действующее имя пользователя передается на мой локальный сервер служб Analysis Services? 

**Ответ.** Ответ на этот вопрос есть в [статье об устранении неполадок](service-gateway-onprem-tshoot.md).

## <a name="next-steps"></a>Дальнейшие действия

* [Устранение неполадок локального шлюза данных](/data-integration/gateway/service-gateway-tshoot)

Появились дополнительные вопросы? Ответы на них см. в [сообществе Power BI](https://community.powerbi.com/).