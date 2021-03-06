---
title: Лицензирование Power BI для пользователей в организации
description: Общие сведения о различных типах пользовательских лицензий, доступных в Power BI, а также о том, как администраторы приобретают лицензии для пользователей в своей организации и управляют ими.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 06/24/2020
ms.author: kfollis
ms.custom: licensing support
LocalizationGroup: Administration
ms.openlocfilehash: 825b336a96b998c04b019195ad3f3beea96d0a19
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90857296"
---
# <a name="licensing-the-power-bi-service-for-users-in-your-organization"></a>Лицензирование службы Power BI для пользователей в организации

Действия, которые может выполнять пользователь в службе Power BI, зависят от типа имеющейся у пользователя лицензии. Уровень доступа, предоставляемый лицензией, зависит от того, назначена ли рабочая область, к которой выполняется доступ, емкости Power BI Premium. У каждого пользователя службы Power BI должна быть лицензия.

Получить лицензии для пользователей можно двумя способами. Пользователь может получить бесплатную лицензию или лицензию Pro самостоятельно, используя возможности самостоятельной регистрации и свою рабочую или учебную учетную запись. Администраторы могут получить подписку Power BI и назначить лицензии пользователям.

В этой статье приобретение лицензий и лицензирование "на пользователя" рассматривается с точки зрения администратора. Дополнительные сведения о самостоятельном получении лицензий пользователями см. в статье [Регистрация учетной записи отдельного пользователя в Power BI](../fundamentals/service-self-service-signup-for-power-bi.md).

## <a name="who-can-purchase-and-assign-licenses"></a>Кто может приобретать и назначать лицензии?

Для приобретения или назначения лицензий в организации требуется роль администратора. Она назначается с помощью центра администрирования Azure Active Directory или центра администрирования Microsoft 365. В приведенной ниже таблице показано, какая роль необходима для выполнения задач, связанных с покупкой и лицензированием. Дополнительные сведения о ролях администраторов в Azure Active Directory см. в руководстве по [просмотру и назначению ролей администратора в Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal). Дополнительные сведения о ролях администраторов в Microsoft 365, включая рекомендации, см. в статье [Роли администраторов](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide).

| Кто может приобретать службы и лицензии? | Кто может управлять лицензиями пользователей? |
| --------------- | --------------- |
| Администратор выставления счетов | Администратор лицензий |
| Глобальный администратор | Администратор пользователей |
|  | Глобальный администратор |

Эти роли управляют организацией. Сведения о ролях администраторов в службе Power BI см. в статье [Основные сведения о ролях администратора службы Power BI](service-admin-role.md).

## <a name="get-power-bi-for-your-organization"></a>Получение Power BI для вашей организации

Сведения о ценах см. на странице с [ценами и сравнением продуктов](https://powerbi.microsoft.com/pricing/).

Глобальный администратор или администратор выставления счетов может зарегистрироваться в службе Power BI и приобрести лицензии для пользователей в организации. Если вы не готовы к покупке, выберите пробную версию Power BI Pro. Вы получите 25 лицензий на один месяц. Пошаговые инструкции по регистрации см. в статье [Получение подписки Power BI для организации](service-admin-org-subscription.md).

## <a name="about-self-service-sign-up"></a>Самостоятельная регистрация

Отдельные пользователи могут получать лицензии Power BI, регистрируясь с помощью своих рабочих или учебных учетных записей. С бесплатной лицензией пользователь может использовать Power BI для анализа и визуализации личных данных в разделе "Моя рабочая область", но не может поделиться ей с другими пользователями. Для совместного использования содержимого требуется лицензия Power BI Pro. Пользователь может повысить уровень своей лицензии до Pro или зарегистрировать лицензию Pro напрямую, если в организации используется коммерческое облако. Прямое приобретение лицензий или их повышение до уровня Pro недоступно для учебных заведений или организаций, развернутых в Azure для государственных организаций, Azure для Германии или Azure для Китая (21Vianet).

Если вы не хотите, чтобы пользователям вашей организации была доступна самостоятельная регистрация, см. инструкции по ее отключению в статье [Включение или отключение самостоятельной регистрации](service-admin-disable-self-service.md).

При отключенной самостоятельной регистрации пользователи не смогут изучать возможности визуализации и анализа данных в Power BI. Если вы заблокируете индивидуальную регистрацию, мы рекомендуем вам получить лицензии Power BI (бесплатная версия) для организации и назначить их всем пользователям. Выполните следующие действия, чтобы автоматически назначить лицензии Power BI (бесплатная версия) всем существующим пользователям:

1. Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com), используя учетные данные глобального администратора или администратора выставления счетов.
1. В левой боковой панели выберите **Выставление счетов** > **Приобретение служб**.
1. Найдите предложение Power BI (бесплатная версия) или прокрутите к нему. Выберите предложение, а затем выберите **Получить**.
1. Введите количество лицензий, которое потребуется для их назначения всем пользователям.
1. Выберите **Автоматически назначить всем пользователям без лицензий**, а затем оформите заказ.

  ![Снимок экрана: Power BI: бесплатная автоматически назначаемая подписка Power BI, в которой показана самостоятельная регистрация](media/service-admin-licensing-organization/m365-auto-assign.png)

