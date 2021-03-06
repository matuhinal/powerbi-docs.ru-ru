---
title: Плановое обслуживание Power BI
description: Сведения для администраторов о том, как плановое обслуживание Power BI влияет на их организацию и какие дальнейшие действия могут от них потребоваться.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/19/2020
ms.author: kfollis
ms.custom: MC
ROBOTS: NOINDEX
LocalizationGroup: Admin
ms.openlocfilehash: 19933ccbf18003e293e823c2b1f201e953c7bde0
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90854789"
---
# <a name="power-bi-planned-maintenance"></a>Плановое обслуживание Power BI

Плановое обслуживание службы Power BI — обязательный компонент в рамках нашего обязательства по обеспечению надежного продукта для клиентов. Во время планового обслуживания служба Power BI будет какое-то время недоступна для вашей организации. Возможно, пользователи не смогут получить доступ к службе Power BI, а фоновые операции не будут выполняться надлежащим образом. Мы рассчитываем, что по завершении периода обслуживания служба начнет работать нормально, а интерактивные и фоновые операции будут выполняться успешно.  

Чтобы свести к минимуму влияние на организацию, обслуживание планируется выполнять вне обычного рабочего времени. Мы понимаем, что в организациях с пользователями по всему миру понятие "вне обычного рабочего времени" носит условный характер. Приносим свои извинения за любые последствия для пользователей. Мы работаем над улучшением Power BI и стараемся свести к минимуму эти периоды обслуживания.

Если обслуживание повлияет на вашу организацию, мы уведомим вас об этом заранее. Администраторы Microsoft 365 получат предварительное уведомление в Центре сообщений Microsoft 365 и по электронной почте. Кроме того, клиентов с контрактами на поддержку Premier уведомит служба технической поддержки учетных записей Майкрософт.

## <a name="actions-to-take-now"></a>Необходимые действия

* Администраторы Microsoft 365 должны следить за сообщениями о плановом обслуживании Power BI в [Центре сообщений](https://admin.microsoft.com/Adminportal/Home#/MessageCenter). Поделитесь сообщением с теми, кого следует уведомить, но у кого нет доступа к Центру сообщений.
* Если вы не являетесь администратором Microsoft 365, обратитесь в ИТ-службу или внутреннюю службу поддержки, чтобы узнать о предстоящем обслуживании.

## <a name="actions-to-take-when-maintenance-is-complete"></a>Действия после завершения обслуживания

* Пользователи должны обновить все открытые окна браузера.
* Пользователи приложений Power BI Mobile должны убедиться, что они используют новейшую версию, выйти из нее, а затем войти снова. Проверьте магазин приложений на телефоне или посетите страницу [Power BI Mobile](https://powerbi.microsoft.com/mobile/).
* Клиенты, активно редактирующие или публикующие отчеты с визуальными элементами организации (локально или в OneDrive и SharePoint), должны либо повторно импортировать эти элементы с помощью хранилища визуальных элементов организации, либо загрузить обновленный PBIX-файл перед повторной публикацией. Дополнительные сведения см. в статье о [визуальных элементах организации](organizational-visuals.md).
* Если книги Excel, в которых используется функция "Анализ в Excel", не обновляются, возможно, потребуется обновить строку подключения или повторно скачать ODC-файл подключения для этого набора данных. Дополнительные сведения см. в статье о функции [Анализ в Excel](../collaborate-share/service-analyze-in-excel.md#connect-to-power-bi-data).
* После завершения обслуживания ссылки на Power BI, внедренные в содержимое, могут не работать. Например, при попытке перейти по внедренной ссылке в SharePoint или Teams у пользователя может произойти ошибка. Чтобы устранить эту проблему, необходимо повторно создать внедренную ссылку в Power BI, а затем обновить расположения, в которых она используются. Дополнительные сведения о внедренных ссылках см. в статьях [Внедрение веб-части отчетов в SharePoint Online](../collaborate-share/service-embed-report-spo.md) и [Совместная работа в Microsoft Teams с использованием Power BI](../collaborate-share/service-collaborate-microsoft-teams.md).

## <a name="next-steps"></a>Дальнейшие действия

* [Включение уведомлений о прерывании в работе служб](service-interruption-notifications.md)
* [Отслеживание предстоящих изменений в Центре сообщений](/microsoft-365/admin/manage/message-center?view=o365-worldwide)