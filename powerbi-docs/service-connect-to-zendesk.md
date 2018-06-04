---
title: Подключение к Zendesk с помощью Power BI
description: Zendesk для Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 997dd8b598e67d590723c72fb35245c3b3486c8b
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34242453"
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

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](power-bi-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

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
* [Приступая к работе с Power BI](service-get-started.md)
* [Получение данных](service-get-data.md)

