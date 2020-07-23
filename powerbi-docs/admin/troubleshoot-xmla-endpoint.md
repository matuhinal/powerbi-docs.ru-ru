---
title: Устранение неполадок с подключением конечных точек XMLA в Power BI Premium (предварительная версия)
description: Эта статья содержит сведения об устранении неполадок с подключением конечных точек XMLA в Power BI Premium.
author: minewiskan
ms.author: owend
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: troubleshooting
ms.date: 06/16/2020
ms.custom: seodec18, css_fy20Q4
LocalizationGroup: Premium
ms.openlocfilehash: be55180f57fec683b8da426e6c73bb95d6365d2f
ms.sourcegitcommit: a453ba52aafa012896f665660df7df7bc117ade5
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2020
ms.locfileid: "85485537"
---
# <a name="troubleshoot-xmla-endpoint-connectivity"></a>Устранение неполадок с подключением конечных точек XMLA

Конечные точки XMLA в Power BI Premium используют собственный протокол связи Analysis Services для доступа к наборам данных Power BI. Поэтому устранение неполадок в конечной точке XMLA во многом аналогично устранению неполадок типичного подключения Analysis Services. Однако есть некоторые различия, связанные с Power BI.

## <a name="before-you-begin"></a>Перед началом

Прежде чем устранять неполадки в сценарии конечной точки XMLA, ознакомьтесь с основными сведениями, изложенными в статье [Возможность подключения к набору данных с помощью конечной точки XMLA (предварительная версия)](service-premium-connect-tools.md). Здесь рассматриваются наиболее распространенные варианты использования конечной точки XMLA. Другие руководства [по устранению неполадок со шлюзами в Power BI](../connect-data/service-gateway-onprem-tshoot.md) и [устранению неполадок с анализом в Excel](../collaborate-share/desktop-troubleshooting-analyze-in-excel.md) также могут быть полезными.

## <a name="enabling-the-xmla-endpoint"></a>Включение конечной точки XMLA

Конечную точку XMLA можно включить как в емкости Power BI Premium, так и Power BI Embedded. В небольших емкостях, таких как емкость A1 (с размером памяти всего 2,5 ГБ), при попытке задать конечную точку XMLA для **чтения и записи** и выборе **Применить** может возникнуть ошибка в параметрах емкости. Ошибка будет содержать следующее сообщение There was an issue with your workload settings. Try again in a little while. (Возникла проблема в параметрах рабочей нагрузки. Повторите попытку позже.)

Вот несколько способов устранить эту проблему:

- Ограничьте потребление памяти другими службами в емкости, например потоками данных, до 40 % или ниже или полностью отключите ненужную службу.  
- Повысьте емкость, перейдя на больший номер SKU. Например, проблема конфигурации будет решена без отключения потоков данных, если обновить емкость с A1 до A3.

