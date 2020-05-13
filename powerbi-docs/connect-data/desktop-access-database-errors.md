---
title: Устранение проблем с импортом файлов Access и XLS в Power BI Desktop
description: Решение проблем с импортом баз данных Access и электронных таблиц XLS в Power BI Desktop и Power Query
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/21/2019
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 1816fb7926ed378cdb70ce2e0ade08893828ce4c
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83301340"
---
# <a name="troubleshoot-importing-access-and-excel-xls-files-in-power-bi-desktop"></a>Устранение неполадок с импортом XLS-файлов Excel и Access в Power BI Desktop

В Power BI Desktop как базы данных Access, так и книги Excel предыдущих версий (XLS-файлы типа Excel 97–2003) используют *ядро СУБД Access*. Правильная работа ядра СУБД Access может нарушаться в трех распространенных случаях.

## <a name="situation-1-no-access-database-engine-is-installed"></a>Ситуация 1. Ядро СУБД Access не установлено

Когда сообщение об ошибке Power BI Desktop указывает на отсутствие установленного ядра СУБД Access, необходимо установить 32-разрядную или 64-разрядную версию ядра СУБД Access, соответствующую используемой версии Power BI Desktop. Ядро СУБД Access можно установить со [страницы загрузки](https://www.microsoft.com/download/details.aspx?id=13255).

>[!NOTE]
>Когда разрядность установленной версии ядра СУБД Access отличается от разрядности установки Microsoft Office, приложения Office не смогут использовать ядро СУБД Access.

## <a name="situation-2-the-access-database-engine-bit-version-32-bit-or-64-bit-is-different-from-your-power-bi-desktop-bit-version"></a>Ситуация 2. Разрядность версии ядра СУБД Access (32-разрядная или 64-разрядная) отличается от разрядности используемой версии Power BI Desktop

Такая ситуация часто возникает, когда установлена 32-разрядная версия Microsoft Office и 64-разрядная версия Power BI Desktop. Может возникать и обратная ситуация, и в обоих случаях имеет место несовпадение версий. Если вы используете подписку Office 365, см. раздел [Ситуация 3](#situation-3-trouble-using-access-or-xls-files-with-an-office-365-subscription) для устранения других неполадок. Устранить эту ошибку несоответствия можно любым из следующих способов.

### <a name="solution-1"></a>Решение 1

Измените версию Power BI Desktop, чтобы она совпадала по разрядности с установкой Microsoft Office. 

1. Чтобы изменить разрядность Power BI Desktop, удалите Power BI Desktop, а затем установите версию Power BI Desktop, соответствующую вашей установке Office. 

1. Чтобы выбрать версию Power BI Desktop, на странице скачивания выберите **Дополнительные параметры скачивания**.
   
   ![Дополнительные параметры скачивания Power BI Desktop](media/desktop-access-database-errors/desktop-access-errors-1.png)
   
1. На странице скачивания выберите язык, а затем нажмите кнопку **Скачать** . 
 
1. На появившемся экране установите флажок рядом с элементом PBIDesktop.msi для 32-разрядной версии или рядом с элементом PBIDesktop_x64.msi для 64-разрядной версии. 

   На следующем экране выбрана 64-разрядная версия.
   
   ![Выберите тип скачивания Power BI Desktop](media/desktop-access-database-errors/desktop-access-errors-2.png)
   
   >[!NOTE]
   >При создании очень больших моделей данных в 32-разрядной версии Power BI Desktop могут возникнуть проблемы нехватки памяти.

### <a name="solution-2"></a>Решение 2

Измените версию Microsoft Office, чтобы она совпадала по разрядности с установкой Power BI Desktop.

1. Удаление Microsoft Office

2. Установите версию Office, соответствующую установке Power BI Desktop.

### <a name="solution-3"></a>Решение 3

Если ошибка возникла при попытке открыть XLS-файл (книгу Excel 97–2003), можно не использовать ядро СУБД Access, открыв XLS-файл в Excel и сохранив его как XLSX-файл.

### <a name="solution-4"></a>Решение 4

Если три предыдущих решения вам не подходят, можно установить обе версии ядра СУБД Access. Однако это решение не рекомендуется. Хотя установка обеих версий позволит решить эту проблему для Power Query для Excel и Power BI Desktop, она вызовет проблемы и ошибки для любого приложения, которое автоматически (по умолчанию) использует ту версию ядра СУБД Access, которая была установлена первой. 

Чтобы установить обе версии ядра СУБД Access, выполните следующие действия.

1. Установите обе версии ядра СУБД Access со [страницы скачивания](https://www.microsoft.com/download/details.aspx?id=13255). 

1. Запускайте обе версии ядра СУБД доступа с указанием параметра */passive*. Например:
   
       c:\users\joe\downloads\AccessDatabaseEngine.exe /passive
   
       c:\users\joe\downloads\AccessDatabaseEngine_x64.exe /passive

## <a name="situation-3-trouble-using-access-or-xls-files-with-an-office-365-subscription"></a>Ситуация 3. Проблемы при использовании файлов Access или XLS с подпиской на Office 365

Если используется подписка на Office 365 (**Office 2013** или **Office 2016**), поставщик ядра СУБД Access регистрируется в расположении виртуального реестра с доступом *только* к процессам Microsoft Office. В результате подсистема гибридного веб-приложения (отвечает за запуск отличных от Office 365 Excel и Power BI Desktop решений и не является процессом Office) не может использовать поставщик ядра СУБД Access.

Чтобы исправить эту ситуацию, можно [скачать и установить распространяемый пакет ядра СУБД Access](https://www.microsoft.com/download/details.aspx?id=13255), который соответствует разрядности версии установки Power BI Desktop. См. дополнительные сведения о разрядности версий в предыдущих разделах.

## <a name="other-situations-that-can-cause-import-issues"></a>Другие ситуации, которые могут вызвать проблемы с импортом

Мы стараемся описать как можно больше проблем, связанных с использованием файлов XLS или Access. Если у вас возникли проблемы, описания которых нет в этой статье, отправьте свой вопрос в [службу поддержки Power BI](https://powerbi.microsoft.com/support/). Мы регулярно просматриваем описание проблем, которые возникают у многих наших клиентов, и включаем их в наши статьи.

