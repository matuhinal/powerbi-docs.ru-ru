---
title: Фрагменты панели мониторинга в Power BI для бизнес-пользователей
description: Все о Фрагментх панелей мониторинга в Power BI для бизнес-пользователей. Это плитки, созданные в SQL Server Reporting Services (SSRS).
author: mihart
ms.reviewer: mihart
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: how-to
ms.date: 10/06/2020
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: ab8cfefab74d3120451b56c3ea30518e538ad543
ms.sourcegitcommit: d2f633b4bfa271051ba1d2ef0e6e8da7dcf42818
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2020
ms.locfileid: "91830551"
---
# <a name="dashboard-tiles-in-power-bi"></a>Плитки панели мониторинга в Power BI

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-ynny.md)]

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Фрагмент представляет собой моментальный снимок данных, закрепленный на панели мониторинга при помощи *конструктора* . *Разработчики* могут создавать плитки на основе отчета, набора данных, информационной панели, поля вопросов и ответов, Excel, а также служб SQL Server Reporting Services (SSRS) и многого другого.  На предыдущем снимке экрана показано множество различных плиток, закрепленных на информационной панели.

![Панель мониторинга Power BI](./media/end-user-tiles/power-bi-dash.png)


Кроме плиток, закрепленных из отчетов, *конструкторы* позволяют добавить автономные плитки непосредственно на панели мониторинга с помощью команды **Добавить плитку** . Автономные плитки содержат следующие данные: текстовые поля, изображения, видео, потоковую передачу данных и веб-содержимое.

Нужна помощь со стандартными блоками Power BI?  См. раздел [Power BI — основные понятия](end-user-basic-concepts.md).


## <a name="interacting-with-tiles-on-a-dashboard"></a>Взаимодействие с плитками на информационной панели

1. Наведите указатель на плитку , чтобы отобразить многоточие.
   
    ![плитка с многоточием](./media/end-user-tiles/power-bi-ellipsis.png)
2. Выберите многоточие, чтобы открыть меню действий плитки. Доступные параметры зависят от разрешений, типа визуального элемента и метода, используемого для создания фрагмента. Например, пункты меню, доступные для фрагментов, закрепленных из раздела "Вопросы и ответы", отличаются от фрагментов, закрепленных из отчета. Ниже приведено меню действий для фрагмента, созданной из раздела "Вопросы и ответы"


   
    ![Снимок экрана: меню с девятью параметрами.](./media/end-user-tiles/power-bi-qna-menu.png)

   
    Доступные в этих меню действия:
   
   * [открыть отчет, который использовался для создания этого фрагмента](end-user-reports.md) ![значок отчета](./media/end-user-tiles/chart-icon.jpg);  
   
   * [открыть вопрос, который использовался для создания плитки ](end-user-reports.md) ![значок вопросов и ответов](./media/end-user-tiles/qna-icon.png);  
   

   * [открыть книгу, которая использовалась для создания фрагмента](end-user-reports.md) ![значок листа](./media/end-user-tiles/power-bi-open-worksheet.png);  
   * [просмотреть плитку в режиме фокусировки](end-user-focus.md) ![значок фокусировки](./media/end-user-tiles/fullscreen-icon.jpg);  
   * [просмотреть аналитические сведения](end-user-insights.md) ![значок аналитики](./media/end-user-tiles/power-bi-insights.png);
   * [добавить комментарий и начать обсуждение](end-user-comment.md) ![значок комментария](./media/end-user-tiles/comment-icons.png);
   * [управлять оповещениями, настроенными на плитке панели мониторинга](end-user-alerts.md) ![значок оповещения](./media/end-user-tiles/power-bi-alert-icon.png);
   * [открыть данные в Excel](end-user-export.md) ![значок экспорта](./media/end-user-tiles/power-bi-export-icon.png).


3. Чтобы закрыть меню действий, выберите пустую область на холсте.

### <a name="select-click-a-tile"></a>Выбор плитки
То, что происходит при выборе плитки, зависит от того, как плитка была создана и имеет ли она [пользовательскую ссылку](../create-reports/service-dashboard-edit-tile.md). Если пользовательская ссылка присутствует, при выборе плитки осуществляется переход по этой ссылке. Иначе при выборе плитки открываются отчет, книга Excel Online, локальный отчет SQL Server Reporting Services или вопрос функции "Вопросы и ответы", которые использовались для создания плитки.

> [!NOTE]
> Исключением являются фрагмента видео, добавленные на панели мониторинга *конструкторами* . При выборе такой плитки видео воспроизводится прямо на панели мониторинга.   
> 
> 

## <a name="considerations-and-troubleshooting"></a>Рекомендации и устранение неполадок
* Если при выборе (щелчке) фрагмента ничего не происходит или появляется сообщение об ошибке, возможно это происходит по следующим причинам.
  - Отчет, использованный для создания визуализации, не был сохранен или удален.
  - Фрагмент была создана из книги в Excel Online, и вам не требуется по крайней мере разрешение на чтение для этой книги.
  - Если Фрагмент была создана из служб SSRS и у вас нет разрешения на доступ к отчету SSRS или у вас нет доступа к сети, в которой находится сервер SSRS.
* Если для плиток, созданных непосредственно на панели мониторинга с помощью команды **Добавить плитку** , задана пользовательская гиперссылка, при выборе заголовка или подзаголовка в плитке откроется этот URL-адрес.  В противном случае по умолчанию при выборе одной из плиток, созданных непосредственно на панели мониторинга для изображения, веб-кода или текстового поля, не выполняются никакие действия.
* Если исходная визуализация, использованная для создания плитки, изменяется, сама плитка не изменяется.  Например, если *конструктор* закрепил график из отчета, а затем изменил график на гистограмму, график будет по-прежнему отображаться на плитке информационной панели. Данные обновляются, а тип визуализации — нет.

## <a name="next-steps"></a>Дальнейшие действия
[Обновление данных](../connect-data/refresh-data.md)

[Power BI — основные понятия](end-user-basic-concepts.md)


