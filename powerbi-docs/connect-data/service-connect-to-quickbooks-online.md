---
title: Подключение к QuickBooks Online с помощью Power BI
description: QuickBooks Online для Power BI
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/04/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 4c21c36694f36e4d6f95b8edc920648313dc8a7a
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348512"
---
# <a name="connect-to-quickbooks-online-with-power-bi"></a>Подключение к QuickBooks Online с помощью Power BI
При подключении к данным QuickBooks Online из Power BI вы немедленно получаете панель мониторинга и отчеты Power BI, предоставляющие информацию о денежном потоке, прибыльности, клиентах и многом другом. Используйте стандартные панели мониторинга и отчеты или настройте их так, чтобы выделить информацию, которая наиболее важна для вас. Данные автоматически обновляются раз в день.

Подключитесь к [приложению-шаблону QuickBooks Online](https://dxt.powerbi.com/getdata/services/quickbooks-online) для Power BI.

>[!NOTE]
>Для импорта данных QuickBooks Online в Power BI необходимо быть администратором учетной записи QuickBooks Online и выполнить вход с использованием учетных данных администратора. Этот соединитель нельзя использовать с программным обеспечением QuickBooks Desktop. 

## <a name="how-to-connect"></a>Способы подключения

[!INCLUDE [powerbi-service-apps-get-more-apps](../includes/powerbi-service-apps-get-more-apps.md)]

3. Выберите **QuickBooks Online**, а затем **Получить**.
   
   ![Получение QuickBooks](media/service-connect-to-quickbooks-online/qbo.png)

4. В окне **Установить это приложение Power BI?** выберите **Установить**.

    ![Установка QuickBooks](media/service-connect-to-quickbooks-online/power-bi-install-quickbooks.png)

4. В области **Приложения** выберите плитку **QuickBooks**.

   ![Выбор плитки QuickBooks](media/service-connect-to-quickbooks-online/power-bi-quickbooks-tile.png)

6. На экране **Начало работы с новым приложением** выберите **Подключиться**.

    ![Начало работы с новым приложением](media/service-connect-to-zendesk/power-bi-new-app-connect-get-started.png)

4. В качестве метода аутентификации выберите **oAuth2** и щелкните **Войти**. 
5. При появлении запроса введите учетные данные QuickBooks Online и пройдите проверку подлинности QuickBooks Online. Если вы уже выполнил вход в QuickBooks Online в браузере, учетные данные могут не запрашиваться.
   >[!NOTE]
   >Вам необходимы учетные данные администратора для учетной записи QuickBooks Online.
6. Выберите компанию, которые требуется подключить к Power BI, на следующем экране.
   
   ![Почти готово в QuickBooks](media/service-connect-to-quickbooks-online/pbi_qbo_almost.png)

7. Выберите **Авторизовать** на следующем экране, чтобы начать импорт. Этот процесс может занять несколько минут в зависимости от размера данных компании. 
   
   ![Авторизация QuickBooks](media/service-connect-to-quickbooks-online/pbi_qbo_authorizesm.png)
   
8. После импорта данных Power BI появится список содержимого приложения QuickBooks: новая панель мониторинга, отчет и набор данных.
9. Выберите панель мониторинга QuickBooks, чтобы начать процесс исследования. Служба Power BI создает ее автоматически для отображения импортированных данных.

    ![Панель мониторинга QuickBooks](media/service-connect-to-quickbooks-online/power-bi-connect-quickbooks-sample.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](../consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](../create-reports/service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](../consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="troubleshooting"></a>Устранение неполадок
**Ой! Произошла ошибка".**

Если это сообщение отображается после того, как вы выбрали команду **Авторизовать**:

"Ой. Произошла ошибка". Закройте это окно и повторите попытку.

Другой пользователь уже подписался на это приложение для этой компании. Обратитесь по адресу [электронный адрес администратора] для изменения этой подписки".

![Ой! Произошла ошибка.](media/service-connect-to-quickbooks-online/pbi_qbo_oopssm.png)

... она означает, что другой администратор в вашей компании уже подключился к данным компании с помощью Power BI. Попросите этого администратору предоставить вам доступ к панели мониторинга. В настоящее время только один администратор может подключить набор данных QuickBooks Online определенной компании к Power BI. Когда Power BI создаст панель мониторинга, администратор может предоставить к ней общий доступ для нескольких сотрудников в тех же клиентах Power BI.

**"Это приложение не разрешает подключения из вашей страны".**

В настоящее время Power BI поддерживает только выпуски QuickBooks Online для США. 

![Это приложение не разрешает подключения из вашей страны.](media/service-connect-to-quickbooks-online/pbi_qbo_countrynotsupported.png)

## <a name="next-steps"></a>Дальнейшие действия
[Что такое Power BI?](../fundamentals/power-bi-overview.md)

[Основные понятия для разработчиков в службе Power BI](../fundamentals/service-basic-concepts.md)
