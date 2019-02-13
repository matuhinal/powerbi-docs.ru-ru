---
title: Устранение неполадок локального шлюза данных
description: В этой статье объясняется, как устранять неполадки с локальным шлюзом данных. Здесь описаны обходные решения для известных проблем, а также соответствующие инструменты.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 08/08/2018
LocalizationGroup: Gateways
ms.openlocfilehash: afc4df99b90d6c6d7016f34983ca3691fb500325
ms.sourcegitcommit: 80961ace38ff9dac6699f81fcee0f7d88a51edf4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/13/2019
ms.locfileid: "56223927"
---
# <a name="troubleshooting-the-on-premises-data-gateway"></a>Устранение неполадок локального шлюза данных

В этой статье описаны распространенные проблемы при работе с **локальным шлюзом данных**.

<!-- Shared Community & support links Include -->
[!INCLUDE [gateway-onprem-tshoot-support-links-include](./includes/gateway-onprem-tshoot-support-links-include.md)]

<!-- Shared Troubleshooting Install Include -->
[!INCLUDE [gateway-onprem-tshoot-install-include](./includes/gateway-onprem-tshoot-install-include.md)]

## <a name="configuration"></a>Конфигурации

### <a name="how-to-restart-the-gateway"></a>Как перезапустить шлюз

Шлюз работает как служба Windows. Его можно запустить и остановить несколькими способами. Например, вы можете открыть окно командной строки с более высоким уровнем разрешений на компьютере, на котором запущен шлюз, а затем выполнить нужную команду из указанных ниже.

* Чтобы остановить службу, выполните следующую команду.

    ```
    net stop PBIEgwService
    ```

* Чтобы запустить службу, выполните следующую команду.

    ```
    net start PBIEgwService
    ```

### <a name="log-file-configuration"></a>Конфигурация файла журнала

Журналы службы шлюза делятся на три категории: "Сведения", "Ошибка" и "Сеть". Благодаря этой категоризации можно более эффективно устранять неполадки, концентрируясь на определенной области с учетом ошибки или проблемы. Эти три категории можно увидеть в следующем фрагменте из файла конфигурации шлюза: `GatewayInfo.log,GatewayErrors.log,GatewayNetwork.log`.

```xml
  <system.diagnostics>
    <trace autoflush="true" indentsize="4">
      <listeners>
        <remove name="Default" />
        <add name="ApplicationFileTraceListener"
             type="Microsoft.PowerBI.DataMovement.Pipeline.Common.Diagnostics.RotatableFilesManagerTraceListener, Microsoft.PowerBI.DataMovement.Pipeline.Common"
             initializeData="%LOCALAPPDATA%\Microsoft\On-premises data gateway\,GatewayInfo.log,GatewayErrors.log,GatewayNetwork.log,20,50" />
      </listeners>
    </trace>
  </system.diagnostics>
```

Расположение этого файла по умолчанию: *\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config*. Чтобы настроить количество файлов журнала для хранения, измените первое число (в этом примере — 20): `GatewayInfo.log,GatewayErrors.log,GatewayNetwork.log,20,50`.

### <a name="error-failed-to-create-a-gateway-try-again"></a>Ошибка Не удалось создать шлюз. Повторите попытку.

Все данные доступны, но обращение к службе Power BI завершилось ошибкой. Отображается ошибка и идентификатор действия. Это может быть вызвано разными причинами. Вы можете собирать и просматривать журналы указанным ниже образом для получения более полной картины.

Проблема также может быть вызвана неправильной конфигурацией прокси-сервера. Теперь пользовательский интерфейс позволяет настраивать конфигурацию прокси-сервера. Вы можете ознакомиться с дополнительными сведениями о внесении [изменений в конфигурацию прокси-сервера](service-gateway-proxy.md).

### <a name="error-failed-to-update-gateway-details-please-try-again"></a>Ошибка Не удалось обновить сведения о шлюзе. Повторите попытку.

Сведения были получены в шлюз из службы Power BI. Сведения были переданы в локальную службу Windows, но она не вернулась либо возникла проблема с формированием симметричного ключа. Внутреннее исключение появится в разделе **Показать сведения**. Вы можете собирать и просматривать журналы, перечисленные ниже, для получения более полной картины.

### <a name="error-power-bi-service-reported-local-gateway-as-unreachable-restart-the-gateway-and-try-again"></a>Ошибка Из службы Power BI поступило сообщение о том, что локальный шлюз недоступен. Перезапустите шлюз и повторите попытку

После завершения настройки служба Power BI будет вызвана снова, чтобы проверить шлюз. Служба Power BI не объявляет шлюз *активным*. Обеспечить подключение может перезапуск службы Windows. Вы можете собирать и просматривать журналы указанным ниже образом для получения более полной картины.

### <a name="script-error-during-sign-into-power-bi"></a>Ошибка сценария при входе в Power BI

