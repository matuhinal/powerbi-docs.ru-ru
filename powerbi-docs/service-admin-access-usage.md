---
title: Поиск пользователей Power BI, выполнивших вход
description: Если вы — администратор клиента и хотите узнать, кто выполнил вход в Power BI, можно использовать отчеты о доступе и использовании Azure Active Directory, чтобы получить сведения.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/31/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: f685a900465cc0f1b635aad7609aaae4356da6b3
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2019
ms.locfileid: "54284640"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Поиск пользователей Power BI, выполнивших вход

Если вы — администратор клиента и хотите узнать, кто выполнил вход в Power BI, можно использовать [отчеты о доступе и использовании Azure Active Directory](/azure/active-directory/reports-monitoring/concept-sign-ins), чтобы получить сведения.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Этот отчет о действиях предоставляет полезную информацию, но не определяет тип лицензии каждого пользователя. Используйте Центр администрирования Office 365 для просмотра лицензий.

## <a name="requirements"></a>Требования

Любой пользователь (в том числе без прав администратора) может просмотреть отчет о своих событиях входа в систему, но для просмотра отчета для всех пользователей необходимо выполнить следующие требования.

* У клиента должна быть лицензия Azure AD Premium.

* У вас должна быть одна их следующих ролей: глобальный администратор, администратор системы безопасности или читатель сведений о безопасности.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Просмотр событий входа с помощью портала Azure

Чтобы просмотреть событие входа в систему, выполните следующие действия.

1. На **портале Azure**выберите **Azure Active Directory**.

1. В разделе **Мониторинг** выберите **События входа**.
   
    ![События входа в Azure AD](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. Отфильтруйте приложение по **Microsoft Power BI** или **Power BI Gateway** и выберите **Применить**.

    Параметр **Microsoft Power BI** отфильтровывает события входа, связанные со службой, тогда как **Power BI Gateway** — конкретные события входа, связанные с локальным шлюзом данных.
   
    ![Фильтрация событий входа](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Экспорт данных

Экспортировать данные входа можно одним из двух способов: скачав файл с расширением .cvs или используя PowerShell. В верхней части отчета о событии входа выберите один из следующих вариантов:

* **Скачать** для скачивания файла с расширением .cvs для текущих отфильтрованных данных.

* **Скрипт** для скачивания скрипта PowerShell для текущих отфильтрованных данных. Вы можете обновить фильтр в скрипте при необходимости.

![Скачивание файла с расширением .cvs или скрипта](media/service-admin-access-usage/download-sign-in-data-csv.png)

## <a name="data-retention"></a>Хранение данных

Данные о событиях входа доступны в течение 30 дней. Дополнительные сведения см. в статье [Политики хранения отчетов Azure Active Directory](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Дальнейшие действия

[Применение функции аудита в своей организации](service-admin-auditing.md)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

