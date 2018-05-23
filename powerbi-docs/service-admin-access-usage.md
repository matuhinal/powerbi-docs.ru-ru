---
title: Поиск пользователей Power BI, выполнивших вход
description: Если вы — администратор клиента и хотите узнать, кто выполнил вход в Power BI, можно использовать отчеты о доступе и использовании Azure Active Directory, чтобы получить сведения.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 1f482cf9e3f0cf344a2808ca778839a50d851ac7
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Поиск пользователей Power BI, выполнивших вход
Если вы — администратор клиента и хотите узнать, кто выполнил вход в Power BI, можно использовать отчеты о доступе и использовании Azure Active Directory, чтобы получить сведения.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

Вы можете получить доступ к отчету о действиях на [новом](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-activity-sign-ins) и [классическом](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) порталах Azure Active Directory (Azure AD). Хотя в приведенном выше видео используется классический портал в качестве примера, в этой статье рассматривается новый портал.

> [!NOTE]
> Данный отчет о действиях включает пользователей бесплатной версии Power BI и версии Pro, но не определяет их по приобретенной лицензии.
> 
> 

## <a name="requirements"></a>Требования
Ниже приведены требования для просмотра отчета о действиях входа.

* Пользователи с ролью глобального администратора, администратора безопасности или читателя безопасности могут получить доступ к данным.
* Любой пользователь (не являющийся администратором) может просматривать сведения о собственных операциях входа.
* Для просмотра отчета обо всех действиях входа у клиента должна быть лицензия Azure AD Premium.

## <a name="using-the-azure-portal-to-view-sign-ins"></a>Просмотр событий входа с помощью портала Azure
Вы можете просмотреть действия входа на портале Azure.

1. Перейдите на **портал Azure** и выберите **Azure Active Directory**.
2. В разделе **Действие** выберите **События входа**.
   
    ![](media/service-admin-access-usage/azure-portal-sign-ins.png)
3. Выполните фильтрацию приложения по **Microsoft Power BI** или **Power BI Gateway** и выберите **Применить**.
   
    Параметр **Microsoft Power BI** предназначен для действий входа, связанных со службой, тогда как **Power BI Gateway** — для конкретных событий входа для локального шлюза данных.
   
    ![](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Экспорт данных
Экспортировать данные входа можно одним из двух способов. Для этого можно скачать CSV-файл или использовать PowerShell.

### <a name="download-csv"></a>Скачивание CSV-файла
В окне действия на панели инструментов можно выбрать **Скачать**. Будет скачан CSV-файл для текущих отфильтрованных данных.

![](media/service-admin-access-usage/download-sign-in-data-csv.png)

### <a name="powershell"></a>PowerShell
Вы можете использовать PowerShell для экспорта данных входа. [Пример](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-sign-in-activity-samples#powershell-script) можно найти в документации по Azure AD.

> [!NOTE]
> Чтобы пример PowerShell работал, обязательно обеспечьте соответствие [предварительным требованиям для доступа к API отчетов Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-reporting-api-prerequisites).
> 
> 

## <a name="data-retention"></a>Хранение данных
Данные для входа могут быть доступны в течение 30 дней. Дополнительные сведения см. в статье [Политики хранения отчетов Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-retention).

## <a name="next-steps"></a>Дальнейшие действия
[Отчеты о действиях входа на портале Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-activity-sign-ins)  
[Просмотр или скачивание отчета](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports#view-or-download-a-report)  
[Сценарий PowerShell](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-sign-in-activity-samples#powershell-script)  
[Политики хранения отчетов Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-retention)  
[Применение функции аудита в своей организации](service-admin-auditing.md)  
[Активация расширенной пробной версии Power BI Pro](service-extended-pro-trial.md)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

