---
title: "Подключение к Microsoft Azure Enterprise с помощью Power BI"
description: "Microsoft Azure Enterprise для Power BI"
services: powerbi
documentationcenter: 
author: joeshoukry
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: yshoukry
ms.openlocfilehash: 39c3fd776e3aed821c7c10c1e905d7400ca64efd
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-microsoft-azure-enterprise-with-power-bi"></a>Подключение к Microsoft Azure Enterprise с помощью Power BI
Просматривайте и отслеживайте данные Microsoft Azure Enterprise в Power BI с помощью пакета содержимого Power BI. Данные автоматически обновляются раз в день.

Подключитесь к [пакету содержимого Microsoft Azure Enterprise](https://app.powerbi.com/getdata/services/azure-enterprise) для Power BI.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.
   
    ![](media/service-connect-to-azure-enterprise/getdata.png)
2. В поле **Службы** выберите **Получить**.
   
   ![](media/service-connect-to-azure-enterprise/services.png)
3. Выберите **Microsoft Azure Enterprise** \> **Получить**.
   
   ![](media/service-connect-to-azure-enterprise/mazureenterprise.png)
4. Укажите URL-адрес среды Azure, число месяцев, за которое необходимо импортировать данные, и номер регистрации Azure Enterprise. URL-адрес среды Azure будет иметь вид `https://ea.azure.com` или `https://ea.windowsazure.cn`. Сведения о том, как [найти эти параметры](#FindingParams), см. ниже.
   
    ![](media/service-connect-to-azure-enterprise/params.png)
5. Укажите ключ доступа для подключения. Ключ для вашей регистрации можно найти на портале Azure EA.
   
    ![](media/service-connect-to-azure-enterprise/creds.png)
6. Процесс импорта начнется автоматически. После завершения в области навигации появятся новая панель мониторинга, отчет и модель. Выберите панель мониторинга, чтобы просмотреть импортированные данные.
   
   ![](media/service-connect-to-azure-enterprise/dashboard.png)

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](service-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="whats-included"></a>Содержимое
Пакет содержимого Azure Enterprise включает данные из ежемесячных отчетов за месяцы, которые вы указываете во время подключения. Диапазон динамический, поэтому входящие в него даты будут обновляться при обновлении набора данных.

## <a name="system-requirements"></a>Требования к системе
Для пакета содержимого требуется доступ к функциям Enterprise на портале Azure.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Поиск параметров
Отчеты Power BI доступны для прямых клиентов EA, партнеров и непрямых клиентов, которые могут просматривать сведения об оплате. Ниже приведены дополнительные сведения о поиске каждого из значений, которые потребуются во время процедуры подключения.

**URL-адрес среды Azure**

* Это значение обычно равно https://ea.azure.com, однако вы можете проверить URL-адрес после входа, чтобы подтвердить его.
  
    ![](media/service-connect-to-azure-enterprise/params3.png)

**Число месяцев**

* Это число должно находиться в пределах от 1 до 36, обозначая число месяцев (с сегодняшнего дня), за которое вы хотите импортировать данные.

**Номер регистрации**

* Это номер соглашения о регистрации Azure Enterprise, который можно найти на домашней странице [портала Azure Enterprise](https://ea.azure.com/) в разделе "Сведения о соглашении о регистрации".
  
    ![](media/service-connect-to-azure-enterprise/params2.png)

**Ключ доступа**

* Ключ можно найти на портале Azure Enterprise в разделе "Скачать сведения об использовании" > "API Access Key" (Ключ доступа к API).
  
    ![](media/service-connect-to-azure-enterprise/creds2.png)

**Дополнительная справка**

* Для дополнительной помощи в настройке пакета Azure Enterprise Power BI войдите на портал Azure Enterprise, чтобы просмотреть файл справки по API в разделе "Справка" и дополнительные инструкции в меню "Отчеты" -> "Скачать сведения об использовании" -> "Ключ доступа к API".

## <a name="next-steps"></a>Дальнейшие действия
[Приступая к работе с Power BI](service-get-started.md)

[Получение данных в Power BI](service-get-data.md)

