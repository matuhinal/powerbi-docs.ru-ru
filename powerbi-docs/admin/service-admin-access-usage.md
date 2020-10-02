---
title: Поиск пользователей Power BI, выполнивших вход
description: Если вы являетесь администратором и хотите узнать, кто выполнил вход в Power BI, можете использовать отчеты о доступе и использовании Azure Active Directory.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 09/25/2020
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: e278918fdcf19a8de5cd5af1995bbc050dd765ec
ms.sourcegitcommit: 02b5d031d92ea5d7ffa70d5098ed15e4ef764f2a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2020
ms.locfileid: "91374752"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Поиск пользователей Power BI, выполнивших вход

Если вы являетесь администратором в организации и хотите узнать, кто выполнил вход в Power BI, воспользуйтесь [отчетами о доступе и использовании Azure Active Directory](/azure/active-directory/reports-monitoring/concept-sign-ins).

> [!NOTE]
> В отчете **Входы** предоставляется полезная информация, но в нем не определяется тип лицензии каждого пользователя. Используйте Центр администрирования Microsoft 365 для просмотра лицензий.

## <a name="requirements"></a>Требования

Любой пользователь может просмотреть отчет о своих операциях входа. Чтобы просмотреть отчет для всех пользователей, требуется одна из следующих ролей: глобальный администратор, администратор безопасности, читатель сведений о безопасности, глобальный читатель или читатель отчетов.

## <a name="use-the-azure-active-directory-admin-center-to-view-sign-ins"></a>Использование центра администрирования Azure Active Directory для просмотра сведений о входах

Чтобы просмотреть событие входа в систему, выполните следующие действия.

1. Войдите в [центр администрирования Azure Active Directory](https://aad.portal.azure.com) и в меню портала выберите **Azure Active Directory**.

1. В меню ресурсов выберите **Мониторинг** > **Входы**.
   
    ![Снимок экрана: центр администрирования Azure Active Directory с выделенным параметром "Входы".](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. По умолчанию отображаются все операции входа для всех пользователей и всех приложений за последние 24 часа. Чтобы выбрать другой период времени, в рабочей области щелкните **Дата** и выберите один из доступных интервалов времени. Доступны сведения только за последние семь дней. Чтобы просмотреть только операции входа для Power BI, добавьте фильтры. Щелкните **Добавить фильтр**, выберите **Приложение** в качестве поля для фильтрации, а затем нажмите кнопку **Применить**. В верхней части рабочей области выберите **Application starts with** (Имя приложения начинается с) и введите имя приложения. Нажмите кнопку **Применить**.

    Фильтр **Microsoft Power BI** позволяет отобразить действия входа, связанные со службой. Фильтр **Power BI Gateway** (Шлюз Power BI) позволяет отобразить действия входа, связанные с локальным шлюзом данных.
   
    ![Снимок экрана фильтра "Входы" с выделенным полем "Приложения".](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Экспорт данных

Вы можете [скачать отчет о входах](/azure/active-directory/reports-monitoring/quickstart-download-sign-in-report) в двух форматах: CSV или JSON.

1. На панели команд для отчета **Входы** выберите **Скачать** и один из следующих вариантов:

   * **CSV** для скачивания CSV-файла для текущих отфильтрованных данных.

   * **JSON** для скачивания JSON-файла для текущих отфильтрованных данных.

2. Введите имя файла и нажмите кнопку **Скачать**.

![Снимок экрана экспорта данных с выделенным параметром скачивания](media/service-admin-access-usage/download-sign-in-data-csv.png)

## <a name="data-retention"></a>Хранение данных

Данные о входах доступны в течение семи дней, если у вашей организации нет лицензии Azure AD Premium. Если вы используете лицензию Azure AD Premium P1 или Azure AD Premium P2, вам доступны данные за последние 30 дней. Дополнительные сведения см. в статье [Политики хранения отчетов Azure Active Directory](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Дальнейшие действия

[Аудит активности пользователей](service-admin-auditing.md)

Остались вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)