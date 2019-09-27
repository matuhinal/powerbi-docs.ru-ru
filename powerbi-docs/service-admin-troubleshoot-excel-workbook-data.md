---
title: Ошибка Не найдены данные в книге Excel
description: Ошибка Не найдены данные в книге Excel
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/30/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 6fb02e6cbaca30859aa00f58ae07c9a3fd7f6fe0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "65101582"
---
# <a name="error-we-couldnt-find-any-data-in-your-excel-workbook"></a>Ошибка Не найдены данные в книге Excel

>[!NOTE]  
>Эта статья относится к Excel 2007 и более поздних версий.

При импорте книги Excel в Power BI может появиться следующая ошибка:

*Ошибка Не удалось найти данные, отформатированные в виде таблицы. Для импорта из Excel в службу Power BI необходимо отформатировать данные в виде таблицы. Выберите все данные, которые нужно добавить в таблицу, и нажмите сочетание клавиш CTRL+T.*

![Не удалось найти данные в книге](media/service-admin-troubleshoot-excel-workbook-data/power-bi-we-couldnt-find-any-data.png)

## <a name="quick-solution"></a>Быстрое решение
1. Отредактируйте книгу в Excel.
2. Выделите диапазон ячеек, содержащих данные. Первая строка должна содержать заголовки столбцов (имена столбцов).
3. Нажмите сочетание клавиш **CTRL + T** , чтобы создать таблицу.
4. Сохраните книгу.
5. Вернитесь в Power BI и повторите импорт книги, если же вы работаете в Excel 2016 и сохранили книгу в OneDrive для бизнеса, в Excel выберите "Файл" > "Опубликовать".

## <a name="details"></a>Сведения
### <a name="cause"></a>Причина
В Excel можно создать **таблицу** вне диапазона ячеек, что упрощает сортировку, фильтрацию и форматирование данных.

При импорте книги Excel Power BI ищет эти таблицы и импортирует их в набор данных; если он не находит какие-либо таблицы, появляется следующее сообщение об ошибке.

### <a name="solution"></a>Решение
1. Откройте книгу в Excel. 
    >[!NOTE]
    >Рисунки приведены для Excel 2013. При использовании другой версии картинка может отличаться, но действия будут теми же самыми.
    
    ![Открытая книга](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-worksheet-1.png)
2. Выделите диапазон ячеек, содержащих данные. Первая строка должна содержать заголовки столбцов (имена столбцов):
   
    ![Выделение диапазона ячеек](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-worksheet-2.png)
3. На вкладке **Вставка** ленты щелкните элемент **Таблица**. (Или используйте сочетание клавиш **CTRL + T**.)
   
    ![Вставка таблицы](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-worksheet-3.png)
4. Вы увидите следующее диалоговое окно. Убедитесь, что флажок **Таблица с заголовками** установлен, и нажмите кнопку **ОК**:
   
    ![Создание таблицы](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-create-table.png)
5. Теперь данные форматируются в виде таблицы:
   
    ![Форматирование данных в виде таблицы](media/service-admin-troubleshoot-excel-workbook-data/power-bi-troubleshoot-excel-table.png)
6. Сохраните книгу.
7. Вернитесь в Power BI. Выберите "Получить данные" в нижней части левой панели навигации.
   
    ![Получить данные](media/service-admin-troubleshoot-excel-workbook-data/power-bi-get-data.png)
8. В поле **Файлы** выберите **Получить**.
   
    ![Получение файлов](media/service-admin-troubleshoot-excel-workbook-data/power-bi-get-files.png)
9. Повторите импорт книги Excel. На этот раз импорт должен найти таблицу и выполниться успешно.
   
    Если импорт по-прежнему не удается, свяжитесь с нами, выбрав в меню "Справка" пункт **Сообщество**:
   
    ![Ссылка "Сообщество"](media/service-admin-troubleshoot-excel-workbook-data/power-bi-question-menu-community.png)
