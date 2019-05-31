---
title: Виртуальный аналитик "Вопросы и ответы" в приложениях iOS (Power BI)
description: Вы можете задать вопросы о тестовых данных в свободной текстовой форме с помощью виртуального аналитика "Вопросы и ответы" в мобильном приложении Power BI на устройстве iOS.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 05/05/2018
ms.author: mshenhav
ms.openlocfilehash: 0517299240137bf63ace8aca6a1da577a4443d2d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2019
ms.locfileid: "60977478"
---
# <a name="qa-virtual-analyst-in-ios-apps---power-bi"></a>Виртуальный аналитик "Вопросы и ответы" в приложениях iOS (Power BI)

Чтобы получить ответ на вопрос о своих данных, задайте его своими словами. При изучении этой статьи вы будете задавать вопросы и просматривать аналитические сведения о тестовых данных в виртуальном аналитике "Вопросы и ответы", который доступен в мобильном приложении Microsoft Power BI на iPad, iPhone и iPod Touch. 

Область применения:

| ![iPhone](./media/mobile-apps-ios-qna/iphone-logo-50-px.png) | ![iPad](./media/mobile-apps-ios-qna/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhone |iPad |

Виртуальный аналитик "Вопросы и ответы" — это диалоговый интерфейс бизнес-аналитики, который обращается к базовым данным функции "Вопросы и ответы" в службе Power BI [(https://powerbi.com)](https://powerbi.com). Он предлагает аналитические сведения, а также может отвечать на вопросы, которые вы вводите или произносите.

![Виртуальный аналитик "Вопросы и ответы": данные по основным продажам](./media/mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-intro.png)

Если вы не зарегистрированы в Power BI, перед началом работы [пройдите бесплатную регистрацию](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="prerequisites"></a>Предварительные требования

### <a name="install-the-power-bi-for-ios-app"></a>Установка приложения Power BI для iOS
[Скачайте приложение для iOS](http://go.microsoft.com/fwlink/?LinkId=522062 "Скачайте приложение для iPhone") из Apple App Store на устройство iPad, iPhone или iPod Touch.

Приложение Power BI для iOS поддерживается в следующих версиях ОС:
- iPad под управлением iOS 10 или более поздней версии;
- iPhone 5 и более поздней версии под управлением iOS 10 или выше; 
- iPod Touch под управлением iOS 10 или более поздней версии.

### <a name="download-samples"></a>Скачать образцы
Первым делом вам нужно скачать примеры "Анализ розничной торговли" и "Анализ возможных сделок" из службы Power BI.

**Получение примера "Анализ розничной торговли"**

1. Откройте службу Power BI (app.powerbi.com) и войдите в нее.

2. На панели навигации слева выберите **Рабочие области**, а затем щелкните **Моя рабочая область**.

3. В левом нижнем углу выберите **Получить данные**.
   
    ![](media/mobile-apps-ios-qna/power-bi-get-data.png)

3. На странице "Получение данных" щелкните значок **Примеры**.
   
   ![](media/mobile-apps-ios-qna/power-bi-samples-icon.png)

4. Выберите пример **Анализ розничной торговли**.
 
    ![Анализ розничной торговли — пример](./media/mobile-apps-ios-qna/power-bi-rs.png)
 
8. Нажмите кнопку **Подключиться**.  
  
   ![Анализ розничной торговли — пример](./media/mobile-apps-ios-qna/retail16.png)
   
5. Power BI импортирует пакет содержимого и добавляет новую информационную панель, отчет и набор данных в текущую рабочую область.
   
   ![Анализ розничной торговли — пример](./media/mobile-apps-ios-qna/power-bi-service-retail-sample.png)

**Получение примера "Анализ возможных сделок"** .

- Выполните те же действия, что описаны выше для анализа розничной торговли, но на шаге 4 выберите пример **Анализ возможных сделок**.

    ![Анализ розничной торговли — пример](./media/mobile-apps-ios-qna/power-bi-oa.png)
  
Теперь все готово для просмотра примеров на устройстве iOS.

## <a name="try-asking-questions-on-your-iphone-or-ipad"></a>Отправка вопросов на устройствах iPhone и iPad
1. На устройстве iPhone или iPad коснитесь кнопки глобальной навигации ![Кнопка глобальной навигации](./media/mobile-apps-ios-qna/power-bi-iphone-global-nav-button.png) > **Рабочие области** > **Моя рабочая область** и откройте панель мониторинга из примера "Анализ розничной торговли".

2. Коснитесь значка виртуального аналитика "Вопросы и ответы" ![Значок виртуального аналитика "Вопросы и ответы"](././media/mobile-apps-ios-qna/power-bi-ios-q-n-a-icon.png) в меню действий в нижней части страницы (на iPad — в верхней части страницы).
     Виртуальный аналитик "Вопросы и ответы" предоставляет ряд предложений для начала работы.
3. Введите **show**, в списке предложений выберите **sales** (продажи) и нажмите кнопку **Send** (Отправить) ![значок отправки](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png).

    ![Показать продажи](./media/mobile-apps-ios-qna/power-bi-ios-q-n-a-show-sales.png)
4. Выберите **by** из ключевых слов, затем щелкните **item** (элемент) в списке предложений и нажмите кнопку **Send** (Отправить) ![](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png).

    ![Продажи по элементам](./media/mobile-apps-ios-qna/power-bi-ios-q-n-a-sale-by-item.png)
5. Выберите **as** (как) из ключевых слов, затем щелкните значок гистограммы ![](./media/mobile-apps-ios-qna/power-bi-ios-q-n-a-column-chart-icon.png) и нажмите кнопку **Send** (Отправить) ![](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png).
6. Нажмите и удерживайте полученную гистограмму, а затем нажмите кнопку **Expand** (Развернуть).

    ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-tap-expand-feedback.png)

    Гистограмма откроется в приложении в режиме фокусировки.

    ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-expanded-chart.png)
7. Нажмите кнопку со стрелкой в верхнем левом углу, чтобы вернуться в окно чата виртуального аналитика "Вопросы и ответы".
8. Нажмите кнопку X справа от текстового поля, чтобы удалить текст и начать заново.
9. Попробуйте отправить новый вопрос. Выберите **top** из ключевых слов, затем выберите **sale by avg $/unit ly** > **Send** (Отправить) ![](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png).

    ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-2.png)
10. Выберите **by** (по) из ключевых слов, затем выберите **time** (время) из списка предложений в верхней части и нажмите кнопку **Send** (Отправить) ![](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png).

     ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-by-time.png)
11. Введите **as** (как), выберите значок графика ![](./media/mobile-apps-ios-qna/power-bi-ios-q-n-a-line-chart-icon.png) из списка предложений и нажмите кнопку **Send** (Отправить) ![](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png).

    ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-as-line.png)

