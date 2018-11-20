---
title: Командлеты PowerShell, REST API и пакет SDK .NET для администраторов
description: Сведения о способах администрирования Power BI с помощью сценариев и API-интерфейсов программирования.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: overview
ms.date: 06/25/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: f4455fef5a2ed0e7ee23ff8ca3a0b626cd695838
ms.sourcegitcommit: a1b7ca499f4ca7e90421511e9dfa61a33333de35
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51507998"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>Командлеты PowerShell, REST API и пакет SDK .NET для администрирования Power BI
Power BI позволяет администраторам создавать сценарии для типовых задач с помощью командлетов PowerShell. Кроме того, это решение предоставляет интерфейсы REST API и пакет SDK .NET для разработки административных решений. В этом разделе приводится список командлетов и соответствующих методов пакета SDK и конечных точек REST API. Для получения дополнительной информации см.

  - PowerShell: [загрузка](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) и [документация](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
  - [Документация](https://docs.microsoft.com/rest/api/power-bi/admin) по REST API
  - [Загрузка](https://www.nuget.org/packages/Microsoft.PowerBI.Api/) пакета SDK .NET 


| **Имя командлета** | **Метод пакета SDK** | **Конечная точка REST API** | **Описание** |
| --- | --- | --- | --- |
| **Get-PowerBIDatasource** | Datasets\_GetDataSourcesAsAdmin | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Получает источники данных для заданного набора данных. |
| **Get-PowerBIDataset** | Datasets\_GetDatasetsAsAdmin | /v1.0/myorg/admin/datasets | Получает полный список наборов данных в клиенте Power BI. |
| **Get-PowerBIWorkspace** | Groups\_GetGroupsAsAdmin | /v1.0/myorg/admin/groups | Получает полный список рабочих областей в клиенте Power BI. |
| **Add-PowerBIWorkspaceUser** | Groups\_AddUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users | Добавляет пользователя в качестве члена в заданную рабочую область. |
| **Remove-PowerBIWorkspaceUser** | Groups\_DeleteUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Удаляет пользователя из списка членства в заданной рабочей области. |
| **Restore-PowerBIWorkspace** | Groups\_RestoreDeletedGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId}/restore | Восстанавливает удаленную рабочую область. |
| **SET-PowerBIWorkspace** | Groups\_UpdateGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId} | Обновляет свойства заданной рабочей области. |
| **Get-PowerBIDataset -WorkspaceId** | Groups\_GetDatasetsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/datasets | Получает наборы данных в заданной рабочей области. |
| **Export-PowerBIReport** | Reports\_ExportReportAsAdmin | Н/Д | Экспортирует отчет в локальный файл. |
| **Get-PowerBIReport** | Reports\_GetReportsAsAdmin | /v1.0/myorg/admin/reports | Получает полный список отчетов в клиенте Power BI. |
| **Get-PowerBIDashboard** | Dashboards\_GetDashboardsAsAdmin | /v1.0/myorg/admin/dashboards | Получает полный список панелей мониторинга в клиенте Power BI. |
| **Get-PowerBIDashboard -WorkspaceId** | Groups\_GetDashboardsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Получает панели мониторинга в заданной рабочей области. |
| **Get-PowerBITile -DashboardId** | Dashboards\_GetTilesAsAdmin | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Получает плитки заданной панели мониторинга. |
| **Get-PowerBIReport -WorkspaceId** | Groups\_GetReportsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/reports | Получает отчеты в заданной рабочей области. |
| **Get-PowerBIImport** | Imports\_GetImportsAsAdmin | /v1.0/myorg/admin/imports | Получает полный список операций импорта в клиенте Power BI. |
| **Connect-PowerBIServiceAccount** | Н/Д | Н/Д | Вход в Power BI и запуск сеанса. |
| **Disconnect-PowerBIServiceAccount** | Н/Д | Н/Д | Выход из Power BI и закрытие существующего сеанса. |
| **Invoke-PowerBIRestMethod** | Н/Д | Н/Д | Отправка произвольных вызовов REST API в Power BI. |
| **Get-PowerBIAccessToken** | Н/Д | Н/Д | Получение маркера доступа Power BI в сеансе. |
| **Resolve-PowerBIError** | Н/Д | Н/Д | Получение подробных сведений об ошибке для неудачных вызовов командлетов. |