---
title: Использование элементов управления Microsoft Cloud App Security в Power BI
description: Сведения о применении меток конфиденциальности данных в Power BI
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/25/2019
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: 18062c770b93bcd1295026d841f923a81c11d84f
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/09/2019
ms.locfileid: "73851243"
---
# <a name="using-microsoft-cloud-app-security-controls-in-power-bi-preview"></a>Использование элементов управления Microsoft Cloud App Security в Power BI (предварительная версия)

Используя Microsoft Cloud App Security вместе с Power BI, вы сможете защитить отчеты, данные и службы Power BI от непредвиденных утечек и нарушений. С помощью Cloud App Security вы можете создавать политики условного доступа к данным организации, используя элементы управления сеансами в реальном времени в Azure Active Directory (Azure AD), что позволяет гарантировать безопасность аналитических данных в Power BI. После настройки необходимых политик администраторы смогут отслеживать доступ пользователей и осуществляемые ими действия, выполнять анализ рисков в реальном времени, а также задавать элементы управления для меток. 

![Использование области элементов управления Microsoft Cloud App Security](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-01.png)

Microsoft Cloud App Security можно настраивать не только для Power BI, но и для самых разных приложений и служб. Cloud App Security — это служба Майкрософт, которая защищает приложения и устройства и управляется посредством собственной панели мониторинга. Чтобы использовать преимущества этой службы для защиты данных и результатов аналитики в Power BI, необходимо настроить Cloud App Security. Дополнительные сведения об этой службе, в том числе описание принципов ее работы, панели мониторинга и оценок рисков для приложений, см. в документации по [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/).


## <a name="using-microsoft-cloud-app-security-with-power-bi"></a>Использование Microsoft Cloud App Security в Power BI

Чтобы использовать Microsoft Cloud App Security в Power BI, необходимо задействовать и настроить соответствующие службы безопасности Майкрософт, причем в некоторых случаях это требуется сделать вне среды Power BI.

### <a name="microsoft-cloud-app-security-licensing"></a>Лицензирование Microsoft Cloud App Security

Чтобы использовать Microsoft Cloud App Security для своего клиента, вам потребуются следующие лицензии:
* MCAS: предоставляет возможности OCAS для всех поддерживаемых приложений; входит в состав наборов EMS E5 и M365 E5.
* CAS-D: предоставляет доступ только для обнаружения MCAS.
* OCAS: предоставляет возможности MCAS только для Office 365; входит в состав набора Office E5.
* Необязательно: AAD P1 и AIP P1, чтобы использовать преимущества основных возможностей Microsoft Cloud App Security.

Далее в этой статье описываются шаги, которые необходимо выполнить для использования Microsoft Cloud App Security в Power BI.

### <a name="set-session-policies-in-azure-active-directory-required"></a>Настройка политик сеансов в Azure Active Directory (обязательно)
Действия по настройке элементов управления сеансами выполняются на порталах Azure AD и Microsoft Cloud App Security. На портале Azure AD вы создаете политику условного доступа для Power BI и перенаправляете сеансы, используемые в Power BI, через службу Microsoft Cloud App Security. 

Служба Microsoft Cloud App Security работает на основе архитектуры обратного прокси-сервера и интегрируется с инфраструктурой условного доступа Azure AD, позволяя отслеживать действия пользователя Power BI в реальном времени. Ниже приводится общее описание процесса. Подробные инструкции можно найти по ссылкам, которые приводятся для каждого из рассматриваемых шагов. Кроме того, общее описание можно найти в этой [статье, посвященной Cloud App Security](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad).

