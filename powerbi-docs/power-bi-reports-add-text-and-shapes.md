---
title: Текстовые поля и фигуры в отчетах Power BI
description: Документация о добавлении и создании текстовых полей и фигур в отчетах Microsoft Power BI.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: _3q6VEBhGew
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 03/22/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 7a002bb99cb80d805298d29916d4eb56f692b479
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34310298"
---
# <a name="static-content-in-power-bi-reports"></a>Статическое содержимое в отчетах Power BI
Текстовые поля и фигуры можно добавлять в отчеты как с помощью службы Power BI, так и Power BI Desktop. В обоих случаях требуются разрешения на изменение отчета. Если доступ к отчету в службе Power BI вам предоставил другой пользователь, у вас не будет прав на редактирование. 

Посмотрите видео о том, как с помощью Power BI Desktop [добавить статические изображения в отчет](guided-learning/visualizations.yml?tutorial-step=11). Затем сделайте это самостоятельно только уже в службе Power BI, следуя приведенным ниже инструкциям.
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/_3q6VEBhGew" frameborder="0" allowfullscreen></iframe>
> 

## <a name="add-a-text-box-to-a-report"></a>Добавление текстового поля в отчет
1. Откройте отчет в режиме редактирования.

2. Поместите курсор в любом пустом месте холста отчета и выберите **Текстовое поле**.
   
   ![](media/power-bi-reports-add-text-and-shapes/pbi_textbox.png)
2. Введите текст в текстовое поле и, по желанию, выберите шрифт, цвет и выравнивание текста. 
   
   ![](media/power-bi-reports-add-text-and-shapes/pbi_textbox2new.png)
3. Чтобы изменить расположение текстового поля, выберите серую область вверху и перетащите поле. Чтобы изменить размер текстового поля, выберите и перетащите один из маркеров. 
   
   ![](media/power-bi-reports-add-text-and-shapes/textboxsmaller.gif)

4. Выбрав текстовое поле, добавьте параметры форматирования на панели "Визуализации". В этом примере мы отформатировали фон и границы. Можно также создать точный размер и положение для текстового поля.  

   ![](media/power-bi-reports-add-text-and-shapes/power-bi-borders.png)

5. Чтобы закрыть текстовое поле, выберите любое пустое место на холсте отчета. 

5. Выберите значок булавки ![](media/power-bi-reports-add-text-and-shapes/pbi_pintile.png), чтобы закрепить текстовое поле на панели мониторинга. 

## <a name="add-a-shape-to-a-report"></a>Добавление фигуры в отчет
1. Поместите курсор в любом месте холста отчета и выберите **Фигуры**.
   
   ![](media/power-bi-reports-add-text-and-shapes/power-bi-shapes.png)
2. В раскрывающемся списке выберите фигуру, чтобы добавить ее на холст отчета. Давайте добавим стрелку, чтобы направить внимание на пузырек с наибольшим суммарным отклонением продаж. 
   
   В области **Формат фигуры** настройте фигуру. В этом примере мы создали красную стрелку с темной красной границей, повернутую на 90 градусов.
   
   ![](media/power-bi-reports-add-text-and-shapes/power-bi-arrrow.png)
3. Чтобы изменить расположение фигуры, выберите серую область вверху и перетащите фигуру. Чтобы изменить размер фигуры, выберите и перетащите один из маркеров. Как и для текстового поля, для фигуры можно также создать точный размер и положение.

> **Примечание**. Фигуры невозможно закрепить на панели мониторинга, только если это не один из визуальных элементов на [закрепляемой динамической странице](service-dashboard-pin-live-tile-from-report.md). 
> 
> 

### <a name="next-steps"></a>Дальнейшие действия
[Добавление гиперссылки в текстовое поле](service-add-hyperlink-to-text-box.md)

[Power BI — основные понятия](service-basic-concepts.md)

Появились дополнительные вопросы? [Ответы на них см. в сообществе Power BI.](http://community.powerbi.com/)