При входе в Power BI может отобразиться сообщение об ошибке в скрипте, которая возникла при настройке локального шлюза данных. Установка следующих обновлений безопасности поможет решить эту проблему. Это можно сделать с помощью Центра обновления Windows.

[MS16-051. Обновление для системы безопасности Internet Explorer: 10 мая 2016 г. (статья базы знаний 3154070)](https://support.microsoft.com/kb/3154070)

### <a name="gateway-configuration-failed-with-a-null-reference-exception"></a>Сбой настройки шлюза с исключением пустой ссылки

При работе вы можете столкнуться с ошибкой наподобие следующей:

        Failed to update gateway details.  Please try again.
        Error updating gateway configuration.

При этом выполняется трассировка стека, результаты которой могут содержать следующее сообщение:

        Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.CouldNotUpdateGatewayConfigurationException: Error updating gateway configuration. ----> System.ArgumentNullException: Value cannot be null.
        Parameter name: serviceSection

Если вы выполняете обновление с более старой версии шлюза, мы сохраняем конфигурационный файл. В нем может отсутствовать определенный раздел. Когда шлюз пытается прочитать его, может возникать указанное выше исключение пустой ссылки.

Чтобы исправить эту ошибку, выполните следующие действия.

1. Удалите шлюз.
2. Удалите следующую папку:

        c:\Program Files\On-premises data gateway
3. Установите шлюз снова.
4. При необходимости восстановите существующий шлюз с помощью ключа восстановления.

## <a name="support-for-tls-12"></a>Поддержка протокола TLS 1.2

Локальный шлюз данных по умолчанию использует протокол TLS 1.2 для обмена данными со службой Power BI. Чтобы при передаче всего трафика шлюза использовался протокол TLS 1.2, необходимо добавить или изменить следующие разделы реестра на компьютере, где запущена служба шлюза:

```
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001
[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001
```

> [!NOTE]
> При добавлении или изменении этих разделов реестра обновления распространяются на все приложения .NET. Сведения об изменениях реестра, которые влияют на использование TLS в других приложениях, см. в описании [параметров реестра для протокола TLS](https://docs.microsoft.com/windows-server/security/tls/tls-registry-settings).

## <a name="data-sources"></a>Источники данных

### <a name="error-unable-to-connect-details-invalid-connection-credentials"></a>Ошибка Не удается установить подключение. Сведения: "Недействительные учетные данные подключения"

В разделе **Показать сведения** должно появиться сообщение об ошибке, полученное из источника данных. В случае SQL Server оно будет выглядеть следующим образом.

    Login failed for user 'username'.

Убедитесь, что имя пользователя и пароль указаны правильно. Также убедитесь, что эти учетные данные позволяют подключиться к источнику данных. Убедитесь, что учетная запись соответствует **методу проверки подлинности**.

### <a name="error-unable-to-connect-details-cannot-connect-to-the-database"></a>Ошибка Не удается установить подключение. Сведения: "Не удается подключиться к базе данных"

Удалось подключиться к серверу, но не к указанной базе данных. Проверьте имя базы данных и убедитесь, что учетные данные пользователя позволяют получить доступ к базе данных.

В разделе **Показать сведения** должно появиться сообщение об ошибке, полученное из источника данных. В случае SQL Server оно будет выглядеть следующим образом.

    Cannot open database "AdventureWorks" requested by the login. The login failed. Login failed for user 'username'.

### <a name="error-unable-to-connect-details-unknown-error-in-data-gateway"></a>Ошибка Не удается установить подключение. Сведения: "Неизвестная ошибка в шлюзе данных"

Эта ошибка может возникнуть по разным причинам. Не забудьте проверить подключение к источнику данных с компьютера, на котором находится шлюз. Это может быть связано с недоступностью сервера.

В разделе **Показать сведения** появится код ошибки **DM_GWPipeline_UnknownError**.

Чтобы получить дополнительные сведения, выберите "Журналы событий" > **Журналы приложений и служб** > **Служба локального шлюза данных**.

### <a name="error-we-encountered-an-error-while-trying-to-connect-to-server-details-we-reached-the-data-gateway-but-the-gateway-cant-access-the-on-premises-data-source"></a>Ошибка При попытке подключения к <server> произошла ошибка. Сведения: "Выполнено подключение к шлюзу данных, но шлюз не может получить доступ к локальному источнику данных"

Не удалось подключиться к указанному источнику данных. Не забудьте проверить сведения, указанные для этого источника данных.

В разделе **Показать сведения** появится код ошибки **DM_GWPipeline_Gateway_DataSourceAccessError**.

Если базовое сообщение об ошибке аналогично следующему, это означает, что учетная запись, которую вы используете для источника данных, не имеет прав администратора сервера для этого экземпляра служб Analysis Services. [Дополнительные сведения](https://docs.microsoft.com/sql/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance)

    The 'CONTOSO\account' value of the 'EffectiveUserName' XML for Analysis property is not valid.

Если базовое сообщение об ошибке аналогично следующему, это может означать, что в учетной записи службы для Analysis Services отсутствует атрибут каталога [token-groups-global-and-universal](https://msdn.microsoft.com/library/windows/desktop/ms680300.aspx) (TGGAU):

    The username or password is incorrect.

В доменах с поддержкой доступа на базе технологий, предшествующих версии Windows 2000, атрибут TGGAU включен. Однако в большинстве новых доменов он по умолчанию отключен. Дополнительные сведения об этом можно найти [здесь](https://support.microsoft.com/kb/331951).

Чтобы уточнить, включен ли этот атрибут, выполните указанные ниже действия.

1. Подключитесь к компьютеру со службами Analysis Services из приложения SQL Server Management Studio. В дополнительных свойствах соединения укажите параметр EffectiveUserName для соответствующего пользователя и посмотрите, повторится ли ошибка.
2. Проверить, указан ли этот атрибут, можно с помощью программы dsacls для Active Directory. Эта программа есть на контроллере домена. Вам потребуется передать в эту программу различающееся имя домена для учетной записи.

        dsacls "CN=John Doe,CN=UserAccounts,DC=contoso,DC=com"

    Результаты должны содержать что-то наподобие этого:

            Allow BUILTIN\Windows Authorization Access Group
                                          SPECIAL ACCESS for tokenGroupsGlobalAndUniversal
                                          READ PROPERTY

Чтобы устранить эту проблему, потребуется включить атрибут TGGAU для учетной записи, которую использует служба Analysis Services.

#### <a name="another-possibility-for-username-or-password-incorrect"></a>Другой вариант, связанный с неправильным именем пользователя или паролем

Эта ошибка также может возникнуть, если сервер Analysis Services и пользователи находятся в разных доменах, и для них не установлено двустороннее доверие.

Чтобы установить отношения доверия между доменами, вам потребуется обратиться к их администраторам.

#### <a name="unable-to-see-the-data-gateway-data-sources-in-the-get-data-experience-for-analysis-services-from-the-power-bi-service"></a>Источники данных шлюза данных в интерфейсе "Получить данные" для служб Analysis Services недоступны из службы Power BI

Убедитесь, что ваша учетная запись указана на вкладке **Пользователи** источника данных в конфигурации шлюза. Если у вас нет доступа к шлюзу, свяжитесь с его администратором и попросите его проверить это для вас. Только учетным записям в списке **Пользователи** доступен источник данных, указанный в списке служб Analysis Services.

### <a name="error-you-dont-have-any-gateway-installed-or-configured-for-the-data-sources-in-this-dataset"></a>Ошибка Не установлен или не настроен шлюз для источников данных в этом наборе

Обязательно добавьте в шлюз источники данных, как описано в разделе [Добавление источника данных](service-gateway-manage.md#add-a-data-source). Если шлюз не отображается в разделе **Управление шлюзами** на портале администрирования, попробуйте очистить кэш браузера или выйти из службы, а затем войти в нее заново.

## <a name="datasets"></a>Наборы данных

### <a name="error-there-is-not-enough-space-for-this-row"></a>Ошибка Недостаточно места для этой строки

Это происходит, если размер одной строки превышает 4 МБ. Необходимо найти эту строку в источнике данных и попытаться отфильтровать ее или уменьшить ее размер.

### <a name="error-the-server-name-provided-doesnt-match-the-server-name-on-the-sql-server-ssl-certificate"></a>Ошибка Указанное имя сервера не соответствует имени сервера в SSL-сертификате сервера SQL Server

Это может произойти, если общее имя сертификата предназначено для полного доменного имени сервера (FQDN), а пользователь указал только NetBIOS-имя для сервера. Это вызывает несоответствие сертификата. Для устранения проблемы необходимо, чтобы для имени сервера в источнике данных шлюза и PBIX-файле использовалось полное доменное имя сервера.

### <a name="i-dont-see-the-on-premises-data-gateway-present-when-configuring-scheduled-refresh"></a>Локальный шлюз данных не отображается при настройке запланированного обновления

Это может быть из-за нескольких причин.

1. Имена сервера и базы данных не совпадают со значениями, указанными в Power BI Desktop и источнике данных, настроенном для шлюза. Эти значения должны быть одинаковыми. Для них регистр не учитывается.
2. Ваша учетная запись не указана на вкладке **Пользователи** источника данных в конфигурации шлюза. Необходимо, чтобы администратор шлюза добавил вашу учетную запись в этот список.
3. Файл Power BI Desktop содержит несколько источников данных, но шлюз настроен не для всех. Необходимо определить для каждого источника данных шлюз, чтобы он отображался в запланированном обновлении.

### <a name="error-the-received-uncompressed-data-on-the-gateway-client-has-exceeded-the-limit"></a>Ошибка Превышен допустимый объем полученных несжатых данных в клиенте шлюза

Точное ограничение составляет 10 ГБ несжатых данных для каждой таблицы. Есть несколько эффективных вариантов оптимизации и предотвращения этой проблемы. В частности, для этого можно уменьшить использование часто повторяющихся значений длинных строк, а вместо них применять нормализованный ключ или удалять неиспользуемые столбцы.

## <a name="reports"></a>Отчеты

### <a name="report-could-not-access-the-data-source-because-you-do-not-have-access-to-our-data-source-via-an-on-premises-data-gateway"></a>Отчету не удалось получить доступ к источнику данных, так как у вас нет доступа к нашему источнику данных в локальном шлюзе данных

Это обычно происходит из-за одной из следующих проблем.

1. Сведения об источнике данных не совпадают со сведениями в базовом наборе данных. Имена сервера и базы данных в источнике данных, заданном для локального шлюза, должны совпадать с теми, что вы указали в Power BI Desktop. Если вы используете IP-адрес в Power BI Desktop, источник данных локального шлюза должен также использовать IP-адрес.
2. В шлюзах вашей организации нет ни одного доступного источника данных. Вы можете настроить источник данных в новом или существующем локальном шлюзе.

### <a name="error-data-source-access-error-please-contact-the-gateway-administrator"></a>Ошибка Ошибка доступа к источнику данных. Обратитесь к администратору шлюза

Если в этом отчете используется подключение к службам Analysis Services, возможно, ошибка связана с передачей недействительного значения EffectiveUserName или отсутствием разрешений на компьютере с Analysis Services. Как правило, проблемы с проверкой подлинности возникают в ситуации, когда передаваемое значение EffectiveUserName не совпадает с локальным именем участника-пользователя.

Чтобы выяснить, так ли это, выполните указанные ниже действия.

1. Найдите действующее имя пользователя в [журналах шлюза](#logs).
2. Обнаружив значение, которое передается, проверьте его правильность. Если это ваш пользователь, вы можете уточнить его имя участника-пользователя с помощью следующей команды в командной строке. Имя имеет форму адреса электронной почты.

        whoami /upn

Вы также можете посмотреть, что именно Power BI получает из каталога Azure Active Directory.

1. Перейдите к [https://developer.microsoft.com/graph/graph-explorer](https://developer.microsoft.com/graph/graph-explorer).
2. Выберите **Войти** в правом верхнем углу.
3. Выполните следующий запрос: Вы увидите довольно большой ответ в формате JSON.

        https://graph.windows.net/me?api-version=1.5
4. Найдите атрибут **userPrincipalName**.

Если имя участника-пользователя Azure Active Directory не совпадает с аналогичным значением в локальном каталоге Active Directory, вы можете заменить его действительным значением с помощью функции [Сопоставление имен пользователей](service-gateway-enterprise-manage-ssas.md#map-user-names). Вы также можете попросить администратора своего клиента или локального каталога Active Directory изменить имя участника-пользователя.

<!-- Shared Troubleshooting Firewall/Proxy Include -->
[!INCLUDE [gateway-onprem-tshoot-firewall-include](./includes/gateway-onprem-tshoot-firewall-include.md)]

Чтобы определить регион своего центра данных, выполните указанные ниже действия.

1. Нажмите кнопку **?** в правом верхнем углу окна службы Power BI.
2. Выберите **О Power BI**.
3. Регион, в котором хранятся ваши данные, будет указан в строке **Ваши данные сохранены в**.

    ![Область данных](media/service-gateway-onprem-tshoot/power-bi-data-region.png)

Если это все равно не помогает, вы можете попытаться выполнить сетевую трассировку с помощью такого инструмента, как [fiddler](#fiddler) или netsh, хотя это уже более сложные способы сбора информации, и вам может потребоваться помощью в анализе полученных данных. Вы можете обратиться за помощью в [службу поддержки](https://support.microsoft.com).

## <a name="performance"></a>Производительность

<iframe width="560" height="315" src="https://www.youtube.com/embed/IJ_DJ30VNk4?showinfo=0" frameborder="0" allowfullscreen></iframe>

### <a name="performance-counters"></a>Счетчики производительности

Существует ряд счетчиков производительности, используемых для оценки действий шлюза. Благодаря им можно определить большой объем действий и необходимость в создании шлюза. Эти счетчики не отражают продолжительность действий.

К ним можно получить доступ с помощью средства "Монитор производительности Windows".

![](media/service-gateway-onprem-tshoot/gateway-perfmon.png)

Эти счетчики разделены на общие группы.

| Тип счетчика | Описание |
| --- | --- |
| ADO.NET |Используется для любого подключения DirectQuery. |
| ADOMD |Используется для служб Analysis Services 2014 и более ранних версий. |
| OLEDB |Используется некоторыми источниками данных. Например, SAP HANA и служба Analysis Service 2016 или более поздних версий. |
| Гибридное веб-приложение |Включает в себя любые источники импортируемых данных. При планировании обновления или выполнении обновления по требованию задействована подсистема гибридных веб-приложений. |

Ниже приведен список доступных счетчиков производительности.

| Счетчик | Описание |
| --- | --- |
| # of ADO.NET open connection executed / sec |Количество открытых действий подключения ADO.NET, выполненных в секунду (завершившихся успешно или с ошибкой). |
| # of ADO.NET open connection failed / sec |Количество открытых действий подключения ADO.NET в секунду, завершившихся с ошибкой. |
| # of ADO.NET queries executed / sec |Количество запросов ADO.NET, выполненных в секунду (завершившихся успешно или с ошибкой). |
| # of ADO.NET queries failed / sec |Количество выполненных в секунду запросов ADO.NET, завершившихся с ошибкой. |
| # of ADOMD open connection executed / sec |Количество открытых действий подключения ADOMD, выполненных в секунду (завершившихся успешно или с ошибкой). |
| # of ADOMD open connection failed / sec |Количество открытых действий подключения ADOMD в секунду, завершившихся с ошибкой. |
| # of ADOMD queries executed / sec |Количество запросов ADOMD, выполненных в секунду (завершившихся успешно или с ошибкой). |
| # of ADOMD queries failed / sec |Количество выполненных в секунду запросов ADOMD, завершившихся с ошибкой. |
| # of all open connection executed / sec |Количество открытых действий подключения, выполненных в секунду (завершившихся успешно или с ошибкой). |
| # of all open connection failed / sec |Количество выполненных в секунду открытых действий подключения, завершившихся с ошибкой. |
| # of all queries executed / sec |Количество запросов, выполненных в секунду (завершившихся успешно или с ошибкой). |
| # of items in the ADO.NET connection pool |Количество элементов в пуле подключений ADO.NET. |
| # of items in the OLEDB connection pool |Количество элементов в пуле подключений OLEDB. |
| # of items in the Service Bus pool |Количество элементов в пуле служебной шины. |
| # of Mashup open connection executed / sec |Количество действий открытых подключений гибридных приложений, выполненных в секунду (завершившихся успешно или с ошибкой). |
| # of Mashup open connection failed / sec |Количество выполненных в секунду действий открытых подключений гибридных приложений, завершившихся с ошибкой. |
| # of Mashup queries executed / sec |Количество запросов гибридных приложений, выполненных в секунду (завершившихся успешно или с ошибкой). |
| # of Mashup queries failed / sec |Количество выполненных в секунду запросов гибридных приложений, завершившихся с ошибкой. |
| # of OLEDB multiple result set queries failed / sec |Количество выполненных в секунду запросов нескольких результирующих наборов OLEDB, завершившихся с ошибкой. |
| # of OLEDB multiple result sets of queries executed / sec |Количество запросов нескольких результирующих наборов OLEDB, выполненных в секунду (завершившихся успешно или с ошибкой). |
| # of OLEDB open connection executed / sec |Количество действий открытых подключений OLEDB, выполненных в секунду (завершившихся успешно или с ошибкой). |
| # of OLEDB open connection failed / sec |Количество выполненных в секунду действий открытых подключений OLEDB, завершившихся с ошибкой. |
| # of OLEDB queries executed / sec |Количество запросов нескольких результирующих наборов OLEDB, выполненных в секунду (завершившихся успешно или с ошибкой). |
| # of OLEDB queries failed / sec |Количество выполненных в секунду запросов нескольких результирующих наборов OLEDB, завершившихся с ошибкой. |
| # of OLEDB single result set queries executed / sec |Количество запросов одного результирующего набора OLEDB, выполненных в секунду (завершившихся успешно или с ошибкой). |
| # of queries failed / sec |Количество выполненных в секунду запросов, завершившихся с ошибкой. |
| # of single result set OLEDB queries failed / sec |Количество выполненных в секунду запросов одного результирующего набора OLEDB, завершившихся с ошибкой. |

## <a name="reviewing-slow-performing-queries"></a>Анализ медленной производительности запросов

Время от времени вы можете сталкиваться с проблемой медленного отклика через шлюз. Такое случается при обработке запросов DirectQuery или при обновлении импортированного набора данных. Вы можете включить дополнительную регистрацию данных по выходным запросам и срокам их выполнения, чтобы понять, что именно работает медленно. При обнаружении длительно выполняющегося запроса может потребоваться внести дополнительные изменения в источник данных для настройки производительности запросов. Например, можно настроить индексы запросов SQL Server.

Необходимо изменить два файла конфигурации, чтобы определить продолжительность выполнения запроса.

### <a name="microsoftpowerbidatamovementpipelinegatewaycoredllconfig"></a>Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config

В файле *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* измените значение параметра `EmitQueryTraces` с `False` на `True`. По умолчанию этот файл находится в каталоге *C:\Program Files\On-premises data gateway*. Если включить параметр `EmitQueryTraces`, начнется запись запросов в журнал, отправленных из шлюза в источник данных.

> [!IMPORTANT]
> Включение параметра EmitQueryTraces может существенно увеличить размер журнала в зависимости от режима использования шлюза. После завершения проверки журналов может потребоваться присвоить параметру EmitQueryTraces значение False. Не рекомендуется включать эту функцию на продолжительное время.

```xml
<setting name="EmitQueryTraces" serializeAs="String">
    <value>True</value>
</setting>
```

**Пример ввода запроса**

```
DM.EnterpriseGateway Information: 0 : 2016-09-15T16:09:27.2664967Z DM.EnterpriseGateway    4af2c279-1f91-4c33-ae5e-b3c863946c41    d1c77e9e-3858-4b21-3e62-1b6eaf28b176    MGEQ    c32f15e3-699c-4360-9e61-2cc03e8c8f4c    FF59BC20 [DM.GatewayCore] Executing query (timeout=224) "<pi>
SELECT
TOP (1000001) [t0].[ProductCategoryName],[t0].[FiscalYear],SUM([t0].[Amount])
 AS [a0]
FROM
(
(select [$Table].[ProductCategoryName] as [ProductCategoryName],
    [$Table].[ProductSubcategory] as [ProductSubcategory],
    [$Table].[Product] as [Product],
    [$Table].[CustomerKey] as [CustomerKey],
    [$Table].[Region] as [Region],
    [$Table].[Age] as [Age],
    [$Table].[IncomeGroup] as [IncomeGroup],
    [$Table].[CalendarYear] as [CalendarYear],
    [$Table].[FiscalYear] as [FiscalYear],
    [$Table].[Month] as [Month],
    [$Table].[OrderNumber] as [OrderNumber],
    [$Table].[LineNumber] as [LineNumber],
    [$Table].[Quantity] as [Quantity],
    [$Table].[Amount] as [Amount]
from [dbo].[V_CustomerOrders] as [$Table])
)
 AS [t0]
GROUP BY [t0].[ProductCategoryName],[t0].[FiscalYear] </pi>"
```

### <a name="microsoftpowerbidatamovementpipelinediagnosticsdllconfig"></a>Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.dll.config

В файле *Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.dll.config* измените значение параметра `TracingVerbosity` с `4` на `5`. По умолчанию этот файл находится в каталоге *C:\Program Files\On-premises data gateway*. После изменения этого параметра в журнале шлюза будут регистрироваться подробные данные. Это касается и записей, содержащих сведения о продолжительности. Можно также включить ведение подробных записей, щелкнув переключатель "Дополнительное ведение журнала" в приложении локального шлюза.

   ![Дополнительное ведение журнала](media/service-gateway-onprem-tshoot/additional-logging.png)

> [!IMPORTANT]
> Если задать для параметра TracingVerbosity значение `5`, размер журнала может существенно увеличиться в зависимости от использования шлюза. Проверив журналы, установите для параметра TraceVerbosity значение `4`. Не рекомендуется включать эту функцию на продолжительное время.

```xml
<setting name="TracingVerbosity" serializeAs="String">
    <value>5</value>
</setting>
```

<a name="activities"></a>

### <a name="activity-types"></a>Типы действий

| Тип действия | Описание |
| --- | --- |
| MGEQ |Запросы, выполняемые через ADO.NET. К этому типу действий относятся источники данных DirectQuery. |
| MGEO |Запросы, выполняемые через OLEDB. К этому типу действий относятся SAP HANA и Analysis Services 2016. |
| MGEM |Запросы, выполняемые с помощью подсистемы гибридного веб-приложения. Они используются для импортированных наборов данных с запланированным обновлением или обновлением по требованию. |

### <a name="determine-the-duration-of-a-query"></a>Определение продолжительности выполнения запроса
Чтобы определить время, потраченное на выполнение запроса к источнику данных, сделайте следующее:

1. Откройте журнал шлюза.
2. Найдите запрос по [типу действия](#activities). Например, MGEQ.
3. Запишите второй GUID, так как он является идентификатором запроса.
4. Продолжите поиск MGEQ, пока не найдете запись FireActivityCompletedSuccessfullyEvent со сведениями о продолжительности. Можете проверить запись на наличие аналогичного идентификатора запроса. Длительность указана в миллисекундах.

        DM.EnterpriseGateway Verbose: 0 : 2016-09-26T23:08:56.7940067Z DM.EnterpriseGateway    baf40f21-2eb4-4af1-9c59-0950ef11ec4a    5f99f566-106d-c8ac-c864-c0808c41a606    MGEQ    21f96cc4-7496-bfdd-748c-b4915cb4b70c    B8DFCF12 [DM.Pipeline.Common.TracingTelemetryService] Event: FireActivityCompletedSuccessfullyEvent (duration=5004)

   > [!NOTE]
   > FireActivityCompletedSuccessfullyEvent считается подробной записью. Эта запись не регистрируется, если TraceVerbosity не находится на уровне 5.

## <a name="firewall-or-proxy"></a>Брандмауэр или прокси-сервер

Дополнительные сведения см. в разделе о [настройке параметров прокси-сервера для шлюзов Power BI](service-gateway-proxy.md).

Возможно, ваш брандмауэр или прокси-сервер блокирует подключения. Чтобы это проверить, выполните команду [Test-NetConnection](https://docs.microsoft.com/powershell/module/nettcpip/test-netconnection) в командной строке PowerShell. Эта команда выполняет проверку подключения к служебной шине Azure. При этом проверяется только возможность подключения к сети, а не работоспособность облачной серверной службы или шлюза. Этот способ помогает выяснить, подключен ли ваш компьютер к Интернету.

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> Команда Test-NetConnection доступна только в Windows Server 2012 R2 и более поздних версиях. Ее также можно выполнить в Windows 8.1 и более поздних версиях. Для проверки подключения к порту в более ранних версиях ОС можно использовать Telnet.

Результат выглядит следующим образом. Отличие заключается в значении параметра TcpTestSucceeded. Если значение **TcpTestSucceeded** не *true*, это указывает на блокировку брандмауэра.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Чтобы выполнить более полную проверку, замените значения параметров **ComputerName** и **Port** значениями, указанными для [портов](https://docs.microsoft.com/power-bi/service-gateway-onprem#ports).

Возможно, брандмауэр также блокирует подключения служебной шины Azure к центрам данных Azure. В этом случае вам придется добавить в список разрешений (разблокировать) IP-адреса центров данных своего региона. Найти список IP-адресов Azure можно [здесь](https://www.microsoft.com/download/details.aspx?id=41653).

### <a name="network-ports-test"></a>Проверка сетевых портов

Проверка сетевых портов — это инструмент для проверки возможности получения шлюзом доступа к необходимым портам для всех удаленных серверов, которые требуются шлюзу для передачи данных. Сбой проверки сетевых портов для любого порта шлюза может означать проблемы с сетевым подключением шлюза. Если вы испытываете проблемы с сетевым подключением шлюза, выполните проверку сетевых портов, чтобы убедиться в наличии оптимальной сетевой среды.  

#### <a name="start-a-new-test"></a>Запуск новой проверки

Запуск новой проверки сетевых портов в пользовательском интерфейсе локального шлюза данных.

![Запуск проверки портов](media/service-gateway-onprem-tshoot/gateway-onprem-porttest-starttest.png)

При выполнении проверки сетевых портов шлюз получает список портов и серверов из служебной шины Azure, а затем пытается подключиться ко всем этим серверам и портам. Когда ссылка "Запустить новую проверку" появляется снова, это означает завершение проверки сетевых портов.  

#### <a name="test-results"></a>Результаты проверки

Сводка проверки отображается под ссылкой "Запустить новую проверку" как "Результаты последней проверки". Доступно два результата: "Завершено (успешно)" и "Завершено (сбой; см. результаты последней проверки)". Если проверка пройдена, шлюз успешно подключается ко всем нужным портам. Сбой проверки может означать, что сетевая среда может блокировать такие порты и серверы. 

![Результаты проверки портов](media/service-gateway-onprem-tshoot/gateway-onprem-porttest-result.png)

Для просмотра результатов выполнения последней проверки перейдите по ссылке "Открыть результаты последней выполненной проверки", как показано ниже. Результаты проверки открываются в текстовом редакторе Windows по умолчанию.  

В результатах проверки указаны все серверы, порты и IP-адреса, которые требуются шлюзу. Если в результатах проверки отображается "Закрыто" для каких-либо портов, как показано ниже, убедитесь, что сетевая среда не блокирует подключение. Возможно, вам потребуется обратиться к администратору сети, чтобы открыть необходимые порты.

![Файл результатов проверки портов](media/service-gateway-onprem-tshoot/gateway-onprem-porttest-result-file.png)

## <a name="kerberos"></a>Kerberos

Если основной сервер базы данных и локальный шлюз данных неправильно настроены для [ограниченного делегирования Kerberos](service-gateway-sso-kerberos.md), включите [подробное ведение журнала](#microsoftpowerbidatamovementpipelinediagnosticsdllconfig) на шлюзе и проанализируйте ошибки или трассировки в файлах журналов шлюза, чтобы начать устранение неполадок.

### <a name="impersonationlevel"></a>ImpersonationLevel

Значение ImpersonationLevel связано с настройкой имени субъекта-службы или параметрами локальной политики.

```
[DataMovement.PipeLine.GatewayDataAccess] About to impersonate user DOMAIN\User (IsAuthenticated: True, ImpersonationLevel: Identification)
```

**Решение**

Чтобы устранить проблему, выполните следующие действия:
1. Настройте имя субъекта-службы для локального шлюза.
2. Настройте ограниченное делегирование в Active Directory (AD).

### <a name="failedtoimpersonateuserexception-failed-to-create-windows-identity-for-user-userid"></a>FailedToImpersonateUserException: Не удалось создать удостоверение Windows для идентификатора пользователя

Исключение FailedToImpersonateUserException может возникнуть, если не удается олицетворить другого пользователя. Это также может произойти, если вы пытаетесь олицетворить учетную запись из другого домена, отличного от того, в котором включена служба шлюза (ограничение).

**Решение**

* Проверьте правильность конфигурации согласно инструкциям в предыдущем разделе ImpersonationLevel.
* Убедитесь, что идентификатор пользователя, который используется для олицетворения, представляет действительную учетную запись AD.

### <a name="general-error-1033-error-while-parsing-the-protocol"></a>Общая ошибка. Ошибка 1033 при анализе протокола

Ошибка 1033 может произойти, если внешний идентификатор, настроенный в SAP HANA, не соответствует имени пользователя при олицетворении с помощью имени участника-пользователя (alias@domain.com). В верхней части журналов ошибок отображается сообщение Original UPN "alias@domain.com" replaced with a new UPN "alias@domain.com" (Исходное имя участника-пользователя alias@domain.com заменено новым alias@domain.com), как показано ниже.

```
[DM.GatewayCore] SingleSignOn Required. Original UPN 'alias@domain.com' replaced with new UPN 'alias@domain.com.'
```

**Решение**

* Для SAP HANA требуется, чтобы олицетворенный пользователь применил атрибут sAMAccountName в AD (псевдоним пользователя). В противном случае появится ошибка 1033.

    ![sAMAccount](media/service-gateway-onprem-tshoot/sAMAccount.png)

* В журналах будет отображаться не имя участника-пользователя, а sAMAccountName (псевдоним), после которого указан домен (alias@doimain.com).

    ![sAMAccount](media/service-gateway-onprem-tshoot/sAMAccount-02.png)

```xml
      <setting name="ADUserNameReplacementProperty" serializeAs="String">
        <value>sAMAccount</value>
      </setting>
      <setting name="ADServerPath" serializeAs="String">
        <value />
      </setting>
      <setting name="CustomASDataSource" serializeAs="String">
        <value />
      </setting>
      <setting name="ADUserNameLookupProperty" serializeAs="String">
        <value>AADEmail</value>
```

### <a name="sap-aglibodbchdb-dllhdbodbc-communication-link-failure-10709-connection-failed-rte-1-kerberos-error-major-miscellaneous-failure-851968-minor-no-credentials-are-available-in-the-security-package"></a>[SAP AG] [LIBODBCHDB DLL] [HDBODBC] Ошибка связи. -10709 Не удалось установить подключение (RTE:[-1] Ошибка Kerberos. Major: "Общий сбой [851968]", minor: "В пакете безопасности отсутствуют учетные данные"

Сообщение о сбое подключения 10709 появляется, если делегирование неправильно настроено в AD.

**Решение**

* Убедитесь, что вы указали сервер SAP HANA на вкладке делегирования в AD для учетной записи службы шлюза.

   ![Вкладка делегирования](media/service-gateway-onprem-tshoot/delegation-in-AD.png)

<!-- Shared Troubleshooting tools Include -->
[!INCLUDE [gateway-onprem-tshoot-tools-include](./includes/gateway-onprem-tshoot-tools-include.md)]

### <a name="refresh-history"></a>Журнал обновления

При использовании шлюза для запланированного обновления **Журнал обновлений** может помочь выявить возникшие ошибки, а также предоставляет полезные данные, если понадобится создать запрос на техническую поддержку. Можно просматривать как запланированные обновления, так и обновления по запросу. Ниже описано, как можно открыть **журнал обновления**.

1. В области навигации Power BI в разделе **Наборы данных** выберите набор данных, затем &gt; меню "Открыть" &gt; **Запланировать обновление**.

    ![](media/service-gateway-onprem-tshoot/scheduled-refresh.png)
2. В **Параметры для...** &gt; **Запланировать обновление** выберите **Журнал обновления**.

    ![](media/service-gateway-onprem-tshoot/scheduled-refresh-2.png)

    ![](media/service-gateway-onprem-tshoot/refresh-history.png)

См. дополнительные сведения об [устранении неполадок в сценариях обновления](refresh-troubleshooting-refresh-scenarios.md).

## <a name="next-steps"></a>Дальнейшие действия
[Настройка параметров прокси-сервера для шлюзов Power BI](service-gateway-proxy.md)  
[Локальный шлюз данных](service-gateway-onprem.md)  
[Локальный шлюз данных: подробный обзор](service-gateway-onprem-indepth.md)  
[Управление своим источником данных — службы Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[Управление своим источником данных — SAP HANA](service-gateway-enterprise-manage-sap.md)  
[Управление своим источником данных — SQL Server](service-gateway-enterprise-manage-sql.md)  
[Управление источником данных — импорт или запланированное обновление](service-gateway-enterprise-manage-scheduled-refresh.md)  
Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)