Помните, что необходимо также включить параметр [Экспорт данных](service-premium-connect-tools.md#security) на уровне клиента на портале администрирования Power BI. Этот параметр также необходим для функции "Анализировать в Excel".

## <a name="establishing-a-client-connection"></a>Установление подключения клиента

После включения конечной точки XMLA рекомендуется проверить возможность подключения к рабочей области в емкости. Дополнительные сведения см. в разделе [Подключение к рабочей области Premium](service-premium-connect-tools.md#connecting-to-a-premium-workspace). Кроме того, ознакомьтесь с разделом [Требования к подключению](service-premium-connect-tools.md#connection-requirements) на предмет полезных советов и сведений о текущих ограничениях для подключения XMLA.

### <a name="connecting-with-a-service-principal"></a>Соединение с субъектом-службой

Если вы включили параметры клиента, чтобы разрешить субъектам-службам использовать API-интерфейсы Power BI, как описано в разделе [Включение субъектов-служб](service-premium-service-principal.md#enable-service-principals), можно подключиться к конечной точке XMLA с помощью субъекта-службы. Помните, что субъекту-службе требуется тот же уровень разрешений доступа на уровне рабочей области или набора данных, что и обычным пользователям.

Чтобы использовать субъект-службу, обязательно укажите сведения об удостоверении приложения в строке подключения следующим образом:

- `User ID=<app:appid@tenantid>`
- `Password=<application secret>`

Пример:

`Data Source=powerbi://api.powerbi.com/v1.0/myorg/Contoso;Initial Catalog=PowerBI_Dataset;User ID=app:91ab91bb-6b32-4f6d-8bbc-97a0f9f8906b@19373176-316e-4dc7-834c-328902628ad4;Password=6drX...;`

Если вы получаете следующую ошибку:

We cannot connect to the dataset due to incomplete account information. For service principals, make sure you specify the tenant ID together with the app ID using the format app: \<appId>@\<tenantId>, then try again. (Не удается подключиться к набору данных из-за неполной информации об учетной записи. Для субъектов-служб убедитесь, что идентификатор клиента указан вместе с идентификатором приложения в следующем формате приложения: \<appId>@\<tenantId>. Затем повторите попытку.)

Убедитесь, что идентификатор клиента и приложения указаны в правильном формате.

Вы также можете указать идентификатор приложения без идентификатора клиента. Однако в этом случае необходимо заменить псевдоним `myorg` в URL-адресе источника данных фактическим идентификатором клиента. После этого Power BI может выбрать субъект-службу в правильном клиенте. Но рекомендуется использовать псевдоним `myorg` и указать идентификатор клиента вместе с идентификатором приложения в параметре идентификатора пользователя.

### <a name="connecting-with-azure-active-directory-b2b"></a>Подключение к Azure Active Directory B2B

Благодаря поддержке Azure Active Directory (Azure AD) "бизнес — бизнес" (B2B) в Power BI вы можете предоставить внешним гостевым пользователям доступ к наборам данных через конечную точку XMLA. Включите параметр [Предоставление внешним пользователям общего доступа к содержимому](service-admin-portal.md#export-and-sharing-settings) на портале администрирования Power BI. Дополнительные сведения см. в статье [Предоставление содержимого Power BI внешним гостевым пользователям с помощью Azure AD B2B](service-admin-azure-ad-b2b.md).

## <a name="deploying-a-dataset"></a>Развертывание набора данных

Развертывание проекта табличной модели из Visual Studio (SSDT) в рабочую область Power BI Premium во многом аналогично развертыванию в службах Azure Analysis Services. Однако при развертывании в рабочей области Power BI Premium необходимо учитывать некоторые дополнительные особенности. Обязательно ознакомьтесь с разделом [Развертывание проектов модели из Visual Studio (SSDT)](service-premium-connect-tools.md#deploy-model-projects-from-visual-studio-ssdt) статьи о подключении к набору данных с помощью конечной точки XMLA.

### <a name="deploying-a-new-model"></a>Развертывание новой модели

В конфигурации по умолчанию Visual Studio пытается обработать модель как часть операции развертывания, чтобы загрузить данные из источников данных в набор данных. Как описано в разделе [Развертывание проектов модели из Visual Studio (SSDT)](service-premium-connect-tools.md#deploy-model-projects-from-visual-studio-ssdt), эта операция может завершиться ошибкой, так как учетные данные источника данных не могут быть указаны в ходе операции развертывания. Вместо этого, если учетные данные для источника данных еще не определены для какого-либо из существующих наборов, необходимо указать учетные данные источника в параметрах набора данных с помощью пользовательского интерфейса Power BI (**Наборы данных** > **Параметры** > **Учетные данные источника данных** > **Изменить учетные данные**). Определив учетные данные источника данных, Power BI может автоматически применять учетные данные к этому источнику данных для любого нового набора данных, после того как успешно выполнено развертывание метаданных и создан набор данных.

Если Power BI не удается привязать новый набор данных к учетным данным источника данных, появится сообщение об ошибке "Не удается обработать базу данных. Причина: Не удалось сохранить изменения на сервере." с кодом ошибки "DMTS_DatasourceHasNoCredentialError", как показано ниже.

:::image type="content" source="media/troubleshoot-xmla-endpoint/deploy-refresh-error.png" alt-text="Ошибка развертывания модели":::

Чтобы избежать сбоя обработки, задайте для раздела **Параметры развертывания** > **Параметры обработки** значение **Не обрабатывать**, как показано на следующем рисунке. Затем Visual Studio развертывает только метаданные. Далее можно настроить учетные данные источника данных и щелкнуть **Обновить** для набора данных в пользовательском интерфейсе Power BI. Сведения об устранении неполадок, связанных с обработкой, см. в разделе [Обновление набора данных](#refreshing-a-dataset) далее в этой статье.

:::image type="content" source="media/troubleshoot-xmla-endpoint/do-not-process.png" alt-text="Параметр Не обрабатывать":::

### <a name="new-project-from-an-existing-dataset"></a>Создание проекта с помощью существующего набора данных

Создание табличного проекта в Visual Studio путем импорта метаданных из существующего набора данных в рабочей области Power BI Premium не поддерживается. Однако можно подключиться к набору данных с помощью SQL Server Management Studio, создать скрипт для метаданных и повторно использовать его в других табличных проектах.

## <a name="migrating-a-dataset-to-power-bi"></a>Перенос набора данных в Power BI

Рекомендуется для табличных моделей указать уровень совместимости 1500 (или выше). Этот уровень совместимости поддерживает большинство возможностей и типов источников данных. Более поздние уровни совместимости имеют обратную совместимость с предыдущими уровнями.

### <a name="unsupported-data-providers"></a>Неподдерживаемые типы данных

При уровне совместимости 1500 Power BI поддерживает следующие типы данных:

- Источники данных поставщика (прежние версии со строкой подключения в метаданных модели).
- Структурированные источники данных (представлены на уровне совместимости 1400).
- Объявления источников данных в строке M (как Power BI Desktop объявляет их).

Рекомендуется использовать структурированные источники данных, которые Visual Studio создает по умолчанию при работе с потоком данных импорта. Однако если планируется перенос существующей модели в Power BI, использующей источник данных поставщика, убедитесь, что источник данных поставщика использует поддерживаемый поставщик данных. В частности, драйвер Microsoft OLE DB для SQL Server и любых сторонних драйверов ODBC. Для драйвера OLE DB для SQL Server необходимо переключить определение источника данных на поставщика данных .NET Framework для SQL Server. Для сторонних драйверов ODBC, которые могут быть недоступны в службе Power BI, необходимо переключиться на определение структурированного источника данных.

Также рекомендуется заменить устаревший драйвер Microsoft OLE DB для SQL Server (SQLNCLI11) в определениях источников данных SQL Server на поставщика данных .NET Framework для SQL Server.

В следующей таблице приведен пример строки подключения поставщика данных .NET Framework для SQL Server, в которой заменяется соответствующая строка подключения для драйвера OLE DB для SQL Server.

|Драйвер OLE DB для SQL Server  |Поставщик данных .NET Framework для SQL Server   |
|---------|---------|
|`Provider=SQLNCLI11;Data Source=sqldb.database.windows.net;Initial Catalog=AdventureWorksDW;Trusted_Connection=yes;`    |   `Data Source=sqldb.database.windows.net;Initial Catalog=AdventureWorksDW2016;Integrated Security=SSPI;Encrypt=true;TrustServerCertificate=false`       |

### <a name="cross-referencing-partition-sources"></a>Источники секций перекрестных ссылок

Так же как существует несколько типов источников данных, существует и несколько типов источников секций, которые могут быть включены в табличную модель для импорта данных в таблицу. В частности, секция может использовать источник секции запроса или M. Эти типы источников секций, в свою очередь, могут ссылаться на источники данных поставщика или структурированные источники данных. Табличные модели в Azure Analysis Services поддерживают перекрестные ссылки на эти различные типы источников данных и секций, а Power BI обеспечивает более строгую связь. Источники секций запросов должны ссылаться на источники данных поставщика, а источники разделов M — на структурированные источники данных. Другие сочетания не поддерживаются в Power BI. Если требуется выполнить миграцию набора данных с перекрестными ссылками, в следующей таблице описаны поддерживаемые конфигурации:  

|Источник данных   |Источник секции   |Комментарии   |Поддерживается в Power BI Premium с конечной точкой XMLA   |
|---------|---------|---------|---------|
|Поставщик источника данных      |   Источник секции запроса      |   Ядро AS использует стек подключений на основе картриджей для доступа к источнику данных.       |     Да     |
|Поставщик источника данных      |   Источник секции M       |   Ядро AS преобразует источник данных поставщика в универсальный структурированный источник данных, а затем использует подсистему гибридного веб-приложения для импорта данных.       |    Нет     |
|Структурированный источник данных      |     Источник секции запроса     |    Ядро AS заключает в оболочку собственный запрос к источнику секции в выражении M, а затем использует подсистему гибридного веб-приложения для импорта данных.      |    Нет     |
|Структурированный источник данных      |    Источник секции M      |     Ядро AS использует подсистему гибридного веб-приложения для импорта данных.     |   Да      |

## <a name="refreshing-a-dataset"></a>Обновление набора данных

Конечные точки XMLA позволяют выполнять операции обновления для табличных моделей, а также наборов данных, созданных в Power BI Desktop. Для поддержки второго варианта убедитесь, что задан параметр формата расширенного хранилища. Этот параметр является обязательным, если требуется выполнить обработку или другие операции чтения и записи с помощью конечной точки XMLA. Этот параметр можно найти в Power BI Desktop в разделе "Функции предварительной версии". После настройки опубликуйте решение PBIX еще раз в рабочей области Power BI Premium.  

Power BI возвращает указанную ниже ошибку, если вы выполняете обновление через конечную точку XMLA для модели без расширенных метаданных: "Эта операция поддерживается только для модели со свойством "DefaultPowerBIDataSourceVersion", имеющим значение "PowerBI_V3", в Power BI Premium."

### <a name="data-sources-and-impersonation"></a>Источники данных и олицетворение

Параметры олицетворения, которые можно определить для источников данных поставщика, не относятся к Power BI. Power BI использует другой механизм на основе параметров набора данных для управления учетными данными источника данных. По этой причине убедитесь, что при создании источника данных поставщика выбрана **Учетная запись службы**.

:::image type="content" source="media/troubleshoot-xmla-endpoint/impersonate-services-account.png" alt-text="Олицетворение учетной записи службы":::

### <a name="fine-grained-processing"></a>Детализированная обработка

В Power BI при запуске запланированного обновления или обновления по запросу обычно обновляется весь набор данных. Во многих случаях более эффективно выполнять обновление выборочно. Вы можете выполнять задачи детализированной обработки в SQL Server Management Studio (SSMS), как показано ниже, или с помощью средств или сценариев сторонних разработчиков.

:::image type="content" source="media/troubleshoot-xmla-endpoint/process-tables.png" alt-text="Обработка таблиц в SSMS":::

## <a name="see-also"></a>См. также раздел

[Возможность подключения к набору данных с помощью конечной точки XMLA](service-premium-connect-tools.md)   
[Автоматизация задач по управлению рабочими областями Premium и наборами данных с помощью субъектов-служб](service-premium-service-principal.md)   
[Устранение неполадок с анализом в Excel](../collaborate-share/desktop-troubleshooting-analyze-in-excel.md)   
[Развертывание решений табличной модели](https://docs.microsoft.com/analysis-services/deployment/tabular-model-solution-deployment?view=power-bi-premium-current)