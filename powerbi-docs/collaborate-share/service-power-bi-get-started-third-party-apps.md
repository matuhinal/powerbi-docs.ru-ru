---
title: Начало работы со сторонними приложениями в Power BI
description: Начало работы со сторонними приложениями в Power BI
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.cunstom: ''
ms.date: 09/16/2019
LocalizationGroup: Get started
ms.openlocfilehash: 9e83d8689564471365666f9b4adfe2c3b9d1c05e
ms.sourcegitcommit: d153cfc0ce559480c53ec48153a7e131b7a31542
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91526750"
---
# <a name="get-started-with-third-party-apps"></a>Начало работы со сторонними приложениями

В Power BI можно использовать приложения, разработанные не корпорацией Майкрософт, а сторонними компаниями и программистами. Например, с помощью такого приложения можно интегрировать плитки Power BI в пользовательское веб-приложение. При использовании стороннего приложения вам будет предложено предоставить ему определенные разрешения на доступ к вашей учетной записи и ресурсам Power BI. Разрешения следует предоставлять только известным и надежным приложениям. Вы можете в любой момент отозвать у приложения предоставленные ему разрешения. См. раздел [Отзыв разрешений для стороннего приложения](#revoke).

Ниже перечислены типы доступа, которые может запросить приложение.

## <a name="power-bi-app-permissions"></a>Разрешения приложений Power BI

* **Просмотр всех информационных панелей**
  
  * С этим разрешением приложение может просматривать все панели мониторинга, к которым у вас есть доступ. Сюда относятся панели, которые вам принадлежат, входят в пакеты содержимого, а также панели, к которым предоставлен доступ вам и группам, в которых вы участвуете. Приложение не может вносить изменения в саму панель мониторинга. Помимо прочего, с помощью этого разрешения приложение может встраивать содержимое ваших панелей мониторинга в свои визуальные элементы.

* **Просмотр всех отчетов**
  
  * С этим разрешением приложение может просматривать все отчеты, к которым у вас есть доступ. Сюда относятся отчеты, которые вам принадлежат, входят в пакеты содержимого, а также отчеты в группах, в которых вы участвуете. Просмотр отчета означает, что приложению доступны и содержащиеся в нем данные. Приложение не может вносить изменения в сами отчеты. Помимо прочего, с помощью этого разрешения приложение может встраивать содержимое ваших отчетов в свои визуальные элементы.

* **Просмотр всех наборов данных**
  
  * С этим разрешением приложение может составить список всех наборов данных, к которым у вас есть доступ. Сюда относятся наборы данных, которые вам принадлежат, входят в пакеты содержимого, а также отчеты в группах, в которых вы участвуете. Приложение видит названия всех ваших наборов, а также их структуру, включая названия таблиц и столбцов. Это разрешение дает права на чтение данных в наборе данных. Разрешение не дает приложению прав на добавление данных в набор или его изменение.
* **Чтение и запись всех наборов данных**
  
  * С этим разрешением приложение может составить список всех наборов данных, к которым у вас есть доступ. Сюда относятся наборы данных, которые вам принадлежат, входят в пакеты содержимого, а также отчеты в группах, в которых вы участвуете. Приложение видит названия всех ваших наборов, а также их структуру, включая названия таблиц и столбцов. Это разрешение дает права на чтение и запись данных в наборе данных. Приложение также может создавать новые наборы или вносить изменения в существующие. Это разрешение часто используется приложениями для отправки данных непосредственно в Power BI.

* **Просмотр групп пользователя**
  
  * С этим разрешением приложение может составить список всех групп, в которые вы входите. Затем с помощью этого и других перечисленных разрешений оно может просматривать и обновлять содержимое определенной группы. Приложение не может вносить изменения в саму группу.

<a name="revoke"/>

## <a name="revoke-third-party-app-permissions"></a>Отзыв разрешений для стороннего приложения

Отозвать разрешения, предоставленные стороннему приложению, можно на странице "Мои приложения" сайта Office 365.

Ниже описаны действия, которые необходимо выполнить на странице **Мои приложения** сайта Office 365.

1. Откройте [сайт "Мои приложения" Office 365](https://portal.office.com/myapps).

2. На странице **Мои приложения** найдите стороннее приложение.

3. Наведите указатель мыши на название приложения, нажмите кнопку **(...)** и выберите **Удалить** .

   ![Снимок экрана, на котором показан пункт "Удалить" для отзыва разрешений для стороннего приложения.](media/service-power-bi-get-started-third-party-apps/remove.png)