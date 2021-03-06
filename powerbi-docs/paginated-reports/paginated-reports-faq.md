---
title: 'Отчеты с разбивкой на страницы в Power BI: Часто задаваемые вопросы'
description: В этой статье содержатся ответы на часто задаваемые вопросы об отчетах с разбивкой на страницы. Это отчеты с широкой поддержкой форматирования и идеальной попиксельной оптимизацией для печати или создания PDF.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 10/19/2020
ms.openlocfilehash: 2a0490106d5954a57abea1dd5de61f26f2fe2377
ms.sourcegitcommit: eab5a02520c421a57019595c03e9ecfdb41d52ad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "92257032"
---
# <a name="paginated-reports-in-power-bi-faq"></a>Отчеты с разбивкой на страницы в Power BI: Часто задаваемые вопросы 

В этой статье содержатся ответы на часто задаваемые вопросы об отчетах с разбивкой на страницы. Это отчеты с широкой поддержкой форматирования и идеальной попиксельной оптимизацией для печати или создания PDF. Под термином "с разбивкой на страницы" подразумевается то, что формат отчетов подбирается с учетом отображения на нескольких страницах. Отчеты с разбивкой на страницы создаются на основе технологии RDL (языка определения отчетов), используемой в SQL Server Reporting Services. 

В этой статье содержатся ответы на многие распространенные вопросы, которые возникают у пользователей об отчетах с разбивкой на страницы в Power BI Premium, и о специальном средстве для создания отчетов с разбивкой на страницы, которое называется "построитель отчетов". Для публикации отчета в службе нужна лицензия Power BI Pro. Вы можете публиковать и совместно использовать отчеты с разбивкой на страницы в разделе "Моя рабочая область" или в рабочей области, которая находится в емкости Power BI Premium. 

## <a name="administration"></a>Администрирование

### <a name="what-size-premium-capacity-do-i-need-for-paginated-reports"></a>Какой размер емкости Premium требуется для отчетов с разбивкой на страницы?

Рабочая нагрузка отчетов с разбивкой на страницы доступна для номеров SKU P1 – P3.  Вы также можете использовать ее в сценариях внедрения или тестирования и разработки в номерах SKU A4–A6.

### <a name="what-is-the-maximum-memory-threshold-i-can-put-for-paginated-reports-in-my-capacity"></a>Какое максимальное пороговое значение памяти я могу указать в моей емкости для отчетов с разбивкой на страницы?

Вы можете использовать до 100 % памяти для этой рабочей нагрузки.

### <a name="how-does-user-access-work-for-paginated-reports"></a>Как работает доступ пользователей к отчетам с разбивкой на страницы?

Доступ пользователей к отчетам с разбивкой на страницы организован так же, как к любому содержимому в службе Power BI. 

### <a name="how-do-i-turn-onoff-my-paginated-reports-workload"></a>Как мне включить или выключить рабочую нагрузку "Отчеты с разбивкой на страницы"?

Рабочую нагрузку "Отчеты с разбивкой на страницы" может включить и (или) выключить администратор емкости на странице портала администрирования емкости.  Для всех новых емкостей эта рабочая нагрузка будет включена по умолчанию, но она не будет потреблять ресурсы памяти, пока вы не отправите первый отчет с разбивкой на страницы.  

### <a name="how-can-i-monitor-usage-of-paginated-reports-in-my-tenant"></a>Как мне отслеживать использование отчетов с разбивкой на страницы в клиенте?

В журналах аудита Microsoft 365 сохраняется подробная информация об использовании отчетов этого типа во время следующих событий:

- просмотр отчета Power BI;
- удаление отчета Power BI;
- создание отчета Power BI;
- Скачанный отчет Power BI

Для отчетов с разбивкой на страницы поле ReportType имеет значение PaginatedReport, чтобы отличать их от обычных отчетов Power BI.

Также журналы аудита предоставляют для отчетов с разбиением на страницы данные о следующих событиях:

