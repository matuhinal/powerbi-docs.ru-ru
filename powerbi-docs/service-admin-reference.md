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
ms.openlocfilehash: 1ed4298e4ed4cddcdf965bd427c654cab6adf1e6
ms.sourcegitcommit: 46f1ba3f972f6e64bce05ad0fd527b27c49aedd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52157018"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>Командлеты PowerShell, REST API и пакет SDK .NET для администрирования Power BI
Power BI позволяет администраторам создавать сценарии для типовых задач с помощью командлетов PowerShell. Кроме того, это решение предоставляет интерфейсы REST API и пакет SDK .NET для разработки административных решений. В этом разделе приводится список командлетов и соответствующих методов пакета SDK и конечных точек REST API. Для получения дополнительной информации см.

- PowerShell: [загрузка](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) и [документация](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
- [Документация](https://docs.microsoft.com/rest/api/power-bi/admin) по REST API
- [Загрузка](https://www.nuget.org/packages/Microsoft.PowerBI.Api/) пакета SDK .NET

| **Имя командлета** | **Псевдонимы** | **Метод пакета SDK** | **Конечная точка REST API** | **Описание** |
| --- | --- | --- | --- | --- |
| **Get-PowerBIDatasource** | Н/Д | Datasets\_GetDataSourcesAsAdmin | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Получает источники данных для заданного набора данных. |
| **Get-PowerBIDataset** | Н/Д | Datasets\_GetDatasetsAsAdmin | /v1.0/myorg/admin/datasets | Получает полный список наборов данных в клиенте Power BI. |
| **Get-PowerBIWorkspace** | **Get-PowerBIGroup** | Groups\_GetGroupsAsAdmin | /v1.0/myorg/admin/groups | Получает полный список рабочих областей в клиенте Power BI. |
| **Add-PowerBIWorkspaceUser** | **Add-PowerBIGroupUser** |Groups\_AddUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users | Добавляет пользователя в качестве члена в заданную рабочую область. |
| **Remove-PowerBIWorkspaceUser** | **Remove-PowerBIGroupUser** | Groups\_DeleteUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Удаляет пользователя из списка членства в заданной рабочей области. |
| **Restore-PowerBIWorkspace** |**Restore-PowerBIGroup** | Groups\_RestoreDeletedGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId}/restore | Восстанавливает удаленную рабочую область. |
| **SET-PowerBIWorkspace** |**Set-PowerBIGroup** | Groups\_UpdateGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId} | Обновляет свойства заданной рабочей области. |
| **Get-PowerBIDataset -WorkspaceId** | Н/Д | Groups\_GetDatasetsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/datasets | Получает наборы данных в заданной рабочей области. |
| **Export-PowerBIReport** | Н/Д | Reports\_ExportReportAsAdmin | Н/Д | Экспортирует отчет в локальный файл. |
| **Get-PowerBIReport** | Н/Д | Reports\_GetReportsAsAdmin | /v1.0/myorg/admin/reports | Получает полный список отчетов в клиенте Power BI. |
| **Get-PowerBIDashboard** | Н/Д | Dashboards\_GetDashboardsAsAdmin | /v1.0/myorg/admin/dashboards | Получает полный список панелей мониторинга в клиенте Power BI. |
| **Get-PowerBIDashboard** | Н/Д | Groups\_GetDashboardsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Получает панели мониторинга в заданной рабочей области. |
| **Get-PowerBITile** | **Get-PowerBIDashboardTile** | Dashboards\_GetTilesAsAdmin | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Получает плитки заданной панели мониторинга. |
| **Get-PowerBIReport** | Н/Д | Groups\_GetReportsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/reports | Получает отчеты в заданной рабочей области. |
| **Get-PowerBIImport** | Н/Д | Imports\_GetImportsAsAdmin | /v1.0/myorg/admin/imports | Получает полный список операций импорта в клиенте Power BI. |
| **Connect-PowerBIServiceAccount** | **Login-PowerBI** &  **Login-PowerBIServiceAccount** | Н/Д | Н/Д | Вход в Power BI и запуск сеанса. |
| **Disconnect-PowerBIServiceAccount** | **Logout-PowerBI** & **Logout-PowerBIServiceAccount** | Н/Д | Н/Д | Выход из Power BI и закрытие существующего сеанса. |
| **Invoke-PowerBIRestMethod**| Н/Д | Н/Д | Н/Д | Отправка произвольных вызовов REST API в Power BI. |
| **Get-PowerBIAccessToken**| Н/Д | Н/Д | Н/Д | Получение маркера доступа Power BI в сеансе. |
| **Resolve-PowerBIError**| Н/Д | Н/Д | Н/Д | Получение подробных сведений об ошибке для неудачных вызовов командлетов. |