## <a name="try-saying-your-questions"></a>Попробуйте задать вопрос с помощью голосового ввода
Теперь вы можете задавать вопросы о данных в мобильном приложении Power BI не только с помощью текста, но и речи.

1. Коснитесь значка виртуального аналитика "Вопросы и ответы" ![Значок виртуального аналитика "Вопросы и ответы"](././media/mobile-apps-ios-qna/power-bi-ios-q-n-a-icon.png) в меню действий в нижней части страницы (на iPad — в верхней части страницы).
2. Коснитесь значка микрофона ![](media/mobile-apps-ios-qna/power-bi-ios-qna-mic-icon.png).

    ![](media/mobile-apps-ios-qna/power-bi-ios-qna-mic-on.png)

1. Когда значок микрофона станет активным, начните говорить. Например, скажите "средняя цена за единицу по времени", а затем коснитесь **Отправить** ![](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png).

    ![](media/mobile-apps-ios-qna/power-bi-ios-qna-speech-complete.png)

### <a name="questions-about-privacy-when-using-speech-to-text"></a>Вопросы о конфиденциальности при использовании голосового ввода
См. раздел с описанием [новых возможностей iOS](https://go.microsoft.com/fwlink/?linkid=845624), посвященный распознаванию речи, в руководстве для разработчиков Apple iOS.

## <a name="help-and-feedback"></a>Справка и отзывы
* Требуется помощь? Введите слово Hi (Привет) или Help (Справка), и вы получите помощь и сможете задать новый вопрос.
* Хотите поделиться своим мнением о результатах? Щелкните и удерживайте диаграмму или другой результат, а затем коснитесь значка в виде улыбающегося или хмурого лица.

    ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-tap-feedback.png)

    Ваши отзывы анонимны. Они помогают нам лучше отвечать на ваши вопросы.

## <a name="enhance-your-qa-virtual-analyst-results"></a>Улучшение результатов, полученных с помощью виртуального аналитика "Вопросы и ответы"
Вы можете улучшить результаты, которые получаете вы или ваши клиенты при использовании виртуального аналитика "Вопросы и ответы" с набором данных. Для этого нужно задать более точный вопрос или усовершенствовать набор данных.

### <a name="how-to-ask-questions"></a>Как задавать вопросы
* Следуйте этим [рекомендациям по отправке вопросов с помощью функции "Вопросы и ответы"](../end-user-q-and-a-tips.md) в службе Power BI или виртуального аналитика "Вопросы и ответы" в мобильном приложении iOS.

### <a name="how-to-enhance-the-dataset"></a>Как улучшить набор данных
* Усовершенствуйте набор данных в Power BI Desktop или в службе Power BI, чтобы [ваши данные правильно работали с функцией "Вопросы и ответы" и виртуальным аналитиком "Вопросы и ответы"](../../service-prepare-data-for-q-and-a.md).

## <a name="next-steps"></a>Дальнейшие действия
* [Вопросы и ответы в Power BI](../end-user-q-and-a.md)
* У вас появились вопросы? См. [раздел мобильных приложений в сообществе Power BI](https://go.microsoft.com/fwlink/?linkid=839277)
