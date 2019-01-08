---
title: Подключение к Zendesk с помощью Power BI
description: Zendesk для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 72b934357ec4208fa07266143b08af861659e465
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008334"
---
# <a name="connect-to-zendesk-with-power-bi"></a>Подключение к Zendesk с помощью Power BI
Пакет содержимого Zendesk включает панель мониторинга Power BI с отчетами, с помощью которых можно получить представление об объемах заявок и производительности операторов. Используйте стандартные панели мониторинга и отчеты или настройте их так, чтобы выделить информацию, которая наиболее важна для вас.  Данные автоматически обновляются раз в день. 

Подключитесь к [пакету содержимого Zendesk](https://app.powerbi.com/getdata/services/zendesk) или прочтите дополнительные сведения об [интеграции Zendesk](https://powerbi.microsoft.com/integrations/zendesk) с Power BI.

>[!NOTE]
>Для подключения требуется учетная запись администратора Zendesk. Дополнительные сведения о [требованиях](#Requirements) см. ниже.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
   ![](media/service-connect-to-zendesk/pbi_getdata.png)
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-zendesk/pbi_getservices.png) 
3. Выберите **Zendesk** \> **Получить**.
   
   ![](media/service-connect-to-zendesk/zendesk.png)
4. Укажите URL-адрес, связанный с вашей учетной записью. Он будет в формате **https://company.zendesk.com**. Сведения о том, как [найти эти параметры](#FindingParams), см. ниже.
   
   ![](media/service-connect-to-zendesk/pbi_zendeskconnect.png)
5. При появлении запроса введите учетные данные Zendesk.  Выберите механизм проверки подлинности **oAuth 2** и нажмите **Войти**. Следуйте инструкциям проверки подлинности Zendesk. (Если вы уже выполнил вход в Zendesk в браузере, учетные данные могут не запрашиваться.)
   
   > [!NOTE]
   > Для этого пакета содержимого необходимо подключиться с помощью учетной записи администратора Zendesk. 
   > 
   > 
   
   ![](media/service-connect-to-zendesk/pbi_zendesksignin.png)
6. Нажмите кнопку **Разрешить** , чтобы предоставить Power BI доступ к данным Zendesk.
   
   ![](media/service-connect-to-zendesk/zendesk2.jpg)
7. Нажмите кнопку **Подключить** , чтобы начать импорт. После импорта данных в Power BI в области навигации слева появятся новая панель мониторинга, отчет и набор данных. Новые элементы отмечены желтой звездочкой \*.
   
   ![](media/service-connect-to-zendesk/pbi_zendeskdash.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="whats-included"></a>Содержимое
Пакет содержимого Power BI включает в себя данные из следующих таблиц.  

* Пользователи (конечные пользователи и агенты)  
* Организации  
* Группы  
* Обращения  

Существует также набор мер, таких как среднее время ожидания и решенные обращения за последние семь дней. Полный список указан в пакете содержимого.

<a name="Requirements"></a>

## <a name="system-requirements"></a>Требования к системе
Для доступа к пакету содержимого Zendesk требуется учетная запись администратора Zendesk. Если вы являетесь агентом или конечным пользователем и хотите просмотреть данные Zendesk, добавьте предложение и проверьте соединитель Zendesk в [Power BI Desktop](desktop-connect-to-data.md).

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Поиск параметров
URL-адрес Zendesk будет совпадать с URL-адресом, который используется для входа в учетную запись Zendesk. Если вы не знаете URL-адрес Zendesk, можно использовать [справку по входу](https://www.zendesk.com/login/) Zendesk.

## <a name="troubleshooting"></a>Устранение неполадок
Если у вас возникли проблемы с подключением, проверьте URL-адрес Zendesk и убедитесь, что вы используете учетную запись администратора Zendesk.

## <a name="next-steps"></a>Дальнейшие действия
* [Что такое Power BI?](power-bi-overview.md)
* [Получение данных](service-get-data.md)

