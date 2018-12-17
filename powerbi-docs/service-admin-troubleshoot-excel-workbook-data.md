---
title: Ошибка Не удалось найти данные в этой книге Excel
description: Ошибка Не удалось найти данные в этой книге Excel
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: ea5312178d33986ebc3f4b9e8610012c87d54216
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "53026038"
---
# <a name="error-we-couldnt-find-any-data-in-your-excel-workbook"></a>Ошибка Не удалось найти данные в этой книге Excel

>[!NOTE]
>Эта статья относится к Excel 2007 и более поздних версий.

При импорте книги Excel в Power BI может появиться следующая ошибка:

*Ошибка Не удалось найти данные в этой книге Excel. Возможно, данные имеют неправильный формат. Необходимо отредактировать книгу в Excel, а затем повторить импорт.*

![Не удалось найти данные в книге](media/service-admin-troubleshoot-excel-workbook-data/pbi_wecouldntfindanydata.png)

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
    
    ![Открытая книга](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht1.png)
2. Выделите диапазон ячеек, содержащих данные. Первая строка должна содержать заголовки столбцов (имена столбцов):
   
    ![Выделение диапазона ячеек](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht2.png)
3. На вкладке **Вставка** ленты щелкните элемент **Таблица**. (Или используйте сочетание клавиш **CTRL + T**.)
   
    ![Вставка таблицы](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht3.png)
4. Вы увидите следующее диалоговое окно. Убедитесь, что флажок **Таблица с заголовками** установлен, и нажмите кнопку **ОК**:
   
    ![Создание таблицы](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlcreatetbl.png)
5. Теперь данные форматируются в виде таблицы:
   
    ![Форматирование данных в виде таблицы](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xltbl.png)
6. Сохраните книгу.
7. Вернитесь в Power BI. Выберите "Получить данные" в нижней части левой панели навигации.
   
    ![Получение данных](media/service-admin-troubleshoot-excel-workbook-data/pbi_getdata.png)
8. В поле **Файлы** выберите **Получить**.
   
    ![Получение файлов](media/service-admin-troubleshoot-excel-workbook-data/pbi_getfiles.png)
9. Повторите импорт книги Excel. На этот раз импорт должен найти таблицу и выполниться успешно.
   
    Если импорт по-прежнему не удается, свяжитесь с нами, выбрав в меню "Справка" пункт **Сообщество**:
   
    ![Ссылка "Сообщество"](media/service-admin-troubleshoot-excel-workbook-data/pbi_questionmenucommunity.png)
