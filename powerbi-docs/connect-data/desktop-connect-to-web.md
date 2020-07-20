---
title: Подключение к веб-странице из Power BI Desktop
description: Простое и удобное подключение к данным на веб-страницах из приложения Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 618e2acb415d72870fd599142775720955e8ba88
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2020
ms.locfileid: "86214706"
---
# <a name="connect-to-webpages-from-power-bi-desktop"></a>Подключение к веб-странице из Power BI Desktop

Вы можете подключиться к веб-странице и импортировать информацию с нее в приложение Power BI Desktop, а затем использовать ее в визуальных элементах и моделях данных.

В Power BI Desktop выберите **Получение данных > Интернет** на ленте **Главная**.

![Снимок экрана: Power BI Desktop с выбранным элементом "Интернет"](media/desktop-connect-to-web/connect-to-web_1.png)

Откроется диалоговое окно для ввода URL-адреса веб-страницы, с которой нужно импортировать данные.

![Снимок экрана: диалоговое окно "Интернет" с полем URL-адреса](media/desktop-connect-to-web/connect-to-web_2.png)

Введите или вставьте URL-адрес и нажмите кнопку **ОК**. Power BI Desktop подключится к этой странице и выведет содержащиеся на ней данные в окне **навигатора**. Если вы выберете один из доступных на ней элементов (например, таблицу или всю страницу), в правой части окна **навигатора** появятся в режиме предварительного просмотра соответствующие данные.

![Снимок экрана: диалоговое окно "Навигатор" с предварительным просмотром данных выбранной таблицы](media/desktop-connect-to-web/connect-to-web_3.png)

Вы можете нажать кнопку **Изменить**, чтобы запустить **редактор запросов**, позволяющий отформатировать и преобразовать данные с веб-страницы, прежде чем импортировать их в Power BI Desktop. Если нажать кнопку **Загрузить**, все элементы данных, выбранные в левой области, будут импортированы в приложение.

При нажатии кнопки **Load** Power BI Desktop импортирует выбранные элементы и добавляет их в область **Поля** в правой части представления отчетов в Power BI Desktop.

![Снимок экрана: панель "Поля" со списком выбранных таблиц](media/desktop-connect-to-web/connect-to-web_4.png)

На этом процедура подключения к веб-странице и переноса данных с нее в Power BI Desktop завершена.

После этого вы сможете перетаскивать поля на холст ответа и создавать элементы визуализации. Вы также можете использовать данные на веб-странице, как и любые другие сведения: менять их формат, создавать связи между ними и другими источниками модели, а также выполнять любые другие действия для создания отчетов Power BI.

Более подробно подключение к веб-страницам рассматривается в [руководстве по началу работы с Power BI Desktop](../fundamentals/desktop-getting-started.md).

## <a name="next-steps"></a>Дальнейшие действия
В Power BI Desktop можно подключаться к данным самых разных видов. Дополнительные сведения об источниках данных см. в перечисленных ниже статьях.

* [Источники данных в Power BI Desktop](desktop-data-sources.md)
* [Формирование и объединение данных в Power BI Desktop](desktop-shape-and-combine-data.md)
* [Подключение к данным Excel в Power BI Desktop](desktop-connect-excel.md)   
* [Подключение к CSV-файлам в Power BI Desktop](desktop-connect-csv.md)   
* [Ввод данных непосредственно в Power BI Desktop](desktop-enter-data-directly-into-desktop.md)   
