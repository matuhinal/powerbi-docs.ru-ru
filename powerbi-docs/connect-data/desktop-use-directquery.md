---
title: Использование DirectQuery в Power BI Desktop
description: Использование функции DirectQuery, также называемой активным подключением, в Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1224b7eaa6a19cab4bf6fa8304eb5c5b1fb27581
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83285861"
---
# <a name="use-directquery-in-power-bi-desktop"></a>Использование DirectQuery в Power BI Desktop
При подключении к источнику данных в *Power BI Desktop* всегда можно импортировать копию данных в Power BI Desktop. Для некоторых источников данных доступен альтернативный подход: прямое подключение к источнику данных с помощью DirectQuery.

## <a name="supported-data-sources"></a>Поддерживаемые источники данных
Полный список источников данных, поддерживающих DirectQuery, см. в статье [Источники данных, поддерживаемые DirectQuery](power-bi-data-sources.md).

## <a name="how-to-connect-using-directquery"></a>Подключение с помощью DirectQuery
При использовании команды **Получить данные** для подключения к источнику данных, поддерживаемому функцией DirectQuery, отображается диалоговое окно с вопросом о способе подключения. Например, в Power BI Desktop на ленте **Главная** выберите **Получить данные**  >  **SQL Server**. В диалоговом окне **Сервер базы данных SQL** **Режим подключения к данным**  содержит пункты **Импорт** и **DirectQuery**.

![Пункты "Импорт" и DirectQuery, диалоговое окно базы данных SQL Server, Power BI Desktop](media/desktop-use-directquery/directquery_sqlserverdb.png)

Ниже описаны различия между выбором варианта **Импорт** и **DirectQuery**.

- **Импорт**. Выбранные таблицы и столбцы импортируются в Power BI Desktop. При создании визуализации или взаимодействии с ней Power BI Desktop использует импортированные данные. Чтобы просмотреть изменения, внесенные в базовые данные с момента первоначального импорта или самой последней операции обновления, необходимо обновить данные, которые снова импортируют полный набор данных.

- **DirectQuery**. Данные не импортируются и не копируются в Power BI Desktop. Для реляционных источников выбранные таблицы и столбцы отображаются в списке **Поля**. Для многомерных источников, таких как SAP Business Warehouse, измерения и меры выбранного куба отображаются в списке **Поля**. При создании визуализации или взаимодействии с ней Power BI Desktop запрашивает базовый источник данных, то есть вы всегда видите актуальные данные.

При использовании DirectQuery доступно множество функций моделирования и преобразования данных, хотя и с некоторыми ограничениями. При создании визуализации или взаимодействии с ней необходимо выполнять запрос к базовому источнику. Время для обновления визуализации будет зависеть от производительности базового источника данных. Если данные, необходимые для обслуживания запроса, недавно запрашивались, Power BI Desktop использует эти последние данные для сокращения времени, необходимого для отображения визуализации. При выборе элемента **Обновить** на вкладке **Главная** ленты все визуализации обновляются с использованием актуальных данных.

В статье [Power BI и DirectQuery](desktop-directquery-about.md) подробно описывается DirectQuery. Дополнительные сведения о преимуществах, ограничениях и важных аспектах использования функции DirectQuery см. в следующих разделах.

## <a name="benefits-of-using-directquery"></a>Преимущества использования DirectQuery
Использование DirectQuery дает несколько преимуществ.

- DirectQuery позволяет создавать визуализации на базе очень больших наборов данных, где в противном случае было бы нецелесообразно сначала импортировать все данные с предварительным агрегированием.
- Изменение базовых данных может потребовать обновления данных. Для отображения текущих данных в некоторых отчетах может потребоваться передача большого объема данных, что делает повторный импорт данных невозможным. Отчеты DirectQuery, наоборот, всегда используют актуальные данные.
- Ограничение в 1 ГБ для набора данных *не относится к* DirectQuery.

## <a name="limitations-of-directquery"></a>Ограничения DirectQuery
В настоящее время существует несколько ограничений, связанных с использованием DirectQuery.

- Если запрос в **редакторе запросов** слишком сложный, произойдет ошибка. Чтобы устранить ошибку, удалите проблемный шаг в **редакторе запросов** или *импортируйте данные* вместо использования DirectQuery. Для многомерных источников, таких как SAP Business Warehouse, нет **редактора запросов**.

- Логика операций со временем недоступна в DirectQuery. Например, в режиме DirectQuery специальная обработка столбцов даты (например, год, квартал, месяц, день и т. д.) не поддерживается.

- На выражения DAX, разрешенные в мерах, накладываются ограничения, чтобы обеспечить приемлемую производительность запросов, отправляемых в базовый источник данных.

