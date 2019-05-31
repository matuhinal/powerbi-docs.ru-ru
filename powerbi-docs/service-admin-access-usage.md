---
title: Поиск пользователей Power BI, выполнивших вход
description: Если вы являетесь администратором клиента и хотите просмотреть, кто выполнил вход в Power BI, можно использовать отчеты о доступе и использовании Azure Active Directory, чтобы получить сведения.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: e513607dd89aee15f10145cf62bd461621cc12c0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906754"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Поиск пользователей Power BI, выполнивших вход

Если вы являетесь администратором клиента и хотите узнать, кто выполнил вход в Power BI, используйте [отчеты о доступе и использовании Azure Active Directory](/azure/active-directory/reports-monitoring/concept-sign-ins) для получения сведений.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> **Входы в систему** отчет содержит полезную информацию, но его не определить тип каждого пользователя есть лицензия. Используйте Центр администрирования Microsoft 365 для просмотра лицензий.

## <a name="requirements"></a>Требования

Любой пользователь (в том числе без прав администратора) может просмотреть отчет о своих событиях входа в систему, но для просмотра отчета для всех пользователей необходимо выполнить следующие требования.

* Клиент должен иметь лицензию Azure Active Directory Premium, связанные с ней.

* У вас должна быть одна их следующих ролей: глобальный администратор, администратор системы безопасности или читатель сведений о безопасности.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Просмотр событий входа с помощью портала Azure

Чтобы просмотреть событие входа в систему, выполните следующие действия.

1. На **портале Azure**выберите **Azure Active Directory**.

1. В разделе **Мониторинг** выберите **События входа**.
   
    ![Снимок экрана пользовательского интерфейса Azure с выделенным параметрами Azure Active Directory и входы в систему.](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. Отфильтруйте приложение по **Microsoft Power BI** или **Power BI Gateway** и выберите **Применить**.

    **Microsoft Power BI** фильтры для входа в систему, связанных со службой, тогда как **Power BI Gateway** фильтры для входа в систему действий, характерных для локального шлюза данных.
   
    ![Снимок экрана фильтра входы в систему с выделенным полем приложений.](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Экспорт данных

Вы можете [загрузить отчет вход](/azure/active-directory/reports-monitoring/quickstart-download-sign-in-report) в двух форматах: файл CSV или JSON-файл.

![Снимок экрана «загрузить».](media/service-admin-access-usage/download-sign-in-data-csv.png)

В верхней части **входы в систему** отчета, выберите **загрузить** и затем выберите один из следующих вариантов:

* **CSV-ФАЙЛ** для загрузки CSV-файл для текущих отфильтрованных данных.

* **JSON** скачать JSON-файл для текущих отфильтрованных данных.

## <a name="data-retention"></a>Хранение данных

Данные о событиях входа доступны в течение 30 дней. Дополнительные сведения см. в разделе [политики хранения отчетов Azure Active Directory](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Дальнейшие действия

[Применение функции аудита в своей организации](service-admin-auditing.md)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)