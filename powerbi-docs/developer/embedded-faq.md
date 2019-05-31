---
title: Часто задаваемые вопросы о Power BI Embedded
description: Просмотрите список часто задаваемых вопросов о Power BI Embedded и ознакомьтесь с ответами.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: 1bdc31d550573b926d45776307b8fcade95f0dc0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222180"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Часто задаваемые вопросы о Power BI Embedded

* Если у вас возникли другие вопросы, [задайте их участникам сообщества Power BI](http://community.powerbi.com/).
* Проблема до сих пор не устранена? Посетите [страницу поддержки по Power BI](https://powerbi.microsoft.com/support/).

## <a name="general"></a>Общие

### <a name="what-is-power-bi-embedded"></a>Что такое Power BI Embedded?

[Microsoft Power BI Embedded (PBIE)](azure-pbie-what-is-power-bi-embedded.md) позволяет разработчикам встраивать впечатляющие, полностью интерактивные отчеты в приложения без необходимости создавать свои собственные визуализации данных и элементы управления с нуля.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Какова целевая аудитория службы Power BI Embedded?

Разработчики и компании, также известный как независимые поставщики программного обеспечения (ISV), кода приложения.

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Чем Power BI Embedded отличается от службы Power BI?

Power BI представляет собой решение программного обеспечения как услуги для аналитики, которое предоставляет организациям единое представление их критически важных бизнес-данных.

Корпорация Майкрософт разработала в Power BI Embedded для независимых разработчиков, желающих внедрять визуальных элементов в свои приложения, чтобы помочь своим клиентам принимать аналитические решения. Независимые поставщики программного обеспечения это избавляет от необходимости создавать свои собственные analytics решение сами. [Внедряемая аналитика](embedding.md) позволяет пользователям получить доступ к бизнес-данные и выполнять запросы к ним информативности в приложении.


### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>В чем разница между Power BI Premium и Power BI Embedded?

Power BI Premium — это для предприятий, желающих полноценного решения BI, предоставляет единое представление его организации, партнерами, клиентами и поставщиками. Power BI Premium помогает организациям в принятии решений. Power BI Premium — это продукт SaaS, который позволяет пользователям использовать контент через мобильные приложения, разработанные приложения, или на портале Power BI.

Power BI Embedded предназначена для независимых поставщиков программного обеспечения, которые хотят внедрить визуальных элементов в свои приложения. Power BI Embedded помогает клиентам принимать решения. Так как эта служба создана для разработчиков приложений, пользователи этих приложений, как в организации, так и за ее пределами, могут работать с содержимым, хранящимся в емкости Power BI Embedded. Нельзя совместно использовать Power BI Embedded емкости содержимого с помощью одного щелчка публикации в Интернете или публикации одним щелчком в SharePoint.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>В каких случаях корпорация Майкрософт рекомендует покупать Power BI Premium, а в каких — Power BI Embedded?

Корпорация Майкрософт рекомендует, что организациям покупать Power BI Premium, корпоративного уровня, решения бизнес-Аналитики самообслуживания облака. Мы рекомендуем независимые поставщики программного обеспечения купить Power BI Embedded для его компонентов облачных внедренной аналитики. Тем не менее клиент не имеет ограничения, какому продукту купить.

Возможны некоторые ситуации, когда хочет Независимый (обычно большой), а также внедрения приложения, используйте P SKU, чтобы получить дополнительные возможности предварительно упакованной службы Power BI в своей организации. Некоторые предприятия могут решить использовать номера SKU A в Azure, если они собираются только создавать бизнес-приложения и внедрять в них средства аналитики, но при этом они не заинтересованы использовать предварительно упакованную службу Power BI.

### <a name="how-many-embed-tokens-can-i-create"></a>Сколько можно создать токенов внедрения?

Внедрение маркеров с лицензией PRO предназначены для тестирования разработки, поэтому Power BI главной учетной записи или [субъекта-службы](embed-service-principal.md) можно создавать только ограниченный набор маркеров. Необходимо [приобрести емкость](#technical) для возможности внедрения в рабочей среде. Сколько токенов, создаваемых при покупке емкость внедрения не ограничено. Выберите [Доступные компоненты](https://docs.microsoft.com/rest/api/power-bi/availablefeatures), чтобы проверить данные по использованию Embedded, выраженные в процентах от общей емкости.

## <a name="technical"></a>Технические вопросы

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>В чем разница между номерами SKU A в Azure и SKU EM в Office 365?

PowerBI.com — предприятия программного обеспечения как услуги (SaaS) решение с многие возможности, такие как социального взаимодействия, подписки по электронной почте и другие возможности. PowerBI.com помогает независимым поставщикам программного обеспечения управления свои решения внедренной аналитики, содержимого и параметры на уровне клиента.

Power BI Embedded — это платформа как услуга (PaaS) набора разработчиков API-интерфейсы можно использовать для создания внедряемые решения для аналитики.

Ниже приведен неполный список различия в функциональности.

| Признак | Power BI Embedded | Емкость Power BI Premium | Емкость Power BI Premium |
|----------------------------------------------------------------------------------|-------------------|---------------------------|---------------------------|
|   | (Номера SKU A) | (Номера SKU EM) | (Номера SKU P) |
| Внедрение артефактов из рабочих областей приложения Power BI | Емкость Azure | Емкость Office 365 | Емкость Office 365 |
| Использование отчетов Power BI во внедренном приложении | Да | Да | Да |
| Использование отчетов Power BI в SharePoint | Нет | Да | Да |
| Использование отчетов Power BI в Dynamics | Нет | Да | Да |
| Использование отчетов Power BI в Teams (за исключением мобильного приложения) | Нет | Да | Да |
| Доступ к содержимому с бесплатной лицензией Power BI на Powerbi.com и в Power BI Mobile | Нет | Нет | Да |
| Доступ к содержимому с бесплатной лицензией Power BI в приложениях MS Office | Нет | Да | Да |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Сейчас в Power BI предлагается три типа номеров SKU для внедрения: SKU A, SKU EM и SKU P. Какой из них следует приобрести в моем случае?

|  |SKU A (Power BI Embedded)  |SKU EM (Power BI Premium)  |SKU P (Power BI Premium)  |
|---------|---------|---------|---------|
|Покупка  |Портал Azure |Office |Office |
|Варианты использования | Внедрение содержимого в собственное приложение | <li> Внедрение содержимого в собственное приложение <br><br><br> <li> Внедрение содержимого в приложения MS Office: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (за исключением мобильного приложения)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) | <li> Внедрение содержимого в собственное приложение <br><br><br> <li> Внедрение содержимого в приложения MS Office: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (за исключением мобильного приложения)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) <br><br><br> <li> Предоставление общего доступа к содержимому пользователям Power BI через [службу Power BI](https://powerbi.microsoft.com/)  |
|Выставление счетов |Каждый час |Ежемесячно |Ежемесячно |
|Обязательство  |Никаких обязательств |Ежегодно  |Ежемесячно или ежегодно |
|Отличия |Полная гибкость — масштабируемость, приостановление и возобновление использования ресурсов на портале Azure или с помощью API  |Можно использовать для внедрения содержимого в SharePoint Online и Microsoft Teams (за исключением мобильное приложение) |Объединение возможности внедрения в приложение и использования службы Power BI в одной емкости |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Что необходимо для создания емкости PBIE в Azure?

* Войдите в каталог организации (корпорации Майкрософт, учетные записи не поддерживаются).
* Необходимо иметь клиент Power BI, то есть по крайней мере один пользователь в вашем каталоге зарегистрировался в Power BI. 
* Необходимо иметь подписку Azure в каталоге организации.

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>Как отслеживать использование емкости Power BI Embedded?

* На [портале администрирования Power BI](../service-admin-portal.md#power-bi-embedded).

* Загрузка [приложения метрик](https://review.docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity) в Power BI.

* С помощью [Журнала диагностики Azure](azure-pbie-diag-logs.md).

### <a name="can-my-capacity-scale-automatically-to-adjust-to-my-app-consumption"></a>Можно ли емкость автоматически масштабироваться в соответствии на использование приложения?

Хотя не автоматическое масштабирование сейчас, все API доступны для масштабирования в любое время.

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>Почему создание, масштабирование и возобновление емкости приводит к переводу емкости в приостановленное состояние?

Может произойти сбой подготовки емкости (масштаб или resume или создания). API получения сведений можно использовать для проверки емкости ProvisioningState: [Емкость -> Получить сведения](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails).

### <a name="can-i-only-create-power-bi-embedded-capacities-in-a-specific-region"></a>Я могу создавать емкости Power BI Embedded только в определенном регионе?

С функцией [Поддержка нескольких регионов (предварительная версия)](embedded-multi-geo.md) вы можете приобрести [емкость Power BI Embedded](azure-pbie-create-capacity.md) в регионе, где не расположен ваш домашний клиент Power BI

### <a name="how-can-i-find-my-pbi-tenant-region"></a>Как найти мой регион клиента элемента невыполненной работы?

Чтобы найти регион, элемента невыполненной работы клиента можно использовать на портале элемента невыполненной работы.

[https://app.powerbi.com/](https://app.powerbi.com/) > ? > О Power BI

![О Power BI](media/embedded-faq/about-01.png)
![Регион клиента](media/embedded-faq/tenant-location-01.png)

### <a name="what-does-the-cloud-solution-provider-csp-channel-support"></a>Что поддерживает канал поставщика облачных решений (CSP)?

* Вы можете создать PBIE для вашего клиента с типом подписки CSP.
* Пользователь с партнерской учетной записью может войти в клиент заказчика и приобрести для него PBIE, указав пользователя клиента в качестве администратора емкости Power BI.

### <a name="why-do-i-get-an-unsupported-account-message"></a>Почему я получаю сообщение о неподдерживаемой учетной записи?

Регистрация в Power BI подразумевает использование корпоративной учетной записи. При попытке зарегистрироваться в Power BI, используя учетную запись Майкрософт не поддерживается.

### <a name="can-i-use-apis-to-create-and-manage-azure-capacities"></a>Можно ли использовать API-интерфейсы для создания и управления Azure емкости?

Да, существуют командлеты Powershell и API REST диспетчера ресурсов Azure, можно использовать для создания и управления ресурсами PBIE.

* [Интерфейсы REST API](https://docs.microsoft.com/rest/api/power-bi-embedded/)
* [Командлеты PowerShell](https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/)

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>Что такое роль выделенной емкости PBI Embedded в решении PBI Embedded?

Чтобы [перенос решения в рабочей среде](embed-sample-for-customers.md#move-to-production), необходимо назначить содержимое Power BI (рабочей области приложения), приложение использует емкости Power BI Embedded (SKU).

### <a name="in-what-azure-regions-is-pbi-embedded-available"></a>В каких регионах Azure доступна внедренного элемента невыполненной работы?

[PAM](https://ecosystemmanager.azurewebsites.net/home) (EcoManager) — см. раздел "Менеджер по наличию продуктов"

Доступные регионы (16 — те же регионы, что и для Power BI)

* США (6) — восточная часть США, восточная часть США 2, центрально-северная часть США, центрально-южная часть США, западная часть США, западная часть США 2
* Европа (2) — северная Европа, западная Европа
* Азиатско-Тихоокеанский регион (2) — юго-восточная Азия, восточная Азия
* Бразилия (1) — южная часть Бразилии
* Япония (1) — восточная Япония
* Австралия (1) — юго-восточная часть Австралии
* Индия (1) — западная Индия
* Канада (1) — центральная Канада
* Великобритания (1) — южная часть Соединенного Королевства

### <a name="what-is-power-bi-embeddeds-authentication-model"></a>Что такое Power BI Embedded в модель проверки подлинности?

Power BI Embedded будет продолжать использовать Azure AD для аутентификации главного пользователя (назначенный пользователь лицензией Power BI Pro) или с [субъекта-службы](embed-service-principal.md) для проверки подлинности приложения в Power BI.  

 Приложение (ISV) можно реализовать собственные проверки подлинности и авторизации в своих приложениях.

Можно использовать существующий каталог, если у вас уже есть клиент Azure AD. Также можно создать новый клиент Azure AD для вашей безопасность содержимого приложения.

Чтобы получить токен Azure AD, можно использовать одну из [библиотек проверки подлинности Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries). Клиентские библиотеки доступны для различных платформ.

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-a-user-owns-data-scenario"></a>Мое приложение уже использует AAD для проверки подлинности пользователей. Как можно использовать это удостоверение при проверке подлинности в Power BI в сценарии "Данные, принадлежащие пользователю"?

Это стандартный поток on-behalf-of OAuth (<https://docs.microsoft.com/azure/active-directory/develop/web-api>). Необходимо настроить приложению требуются разрешения Power BI обслуживание (с обязательным области). Получив маркер пользователя к приложению, просто вызовите для ADAL API AcquireTokenAsync, с помощью доступа пользователей маркеров и укажите URL-адрес ресурса Power BI как идентификатор ресурса:

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

### <a name="what-object-id-is-the-service-principal-object-id"></a>То, что объект, идентификатор — идентификатор объекта субъекта-службы?

*Идентификатор объекта* на главном экране зарегистрированного приложения — это идентификатор объекта для приложения.

Объект, находящийся идентификатор в *управляемого приложения в локальном каталоге > свойства* раздела является идентификатор объекта субъекта-службы, необходимо использовать. Этот идентификатор объекта равен для ссылки на субъект-службу для операций или внести изменения в объект субъекта-службы, в код. Например, применение субъекта-службы как администратор в рабочую область.

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Чем Power BI Embedded отличается от других служб Azure?

Прежде чем приобрести Power BI Embedded в Azure, необходимо иметь учетную запись Power BI. В Power BI Embedded развернутых регион определяет учетную запись Power BI. Управляйте ресурсом Power BI Embedded в Azure для следующих действий:

* увеличение или уменьшение масштаба;
* добавление администраторов емкости;
* Приостановка или возобновление службы

Используйте PowerBI.com, чтобы назначать рабочие области и отменять их назначение для емкости Power BI Embedded.

### <a name="what-are-the-supported-deploy-regions"></a>Каковы поддерживаемые регионы развертывания?

Восточная часть США 2, восточная Япония, Западная Европа, западная Индия, западная часть США, западная часть США 2, северная Европа, центрально-северная часть США, центральная Канада, юго-восточная Австралия, Юго-Восточная Азия, центрально-южная часть США, южная Бразилия и южная часть Соединенного Королевства.

### <a name="what-content-pack-data-types-can-you-embed"></a>Какие типы данных пакета содержимого можно внедрять?

Вы *невозможно* внедрить **панелей мониторинга** и **плитки** построен на основе наборов данных в пакете содержимого. Тем не менее вы *можно* внедрить **отчеты** построен на основе набора данных пакета содержимого.

### <a name="what-is-the-difference-between-using-row-level-security-rls-vs-javascript-filters"></a>Какова разница между использованием vs безопасность на уровне строк (RLS). фильтров JavaScript?

Обычно имеется путаться при использовать безопасность на уровне СТРОК и фильтры JavaScript, так как один из методов — об управлении, что можно увидеть конкретного пользователя, а другой — об оптимизации представление пользователя.

При использовании RLS разработчик независимого поставщика программного обеспечения управляет фильтрацией данных в процессе создания модели и поколения токенов внедрения. Конечный пользователь видит только то, на что независимый поставщик программного обеспечения предоставляет доступ. В этом случае пользователь может выбрать меньшее, чем то, что фильтровалось, но не сможет обойти конфигурацию RLS и увидеть больше, чем разрешено.

Для клиентского сценария фильтрации (JavaScript) независимый поставщик может решить, конечный пользователь видит в исходное представление, но они не может контролировать изменения, которые конечный пользователь может применить к самому представлению. Так как пользователь клиентский код Javascript может активировать фильтрации в серверной части данных, он не может считаться безопасным.

Для дополнительной информации см. раздел [Сравнение использования RLS и фильтров JavaScript](embedded-row-level-security.md#using-rls-vs-javascript-filters).

### <a name="how-do-i-manage-permissions-for-service-principals-with-power-bi"></a>Как управлять разрешениями для субъектов-служб в Power BI?

После включения [субъекта-службы](embed-service-principal.md) для использования с Power BI, приложения AD разрешений не вступают в силу больше. В дальнейшем управление разрешениями приложения осуществляется на портале администрирования Power BI.

Субъекты-службы наследуют разрешения для всех параметров клиента Power BI от своей группы безопасности. Чтобы ограничить разрешения, создайте группу безопасности, выделенных для субъектов-служб и добавьте его в **за исключением отдельных групп безопасности** списка для соответствующих, включенных параметров Power BI.

Это важно, когда вы добавляете субъект-службу в качестве **администратора** в новую рабочую область. Эту задачу можно выполнить с помощью [интерфейсов API](https://docs.microsoft.com/rest/api/power-bi/groups/addgroupuser) или службы Power BI.

### <a name="when-to-use-an-application-id-vs-a-service-principal-object-id"></a>Когда следует использовать идентификатор приложения, а когда — идентификатор объекта субъекта-службы?

**[Идентификатор приложения](embed-sample-for-customers.md#application-id)** используется для создания маркера доступа при передаче этого идентификатора для проверки подлинности.

При выполнении операций с субъектом-службой или внесении изменений в него, например добавлении субъекта-службы в качестве администратора в рабочую область, на него необходимо ссылаться по **[идентификатору объекта субъекта-службы](embed-service-principal.md#how-to-get-the-service-principal-object-id)** .

### <a name="can-you-manage-an-on-premises-data-gateway-with-service-principal"></a>Можно ли управлять локальным шлюзом данных с помощью субъекта-службы?

С помощью [субъекта-службы](embed-service-principal.md) нельзя управлять локальным шлюзом данных, как с помощью главной учетной записи.

Используя главную учетную запись, можно установить шлюз данных, добавить в него пользователей, подключиться к источникам данных и выполнять другие задачи администрирования.

С помощью субъекта-службы можно настроить [безопасность на уровне строк (RLS)](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal-preview), используя в качестве источника данных активное подключение к локальным службам SQL Server Analysis Services (SSAS). Это позволит управлять пользователями и их доступом к данным в службах SSAS при интеграции с **Power BI Embedded** посредством субъекта-службы.

### <a name="can-you-sign-into-the-power-bi-service-with-service-principal"></a>Можно ли входить в службу Power BI с помощью субъекта-службы?

Нет, входить в службу Power BI с помощью субъекта-службы нельзя.

Кроме того, нельзя использовать содержимое во внешних приложениях (внедренных по модели SaaS). Для этого требуется создать токен внедрения.

### <a name="what-are-the-best-practices-to-improve-performance"></a>Рекомендации по повышению производительности

[Производительность Power BI Embedded](embedded-performance-best-practices.md)

## <a name="licensing"></a>Лицензирование

### <a name="how-do-i-purchase-power-bi-embedded"></a>Как приобрести Power BI Embedded?

Служба Power BI Embedded доступна в Azure.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-power-bi-embedded-in-azure-benefits"></a>Что произойдет, если я уже приобрели Power BI Premium, и я хочу некоторые Power BI Embedded в Azure преимущества?

Клиенты по-прежнему оплачивать все существующие покупки Power BI Premium до окончания срока действия текущего соглашения и, в этот момент смогут перенести покупки Power BI Premium в их при необходимости.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Требуется ли приобрести Power BI Premium, чтобы получить доступ к Power BI Embedded?

Нет. Power BI Embedded включает в себя емкость Azure, которая требуется для развертывания и распространения решений для клиентов.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Какие существуют обязательства по приобретению Power BI Embedded?

Пользователи могут изменять способ использования на почасовой основе. Нет нет ежегодного или ежемесячного обязательства для службы Power BI Embedded.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Как плата за использование Power BI Embedded отражается в счете?

Плата за использование Power BI Embedded предусматривает прогнозируемую почасовую тарификацию с учетом типа развернутых узлов. Плата взимается, до тех пор, пока ресурс активен, даже если не используется. Необходимо приостановить ресурса необходимо прекратить выставление счетов.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Кому требуется лицензия Power BI Pro для Power BI Embedded и почему?

Вам нужна лицензия Power BI Pro или [субъекта-службы](embed-service-principal.md) использовать интерфейсы REST API. Чтобы добавить отчеты в рабочую область Power BI, аналитик должен лицензия Power BI Pro или службы субъекта. Чтобы управлять клиентом Power BI и емкость, необходим администратор иметь лицензию Power BI Pro.

Так как Power BI Embedded позволяет использовать портала Power BI для управления и проверки внедренного содержимого, лицензия Power BI Pro требуется для проверки подлинности приложения powerbi.com, чтобы получить доступ к отчетам в нужных репозиториях.

Однако для [создания или изменения внедренных отчетов](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View) внутри собственного приложения конечному пользователю не требуется лицензия Pro, так как ему вообще необязательно быть пользователем Power BI.

### <a name="can-i-get-started-for-free"></a>Можно ли начать работу бесплатно?

Да, вы можете использовать [деньги на счете в Azure](https://azure.microsoft.com/free/) для Power BI Embedded.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Можно ли получить пробную версию Power BI Embedded в Azure?

Так как Power BI Embedded является частью Azure, существует возможность использования службы с [200 долл. США, полученных при регистрации в Azure](https://azure.microsoft.com/free/).

### <a name="is-power-bi-embedded-available-for-national-clouds-us-government-germany-china"></a>Доступна ли службы Power BI Embedded в национальных облаках (для государственных организаций США, Германии и Китая)?

Power BI Embedded также доступна для [национальных облаках](embed-sample-for-customers-national-clouds.md).

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Будет ли Power BI Embedded доступна для некоммерческих и образовательных организаций?

Нет нет специальных цен для некоммерческие и образовательные Azure.

## <a name="power-bi-workspace-collection"></a>Коллекция рабочих областей Power BI

### <a name="what-is-power-bi-workspace-collection"></a>Что такое коллекция рабочих областей Power BI?

**Power BI коллекции рабочих областей** (**Power BI Embedded** версии 1) основан на решении **коллекции рабочих областей Power BI** ресурсов Azure. Это решение позволяет создавать приложения **Power BI Embedded** для предоставления клиентам содержимого Power BI, размещенного в решении **Коллекция рабочих областей Power BI** с помощью специальных интерфейсов API и ключей рабочей области для проверки подлинности приложения в Power BI.

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>Можно ли перенести содержимое из коллекции рабочих областей Power BI в Power BI Embedded?

1. Средство миграции позволяет клонировать содержимое из **коллекции рабочих областей Power BI** в Power BI — https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration.

2. Для начала примените POC-приложение **Power BI Embedded**, которое использует содержимое Power BI.

3. Когда вы будете готовы перейти в рабочую среду, приобретите выделенную емкость **Power BI Embedded** и назначьте ей определенное содержимое (рабочую область) Power BI.

    > [!Note]
    > Вы можете продолжать работу с **коллекцией рабочих областей Power BI** параллельно с созданием решения **Power BI Embedded**. Когда вы будете полностью готовы, перенесите данные клиента в новое решение **Power BI Embedded** и прекратите использовать решение **Коллекция рабочих областей Power BI**.

Дополнительные сведения см. в статье [о переносе содержимого из коллекции рабочих областей Power BI в Power BI Embedded](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded).

### <a name="is-power-bi-workspace-collection-on-a-deprecation-path"></a>Коллекции рабочих областей Power BI находится на пути об устаревании?

Да, но клиенты, которые уже применяют **коллекции рабочих областей Power BI** решения можно продолжать использовать его до устаревания. Клиенты также могут создавать коллекции рабочих областей и приложения **Power BI Embedded**, использующие решения на основе **коллекции рабочих областей Power BI**.

Тем не менее, это также означает, что новые функции, не добавляемые в любую **коллекции рабочих областей Power BI** решения. Мы рекомендуем клиентам спланировать их перехода к новому **Power BI Embedded** решения.

### <a name="when-is-power-bi-workspace-collection-support-discontinued"></a>Когда будет прекращена поддержка коллекции рабочих областей Power BI?

Клиенты, которые используют решения на основе **коллекций рабочих областей Power BI**, могут продолжать работу с ними до конца июня 2018 года или до конца текущего соглашения на поддержку.

### <a name="in-what-regions-can-i-create-a-pbi-workspace-collection"></a>В каких регионах можно создать коллекцию рабочей области элемента невыполненной работы?

Это решение доступно в следующих регионах: восточная часть США 2, восточная Япония, Западная Европа, западная Индия, западная часть США, северная Европа, центрально-северная часть США, центральная Канада, юго-восточная Австралия, Юго-Восточная Азия, центрально-южная часть США, южная Бразилия и южная часть Соединенного Королевства.

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>Зачем мне переносить содержимое из коллекции рабочих областей Power BI в Power BI Embedded?

Новые **Power BI Embedded** решение функции и возможности, которые невозможно выполнить с помощью **коллекции рабочих областей Power BI**.

Вот лишь некоторые из них:
* Поддерживаются все источники данных элемента невыполненной работы. Только два **коллекции рабочих областей Power BI** поддерживаемые источники данных. 
* Новые функции, такие как вопросы и ответы, обновление, закладки, внедрение информационных панелей и плиток, а также пользовательские меню поддерживаются только в решении **Power BI Embedded**.
* модель выставления счетов по емкости.

## <a name="embedding-setup-tool"></a>Средство настройки внедрения

### <a name="what-is-the-embedding-setup-tool"></a>Что такое средство настройки внедрения?

[Средство настройки внедрения](https://aka.ms/embedsetup) позволяет быстро приступить к работе и скачать образец приложения, чтобы начать внедрение в Power BI.

### <a name="which-solution-should-i-choose"></a>Какое решение выбрать?

* [Внедрение для клиентов](embedding.md#embedding-for-your-customers) позволяет внедрять панели мониторинга и отчеты для пользователей, у которых нет учетной записи Power BI. Запустите решение [Внедрение для клиентов](https://aka.ms/embedsetup/AppOwnsData).
* [Внедрение для организации](embedding.md#embedding-for-your-organization) позволяет расширить возможности службы Power BI. Запустите решение [Внедрение для организации](https://aka.ms/embedsetup/UserOwnsData).

### <a name="ive-downloaded-the-sample-app-which-solution-do-i-choose"></a>Образец приложения скачан. Какое решение выбрать?

Если вы работаете с решением **Внедрение для клиентов**, сохраните и распакуйте файл *PowerBI-Developer-Samples.zip*. Затем откройте папку *PowerBI-Developer-Samples-master\App Owns Data* и запустите файл *PowerBIEmbedded_AppOwnsData.sln*.

Если вы работаете с решением **Внедрение для организации**, сохраните и распакуйте файл *PowerBI-Developer-Samples.zip*. Затем откройте папку *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* и запустите файл *pbi-saas-embed-report.sln*.

### <a name="how-can-i-edit-my-registered-application"></a>Как изменить зарегистрированное приложение?

Узнать, как изменять зарегистрированные в Azure AD приложения, можно в [руководстве по обновлению приложения в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-update-azure-ad-app).

### <a name="how-can-i-edit-my-power-bi-user-profile-or-data"></a>Как изменить профиль пользователя или данные Power BI?

Узнать, как изменить данные Power BI, можно [здесь](https://docs.microsoft.com/power-bi/service-basic-concepts).

Дополнительные сведения: [Устранение неполадок внедренного приложения](embedded-troubleshoot.md).

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)