- При возврате данных с помощью DirectQuery существует ограничение в один миллион строк, если не используется емкость Premium. Это ограничение не влияет на агрегаты и вычисления, используемые для создания набора данных, возвращаемого с помощью DirectQuery. Он влияет только на возвращаемые строки. Емкость Premium позволяет задать максимальное количество строк, как описано в [этой записи блога](https://powerbi.microsoft.com/blog/five-new-power-bi-premium-capacity-settings-is-available-on-the-portal-preloaded-with-default-values-admin-can-review-and-override-the-defaults-with-their-preference-to-better-fence-their-capacity/). 

    Например, можно агрегировать 10 000 000 строк с помощью запроса, выполняемого в источнике данных. Запрос возвращает точные результаты этого агрегирования в Power BI с помощью DirectQuery, если возвращаемые данные Power BI содержат менее 1 млн строк. Если из DirectQuery будет возвращено более 1 млн строк, в Power BI появится сообщение об ошибке (если не используется емкость Premium, где количество строк не превышает указанное администратором ограничение).


## <a name="important-considerations-when-using-directquery"></a>Важные аспекты использования DirectQuery
При использовании DirectQuery следует учитывать три аспекта.

- **Производительность и балансировка**. Все запросы DirectQuery отправляются в базу данных-источник, поэтому время обновления визуализации зависит от того, как быстро источник на сервере возвратит результаты запросов. При использовании DirectQuery для визуализаций стандартным временем получения запрошенных данных считается пять секунд и меньше. Максимальное время получения ответа не должно превышать 30 секунд. Если на получение ответа уходит больше времени, работа с отчетом сильно затрудняется. После того как отчет опубликован в службе Power BI, все запросы, выполняющиеся более пяти минут, возвращают ошибку о превышении времени ожидания. В этом случае пользователь получает сообщение об ошибке.
  
    Также необходимо учитывать нагрузку на базу данных-источник. Нагрузка зависит от количества пользователей Power BI, которые используют опубликованные отчеты. Использование **Безопасности на уровне строк** (RLS) может также оказать значительное влияние. Плитка панели мониторинга, не относящаяся к RLS, совместно используемая несколькими пользователями, приводит к одному запросу к базе данных. Однако использование RLS на плитке панели мониторинга обычно означает, что для обновления плитки требуется один запрос *на пользователя*, что значительно повышает нагрузку на базу данных-источник и потенциально влияет на производительность.
  
    Power BI создает максимально эффективные запросы, В некоторых ситуациях созданный запрос может оказаться недостаточно эффективным, из-за чего происходит сбой обновления. Например, запрос может извлечь из источника данных на сервере слишком большое количество строк. В этом случае возникает такая ошибка.

    ```output
    The resultset of a query to external data source has exceeded
    ```
  
    Такая ситуация может возникнуть с простой диаграммой, в которой есть столбец с очень большим количеством элементов и выбран параметр статистической обработки **Не суммировать**. В визуализациях нужно использовать столбцы, в которых количество элементов не превышает 1 млн, или применять соответствующие фильтры.

- **Безопасность** — По умолчанию все пользователи опубликованного отчета подключаются к источнику данных на сервере с помощью учетных данных, которые были указаны после публикации отчета в службе Power BI. Такой же процесс используется при импорте данных: все пользователи видят одинаковые данные вне зависимости от того, какие правила безопасности определены в источнике на сервере.

    Клиентам, которым нужно обеспечить безопасность на уровне пользователей с помощью источников DirectQuery, следует использовать RLS или настроить ограниченную аутентификацию Kerberos для источника. Протокол Kerberos доступен не для всех источников. [Дополнительные сведения об RLS](../admin/service-admin-rls.md). [Ознакомьтесь с дополнительными сведениями о Kerberos в DirectQuery](service-gateway-sso-kerberos.md).

- **Поддерживаемые функции**. Некоторые функции Power BI Desktop не работают в режиме DirectQuery, а некоторые имеют определенные ограничения. В службе Power BI есть некоторые возможности (например, *Краткая аналитика*), которые недоступны для наборов данных при использовании DirectQuery. При определении необходимости использования DirectQuery следует учитывать ограничения этих функций.

> [!NOTE]
> При использовании DirectQuery с Базой данных SQL Azure и частным IP-адресом требуется локальный шлюз. 

## <a name="publish-to-the-power-bi-service"></a>Публикация в службу Power BI
Отчеты, созданные с помощью DirectQuery, можно опубликовать в службе Power BI.

Если для источника данных не требуется **локальный шлюз данных** (**база данных SQL Microsoft Azure**, **хранилище данных SQL Azure Data Warehouse** или **Redshift**), нужно указать учетные данные перед тем, как опубликованный отчет сможет отобразиться в службе Power BI. Чтобы указать учетные данные, выполните следующие инструкции.

1. Войдите в [Power BI](https://www.powerbi.com/).
2. В службе Power BI щелкните значок шестеренки **Параметры** и выберите пункт меню **Параметры**.

    ![Параметры — служба Power BI](media/desktop-use-directquery/directquery_pbiservicesettings.png)

3. В службе Power BI откройте вкладку **Наборы данных** и выберите набор данных, использующий **DirectQuery**, а затем выберите **Изменить учетные данные**.

4. Добавьте учетные данные. В противном случае при открытии опубликованного отчета или просмотре набора данных, созданного с помощью подключения DirectQuery, возникает ошибка.

Чтобы выполнить подключение к данным для источников данных, отличных от **Базы данных SQL Azure**, **Хранилища данных SQL Azure**, **Redshift** или **Snowflake Data Warehouse**, использующих DirectQuery, установите **локальный шлюз данных** и зарегистрируйте источник данных. Дополнительную информацию см. в разделе [Что такое локальный шлюз данных?](service-gateway-onprem.md)

## <a name="next-steps"></a>Дальнейшие действия
Дополнительные сведения о DirectQuery см. в следующих статьях:

- [Использование DirectQuery в Power BI](desktop-directquery-about.md)
- [Источники данных, поддерживаемые DirectQuery](power-bi-data-sources.md)
- [Использование DirectQuery и SAP Business Warehouse (BW)](desktop-directquery-sap-bw.md)
- [DirectQuery и SAP HANA](desktop-directquery-sap-hana.md)
- [Что такое локальный шлюз данных?](service-gateway-onprem.md)