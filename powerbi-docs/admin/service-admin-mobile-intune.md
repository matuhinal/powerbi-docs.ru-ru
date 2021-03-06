---
title: Настройка мобильных приложений в Microsoft Intune
description: Настройка мобильных приложений Power BI в Microsoft Intune. Сюда входит описание добавления и развертывания приложения. Здесь также описано создание политики мобильных приложений для управления безопасностью.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 09/25/2020
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: a7a3e0382b80d46ddb41b3f5677763a1a08bf26d
ms.sourcegitcommit: 02484b2d7a352e96213353702d60c21e8c07c6c0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "91981557"
---
# <a name="configure-mobile-apps-with-microsoft-intune"></a>Настройка мобильных приложений в Microsoft Intune

Microsoft Intune позволяет организациям управлять устройствами и приложениями. Мобильные приложения Power BI для iOS и Android интегрируются с Intune. Такая интеграция позволяет управлять приложением на устройствах и обеспечивать защиту. В политиках конфигурации можно управлять такими элементами, как требование ПИН-кода для доступа, способ обработки данных в приложении и даже шифрование данных приложения, когда приложение не используется.

Мобильное приложение Microsoft Power BI позволяет получать доступ к важной бизнес-информации. Вы можете просматривать панели мониторинга и отчеты с данными бизнес-приложений и взаимодействовать с ними на всех управляемых устройствах в организации. Дополнительные сведения о поддерживаемых приложениях Intune см. в статье [Защищенные приложения Microsoft Intune](/intune/apps/apps-supported-intune-apps).

## <a name="general-mobile-device-management-configuration"></a>Общая конфигурация управления мобильными устройствами

В этой статье предполагается, что служба Intune правильно настроена и у вас есть устройства, зарегистрированные в Intune. Эта статья не является полным руководством по настройке Microsoft Intune. Дополнительные сведения об Intune см. в статье [Что такое Intune](/intune/introduction-intune/).

Microsoft Intune может сосуществовать со службой управления мобильными устройствами (MDM) в Microsoft 365. Если вы используете MDM, устройство будет отображаться как зарегистрированное в MDM и будет доступно для управления в Intune.

Прежде чем конечные пользователи смогут использовать приложение Power BI на своих устройствах, администратор Intune должен добавить приложение в Intune и назначить его конечным пользователям.

> [!NOTE]
> Когда вы настроите Intune, фоновое обновление данных будет отключено для мобильного приложения Power BI на устройства iOS или Android. Power BI обновит данные из службы Power BI в Интернете при входе в приложение.

## <a name="step-1-add-the-power-bi-app-to-intune"></a>Шаг 1. Добавление приложения Power BI в Intune

Чтобы добавить приложение Power BI в Intune, выполните действия, описанные в следующих разделах:
- [Добавление в Microsoft Intune приложений из магазина iOS](/intune/apps/store-apps-ios)
- [Добавление приложения из магазина Android в Microsoft Intune](/intune/apps/store-apps-android)

## <a name="step-2-assign-the-app-to-your-end-users"></a>Шаг 2. Назначение приложения конечным пользователям

После добавления приложения Power BI в Microsoft Intune его можно назначить пользователям и устройствам. Важно отметить, что приложение можно назначить устройству независимо от того, управляется ли устройство Intune.

Чтобы назначить приложение Power BI пользователям и устройствам, выполните действия, описанные в статье [Назначение приложений группам с помощью Microsoft Intune](/intune/apps/apps-deploy).

## <a name="step-3-create-and-assign-app-protection-policies"></a>Шаг 3. Создание и назначение политик защиты приложений

Политики защиты приложений — это правила, которые обеспечивают защиту корпоративных данных (включая те, которые хранятся в управляемых приложениях). Политика может быть либо правилом, которое применяется, когда пользователь пытается получить доступ или переместить корпоративные данные, либо набором действий, которые запрещено выполнять или которые отслеживаются, когда пользователь работает с приложением. Под управляемым понимается приложение, к которому применены политики защиты приложений и которое может управляться в Intune.

Политики защиты приложений MAM (управление мобильными приложениями) позволяют управлять данными организации и защищать их в приложении. С помощью MAM без регистрации (MAM-WE) вы можете управлять рабочими или учебными приложениями, которые содержат конфиденциальные данные, практически с любого устройства, включая личные устройства в рамках сценария BYOD. Дополнительные сведения см. в статье [Общие сведения о политиках защиты приложений](/intune/apps/app-protection-policy).

Чтобы создать и назначить политику защиты приложению Power BI, выполните действия, описанные в статье [Как создать и назначить политики защиты приложений](/intune/apps/app-protection-policies).

## <a name="step-4-use-the-application-on-a-device"></a>Шаг 4. Использование приложения на устройстве

Управляемые приложения — это приложения, которые служба поддержки вашей компании может настроить для защиты данных организации, доступных в таком приложении. При доступе к данным организации в управляемом приложении на устройстве можно заметить, что приложение работает немного иначе, чем предполагается. Например, может отсутствовать возможность скопировать и вставить защищенные данные организации или сохранить данные в определенных расположениях.

Чтобы понять, как конечные пользователи могут использовать приложение Power BI на своих устройствах, ознакомьтесь с инструкциями, приведенными в следующих статьях.
- [Использование управляемых приложений на устройстве iOS](/intune-user-help/use-managed-apps-on-your-device-ios#how-do-i-get-managed-apps)
- [Использование управляемых приложений на устройстве Android](/intune-user-help/use-managed-apps-on-your-device-android)

## <a name="next-steps"></a>Дальнейшие действия

[Как создать и назначить политики защиты приложений](/intune/app-protection-policies) 

[Приложения Power BI для мобильных устройств](../consumer/mobile/mobile-apps-for-mobile-devices.md)  

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)