1.  [Создание политики тестирования условного доступа Azure AD](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad#add-azure-ad)
2.  [Вход в каждое приложение под именем пользователя, входящего в область действия политики](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad#sign-in-scoped)
3.  [Проверка конфигурации приложений для использования элементов управления доступом и сеансами](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad#portal)
4.  [Тестирование развертывания](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad#step-4-test-the-deployment)

Процесс настройки политик сеансов подробно описывается в [этой статье](https://docs.microsoft.com/cloud-app-security/session-policy-aad). 

### <a name="set-anomaly-detection-policies-to-monitor-pbi-activities-recommended"></a>Настройка политик обнаружения аномалий для отслеживания действий PBI (рекомендуется)
Вы можете определить политики обнаружения аномалий в Power BI с независимо задаваемой областью действия, при необходимости включая и исключая пользователей и группы, на которых они будут распространяться. [Дополнительные сведения](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy#scope-anomaly-detection-policies).

В Cloud App Security также предусмотрены два специализированных обнаружения для Power BI. [Дополнительные сведения см. далее в этом документе](#built-in-microsoft-cloud-app-security-detections-for-power-bi).

### <a name="use-microsoft-information-protection-sensitivity-labels-recommended"></a>Использование меток конфиденциальности Microsoft Information Protection (рекомендуется)

С помощью меток конфиденциальности вы можете классифицировать и защитить конфиденциальное содержимое. Благодаря этому сотрудники вашей организации смогут работать с находящимися вне ее среды партнерам, не нарушая при этом требований к защите конфиденциального содержимого и данных. 

Дополнительные сведения о применении меток конфиденциальности для Power BI можно найти в [этой статье](../designer/service-security-apply-data-sensitivity-labels.md). Также далее приведен [пример политики Power BI на основе меток конфиденциальности](#example).

## <a name="built-in-microsoft-cloud-app-security-detections-for-power-bi"></a>Встроенные обнаружения Microsoft Cloud App Security для Power BI

Благодаря обнаружениям Microsoft Cloud App Security администраторы могут отслеживать конкретные действия в контролируемом приложении. В Cloud App Security на данный момент предусмотрены два специализированных обнаружения для Power BI: 

* **Подозрительное предоставление доступа** — определяет, когда пользователь предоставляет общий доступ к конфиденциальному отчету незнакомому (стороннему по отношению к организации) адресу электронной почты. Под конфиденциальным понимается отчет, для которого задана метка конфиденциальности **ТОЛЬКО ДЛЯ ВНУТРЕННЕГО ПОЛЬЗОВАНИЯ** или более высокого уровня. 

* **Массовое предоставление общего доступа к отчетам** — определяет, когда пользователь предоставляет общий доступ к нескольким разным отчетам в рамках одного сеанса.

Настройка этих обнаружений осуществляется на портале Cloud App Security. [Дополнительные сведения](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy#unusual-activities-by-user). 

## <a name="power-bi-admin-role-in-microsoft-cloud-app-security"></a>Роль администратора Power BI в Microsoft Cloud App Security

При использовании Microsoft Cloud App Security вместе с Power BI создается новая роль для администраторов Power BI. При входе [на портал Cloud App Security](https://portal.cloudappsecurity.com/) в качестве администратора Power BI вы получаете ограниченный доступ к связанным с Power BI данным, оповещениям, находящимся в зоне риска пользователям, журналам действий и другим сведениям.

## <a name="considerations-and-limitations"></a>Рекомендации и ограничения 
Применение Cloud App Security вместе с Power BI позволяет защитить содержимое и данные вашей организации, используя обнаружения, предназначенные для отслеживания сеансов и действий пользователей. При использовании Cloud App Security вместе с Power BI необходимо учитывать ряд ограничений:

* Microsoft Cloud App Security поддерживает работу только с файлами в форматах Excel, PowerPoint и PDF.
* Если вы планируете использовать возможности меток конфиденциальности в политиках сеансов для Power BI, вам потребуется лицензия Azure Information Protection Premium P1 или Premium P2. Средство Microsoft Azure Information Protection можно приобрести как отдельно, так и в составе одного из наборов лицензирования Майкрософт. Дополнительные сведения см. в статье [Цены на Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection/). Кроме того, вам необходимо применить метки конфиденциальности к своим ресурсам Power BI.

> [!CAUTION]
> * В данный момент Power BI не поддерживает политику *проверки содержимого* Microsoft Cloud App Security при применении файла политики в формате Excel, в связи с чем не следует задавать эту политику для Power BI.
> * Функция защиты в части действия политики сеанса будет работать только в том случае, если для элемента не определена метка. Если метка уже определена, действие защиты не применяется. Это связано с тем, что переопределение существующей метки, примененной к элементу в Power BI, не допускается.

## <a name="example"></a>Пример

В следующем примере демонстрируется, как создать новую политику сеанса с использованием Microsoft Cloud App Security с Power BI.

Для начала создайте новую политику сеанса. На портале **Cloud App Security** в меню слева выберите пункт **Политики**.

![Создание новой политики сеанса](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-02.png)

В появившемся окне щелкните раскрывающийся список **Создать политику**.

![Выбор элемента "Создать политику"](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-03.png)

В раскрывающемся списке выберите элемент **Политика сеанса**.

![Выбор элемента "Политика сеанса"](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-04.png)

Создайте политику сеанса в появившемся окне. Нумерация шагов соответствует подписям параметров на следующем рисунке.

  1. В раскрывающемся списке **Шаблон политики** выберите *Без шаблона*.
  2. В поле **Имя политики** укажите соответствующее имя политики сеанса.
  3. В разделе **Тип управления сеансом** выберите *Управление скачиваемыми файлами (с защитой от потери данных)* .

      В разделе **Источник активности** выберите соответствующие политики блокировки. Мы рекомендуем блокировать неуправляемые и не соответствующие требованиям устройства. Выберите этот параметр, чтобы блокировать скачивание файлов, если сеанс проходит в Power BI.

        ![Создание политики сеанса](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-05.png)

        Выполните прокрутку вниз, чтобы просмотреть дополнительные параметры. Эти параметры с рядом примеров показаны на следующем рисунке. 

  4. Для параметра *Метка конфиденциальности* задайте значение *Строго конфиденциально* или любой другой применяемый в вашей организации уровень защиты.
  5. Для параметра **Метод проверки** задайте значение *Нет*.
  6. В разделе **Блокировать** выберите нужный параметр.
  7. Убедитесь, что для этого действия создано оповещение.

        ![Выбор параметров политики сеанса](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-06.png)

        

  8. На заключительном шаге нажмите кнопку **Создать**, чтобы создать политику сеанса.

        ![Создание политики сеанса](media/service-security-using-microsoft-cloud-app-security-controls/cloud-app-security-controls-07.png)

> [!CAUTION]
> Убедитесь, что вы не создаете политику **проверки содержимого** для файлов Excel в Power BI. Это известное ограничение для данной *предварительной версии*.

## <a name="next-steps"></a>Дальнейшие действия
В этой статье описывается защита данных и содержимого в Power BI с использованием Microsoft Cloud App Security. Также вы можете ознакомиться со следующими статьями, в которых рассматриваются вопросы защиты данных в Power BI, и с дополнительными материалами по службам Azure, которые обеспечивают эти возможности.

* [Общие сведения о защите данных в Power BI](service-security-data-protection-overview.md)
* [Активация меток конфиденциальности данных в Power BI](service-security-enable-data-sensitivity-labels.md)
* [Применение меток конфиденциальности данных в Power BI](../designer/service-security-apply-data-sensitivity-labels.md)

Рекомендуем также ознакомиться со следующими материалами по Azure и обеспечению безопасности:

* [Защита приложений с использованием Microsoft Cloud App Security — элемент управления условным доступом к приложению](https://docs.microsoft.com/cloud-app-security/proxy-intro-aad)
* [Развертывание элемента управления условным доступом к популярным приложениям](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)
* [Политики сеансов](https://docs.microsoft.com/cloud-app-security/session-policy-aad)
* [Общие сведения о метках конфиденциальности](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)