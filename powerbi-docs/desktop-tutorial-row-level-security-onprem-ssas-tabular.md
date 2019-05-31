---
title: Динамическая безопасность на уровне строк при использовании табличной модели служб Analysis Services в Power BI
description: Динамическая безопасность на уровне строк при использовании табличной модели служб Analysis Services
author: selvarms
manager: amitaro
ms.reviewer: davidi
editor: davidi
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 05/08/2019
ms.author: selvar
LocalizationGroup: Connect to data
ms.openlocfilehash: 57a285b075b17b2229ec4267a476cdd4b86ea7ad
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "65513594"
---
# <a name="dynamic-row-level-security-with-analysis-services-tabular-model"></a>Динамическая безопасность на уровне строк при использовании табличной модели служб Analysis Services
В этом учебном руководстве описаны действия, необходимые для реализации **безопасности на уровне строк** в **табличной модели Analysis Services**, и показано, как использовать эти функции в отчете Power BI. Здесь приведены пошаговые инструкции, которые помогут вам познакомиться с последовательностью необходимых действий на примере набора данных.

Ниже перечислены действия, подробно описанные в этом руководстве, чтобы вы могли понять, как реализовать функции безопасности на уровне строк в табличной модели Analysis Services.

* Создание таблицы безопасности в базе данных **AdventureworksDW2012**
* Создание табличной модели с необходимыми таблицами фактов и измерений
* Настройка ролей и разрешений для пользователей
* Развертывание модели в **табличном экземпляре Analysis Services**
* Создание в Power BI отчета, отображающего для пользователей данные с учетом их прав доступа
* Развертывание отчета в **службе Power BI**
* Создание панели мониторинга на основе отчета
* Предоставление доступа к панели мониторинга коллегам.

Для выполнения действий, описанных в этом руководстве, понадобится база данных **AdventureworksDW2012**, которую можно загрузить из **[репозитория](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)** .

## <a name="task-1-create-the-user-security-table-and-define-data-relationship"></a>Задача 1. Создание таблицы безопасности пользователей и определение связей между данными
Существует множество статей, в которых объясняется, как настроить динамическую безопасность на уровне строк в **табличной модели SQL Server Analysis Services (SSAS)** . Для создания этого примера воспользуемся статьей [Реализация динамической безопасности с помощью фильтров строк](https://msdn.microsoft.com/library/hh479759.aspx). Ниже описаны действия для выполнения первой задачи, описанной в этом руководстве:

1. В нашем примере используется реляционная база данных **AdventureworksDW2012**. В этой базе мы создадим таблицу **DimUserSecurity**, как показано на изображении ниже. В этом примере мы используем для создания таблицы приложение SQL Server Management Studio (SSMS).
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable.png)
2. Создав и сохранив таблицу, мы должны установить связь между столбцом **SalesTerritoryID** таблицы **DimUserSecurity** и столбцом **SalesTerritoryKey** таблицы **DimSalesTerritory**, как показано на изображении ниже. В **SSMS** для этого можно щелкнуть таблицу **DimUserSecurity** правой кнопкой мыши и выбрать команду **Конструктор**. Выберите в меню **Конструктор таблиц -> Связи...** .
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_keys.png)
3. Сохраним таблицу, а затем добавим в нее несколько строк с информацией о пользователях. Для этого снова щелкнем таблицу **DimUserSecurity** правой кнопкой мыши и выберем команду **Изменить первые 200 строк**. После добавления пользователей строки таблицы **DimUserSecurity** будут выглядеть так, как показано на следующем изображении:
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_users.png)
   
   Мы вернемся к этим пользователям при выполнении следующих задач.
4. Теперь нам нужно создать *внутреннее соединение* с таблицей **DimSalesTerritory**, которое будет отражать связь между сведениями о регионе и пользователем. следующий код выполняет *внутреннее соединение*, а последующее изображение показывает, как выглядит таблица, как только *внутреннее соединение* будет успешным.
   
       select b.SalesTerritoryCountry, b.SalesTerritoryRegion, a.EmployeeID, a.FirstName, a.LastName, a.UserName from [dbo].[DimUserSecurity] as a join  [dbo].[DimSalesTerritory] as b on a.[SalesTerritoryID] = b.[SalesTerritoryKey]
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_join_users.png)
5. Обратите внимание, что на приведенном выше изображении показаны сведения об ответственности определенных пользователей за тот или иной регион. Эти данные отображаются благодаря связи, которую мы создали на **шаге 2**. Кроме того, обратите внимание, что пользователь **Jon Doe относится к региону продаж Australia**. Мы вернемся к нему в следующих действиях и задачах.

