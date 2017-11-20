---
title: "Подключение к Visual Studio Team Services с помощью Power BI"
description: "Visual Studio Team Services для Power BI"
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
ms.openlocfilehash: 20ea9117cf1eee3d7b05be21e5964226349a58c1
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="connect-to-visual-studio-team-services-with-power-bi"></a>Подключение к Visual Studio Team Services с помощью Power BI
Пакет содержимого Visual Studio Team Services для Power BI позволяет анализировать командные проекты TFVC и git. После подключения данные будут доставляться вам автоматически на панели мониторинга и в отчетах. 

Подключитесь к [пакету содержимого Visual Studio Team Services](https://app.powerbi.com/getdata/services/visual-studio-online) или прочтите дополнительные сведения об [интеграции Visual Studio Team Services](https://powerbi.microsoft.com/integrations/visual_studio_online) с Power BI.

>[!NOTE]
>Для этого пакета требуется доступ к учетной записи, в которой активирован протокол OAuth. Дополнительные сведения о требованиях см. ниже.

## <a name="how-to-connect"></a>Способы подключения
1. Нажмите кнопку **Получить данные** в нижней части левой панели навигации.  
   ![](media/service-connect-to-visual-studio/pbi_getdata.png) 
2. В поле **Службы** выберите **Получить**.  
   ![](media/service-connect-to-visual-studio/pbi_getservices.png) 
3. Выберите пакет содержимого **Visual Studio Team Services** и нажмите кнопку **Получить**.     
   ![](media/service-connect-to-visual-studio/vsts.png)
4. Введите сведения о своей учетной записи Visual Studio Team Services. Сведения о том, как найти необходимые параметры, см. [ниже](#FindingParams).
   
   ![](media/service-connect-to-visual-studio/pbi_vsosignin.png)
   
   Имя учетной записи — это начальная часть URL-адреса для visualstudio.com:    
   ![](media/service-connect-to-visual-studio/urlimage.png)
   
   Имя проекта отображается в верхней части каждой страницы в Visual Studio Team Services.  
   ![](media/service-connect-to-visual-studio/projectimage.png)
5. Пройдите аутентификацию в Visual Studio Team Services с использованием oAuth2. В результате может появиться диалоговое окно входа в VSTS. 
   
   > [!IMPORTANT]
   > Некоторые развертывания Visual Studio Team Services не поддерживают oAuth2.  Если войти не удается, следуйте указаниям в разделе "Устранение неполадок".
   > 
   > 
   
   ![](media/service-connect-to-visual-studio/pbi_vsosignin2.png)
6. Во время аутентификации в Visual Studio Team Services предоставьте пакету содержимого Visual Studio для Power BI разрешение на доступ к данным вашего командного проекта.   
   ![](media/service-connect-to-visual-studio/vsoauthorizeapp450.png)
7. После подключения к проекту Visual Studio Team Services в области навигации слева появится новая панель мониторинга, отчет и набор данных. Новые элементы отмечены желтой звездочкой \*.  
   ![](media/service-connect-to-visual-studio/visualstudioonline800px.png) 

**Дальнейшие действия**

* Попробуйте [задать вопрос в поле "Вопросы и ответы"](service-q-and-a.md) в верхней части информационной панели.
* [Измените плитки](service-dashboard-edit-tile.md) на информационной панели.
* [Выберите плитку](service-dashboard-tiles.md), чтобы открыть соответствующий отчет.
* Хотя набор данных будет обновляться ежедневно по расписанию, вы можете изменить график обновлений или попытаться выполнять обновления по запросу с помощью кнопки **Обновить сейчас**.

## <a name="whats-included"></a>Содержимое
Visual Studio Team Services в Power BI предоставляет широкий набор таблиц и полей для создания отчетов. Полный список компонентов пакета содержимого можно найти здесь: <https://www.visualstudio.com/get-started/report/vso-pbi-whats-available-vs>.

## <a name="system-requirements"></a>Требования к системе
* Доступ к учетной записи Visual Studio Team Services с разрешением на сбор данных с помощью REST API.  
* Разрешение, предоставленное приложению Power BI во время начального подключения. Чтобы отключить службу Power BI и удалить ее права на доступ к вашей учетной записи Visual Studio Team Services, отзовите права доступа в Visual Studio Team Services. См. раздел <https://www.visualstudio.com/get-started/setup/change-application-access-policies-vs>.  

Дополнительные сведения можно найти в статье <https://www.visualstudio.com/en-us/get-started/report/connect-vso-pbi-vs>.

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>Поиск параметров
Имя учетной записи — это начальная часть URL-адреса для visualstudio.com:    
    ![](media/service-connect-to-visual-studio/urlimage.png)

Имя проекта отображается в верхней части каждой страницы в VSTS.  
    ![](media/service-connect-to-visual-studio/projectimage.png)

Чтобы выбрать несколько проектов, можно также использовать подстановочные знаки. Например, можно выбрать все проекты, введя просто "\*", или все проекты, которые начинаются с "Azure", введя "Azure\*".

## <a name="troubleshooting"></a>Устранение неполадок
При попытке войти в Visual Studio Team Services может появиться сообщение об ошибке входа.

Существуют две распространенные причины, препятствующие успешной аутентификации.

1) Вы вошли с личной учетной записью, а не рабочей или школьной учетной записью.  

2) Ваше развертывание Visual Studio Team Services не поддерживает oAuth. 

**Вход с рабочей или учебной учетной записью**  
Возникновение этой проблемы может означать, что вы уже прошли аутентификацию в Visual Studio Team Services с помощью другой учетной записи (не с той, из которой нужно загрузить данные). Например, вы подключились к Visual Studio Team Services, используя личную учетную запись Майкрософт, а к службе Power BI — с помощью рабочей или школьной учетной записи.

Чтобы устранить эту проблему, выполните следующие действия.  

* Закройте диалоговое окно конфигурации.  
* Выйдите из Visual Studio Team Services (используется личная учетная запись).  
* Войдите в Visual Studio Online, используя школьную или рабочую учетную запись.  
* Перезапустите процесс "Получение данных", описанный выше. 

Подключение с помощью рабочей или школьной учетной записи (Azure Active Directory или AAD):  
    ![](media/service-connect-to-visual-studio/vsologinscreen.png)

Если вы видите это диалоговое окно и хотите подключиться, используя рабочую или школьную учетную запись (Azure Active Directory), щелкните ссылку слева, чтобы выполнить вход. Не вводите учетные данные AAD в правой части, так как здесь ожидается учетная запись Майкрософт (ваша личная учетная запись).

**Развертывания Visual Studio Team Services, не поддерживающие oAuth2**  
Администратор VSTS мог отключить oAuth для вашего развертывания Visual Studio Team Services.  В этом случае вы не сможете использовать пакет контента Visual Studio для Power BI в данный момент. 

![](media/service-connect-to-visual-studio/oauth.png)

## <a name="next-steps"></a>Дальнейшие действия
* [Приступая к работе с Power BI](service-get-started.md)
* [Получение данных](service-get-data.md)

