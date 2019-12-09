---
title: URL-адреса Power BI для списка разрешений
description: В этой статье описываются конечные точки, которые должны быть доступны для клиентов, использующих Power BI.
author: kfollis
ms.author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/22/2018
ms.custom: seodec18
ms.openlocfilehash: cd13e36ca7216036a22db332a508e3c825fecf4b
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2019
ms.locfileid: "74698792"
---
# <a name="power-bi-urls-for-whitelisting"></a>URL-адреса Power BI для списка разрешений

**Веб-службе Power BI**, также известной как приложение SaaS (программное обеспечение как услуга) Power BI, требуется подключение к Интернету. Конечные точки ниже должны быть доступны для клиентов, использующих веб-службу Power BI.

Для использования веб-службы Power BI необходимо иметь доступ к конечным точкам, помеченным как **обязательные**, в таблицах ниже и всем конечным точкам, помеченным как **обязательные** на связанных сайтах. Если ссылка на внешний сайт указывает на конкретный раздел, вам потребуется проверить только конечные точки в этом разделе.

Конечные точки, помеченные как **необязательные**, могут также входить в **утвержденный список** для работы определенных функций.

Для работы веб-службы Power BI для указанных конечных точек требуется открыть только TCP-порт 443.

Подстановочные знаки (*) представляют все уровни в корневом домене. Когда информация недоступна, используется "н/д". Столбец **Назначения** представляет собой список полных доменных имен или имен доменов и ссылок на внешние веб-сайты, которые содержат дополнительные сведения о конечной точке.

>[!Important]
>Сведения в приведенных ниже таблицах не представляют **облако для государственных организаций США**, **облако Германии** и **облако Китая**.

## <a name="authentication"></a>Authentication

Работа Power BI зависит от необходимых конечных точек в разделах идентификации и проверки подлинности Office 365. Для использования Power BI необходимо подключиться к конечным точкам в связанном веб-сайте ниже.

| Строка | Цель | Назначение(я) | Порт(ы) |
| --- | --- | --- | --- |
| 1 | **Требуется:** проверка подлинности и идентификация | См. документацию Office 365 по [URL-адресам для Office Online и общим URL-адресам](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online)  | Н/Д |

## <a name="general-site-usage"></a>Общее использование сайта

Для общего использования Power BI необходимо подключиться к конечным точкам в таблице и связанных веб-сайтах ниже.