## <a name="task-2-create-the-tabular-model-with-facts-and-dimension-tables"></a>Задача 2. Создание табличной модели с таблицами фактов и измерений
1. Создав реляционное хранилище данных, мы можем настроить определение табличной модели. Для ее создания можно использовать инструментарий **SQL Server Data Tools (SSDT)** . Сведения о том, как задать табличную модель, см. в статье [Создание нового проекта табличной модели](https://msdn.microsoft.com/library/hh231689.aspx).
2. Импортируем в модель все необходимые таблицы, как показано ниже.
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/ssdt_model.png)
3. После импорта таблиц нужно определить роль под названием **SalesTerritoryUsers** с разрешениями на **чтение**. Для этого нужно открыть меню **Модель** в инструментарии SQL Server Data Tools и выбрать пункт **Роли**. В диалоговом окне **Диспетчер ролей** щелкнем **Создать**.
4. На вкладке **Участники** в **диспетчере ролей** добавим пользователей, созданных в таблице **DimUserSecurity** при выполнении **задачи 1 (шаг 3)** .
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/rolemanager.png)
5. Теперь добавим необходимые функции для таблиц **DimSalesTerritory** и **DimUserSecurity**, как показано ниже на вкладке **Фильтры строк**.
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/rolemanager_complete.png)
6. На этом этапе мы с помощью функции **LOOKUPVALUE** возвращаем значения для столбца, в котором имя пользователя Windows совпадает с именем, возвращаемым функцией **USERNAME**. Для запросов можно настроить ограничение, благодаря которому значения, возвращаемые функцией **LOOKUPVALUE**, будут совпадать со значениями в той же или связанной таблице. В столбце **Фильтр DAX** введем следующую формулу:
   
       =DimSalesTerritory[SalesTerritoryKey]=LOOKUPVALUE(DimUserSecurity[SalesTerritoryID], DimUserSecurity[UserName], USERNAME(), DimUserSecurity[SalesTerritoryID], DimSalesTerritory[SalesTerritoryKey])
    В этой формуле функция **LOOKUPVALUE** возвращает все значения из столбца **DimUserSecurity[SalesTerritoryID]** , для которых **DimUserSecurity[UserName]** совпадает с именем текущего пользователя Windows, а параметр **DimUserSecurity[SalesTerritoryID]** совпадает с параметром **DimSalesTerritory[SalesTerritoryKey]** .
   
    > [!IMPORTANT]
    > Имейте в виду, что функция DAX [USERELATIONSHIP](https://msdn.microsoft.com/query-bi/dax/userelationship-function-dax) не поддерживается при использовании безопасности на уровне строк.

   Набор значений SalesTerritoryKey, возвращаемых функцией **LOOKUPVALUE**, используется для фильтрации списка строк, отображаемых в таблице **DimSalesTerritory**. В ней показаны только строки, в которых значение **SalesTerritoryKey** входит в набор идентификаторов, возвращенных функцией **LOOKUPVALUE**.
8. Для таблицы **DimUserSecurity** в столбце **DAX Filter** введите следующую формулу:
   
       =FALSE()

    Она указывает, что все столбцы возвращают логическое значение false, поэтому столбцы таблицы **DimUserSecurity** не используются в запросе.
1. Теперь нужно обработать и развернуть модель. Сведения о том, как это сделать, см. в статье [Развертывание](https://msdn.microsoft.com/library/hh231693.aspx).

## <a name="task-3-adding-data-sources-within-your-on-premises-data-gateway"></a>Задача 3. Добавление источников данных в локальном шлюзе
1. После того как табличная модель развернута и готова к работе, необходимо добавить подключение к источнику данных на сервер табличного экземпляра Analysis Services на портале Power BI.
2. Чтобы **служба Power BI** могла обращаться к локальной службе аналитики, в вашей среде должен быть установлен и настроен **[локальный шлюз данных](service-gateway-onprem.md)** .
3. Настроив шлюз должным образом, необходимо создать подключение к источнику данных для экземпляра табличной модели **Analysis Services**. В этой статье описывается [добавление источника данных на портале Power BI](service-gateway-enterprise-manage-ssas.md).
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/pbi_gateway.png)
4. После выполнения предыдущего шага шлюз настроен и готов к взаимодействию с локальным источником данных **Analysis Services**.

## <a name="task-4-creating-report-based-on-analysis-services-tabular-model-using-power-bi-desktop"></a>Задача 4. Создание отчета на основе табличной модели Analysis Services с помощью Power BI Desktop
1. Запустите **Power BI Desktop** и выберите **Получение данных > База данных**.
2. В списке источников данных выберите пункт **База данных SQL Server Analysis Services** и щелкните **Подключиться**.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata.png)
3. Введите данные своего экземпляра табличной модели **Analysis Services** и щелкните **Подключение в реальном времени**. Нажмите кнопку **ОК**. В **Power BI** динамическая безопасность работает только при **динамических подключениях**.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata_connectlive.png)
4. Вы увидите, что развернутая модель находится в экземпляре **Analysis Services**. Выберите нужную модель и нажмите кнопку **ОК**.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata_connectlive.png)
5. **Power BI Desktop** выведет все доступные поля справа от холста в области **Поля**.
6. В области **Поля** справа выберите меру **SalesAmount** в таблице **FactInternetSales** и измерение **SalesTerritoryRegion** в таблице **SalesTerritory**.
7. Этот отчет будет простым, поэтому мы не станем добавлять в него другие столбцы. Чтобы сделать данные более осмысленными, выберем режим визуализации **Кольцевой график**.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/donut_chart.png)
8. Создав отчет, мы можем опубликовать его непосредственно на портале Power BI. На ленте **Главная** в **Power BI Desktop** выберем **Опубликовать**.