Если вы хотите узнать, у каких пользователей в организации уже есть лицензии, см. статью [Просмотр пользовательских лицензий и управление ими](service-admin-manage-licenses.md).

## <a name="license-types-and-capabilities"></a>Типы лицензий и возможности

Существует два типа лицензий Power BI "на пользователя": бесплатные и Pro. Требуемый пользователю тип зависит от того, где хранится содержимое и как пользователь будет взаимодействовать с ним. Место хранения содержимого определяется [типом подписки](#subscription-types) вашей организации.

Подписка [Power BI Premium](service-admin-premium-purchase.md) позволяет пользователям с бесплатными лицензиями работать с содержимым в рабочих областях, назначенных емкости Premium. Вне емкости Premium пользователь с бесплатной лицензией может использовать службу Power BI для подключения к данным и создания отчетов и панелей мониторинга только в рабочей области **Моя рабочая область**. Он не может обмениваться содержимым с другими пользователями или публиковать содержимое в других рабочих областях. Дополнительные сведения о типах рабочих областей см. в разделе [Типы рабочих областей](../consumer/end-user-workspaces.md#types-of-workspaces).

Стандартная подписка Power BI использует общую емкость. Если содержимое хранится в общей емкости, пользователи, которым назначены лицензии Power BI Pro, могут работать совместно только с другими пользователями Power BI Pro. Они могут использовать содержимое, предоставленное другими пользователями, публиковать содержимое в рабочих областях приложений, совместно использовать панели мониторинга и подписываться на панели мониторинга и отчеты.  Когда рабочие области находятся в емкости Premium, пользователи с лицензиями Pro могут распространять содержимое для пользователей, у которых нет лицензий Power BI Pro.

В таблице ниже представлены основные возможности каждого типа лицензии. Подробные сведения о доступности функций для каждого типа лицензии см. в статье [Функции по типам лицензий](../fundamentals/service-features-license-type.md).

| Тип лицензии | Возможности, когда рабочая область находится в общей емкости | Дополнительные возможности, когда рабочая область находится в емкости Premium |
| --------- | ----------- | ----------- |
| Power BI (бесплатная версия) | Доступ к содержимому в личной рабочей области | Использование содержимого, к которому предоставлен общий доступ |
| Power BI Pro | Публикация содержимого в других рабочих областях, совместное использование панелей мониторинга, подписка на панели мониторинга и отчеты, предоставление доступа пользователям с лицензиями Pro | Распространение содержимого для пользователей с бесплатными лицензиями |

## <a name="subscription-types"></a>Типы подписок

Все коммерческие подписки с лицензиями "на пользователя" от корпорации Майкрософт основаны на удостоверениях Azure Active Directory. Для использования службы Power BI необходимо войти, используя удостоверение Azure Active Directory, поддерживаемое для коммерческих лицензий. Power BI можно добавить в любую подписку Майкрософт, которая использует Azure Active Directory для идентификации. Некоторые подписки, например Office 365 E5, включают лицензию Power BI Pro, поэтому регистрировать Power BI отдельно не требуется.

Существует два вида подписок Power BI для организаций: Standard и Premium.

При использовании стандартной подписки Power BI Pro с самообслуживанием администраторы назначают лицензии "на пользователя". Лицензии Power BI Pro подразумевают ежемесячную плату за каждого пользователя. Такая лицензия позволяет организовать совместную работу, публикацию, совместный доступ и специализированный анализ. Содержимое сохраняется в общей емкости, которая полностью управляется корпорацией Майкрософт.

При регистрации подписки Power BI Premium организации предоставляется выделенная емкость. Емкость Premium подходит для корпоративной бизнес-аналитики, анализа больших данных, а также создания облачных и локальных отчетов. Она предоставляет расширенные возможности управления и развертывания. Выделенные вычислительные ресурсы и ресурсы хранения управляются администраторами емкости в организации. За выделенную среду взимается ежемесячная плата. Помимо других преимуществ Premium, содержимое, хранящееся в емкости Premium, можно предоставлять и распространять для пользователей, у которых нет лицензий Power BI Pro. При этом по крайней мере у одного пользователя должна быть лицензия Power BI Pro с правом использования емкости Premium, а создателям содержимого и разработчикам по-прежнему требуются лицензии Power BI Pro.

Два типа подписок не являются взаимоисключающими. Можно иметь одновременно и подписку Power BI Premium, и подписку Power BI Pro. В такой конфигурации содержимое, хранящееся в емкости Premium, может использоваться совместно всеми пользователями, а также доступна общая емкость. Сведения об ограничениях емкости см. в статье [Управление хранилищем данных в рабочих областях Power BI](service-admin-manage-your-data-storage-in-power-bi.md).

Сравнение возможностей и цен см. на странице [Цены на Power BI](https://powerbi.microsoft.com/pricing).

## <a name="guest-user-access"></a>Доступ гостевых пользователей

Вам может потребоваться распространить содержимое для пользователей за пределами вашей организации. Чтобы предоставить доступ к содержимому внешним пользователям, можно пригласить их к просмотру содержимого в качестве гостей. Azure Active Directory "бизнес-бизнес" (Azure AD B2B) позволяет совместно использовать содержимое с внешними гостевыми пользователями. Для предоставления доступа внешним пользователям необходимо выполнить следующие предварительные требования:

- должна быть включена возможность совместного использования содержимого с внешними пользователями;

- у гостевого пользователя должна быть соответствующая лицензия для просмотра общего содержимого.

Дополнительные сведения о доступе гостевых пользователей см. в статье [Предоставление содержимого Power BI внешним гостевым пользователям с помощью Azure AD B2B](service-admin-azure-ad-b2b.md).

## <a name="purchase-power-bi-pro-licenses"></a>Приобретение лицензий Power BI Pro

Лицензии Power BI Pro администратор может приобрести через службу Microsoft 365 или через партнера корпорации Майкрософт. После приобретения лицензий они назначаются отдельным пользователям. Дополнительные сведения см. в разделе [Приобретение и назначение лицензий Power BI Pro](service-admin-purchasing-power-bi-pro.md).

### <a name="power-bi-pro-license-expiration"></a>Окончание срока действия лицензии Power BI Pro

После истечения срока действия лицензии Power BI Pro предоставляется льготный период. Для лицензий, которые являются частью корпоративной лицензии, льготный период составляет 90 дней. Если вы приобрели лицензию напрямую, льготный период составляет 30 дней.

У подписки Power BI Pro такой же жизненный цикл, как и у подписки Microsoft 365. См. дополнительные сведения о [работе с данными и доступе после истечения срока действия подписки Microsoft 365 для бизнеса](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires).


## <a name="next-steps"></a>Дальнейшие действия

- [Приобретение и назначение лицензий Power BI Pro](service-admin-purchasing-power-bi-pro.md)
- [Документация по бизнес-подпискам и выставлению счетов](/microsoft-365/commerce/?view=o365-worldwide)
- [Поиск пользователей Power BI, выполнивших вход](service-admin-access-usage.md)
- Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)