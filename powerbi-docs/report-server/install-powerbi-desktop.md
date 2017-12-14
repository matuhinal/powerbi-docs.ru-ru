---
title: "Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI"
description: "Узнайте, как установить приложение Power BI Desktop, оптимизированное для сервера отчетов Power BI"
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/05/2017
ms.author: maggies
ms.openlocfilehash: efae785bb063e1bfb1b8333e36447dcaa66a70b4
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2017
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Установка приложения Power BI Desktop, оптимизированного для сервера отчетов Power BI
Узнайте, как установить приложение Power BI Desktop, оптимизированное для сервера отчетов Power BI.

Чтобы создавать отчеты Power BI для решения "Сервер отчетов Power BI", скачайте и установите приложение Power BI Desktop, оптимизированное для этого решения. Этот выпуск отличается от выпуска Power BI Desktop, который используется в службе Power BI. Использование этого выпуска позволяет обеспечить взаимодействие между сервером отчетов и известной версией отчетов и модели. 

> [!NOTE]
> Power BI Desktop и приложение Power BI Desktop, оптимизированное для решения "Сервер отчетов Power BI", можно устанавливать параллельно на одном компьютере.

## <a name="download-and-install-power-bi-desktop"></a>Загрузка и установка Power BI Desktop

Самый простой способ скачать последнюю версию приложения Power BI Desktop, оптимизированного для решения "Сервер отчетов Power BI", — запустить его из веб-портала сервера отчетов.

1. На веб-портале сервера отчетов последовательно выберите **Загрузка** > **Power BI Desktop**.

    ![Скачивание Power BI Desktop из веб-портала](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Вы также можете перейти непосредственно к приложению [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=861076) (октябрь 2017 г.), оптимизированному для решения "Сервер отчетов Power BI", в Центре загрузки Майкрософт.

2. На странице Центра загрузки нажмите кнопку **Скачать**.

3. В зависимости от компьютера выберите файл: 

    - **PBIDesktopRS.msi** (32-разрядная версия);

    - **PBIDesktopRS_x64.msi** (64-разрядная версия).

1. Когда вы скачаете установщик, запустите мастер установки Power BI Desktop (октябрь 2017 г.).
2. На завершающем этапе процесса установки выберите параметр **Start Power BI Desktop now** (Запустить Power BI Desktop).
   
    После автоматического запуска приложения вы будете готовы к работе.

## <a name="verify-you-are-using-the-correct-version"></a>Проверка используемой версии
Чтобы проверить используемую версию Power BI Desktop, просмотрите экран запуска или строку заголовка в Power BI Desktop. В строке заголовка отображаются месяц и год выпуска.

![Строка заголовка приложения Power BI Desktop, оптимизированного для решения "Сервер отчетов Power BI"](media/quickstart-create-powerbi-report/report-server-desktop-october-2017-version.png)

В строке заголовка версии Power BI Desktop для службы Power BI не указаны месяц и год выпуска.

## <a name="file-extension-association"></a>Сопоставление расширения файла
Если Power BI Desktop и приложение Power BI Desktop, оптимизированное для сервера отчетов Power BI, установлены на одном компьютере, экземпляр Power BI Desktop, который устанавливался последним, будет иметь сопоставление файлов с расширением PBIX. Следовательно, щелкнув дважды PBIX-файл, вы запустите экземпляр Power BI Desktop, который установлен последним.

Если у вас уже есть приложение Power BI Desktop, и вы устанавливаете приложение Power BI Desktop, оптимизированное для сервера отчетов Power BI, все PBIX-файлы будут по умолчанию открываться в приложении Power BI Desktop, оптимизированном для сервера отчетов Power BI. Если необходимо, чтобы при открытии PBIX-файлов по умолчанию запускалось приложение Power BI Desktop, переустановите Power BI Desktop в службе Power BI.

Всегда можно открыть ту версию Power BI Desktop, которую нужно использовать первой, а затем открыть файл в приложении Power BI Desktop.

При редактировании отчета Power BI на сервере отчетов Power BI или создании отчета Power BI на веб-портале всегда будет открываться правильная версия Power BI Desktop.

## <a name="next-steps"></a>Дальнейшие действия
Теперь, когда приложение Power BI Desktop установлено, можно приступить к созданию отчетов Power BI.

[Краткое руководство по созданию отчета Power BI для сервера отчетов Power BI](quickstart-create-powerbi-report.md)  
[Начало работы с Power BI Desktop](../desktop-getting-started.md)  
Интерактивное обучение. [Начало работы с Power BI Desktop](../guided-learning/gettingdata.yml#step-2)  
[Общие сведения о руководстве для пользователя сервера отчетов Power BI](user-handbook-overview.md)

Появились дополнительные вопросы? [Попробуйте задать вопрос в сообществе Power BI.](https://community.powerbi.com/)