- привязка набора данных Power BI к шлюзу;
- обнаружение источника данных Power BI;
- TakeOverDatasource

### <a name="can-i-monitor-this-workload-through-the-premium-capacity-monitoring-app"></a>Могу ли я отслеживать эту рабочую нагрузку через приложение мониторинга емкости Premium?

Да, мониторинг доступен на новой вкладке с теми же важными данными, что и для наборов данных Power BI.

### <a name="do-i-need-a-pro-license-to-create-and-publish-paginated-reports"></a>Нужна ли лицензия Pro, чтобы создавать и публиковать отчеты с разбивкой на страницы?

Без лицензии Pro вы можете отправлять отчеты с разбивкой на страницы в "Мою рабочую область" при условии, что она имеет емкость Premium.  У вас должна быть лицензия Pro для других рабочих областей, чтобы создавать и публиковать в них содержимое. Мы рекомендуем вам загружать и использовать построитель отчетов Power BI даже без лицензии Pro, но вы не сможете публиковать отчеты с разбивкой на страницы, созданные без него. 

### <a name="what-if-i-have-a-paginated-report-in-a-workspace-and-the-paginated-report-workload-is-turned-off"></a>Что произойдет, если в моей рабочей области есть отчет с разбивкой на страницы, но рабочая нагрузка "Отчеты с разбивкой на страницы" в ней отключена?

Вы получите сообщение об ошибке и не сможете просмотреть такой отчет, пока не включите эту рабочую нагрузку. Но вы можете спокойно удалить этот отчет из рабочей области.

### <a name="what-is-the-default-memory-for-each-of-the-premium-skus-that-support-paginated-reports"></a>Каков объем памяти по умолчанию для каждого номера SKU уровня Premium, поддерживающего отчеты с разбивкой на страницы?

Объем памяти по умолчанию для отчетов с разбивкой на страницы для номеров SKU уровня Premium составляет:

- **P1/A4** . По умолчанию 20 %; не менее 10 %
- **P2/A5** . По умолчанию 20 %; не менее 5 %
- **P3/A6** . По умолчанию 20 %; не менее 2,5 %

Администраторы Power BI могут изменять максимальный процент памяти по умолчанию на портале администрирования. Перейдите в раздел рабочей нагрузки **Отчеты с разбивкой на страницы** на вкладке **Параметры емкости** страницы **Power BI Premium** .

:::image type="content" source="media/paginated-reports-faq/paginated-reports-capacity-settings.png" alt-text="Раздел Отчеты с разбивкой на страницы на вкладке Параметры емкости":::

## <a name="general"></a>Общие

### <a name="when-should-i-use-a-paginated-report-vs-a-power-bi-report"></a>В каких случаях отчет с разбивкой на страницы больше подходит, чем отчет Power BI?

Отчеты с разбивкой на страницы подходят в тех случаях, когда важны широкая поддержка форматирования и идеальная попиксельная оптимизация для печати или создания PDF.  Например, отчет с разбивкой на страницы будет правильным выбором для создания отчета о результатах финансовой деятельности организации.  

Отчеты Power BI оптимизированы для исследования данных и интерактивных возможностей.  В формате отчета Power BI лучше создавать, например, отчет о продажах с возможностью выборки данных по конкретным регионам, отраслям и клиентам и с мгновенным отображением соответствующих подытогов.

Дополнительные сведения см. в разделе [В каких случаях использовать отчеты с разбивкой на страницы в Power BI](../guidance/report-paginated-or-power-bi.md).

### <a name="the-documentation-says-power-bi-report-builder-is-the-preferred-authoring-tool-can-i-create-paginated-reports-in-sql-server-data-tools-for-power-bi"></a>В документации сказано, что построитель отчетов Power BI является основным средством разработки. Но могу ли я создавать отчеты с разбивкой на страницы в SQL Server Data Tools для Power BI?