| Строка | Цель | Назначение(я) | Порт(ы) |
| --- | --- | --- | --- |
| 1 | **Требуется:** cерверные API | *.analysis.windows.net | TCP 443 |
| 2 | **Требуется:** интеграция с Office 365 | См. документацию Office 365 по [URL-адресам для Office Online и общим URL-адресам](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | Н/Д |
| 3 | **Требуется:** портал | app.powerbi.com | TCP 443 |
| 4 | **Требуется:** телеметрия службы | dc.services.visualstudio.com | TCP 443 |
| 5 | **Необязательно:** информационные сообщения | dynmsg.modpim.com | TCP 443 |
| 6 | **Необязательно:** опросы сервера политики сети | nps.onyx.azure.net | TCP 443 |
| | | |

## <a name="administration"></a>Администрирование

Для выполнения административных функций в Power BI необходимо иметь возможность подключения к конечным точкам в связанных сайтах ниже.

| Строка | Цель | Назначение(я) | Порт(ы) |
| --- | --- | --- | --- |
| 1 | **Требуется** для управления пользователями и просмотра журналов аудита | См. документацию Office 365 по [URL-адресам для Office Online и общим URL-адресам](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | Н/Д |
| | | |

## <a name="getting-data"></a>Получение данных

Чтобы получать данные из конкретных источников данных, таких как OneDrive, потребуется подключаться к конечным точкам в таблице ниже. Для определенных источников данных, используемых в организации, может потребоваться доступ к дополнительным интернет-доменам и URL-адресам.

| Строка | Цель | Назначение(я) | Порт(ы) |
| --- | --- | --- | --- |
| 1 | **Требуется:** AppSource (внутренние или внешние приложения в Power BI) | appsource.microsoft.com <br> *.s-microsoft.com  | TCP 443 |
| 2 | **Необязательно:** вход и получение данных для пакетов содержимого | Зависит от используемых пакетов содержимого | Зависит от используемых пакетов содержимого |
| 3 | **Необязательно:** импорт файлов из OneDrive — персональный | См. раздел [Требуемые URL-адреса и порты для сайта OneDrive](https://docs.microsoft.com/onedrive/required-urls-and-ports). | Н/Д |
| 4 | **Необязательно:** Power BI в 60-секундном учебном видео | *.doubleclick.net <br> *.ggpht.com <br> *.google.com <br> *.googlevideo.com <br> *.youtube.com <br> *.ytimg.com <br> fonts.gstatic.com | TCP 443 |
| 5 | **Необязательно:** источники данных потоковой передачи PubNub | См. [документацию PubNub](https://support.pubnub.com/support/solutions/articles/14000043522). | Н/Д |
| | | |

## <a name="dashboard-and-report-integration"></a>Интеграция панели мониторинга и отчетов

Поддержка панелей мониторингов и отчетов в Power BI зависит от определенных конечных точек. Для этого необходимо подключиться к конечным точкам в таблице и связанных веб-сайтах ниже.

| Строка | Цель | Назначение(я) | Порт(ы) |
| --- | --- | --- | --- |
| 1 | **Требуется:** интеграция с Excel | См. документацию Office 365 по [URL-адресам для Office Online и общим URL-адресам](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | Н/Д |
| | | |

## <a name="custom-visuals"></a>Настраиваемые визуальные элементы

Возможность просмотра и доступа к пользовательским визуальным элементам в Power BI зависит от определенных конечных точек. Для этого необходимо подключиться к конечным точкам в таблице и связанных веб-сайтах ниже.

| Строка | Цель | Назначение(я) | Порт(ы) |
| --- | --- | --- | --- |
| 1 | **Требуется:** импорт пользовательского визуального элемента из интерфейса Marketplace или из файла | *.azureedge.net <br> *.blob.core.windows.net <br> store.office.com | TCP 443 |
| 2 | **Необязательно:** Карты Bing | bing.com <br> platform.bing.com <br> *.virtualearth.net | TCP 443 |
| 3 | **Необязательно:** PowerApps | См. раздел [Необходимые службы](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services) на сайте требований к системе PowerApps. | Н/Д |
| 4 | **Необязательно:** Visio | См. документацию Office 365 по [URL-адресам Office Online и общим URL-адресам](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online), а также по [SharePoint Online и OneDrive для бизнеса](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business). | Н/Д |
| | | |

## <a name="related-external-sites"></a>Связанные внешние сайты

Ссылки Power BI на другие связанные сайты. В число этих сайтов входят сайты документации, поддержки, запросов новых функций и многие другие. Эти сайты не повлияют на функциональные возможности Power BI, поэтому при необходимости их можно включить в список разрешенных.

| Строка | Цель | Назначение(я) | Порт(ы) |
| --- | --- | --- | --- |
| 1 | **Необязательно:** веб-сайт сообщества | community.powerbi.com <br> oxcrx34285.i.lithium.com | TCP 443 |
| 2 | **Необязательно:** Сайт документации | docs.microsoft.com <br> img-prod-cms-rt-microsoft-com.akamaized.net <br> statics-uhf-eas.akamaized.net <br> cdnssl.clicktale.net <br> ing-district.clicktale.net | TCP 443 |
| 3 | **Необязательно:** веб-сайт с материалами для скачивания (для Power BI Desktop и т. д.) | download.microsoft.com | TCP 443 |
| 4 | **Необязательно:** внешние перенаправления | aka.ms <br> go.microsoft.com | TCP 443 |
| 5 | **Необязательно:** веб-сайт обратной связи| ideas.powerbi.com <br> powerbi.uservoice.com | TCP 443 |
| 6 | **Необязательно:** веб-сайт Power BI — целевая страница, ссылки на дополнительные сведения, веб-сайт службы поддержки, ссылки на материалы для скачивания, демонстрации партнеров и т. д. | powerbi.microsoft.com | TCP 443 |
| 7 | **Необязательно:** Центр по разработке для Power BI | dev.powerbi.com | TCP 443 |
| 8 | **Необязательно:** веб-сайт службы поддержки | support.powerbi.com <br> s3.amazonaws.com <br> *.olark.com <br> logx.optimizely.com <br> mscom.demdex.net <br> tags.tiqcdn.com | TCP 443 |
| | | |