## <a name="task-5-creating-and-sharing-a-dashboard"></a>Задача 5. Создание и совместное использование панели мониторинга
1. Мы создали отчет и воспользовались командой **Опубликовать** в **Power BI Desktop**, поэтому теперь он опубликован в службе **Power BI**. Теперь мы можем продемонстрировать работу нашей модели на основе примера, который создали на предыдущих этапах.
   
   Руководитель продаж **Sumit** видит данные из всех регионов. Он создает этот отчет (который мы сформировали на предыдущих этапах) и публикует его в службе Power BI.
   
   После публикации он создает на его основе в службе Power BI панель мониторинга и называет ее **TabularDynamicSec**. На изображении ниже показано, что руководитель продаж (Sumit) видит все данные для всех регионов продаж.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/donut_chart_1.png)
2. Теперь он предоставляет доступ к панели своему коллеге, которого зовут Jon Doe и который отвечает за продажи в Австралии.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/user_jon_doe.png)
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/pbi_dashboard.png)
3. Когда Jon Doe входит в службу **Power BI** и открывает общую панель мониторинга, созданную пользователем Sumit, он видит **только** показатели продаж в подотчетном ему регионе. Итак, Jon Doe входит, открывает панель мониторинга, доступ к которой ему предоставил пользователь Sumit, и видит **только** продажи в Австралии.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/dashboard_jon_doe.png)
4. Поздравляем! Параметры динамической безопасности на уровне строк, настроенные в локальной табличной модели **Analysis Services**, успешно отражены и соблюдаются в службе **Power BI**. Служба Power BI использует свойство **effectiveusername** для передачи учетных данных текущего пользователя Power BI в локальный источник данных при выполнении запросов.