Да, но служба Power BI позволяет передать за раз только один элемент, поэтому она пока не поддерживает многие распространенные сценарии разработки в SQL Server Data Tools (SSDT). Полный [список неподдерживаемых функций](#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi) размещен далее в этой статье с вопросами и ответами.  

### <a name="what-versions-of-report-builder-do-you-support"></a>Какие версии построителя отчетов поддерживаются?

Мы выпустили Power BI Report Builder в качестве основного средства создания отчетов с разбивкой на страницы в службе Power BI. Установите [построитель отчетов Power BI из Центра загрузки Майкрософт](https://aka.ms/pbireportbuilder).

### <a name="how-do-i-move-existing-reports-i-have-saved-in-sql-server-reporting-services-to-power-bi"></a>Как переместить в Power BI существующие отчеты, сохраненные в SQL Server Reporting Services (SSRS)?

Проект на сайте GitHub теперь поддерживает миграцию содержимого из SQL Server Reporting Services в Power BI.  Просмотрите сведения и скачайте средство: [https://github.com/microsoft/RdlMigration](https://github.com/microsoft/RdlMigration)

### <a name="can-i-open-reports-and-publish-directly-to-the-service"></a>Могу ли я открывать и публиковать отчеты непосредственно в службе?

Да. Мы добавили возможность открывать и публиковать отчеты непосредственно в службе из Power BI Report Builder.

### <a name="what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi"></a>Какие функции SSRS для отчетов с разбивкой на страницы пока не поддерживаются в Power BI?

В настоящее время отчеты с разбивкой на страницы не поддерживают следующие элементы:

- общие источники данных;
- Общие наборы данных
- Детализация и переход по другим отчетам
- связанные отчеты;
- пользовательские шрифты;

Вы получите сообщение об ошибке при попытке отправить файл с функцией, которая пока не поддерживается в службе Power BI, за исключением функций переключения и (или) сортировки.

### <a name="what-data-sources-do-you-support-currently-for-paginated-reports"></a>Какие источники данных поддерживаются сейчас для отчетов с разбивкой на страницы?

Список источников данных см. в статье [Поддерживаемые источники данных для отчетов с разбивкой на страницы Power BI](paginated-reports-data-sources.md). 

### <a name="what-authentication-methods-do-you-support"></a>Какие методы проверки подлинности поддерживаются?

Мы поддерживаем единый вход для источников данных Power BI, Azure Analysis Services и базы данных SQL Azure.  Мы также поддерживаем OAuth для базы данных SQL Azure и Azure Analysis Services.  Для других источников данных сейчас необходимо сохранять на портале или шлюзе имя пользователя и пароль для доступа к источнику данных.  

### <a name="can-i-use-a-power-bi-dataset-as-a-data-source-for-my-paginated-report"></a>Могу ли я использовать набор данных Power BI в качестве источника данных для отчета с разбивкой на страницы?

Да, наборы данных Power BI поддерживаются в качестве источников данных для отчетов с разбивкой на страницы.

### <a name="can-i-use-stored-procedures-through-the-gateway"></a>Могу ли я использовать хранимые процедуры через шлюз?

Да, использование хранимых процедур через шлюз поддерживается для источников данных SQL Server, включая те, которые используют параметры.

### <a name="what-export-formats-are-available-for-my-report-in-the-power-bi-service"></a>Какие форматы экспорта доступны для отчетов в службе Power BI?

Вы можете экспортировать отчеты в Microsoft Excel, Microsoft Word, Microsoft PowerPoint, PDF, CSV, XML и MHTML.

### <a name="can-i-print-paginated-reports"></a>Могу ли я распечатать отчет с разбивкой на страницы?

Да, для отчетов с разбивкой на страницы доступна распечатка, включая новый и улучшенный интерфейс предварительной версии печати. 

### <a name="are-e-mail-subscriptions-available-for-paginated-reports"></a>Доступна ли подписка по электронной почте на отчеты с разбивкой на страницы?

Да, подписки по электронной почте полностью поддерживаются для отчетов с разбивкой на страницы и включают поддержку шести различных форматов файлов и значений параметров.

### <a name="can-i-run-custom-code-in-my-report"></a>Могу ли я запускать в отчете пользовательский код?

Да, мы поддерживаем возможность запуска пользовательского кода в отчетах, как и в службе SSRS.

### <a name="can-i-use-power-bi-embedded-to-embed-my-paginated-reports-into-an-app-im-hosting"></a>Могу ли я с помощью Power BI Embedded внедрить отчеты с разбивкой на страницы в размещаемое приложение?

Внедрение SaaS, включая поддержку безопасного внедрения, уже доступно. Сведения о внедрении PaaS см. в разделе [Внедрение отчетов Power BI с разбивкой на страницы в приложение для клиентов](../developer/embedded/embed-paginated-reports-customers.md).

### <a name="can-i-drill-through-from-a-power-bi-report-to-a-paginated-report"></a>Могу ли я переходить из отчета Power BI в отчет с разбивкой на страницы для просмотра подробных сведений?

Да. Для этого можно использовать параметры URL-адреса в отчетах с разбивкой на страницы.

### <a name="can-i-share-my-paginated-report-content-through-a-power-bi-app"></a>Могу ли я использовать содержимое из отчета с разбивкой на страницы в приложении Power BI?

Да, отчеты с разбивкой на страницы поддерживаются для развертывания с приложениями из рабочих областей v1 и v2. 

### <a name="will-other-report-specific-features-in-power-bi-like-pinning-report-tiles-to-dashboards-work-with-paginated-reports"></a>Будут ли работать для отчетов с разбивкой на страницы другие функции отчетов в Power BI, например закрепление плиток на панелях мониторинга?

Мы планируем обеспечить для отчетов максимально возможную поддержку всех основных сценариев работы службы.  В идеале должно быть так, чтобы пользователь воспринимал эти отчеты так же, как и другие элементы в списке отчетов на портале, несмотря на использование другого средства для их создания. Пользователю не важно, как создан отчет, ему лишь нужно выполнить свою задачу.  Хорошим примером равенства функций можно считать запланированную поддержку комментариев. Эта функция будет работать немного по-разному для отчетов разных типов, но вы сможете использовать комментарии для обоих типов.

### <a name="is-there-a-report-viewer-control-for-paginated-reports-in-the-power-bi-service"></a>Существует ли элемент управления для просмотра отчетов с разбивкой на страницы в службе Power BI?

Нет, в настоящее время не существует элементов управления для просмотра отчетов.

### <a name="can-you-search-for-paginated-reports-from-the-new-home-experience-in-the-power-bi-service"></a>Можно ли найти отчет с разбивкой на страницы через новый интерфейс главной страницы в службе Power BI?

Да, сейчас вы можете выполнять поиск отчетов с разбивкой на страницы на домашней странице.  Но вы также будете их видеть в других разделах нового интерфейса домашней страницы.

## <a name="considerations-and-troubleshooting"></a>Рекомендации и устранение неполадок
При работе с полями DateTime в отчетах с разбивкой на страницы необходимо учитывать указанные ниже моменты.

- В настоящее время существуют некоторые ограничения на глобализацию, связанные с параметрами DateTime. Все параметры типа DateTime в службе Power BI извлекаются в формате США (ММ/ДД/ГГГГ) независимо от того, как они были созданы в построителе отчетов Power BI.

При просмотре отчетов с разбивкой на страницы в службе Power BI может истечь время ожидания сеансов, и пользователь получит следующее уведомление:

:::image type="content" source="media/paginated-reports-faq/expired-session-notification.png" alt-text="Раздел Отчеты с разбивкой на страницы на вкладке Параметры емкости":::

- Время ожидания сеанса истечет после 60 минут бездействия либо ранее, если устройство заблокировано или неактивно либо если отчет не отображается на активной вкладке в браузере.

## <a name="next-steps"></a>Дальнейшие действия

- [Установка построителя отчетов Power BI из Центра загрузки Майкрософт](https://aka.ms/pbireportbuilder)
- [Руководство. Создание отчета с разбивкой на страницы](paginated-reports-quickstart-aw.md)
