---
title: Подключение к Xero с помощью Power BI
description: Xero для Power BI
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 03/06/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: adb2f66b043b09ecb584870cf96f4c491960d59b
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348443"
---
# <a name="connect-to-xero-with-power-bi"></a>Подключение к Xero с помощью Power BI
Xero — простое и удобное программное обеспечение для онлайн-бухгалтерии, предназначенное специально для небольших предприятий. Шаблон приложение Xero для Power BI позволит вам создавать интересные визуализации на основе своих финансовых данных. Панель мониторинга по умолчанию содержит множество метрик, характерных для малого бизнеса. Они предназначены для отслеживания таких показателей, как состояние денежной наличности, доходы и расходы, динамика доходов и расходов, срок покрытия дебиторской задолженности и рентабельность инвестиций.

Подключитесь к [шаблону приложения Xero](https://app.powerbi.com/getdata/services/xero) для Power BI или ознакомьтесь с дополнительными сведениями об интеграции [Xero с Power BI](https://help.xero.com/Power-BI).

## <a name="how-to-connect"></a>Способы подключения

[!INCLUDE [powerbi-service-apps-get-more-apps](../includes/powerbi-service-apps-get-more-apps.md)]

3. Выберите **Xero** \> **Получить сейчас**.
4. В окне **Установить это приложение Power BI?** выберите **Установить**.

    ![Установка Xero](media/service-connect-to-xero/power-bi-install-xero.png)

4. В области **Приложения** выберите плитку **Xero**.

   ![Выберите плитку Xero](media/service-connect-to-xero/power-bi-start-xero.png)

6. На экране **Начало работы с новым приложением** выберите **Подключиться**.

    ![Начало работы с новым приложением](media/service-connect-to-zendesk/power-bi-new-app-connect-get-started.png)

4. Введите псевдоним для организации, связанной с вашей учетной записью Xero. Вы можете ввести любое значение (это название предназначено главным образом для пользователей, которые с помощью Xero управляют несколькими организациями). См. дополнительные сведения о [поиске параметров](#FindingParams) далее в этой статье.

    ![Псевдоним организации](media/service-connect-to-xero/params.png)

5. Для **метода проверки подлинности**выберите **OAuth**. При появлении запроса войдите и выберите организацию, к данным которой хотите подключиться. После завершения входа выберите **Войти**, чтобы начать загрузку.
   
    ![Метод проверки подлинности](media/service-connect-to-xero/creds.png)
   
    ![Вас приветствует Xero](media/service-connect-to-xero/creds2.png)
6. После утверждения процесс импорта начнется автоматически. По завершении в области навигации появится новая панель мониторинга, отчет и модель. Выберите панель мониторинга, чтобы просмотреть импортированные данные.
   
     ![Панель мониторинга Xero](media/service-connect-to-xero/power-bi-xero-dashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](../consumer/end-user-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](../create-reports/service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](../consumer/end-user-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**

## <a name="whats-included"></a>Содержимое
На панели мониторинга данного шаблона приложения представлены плитки и метрики для различных сфер деятельности, которым соответствуют отчеты.  

| С областями | Плитки панели мониторинга | Отчет |
| --- | --- | --- |
| Наличность |Поток денежных средств за сутки <br>Поступления <br>Траты <br>Итоговое сальдо по счету <br>Итоговое сальдо сегодня |Банковские счета |
| Клиент |Фактурные продажи <br>Фактурные продажи по клиентам <br>Динамика роста фактурных продаж <br>Счета к оплате <br>Дебиторская задолженность <br>Просроченная дебиторская задолженность |Клиент <br>Запасы |
| Поставщик |Покупки, по которым выставлен счет <br>Покупки, по которым выставлен счет, по поставщикам <br>Динамика роста покупок, по которым выставлен счет <br> Просроченные счета <br>Кредиторская задолженность <br>Просроченная кредиторская задолженность |Поставщики <br>Запасы |
| Запасы |Сумма продаж за месяц по товарам |Запасы |
| Прибыль и убытки |Прибыль и убытки за месяц <br>Чистая прибыль за текущий фискальный год <br>Чистая прибыль за текущий месяц <br>Основные счета по расходам |Прибыль и убытки |
| Сводный баланс |Суммарные активы <br>Суммарные обязательства <br>Собственный капитал |Сводный баланс |
| Здравоохранение |Текущее соотношение <br>Доля валовой прибыли <br> Доходность суммарных активов <br>Отношение суммарных обязательств к собственному капиталу |Здоровье <br>Глоссарий и технические примечания |

Этот набор данных также содержит перечисленные ниже таблицы для настройки отчетов и панелей мониторинга.  

* Адреса  
* Оповещения  
* Ежедневный баланс по банковской выписке  
* Банковские выписки  
* Контакты  
* Заявки на компенсацию расходов  
* Позиции в счете-фактуре  
* Счета-фактуры  
* Позиции  
* Конец месяца  
* Организация  
* Предварительный баланс  
* Счета Xero

## <a name="system-requirements"></a>Требования к системе
Для доступа к шаблону приложения Xero необходимы следующие роли: "Стандартная + Отчеты" или "Консультант".

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Поиск параметров
Укажите название организации, данные которой хотите отслеживать в Power BI. Конкретное имя позволяет подключаться к данным нескольких организаций. Подключиться к данным одной организации несколько раз нельзя, так как это затронет автоматическое обновление.   

## <a name="troubleshooting"></a>Устранение неполадок
* Для доступа к шаблону приложения Xero для Power BI пользователям Xero необходимы следующие роли: "Стандартная + Отчеты" или "Консультант". Для доступа к данным для отчетов через Power BI шаблон приложения применяет систему разрешений пользователей.
* Во время загрузки плитки на панели мониторинга в состоянии универсальной загрузки. Они остаются такими же до завершения полной загрузки. Если отобразится уведомление о завершении загрузки, но плитки будут продолжать загружаться, попробуйте обновить плитки панели мониторинга с помощью элемента "..." в верхней правой части панели мониторинга.
* Если шаблон приложения не обновляется, убедитесь, что вы не подключались в Power BI к данным одной организации несколько раз. Xero позволяет использовать только по одному активному соединению с каждой организацией, и при попытке подключиться еще раз может появиться сообщение о неправильных учетных данных.  
* В случае возникновения проблем при подключении к шаблону приложения Xero из Power BI (например, сообщений об ошибках или медленной загрузке) сначала очистите кэш, удалите файлы cookie и перезапустите браузер, а затем снова подключитесь к Power BI.  

Если у вас возникнут другие проблемы, устранить которые не удастся, отправьте запрос на сайте https://support.powerbi.com.

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](../fundamentals/service-get-started.md)

[Получение данных в Power BI](service-get-data.md)