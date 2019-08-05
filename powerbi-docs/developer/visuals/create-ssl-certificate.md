---
title: Создание SSL-сертификата
description: Обходной путь для ручного создания сертификатов для сервера разработчика
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: 3287e8a7eb1c36c3f0d8a1fc24faa0442de2dddf
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425443"
---
# <a name="creating-ssl-certificate"></a>Создание SSL-сертификата

Выполните следующую команду, чтобы создать сертификат с помощью командлета PowerShell New-SelfSignedCertificate в Windows 8 или более поздней версии.

Средству требуется установка OpenSSL для **Windows** **7**. Служебная программа `openssll` должна быть доступна из командной строки.

Для установки OpenSSL перейдите по адресу [https://www.openssl.org](https://www.openssl.org) или [https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries).

```cmd
pbiviz --create-cert
```

## <a name="create-certificate-mac-os-x"></a>Создание сертификата (Mac OS X)

Обычно служебные программы OpenSSL доступны в операционных системах Linux или Mac OS X.

В противном случае можно выполнить установку с помощью

диспетчера пакетов *Brew*

```cmd
brew install openssl
brew link openssl --force
```

или *MacPorts*

```cmd
sudo port install openssl
```

После установки OpenSSL выполните следующую команду для создания нового вызова сертификата:

```cmd
pbiviz --create-cert
```

## <a name="create-certificate-linux"></a>Создание сертификата (Linux)

Служебные программы OpenSSL недоступны в операционной системе Linux, для установки можно использовать следующие команды.

Для диспетчера пакетов *APT*:

```cmd
sudo apt-get install openssl
```

Для *Yellowdog Updater*:

```cmd
yum install openssl
```

Для *Redhat Package Manager*:

```cmd
rpm install openssl
```

Если OpenSSl уже доступен в вашей операционной системе, вызовите

```cmd
pbiviz --create-cert
```

для создания сертификата.

Его также можно получить по адресу [https://www.openssl.org](https://www.openssl.org) или [https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries).

## <a name="generate-certificate-manually"></a>Ручное создание сертификата

Вы можете указать сертификаты, созданные с помощью любых средств.

Если в вашей системе установлен OpenSSL, можно выполнить следующую команду, чтобы создать сертификат.

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBICustomVisualTest_private.key -out PowerBICustomVisualTest_public.crt -days 365
```

Обычно сертификаты веб-сервера средств для визуальных элементов Power BI находятся в каталоге

```cmd
%appdata%\npm\node_modules\PowerBI-visuals-tools\certs
```

для глобального экземпляра средств

или

```cmd
<custom visual project root>\node_modules\PowerBI-visuals-tools\certs
```

для локального экземпляра средств.

Вам следует сохранить файл сертификата как `PowerBICustomVisualTest_public.cer`, а закрытый ключ — как `PowerBICustomVisualTest_public.key`, если вы используете формат PEM.
Сохраните файл сертификата как `PowerBICustomVisualTest_public.pfx`, если используется формат PFX.

Если для файла сертификата PFX требуется парольная фраза, укажите ее в

```cmd
\PowerBI-visuals-tools\config.json
```

в разделе сервера:

```cmd
"server":{
    "root":"webRoot",
    "assetsRoute":"/assets",
    "privateKey":"certs/PowerBICustomVisualTest_private.key",
    "certificate":"certs/PowerBICustomVisualTest_public.crt",
    "pfx":"certs/PowerBICustomVisualTest_public.pfx",
    "port":"8080",
    "passphrase":"YOUR PASSPHRASE"
}
```
