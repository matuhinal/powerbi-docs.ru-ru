---
title: Использование внешней среды Python IDE с Power BI
description: Вы можете запускать и использовать внешнюю среду IDE с помощью Power BI.
author: otarb
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/18/2018
ms.author: otarb
LocalizationGroup: Connect to data
ms.openlocfilehash: dbdd4076c9944cf0335ed1f6b6aa43a2a3887189
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "73865964"
---
# <a name="use-an-external-python-ide-with-power-bi"></a>Использование внешней среды Python IDE с Power BI
В **Power BI Desktop** можно использовать внешнюю среду Python IDE (интегрированная среда разработки) для создания и редактирования сценариев на языке Python, которые затем будут использоваться в Power BI.

![](media/desktop-python-ide/python-ide-1.png)

## <a name="enable-an-external-python-ide"></a>Включение внешней среды Python IDE
Можно запускать внешнюю среду Python IDE из **Power BI Desktop**, при этом с импортом, и отображение данных в Python IDE будет происходить автоматически. Вы можете изменять сценарии во внешней среде Python IDE, а затем снова добавлять их в **Power BI Desktop** для создания визуальных элементов и отчетов Power BI.

Вы можете указать, какую интегрированную среду разработки Python вы хотели бы использовать, и запускать ее автоматически в **Power BI Desktop**.

### <a name="requirements"></a>Требования
Чтобы использовать эту функцию, необходимо установить **Python IDE** на локальном компьютере. Так как в **Power BI Desktop** не предусмотрена возможность включения, развертывания или установки подсистемы Python, вам нужно отдельно установить **Python** на локальном компьютере. Используя следующие варианты, вы можете выбрать среду Python IDE для использования.

* Можно установить привычную среду Python IDE из доступных бесплатно, таких как [страница загрузки Visual Studio Code](https://code.visualstudio.com/download/).
* **Power BI Desktop** также поддерживает **Visual Studio**.
* Можно также установить другую среду Python IDE и настроить запуск этой **Python IDE** из **Power BI Desktop** посредством одного из следующих вариантов.
  
  * Можно связать файлы **.PY** с внешней средой IDE, которая должна запускаться с помощью **Power BI Desktop**.
  * Вы можете указать файл EXE, который должно запустить приложение **Power BI Desktop**. Для этого в диалоговом окне *Options* (Параметры) в разделе **Python Script Options** (Параметры сценария Python) выберите **Other** (Другие). Чтобы открыть диалоговое окно **Options** (Параметры), последовательно выбрав элементы **File > Options and settings > Options** (Файл > Параметры и настройки > Параметры).
    
    ![](media/desktop-python-ide/python-ide-2.png)

Если вы установили несколько сред Python IDE, вы можете указать, какую из них следует запустить. Для этого в диалоговом окне *Options* (Параметры) выберите ее в раскрывающемся списке **Detected Python IDEs** (Обнаруженные среды Python IDE).

По умолчанию приложение **Power BI Desktop** запустит **Visual Studio Code** в качестве внешней Python IDE, если она установлена на локальном компьютере. Если **Visual Studio Code** не установлена, но установлена **Visual Studio**, будет запущена последняя. Если не установлена ни одна из указанных сред Python IDE, запустится приложение, сопоставленное с файлами **.PY**.

Если нет сопоставления с файлами **.PY**, вы можете указать путь к пользовательской интегрированной среде разработки в разделе *Browse to your preferred Python IDE* (Переход к предпочтительной Python IDE) диалогового окна **Options** (Параметры). Вы также можете запустить другую среду Python IDE, щелкнув значок **Settings** (Настройки) рядом со стрелкой **Launch Python IDE** (Запуск Python IDE) в приложении **Power BI Desktop**.

## <a name="launch-a-python-ide-from-power-bi-desktop"></a>Запуск Python IDE из Power BI Desktop
Чтобы запустить Python IDE из **Power BI Desktop**, сделайте следующее.

1. Загрузите данные в **Power BI Desktop**.
2. В области **Поля** выберите поля, с которыми вы собираетесь работать. Если вы еще не включили визуальные элементы скрипта, вам будет предложено сделать это.
   
   ![](media/desktop-python-ide/python-ide-3.png)
3. Если визуальные элементы сценария включены, вы можете выбрать визуальный элемент Python в области **Визуализации**. Будет создан пустой визуальный элемент Python, готовый для отображения результатов сценария. Также отобразится область **Редактор сценариев Python**.
   
   ![](media/desktop-python-ide/python-ide-4.png)
4. Теперь вы можете выбрать поля, которые будут использоваться в сценарии Python. Когда вы выберете поля, **Редактор сценариев Python** автоматически создаст код сценария с учетом этого выбора. Вы можете создать (или вставить) сценарий Python непосредственно в область **Редактор Python-скриптов** либо же оставить этот элемент пустым.
   
   ![](media/desktop-python-ide/python-ide-5.png)
   
   > [!NOTE]
   > По умолчанию для визуальных элементов Python используется тип агрегирования *Не суммировать*.
   > 
   > 
5. Теперь можно запускать среду Python IDE непосредственно из **Power BI Desktop**. Нажмите кнопку **Запуск Python IDE** (справа от заголовка окна **Редактор сценариев Python**, как показано ниже).
   
   ![](media/desktop-python-ide/python-ide-6.png)
6. Выбранная среда Python IDE будет запущена службой Power BI Desktop, как показано на следующем рисунке (здесь в качестве среды Python IDE по умолчанию используется **Visual Studio Code**).
   
   ![](media/desktop-python-ide/python-ide-7.png)
   
   > [!NOTE]
   > **Power BI Desktop** добавляет первые три строки скрипта, обеспечивая возможность импорта данных из **Power BI Desktop** после запуска скрипта.
   > 
   > 
7. Любой сценарий, созданный в **области редактора сценариев Python** в **Power BI Desktop**, отобразится, начиная со строки 4 среды Python IDE. Теперь вы можете создавать свой сценарий Python в среде Python IDE. Когда сценарий Python будет выполнен в среде Python IDE, его нужно скопировать и вставить обратно в область **Редактор сценариев Python** в **Power BI Desktop**, *за исключением* первых трех строк сценария, автоматически созданных службой **Power BI Desktop**. Не следует копировать первые три строки сценария в **Power BI Desktop**, так как эти строки предназначены только для импорта данных в Python IDE из **Power BI Desktop**.

### <a name="known-limitations"></a>Известные ограничения
При запуске среды Python IDE непосредственно из Power BI Desktop действуют следующие ограничения.

* Автоматический экспорт сценария из Python IDE в **Power BI Desktop** не поддерживается.

## <a name="next-steps"></a>Дальнейшие действия
Ознакомьтесь с дополнительными материалами по Python в Power BI.

* [Выполнение сценариев Python в Power BI Desktop](desktop-python-scripts.md)
* [Создание визуальных элементов Power BI с помощью Python](desktop-python-visuals.md)

