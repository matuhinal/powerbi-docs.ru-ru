---
title: Обновление, удаление и извлечение приложения-шаблона Power BI
description: Как обновить, удалить и извлечь приложение-шаблон.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 05/04/2020
ms.author: painbar
ms.openlocfilehash: c5bed13799824a0222b2961595108536f66133ee
ms.sourcegitcommit: be424c5b9659c96fc40bfbfbf04332b739063f9c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91634948"
---
# <a name="update-delete-and-extract-template-app"></a>Обновление, удаление и извлечение приложения-шаблона

Теперь, когда приложение доступно в рабочей версии, вы можете вновь запускать этап тестирования, не нарушая работу.
## <a name="update-your-app"></a>Обновление приложения

Если вы внесли изменения в Power BI Desktop, начните с шага (1). Если вы не вносили изменения в Power BI Desktop, начните с шага (4).

1. Отправьте обновленный набор данных и перезапишите существующий набор данных. **Убедитесь, что используется то же имя набора данных**. При использовании другого имени будет создан новый набор данных для пользователей, которые обновляют приложение.
![Снимок экрана: обновление приложения-шаблона Power BI с выбранным элементом "Набор данных".](media/service-template-apps-update-extract-delete/power-bi-template-app-upload-dataset.png)
1. Импортируйте PBIX-файл с компьютера.
![Снимок экрана: страница "Получение данных" с выделенной кнопкой "Получить" в элементе "Файлы".](media/service-template-apps-update-extract-delete/power-bi-template-app-upload-dataset2.png)
1. Подтвердите перезапись.
![Снимок экрана: сообщение с подтверждением "Набор данных с таким именем уже существует" и выделенной кнопкой "Заменить".](media/service-template-apps-update-extract-delete/power-bi-template-app-upload-dataset3.png)

1. В панели **Управление выпусками** выберите **Создать приложение**.
1. Повторите процедуру создания приложения.
1. После установки параметров в категориях **Фирменная символика**, **Содержимое**, **Управление** и **Доступ** вновь выберите **Создать приложение**.
1. Нажмите **Закрыть** и вернитесь в **Управление выпусками**.

   Теперь у вас есть две версии: версия в рабочей среде и новая версия на этапе тестирования.

    ![Две версии приложения-шаблона](media/service-template-apps-update-extract-delete/power-bi-template-app-update1.png)

1. Когда вы будете готовы повысить уровень приложения до предварительного для дальнейшего тестирования вне клиента, вернитесь в область "Управление выпусками" и щелкните **Повысить уровень приложения** рядом с пунктом **Тестирование**.

   Теперь у вас есть версия в рабочей среде и версия в подготовительной среде.

   ![Две версии приложения-шаблона, кнопка "Повысить уровень приложения" недоступна](media/service-template-apps-update-extract-delete/power-bi-template-app-update2.png)

   Теперь ваша ссылка активна. **Обратите внимание, что кнопка "Повысить уровень приложения" на этапе подготовки к работе неактивна**. Это необходимо для предотвращения случайной перезаписи активной рабочей ссылки на текущую версию приложения до того, как портал Cloud Partner проверит и утвердит новую версию приложения.

1. Еще раз отправьте ссылку на портал Cloud Partner, следуя инструкциям в разделе [Обновление предложения приложения Power BI](/azure/marketplace/cloud-partner-portal/power-bi/cpp-update-existing-offer). На портале Cloud Partner необходимо повторно **опубликовать**  предложение, а также повторно его проверить и утвердить.

   Когда предложение будет утверждено, кнопка "Повысить уровень приложения" станет активной. 
1. Повысьте уровень приложения до рабочей среды.
   
### <a name="update-behavior"></a>Поведение при обновлении

1. Обновление приложения позволит установщику приложения-шаблона [обновить приложение-шаблон](service-template-apps-install-distribute.md#update-a-template-app) в уже установленной рабочей области без потери конфигурации подключения.
1. Сведения о том, как изменения в наборе данных влияют на установленное приложение-шаблон, см. в разделе про [поведение установщика при перезаписи](service-template-apps-install-distribute.md#overwrite-behavior).
1. При обновлении (перезаписи) приложение-шаблон сначала возвращается к образцу данных и автоматически повторно подключается к конфигурации пользователя (параметры и проверка подлинности). До завершения обновления отчеты, панели мониторинга и приложение организации будут демонстрировать баннер с образцом данных.
1. Если в обновленный набор данных, требующий ввода пользователей, добавлен новый параметр запроса, необходимо установить флажок *Необходимо*. После обновления приложения в программе установки будет предложено ввести строку подключения.
 ![Необходимые параметры](media/service-template-apps-update-extract-delete/power-bi-template-app-upload-dataset4.png)

## <a name="extract-workspace"></a>Извлечение рабочего пространства
Возврат к предыдущей версии приложения-шаблона теперь реализовать намного проще благодаря возможности извлечения. Описанные ниже шаги позволят извлечь в новое рабочее пространство нужную версию приложения из любого этапа выпуска.

1. В панели управления выпусками нажмите значок **(...)** , а затем **Извлечь**.

    ![Снимок экрана: панель "Управление выпусками" с выделенным пунктом "Извлечь".](media/service-template-apps-update-extract-delete/power-bi-template-app-extract.png)
    ![Снимок экрана: сообщение о подтверждении извлечения этого приложения.](media/service-template-apps-update-extract-delete/power-bi-template-app-extract-dialog.png)
2. В диалоговом окне введите имя для извлеченного рабочего пространства. Новое рабочее пространство будет добавлено.

Версии нового рабочего пространства установятся повторно и можно будет продолжить разработку и распространение приложения-шаблона из недавно извлеченного рабочего пространства.

## <a name="delete-template-app-version"></a>Удаление версии приложения-шаблона
Рабочая область шаблона является источником активного распространяемого приложения-шаблона. В целях обеспечения защиты пользователей приложения-шаблона невозможно удалить рабочую область без предварительного удаления всех созданных версий приложения в рабочей области.
Удаление версии приложения сопровождается удалением URL-адреса приложения, после чего он больше не будет работоспособным.

1. В панели управления выпусками выберите значок **(...)**, а затем щелкните **Удалить**.
 ![Снимок экрана: панель "Управление выпусками" с выделенным пунктом "Удалить".](media/service-template-apps-update-extract-delete/power-bi-template-app-delete.png)
 ![Снимок экрана: сообщение о подтверждении удаления этого приложения.](media/service-template-apps-update-extract-delete/power-bi-template-app-delete-dialog.png)

>[!NOTE]
>Проследите за тем, чтобы не удалить версию приложения, используемую клиентами или **AppSource** иначе они больше не будут работать.

## <a name="next-steps"></a>Дальнейшие действия

Сведения о том, как с вашим приложением-шаблоном взаимодействуют пользователи, см. в разделе [Установка, настройка и распространение приложений-шаблонов в организации](service-template-apps-install-distribute.md).

Дополнительные сведения о распространении приложения: [Предложение приложения Power BI](/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer).