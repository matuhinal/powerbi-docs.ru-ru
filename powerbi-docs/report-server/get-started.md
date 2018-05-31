---
title: Что такое Сервер отчетов Power BI?
description: Общие сведения о Сервере отчетов Power BI и его взаимодействии со службой SQL Server Reporting Services (SSRS) и остальными компонентами Power BI.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.date: 05/07/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.openlocfilehash: 1be2270074011f73c3d942677211dd99d18c6b2b
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
ms.locfileid: "34294578"
---
# <a name="what-is-power-bi-report-server"></a>Что такое Сервер отчетов Power BI?

Сервер отчетов Power BI — это локальный сервер отчетов с веб-порталом, на котором вы можете просматривать и администрировать отчеты и ключевые показатели эффективности, а также дополнительными инструментами для создания отчетов Power BI, отчетов с разбивкой на страницы, мобильных отчетов и ключевых показателей эффективности. У пользователей есть несколько вариантов доступа к этим отчетам: просмотр в веб-браузере, просмотр на мобильном устройстве, получение в виде сообщения электронной почты.

![Веб-портал сервера отчетов Power BI](media/get-started/power-bi-report-server-overview.png)

## <a name="comparing-power-bi-report-server"></a>Сравнительный анализ Сервера отчетов Power BI 
Функции Сервера отчетов Power BI похожи на функции SQL Server Reporting Services и веб-службы Power BI. На службу Power BI Сервер отчетов Power BI похож возможностью размещать отчеты Power BI (.PBIX) и файлы Excel. На Reporting Services Сервер отчетов Power BI похож локальным размещением и возможностью размещать отчеты с разбивкой на страницы (.RDL). Сервер отчетов Power BI является надмножеством Reporting Services и, соответственно, поддерживает все функции Reporting Services, а также ряд дополнительных возможностей, включая отчеты Power BI. См. дополнительные сведения о [сравнении Сервера отчетов Power BI и службы Power BI](compare-report-server-service.md).

## <a name="licensing-power-bi-report-server"></a>Лицензирование Сервера отчетов Power BI
Сервер отчетов Power BI можно использовать с двумя разными лицензиями: [Power BI Premium](../service-premium.md) или [SQL Server Enterprise Edition](https://www.microsoft.com/sql-server/sql-server-2017-editions) по программе Software Assurance. Лицензия Power BI Premium позволяет создавать гибридные развертывания, сочетающие облачные и локальные технологии.  

## <a name="web-portal"></a>Веб-портал
Основной точкой взаимодействия с Сервером отчетов Power BI является защищенный веб-портал, который можно просматривать в любом современном браузере. Здесь вам доступны все отчеты и ключевые показатели эффективности. Содержимое веб-портала организовано в традиционную иерархию папок. Содержимое в этих папках группируется по следующим типам: отчеты Power BI, мобильные отчеты, отчеты с разбивкой на страницы, ключевые показатели эффективности и книги Excel, а также общие наборы данных и общие источники данных в качестве стандартных блоков для создания отчетов. Вы можете отмечать избранные элементы, чтобы просматривать их в отдельной папке. Можно также создавать ключевые показатели эффективности прямо на веб-портале. 

![Веб-портал сервера отчетов Power BI](media/get-started/web-portal.png)

Вы можете управлять содержимым веб-портала в зависимости от предоставленных вам разрешений. Вы можете планировать обработку отчетов, открывать отчет по требованию и (или) подписываться на регулярно публикуемые отчеты. Также вы можете применять к веб-порталу оформление с [фирменной символикой](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal). 

См. дополнительные сведения о [веб-портале (основной режим служб SSRS)](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).

## <a name="power-bi-reports"></a>Отчеты Power BI
Версия Power BI Desktop, оптимизированная для сервера отчетов, позволяет создавать отчеты Power BI (.PBIX). Вы можете опубликовать и просматривать их на веб-портале в созданной вами среде.

![Отчеты Power BI на Сервере отчетов Power BI](media/get-started/powerbi-reports.png)

Отчет Power BI — это разностороннее представление модели данных на основе визуализаций, которые отображают разные результаты и сведения о выбранной модели данных.  В отчете может быть одна визуализация или несколько страниц, заполненных визуализациями. В зависимости от назначенной вам роли, вы можете читать и изучать отчеты или создавать новые отчеты для других пользователей.

[Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI](quickstart-create-powerbi-report.md).

## <a name="paginated-reports"></a>Отчеты с разбивкой на страницы
Отчеты с разбивкой на страницы (.RDL) — это отчеты в формате документа с визуализациями, позволяющие расширять таблицы горизонтально и (или) вертикально на несколько страниц, чтобы поместить все необходимые данные. Они отлично подходят для создания документов с фиксированным макетом и разрешением, оптимизированных для печати, например файлов в формате PDF и Word.

![Отчеты с разбивкой на страницы на Сервере отчетов Power BI](media/get-started/paginated-reports.png)

Для создания этих современных отчетов используется [построитель отчетов](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016) или конструктор отчетов в [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt).

## <a name="reporting-services-mobile-reports"></a>Мобильные отчеты Reporting Services
Мобильные отчеты подключаются к локальным источникам данных и имеют удобный макет, который адаптируется к разным типам, форматам и ориентациям устройств. Для создания таких отчетов применяется издатель мобильных отчетов для SQL Server.

См. дополнительные сведения о [мобильных отчетах Reporting Services](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher). 

## <a name="report-server-programming-features"></a>Функции программирования сервера отчетов
Воспользуйтесь преимуществами функций программирования сервера отчетов Power BI, чтобы расширять и настраивать возможности отчетов с помощью API-интерфейсов для интеграции или расширения данных и обработки отчетов в пользовательских приложениях.

См. дополнительные сведения в [документации разработчика сервера отчетов](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation).

## <a name="next-steps"></a>Дальнейшие действия
[Установка сервера отчетов Power BI](install-report-server.md)  
[Install Report Builder](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder) (Установка построителя отчетов)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)


