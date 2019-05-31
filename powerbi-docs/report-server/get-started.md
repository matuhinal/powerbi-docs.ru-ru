---
title: Что такое Сервер отчетов Power BI?
description: Общие сведения о Сервере отчетов Power BI и его взаимодействии со службой SQL Server Reporting Services (SSRS) и остальными компонентами Power BI.
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.date: 05/22/2019
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.openlocfilehash: 37751117853c8bca686585992108c006c6c76b70
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187481"
---
# <a name="what-is-power-bi-report-server"></a>Что такое Сервер отчетов Power BI?

Сервер отчетов Power BI — это локальный сервер отчетов с веб-порталом, на котором можно просматривать отчеты и ключевые показатели эффективности и управлять ими. Он включает инструменты, позволяющие создавать отчеты Power BI, отчеты с разбивкой на страницы, мобильные отчеты и ключевые показатели эффективности. У пользователей есть несколько вариантов доступа к этим отчетам: просмотр в веб-браузере, просмотр на мобильном устройстве, получение в виде сообщения электронной почты.

![Веб-портал сервера отчетов Power BI](media/get-started/power-bi-report-server-overview.png)

## <a name="comparing-power-bi-report-server"></a>Сравнительный анализ Сервера отчетов Power BI 
Функции Сервера отчетов Power BI похожи на функции SQL Server Reporting Services и веб-службы Power BI. Как и служба Power BI, Power BI Report Server размещает отчеты Power BI (. Pbix-ФАЙЛ) файлы Excel и отчеты с разбивкой на страницы (. ЯЗЫК ОПРЕДЕЛЕНИЯ ОТЧЕТОВ). Как службы Reporting Services сервер отчетов Power BI — на локальном компьютере. Power BI Report Server функции являются подмножеством для служб Reporting Services: позволяет выполнять любые действия в службах Reporting Services, можно делать с сервера отчетов Power BI, а также для отчетов Power BI. См. дополнительные сведения о [сравнении Сервера отчетов Power BI и службы Power BI](compare-report-server-service.md).

## <a name="licensing-power-bi-report-server"></a>Лицензирование Сервера отчетов Power BI
Сервер отчетов Power BI можно использовать с двумя разными лицензиями: [Power BI Premium](../service-premium-what-is.md) или [SQL Server Enterprise Edition](https://www.microsoft.com/sql-server/sql-server-2017-editions) по программе Software Assurance. Лицензия Power BI Premium позволяет создавать гибридные развертывания, сочетающие облачные и локальные технологии.  

> [!NOTE]
> Для Power BI Premium Сервер отчетов Power BI доступен только в SKU серии P. Он не входит в SKU серии EM.

## <a name="web-portal"></a>Веб-портал
Основной точкой взаимодействия с Сервером отчетов Power BI является защищенный веб-портал, который можно просматривать в любом современном браузере. Здесь вам доступны все отчеты и ключевые показатели эффективности. Содержимое веб-портала организовано в традиционную иерархию папок. В папках содержимое группируются по типу: отчеты Power BI, мобильные отчеты, отчеты с разбивкой на страницы, ключевые показатели эффективности и книги Excel. Общие наборы данных и общие источники данных находятся в собственных папках и используются в качестве стандартных блоков для отчетов. Вы можете отмечать избранные элементы, чтобы просматривать их в отдельной папке. Можно также создавать ключевые показатели эффективности прямо на веб-портале. 

![Веб-портал сервера отчетов Power BI](media/get-started/web-portal.png)

Вы можете управлять содержимым веб-портала в зависимости от предоставленных вам разрешений. Вы можете планировать обработку отчетов, открывать отчет по требованию и (или) подписываться на регулярно публикуемые отчеты. Также вы можете применять к веб-порталу оформление с [фирменной символикой](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal). 

См. дополнительные сведения о [веб-портале (основной режим служб SSRS)](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode).

## <a name="power-bi-reports"></a>Отчеты Power BI
Версия Power BI Desktop, оптимизированная для сервера отчетов, позволяет создавать отчеты Power BI (.PBIX). Вы можете опубликовать и просматривать их на веб-портале в созданной вами среде.

![Отчеты Power BI на Сервере отчетов Power BI](media/get-started/powerbi-reports.png)

Отчет Power BI — это разностороннее представление модели данных на основе визуализаций, которые отображают разные результаты и сведения о выбранной модели данных.  В отчете может быть одна визуализация или несколько страниц, заполненных визуализациями. В зависимости от назначенной вам роли, вы можете читать и изучать отчеты или создавать новые отчеты для других пользователей.

Узнайте о [Установка Microsoft Power BI Desktop](install-powerbi-desktop.md).

## <a name="paginated-reports"></a>Отчеты с разбивкой на страницы
Отчеты с разбивкой на страницы (.RDL) — это отчеты в формате документа с визуализациями, позволяющие расширять таблицы горизонтально и (или) вертикально на несколько страниц, чтобы поместить все необходимые данные. Они отлично подходят для создания документов с фиксированным макетом и разрешением, оптимизированных для печати, например файлов в формате PDF и Word. 

![Отчеты с разбивкой на страницы на Сервере отчетов Power BI](media/get-started/paginated-reports.png)

Можно создать с разбивкой на страницы отчетов, с помощью [построитель отчетов](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016) или конструктор отчетов в [SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt).

## <a name="reporting-services-mobile-reports"></a>Мобильные отчеты Reporting Services
Мобильные отчеты подключаются к локальным источникам данных и имеют удобный макет, который адаптируется к разным типам, форматам и ориентациям устройств. Для создания таких отчетов применяется издатель мобильных отчетов для SQL Server.

См. дополнительные сведения о [мобильных отчетах Reporting Services](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher). 

## <a name="report-server-programming-features"></a>Функции программирования сервера отчетов
Воспользуйтесь преимуществами функций программирования сервера отчетов Power BI, чтобы расширять и настраивать отчеты с помощью API-интерфейсов для интеграции или расширения данных и обработки отчетов в пользовательских приложениях.

См. дополнительные сведения в [документации разработчика сервера отчетов](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation).

## <a name="next-steps"></a>Дальнейшие действия
[Установка сервера отчетов Power BI](install-report-server.md)  
[Загрузка построителя отчетов](https://www.microsoft.com/download/details.aspx?id=53613)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)