## <a name="task-6-understanding-what-happens-behind-the-scenes"></a>Задача 6. Понимание происходящего
1. При выполнении этой задачи предполагается, что вы знакомы с приложением SQL Profiler, так как вам нужно выполнить трассировку обмена данными с SQL Server в локальном экземпляре SSAS.
2. Сеанс создается в момент, когда пользователь (в нашем случае — Jon Doe) обращается к панели мониторинга в службе Power BI. Мы видим, что роль **salesterritoryusers** сразу же применяется для действующего имени пользователя **<EffectiveUserName>jondoe@moonneo.com</EffectiveUserName>** .
   
       <PropertyList><Catalog>DefinedSalesTabular</Catalog><Timeout>600</Timeout><Content>SchemaData</Content><Format>Tabular</Format><AxisFormat>TupleFormat</AxisFormat><BeginRange>-1</BeginRange><EndRange>-1</EndRange><ShowHiddenCubes>false</ShowHiddenCubes><VisualMode>0</VisualMode><DbpropMsmdFlattened2>true</DbpropMsmdFlattened2><SspropInitAppName>PowerBI</SspropInitAppName><SecuredCellValue>0</SecuredCellValue><ImpactAnalysis>false</ImpactAnalysis><SQLQueryMode>Calculated</SQLQueryMode><ClientProcessID>6408</ClientProcessID><Cube>Model</Cube><ReturnCellProperties>true</ReturnCellProperties><CommitTimeout>0</CommitTimeout><ForceCommitTimeout>0</ForceCommitTimeout><ExecutionMode>Execute</ExecutionMode><RealTimeOlap>false</RealTimeOlap><MdxMissingMemberMode>Default</MdxMissingMemberMode><DisablePrefetchFacts>false</DisablePrefetchFacts><UpdateIsolationLevel>2</UpdateIsolationLevel><DbpropMsmdOptimizeResponse>0</DbpropMsmdOptimizeResponse><ResponseEncoding>Default</ResponseEncoding><DirectQueryMode>Default</DirectQueryMode><DbpropMsmdActivityID>4ea2a372-dd2f-4edd-a8ca-1b909b4165b5</DbpropMsmdActivityID><DbpropMsmdRequestID>2313cf77-b881-015d-e6da-eda9846d42db</DbpropMsmdRequestID><LocaleIdentifier>1033</LocaleIdentifier><EffectiveUserName>jondoe@moonneo.com</EffectiveUserName></PropertyList>
3. Используя переданное в запросе действующее имя пользователя, службы Analysis Services преобразуют его в учетные данные moonneo\jondoe при отправке запроса в каталог Active Directory. После того как службы **Analysis Services** получают реальные учетные данные из Active Directory, они применяют права и разрешения этого пользователя на доступ к соответствующим данным и возвращают только ту информацию, для работы с которой у него есть разрешение **.**
4. Если на панели мониторинга будет выполнено еще какое-то действие (например, Jon Doe перейдет с панели на связанный с ней отчет), в SQL Profiler отразится соответствующий запрос, который направляется в табличную модель Analysis Services в виде запроса DAX.
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/profiler1.png)
5. Ниже также показан запрос DAX, который выполняется для заполнения отчета данными.
   
   ```
   EVALUATE
     ROW(
       "SumEmployeeKey", CALCULATE(SUM(Employee[EmployeeKey]))
     )
   
   <PropertyList xmlns="urn:schemas-microsoft-com:xml-analysis">``
             <Catalog>DefinedSalesTabular</Catalog>
             <Cube>Model</Cube>
             <SspropInitAppName>PowerBI</SspropInitAppName>
             <EffectiveUserName>jondoe@moonneo.com</EffectiveUserName>
             <LocaleIdentifier>1033</LocaleIdentifier>
             <ClientProcessID>6408</ClientProcessID>
             <Format>Tabular</Format>
             <Content>SchemaData</Content>
             <Timeout>600</Timeout>
             <DbpropMsmdRequestID>8510d758-f07b-a025-8fb3-a0540189ff79</DbpropMsmdRequestID>
             <DbPropMsmdActivityID>f2dbe8a3-ef51-4d70-a879-5f02a502b2c3</DbPropMsmdActivityID>
             <ReturnCellProperties>true</ReturnCellProperties>
             <DbpropMsmdFlattened2>true</DbpropMsmdFlattened2>
             <DbpropMsmdActivityID>f2dbe8a3-ef51-4d70-a879-5f02a502b2c3</DbpropMsmdActivityID>
           </PropertyList>
   ```

## <a name="considerations"></a>Примечания
При работе с безопасностью на уровне строк, SSAS и Power BI следует помнить о ряде моментов:

1. Локальная безопасность на уровне строк при работе с Power BI действует только при динамических подключениях.
2. Все изменения, вносимые в данные после обработки модели, становятся сразу же доступны пользователям, которые работают с отчетом через **динамические подключения** из службы Power BI.

