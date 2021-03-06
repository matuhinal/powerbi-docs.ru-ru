---
title: Тестирование отправки визуального элемента Power BI
description: В этой статье описываются тестовые случаи, которые должен пройти визуальный элемент перед публикацией в AppSource. Кроме того, существуют проверочные варианты.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 04/15/2020
ms.openlocfilehash: 65e00fa5311ea12c9fe0011c6aa7c3e779f33dc5
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83131113"
---
# <a name="submission-testing-of-a-power-bi-visual"></a>Тестирование отправки визуального элемента Power BI

Перед публикацией визуального элемента в [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) он должен пройти эти тестовые случаи. Протестируйте визуальный элемент перед его отправкой. Если визуальный элемент не проходит требуемые тестовые случаи, он будет отклонен.

Дополнительные сведения о процессе публикации см. на странице [Публикация визуализаций Power BI в Центре партнеров](./office-store.md).

## <a name="general-test-cases"></a>Общие тестовые случаи

| Тестовый случай | Ожидаемые результаты
| --------- | ----------------
| Создайте **гистограмму с накоплением** с **категорией** и **значением**. Преобразуйте ее в визуальный элемент, а затем обратно в гистограмму. | После этих преобразований ошибка не возникает. |
| Создайте **Шкалу** с тремя единицами измерения. Преобразуйте ее в визуальный элемент, а затем вернитесь в **шкалу**. | После этих преобразований ошибка не возникает. |
| Сделайте выбор в визуальном элементе. | Другие визуальные элементы соответствуют выбранным параметрам. |
| Выберите элементы в других визуальных элементах. | Визуальный элемент отображает отфильтрованные данные в соответствии с выбором в других визуальных элементах. |
| Проверьте минимальные и максимальные условия **dataViewMapping**. | Контейнеры полей могут принимать несколько полей, одно поле или определяться другими контейнерами. Необходимо правильно настроить максимальные и минимальные условия **dataViewMapping** в возможностях визуального элемента. |
| Удалите все поля в разных порядках. | Очистка визуальных элементов выполняется правильно, так как поля удаляются в произвольном порядке. Ошибки в консоли или в браузере отсутствуют. |
| Откройте панель **Формат** с каждой возможной конфигурацией контейнера. | Этот тест не активирует исключения с пустыми ссылками. |
| Отфильтруйте данные с помощью панели **Фильтр** на уровне визуального элемента, страницы и отчета. | Подсказки отображаются правильно после применения фильтров. В подсказках отображается отфильтрованное значение. |
| Отфильтруйте данные с помощью **среза**. | Подсказки отображаются правильно после применения фильтров. В подсказках отображается отфильтрованное значение. |
| Отфильтруйте данные с помощью опубликованного визуального элемента. Например, выберите сектор круговой диаграммы или столбец. | Подсказки отображаются правильно после применения фильтров. В подсказках отображается отфильтрованное значение. |
| Если перекрестная фильтрация поддерживается, проверьте правильность работы фильтров. | Примененный выбор фильтрует другие визуальные элементы на этой странице отчета. |
| Выберите элементы с помощью клавиш CTRL, ALT и SHIFT. | Непредвиденное поведение не отображается. |
| Задайте для параметра **Режим просмотра** значение **Фактический размер**, **По размеру страницы** или **По ширине**. | Координаты мыши являются точными. |
| Измените размер визуального элемента. | Визуальный элемент реагирует правильно на изменение размера. |
| Установите минимальный размер отчета. | Нет ошибок вывода. |
| Убедитесь, что полосы прокрутки работают правильно. | При необходимости должны существовать полосы прокрутки. Проверьте размеры полосы прокрутки. Полосы прокрутки не должны быть слишком широкими или длинными. Расположение и размер полос прокрутки должны соответствовать другим элементам визуального элемента. Убедитесь, что полосы прокрутки нужны для различных размеров визуального элемента. |
| Закрепите визуальный элемент на **панели мониторинга**. | Визуальный элемент должен отображаться правильно. |
| Добавьте несколько версий визуального элемента на одну страницу отчета. | Все версии визуального элемента отображаются и работают должным образом. |
| Добавьте несколько версий визуального элемента на несколько страниц отчета. | Все версии визуального элемента отображаются и работают должным образом. |
| Выполните переключение между страницами отчета. | Визуальный элемент отображается правильно. |
| Проверьте режим чтения и редактирования визуального элемента. | Все функции работают правильно. |
| Если в визуальном элементе используется анимация, добавьте, измените и удалите элементы визуального элемента. | Анимация визуальных элементов работает правильно. |
| Откройте панель **Свойство**. Включите и выключите свойства, введите пользовательский текст, выделите доступные параметры и введите неверные данные. | Визуальный элемент реагирует правильно. |
| Сохраните отчет и снова откройте его. | Все параметры свойств сохраняются. |
| Переключите страницы в отчете и восстановите прежние параметры. | Все параметры свойств сохраняются. |
| Протестируйте все функциональные возможности визуального элемента, в том числе различные параметры, предоставляемые визуальным элементом. | Все экраны и функции работают правильно. |
| Протестируйте все числовые типы данных, даты и символьные типы данных, как в следующих тестах. | Все данные отформатированы должным образом. |
| Просмотрите форматирование значений всплывающих подсказок, меток осей, меток данных и других визуальных элементов с форматированием. | Все элементы имеют правильный формат. |
| Убедитесь, что в метках данных используется строка формата. | Все метки данных имеют правильный формат. |
| Включите и выключите автоматическое форматирование числовых значений во всплывающих подсказках. | Значения в подсказках отображаются правильно. |
| Протестируйте записи данных с различными типами данных, включая числовые, текстовые, типы данных даты/времени и строки различных форматов из модели. Протестируйте различные тома данных, например тысячи строк, одну или две строки. | Все экраны и функции работают правильно. |
| Укажите для визуального элемента неправильные данные, например нулевые, бесконечные, отрицательные и неправильные типы значений. | Все экраны и функции работают правильно. |

## <a name="optional-browser-testing"></a>Необязательное тестирование браузера

Команда AppSource проверяет визуальные элементы в актуальных версиях Windows Google Chrome, Microsoft Edge и Mozilla Firefox.
При необходимости протестируйте визуальный элемент в следующих браузерах.

| Тестовый случай | Ожидаемые результаты
| --------- | ----------------
| **Windows** |
| Google Chrome (предыдущая версия) | Все экраны и функции работают правильно. |
| Mozilla Firefox (предыдущая версия) | Все экраны и функции работают правильно. |
| Microsoft Edge (предыдущая версия) | Все экраны и функции работают правильно. |
| Microsoft Internet Explorer 11 (необязательно) | Все экраны и функции работают правильно. |
| **macOS** |
| Chrome (предыдущая версия) | Все экраны и функции работают правильно. |
| Firefox (предыдущая версия) | Все экраны и функции работают правильно. |
| Safari (предыдущая версия) | Все экраны и функции работают правильно. |
| **Linux** |
| Firefox (последняя и предыдущая версии) | Все экраны и функции работают правильно. |
| **Мобильное приложение (iOS)** |
| Apple Safari iPad (предыдущая версия Safari) | Все экраны и функции работают правильно. |
| Chrome iPad (последняя версия Safari) | Все экраны и функции работают правильно. |
| **Мобильное приложение (Android)** |
| Chrome (последняя и предыдущая версии) | Все экраны и функции работают правильно. |

## <a name="desktop-testing"></a>Тестирование классических приложений

Протестируйте визуальный элемент в текущей версии [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/).

| Тестовый случай | Ожидаемые результаты
| --------- | ----------------
| Протестируйте все функции визуального элемента. | Все экраны и функции работают правильно. |
| Импортируйте, сохраните, откройте файл и опубликуйте его в веб-службе Power BI с помощью кнопки **Опубликовать** в Power BI Desktop. | Все экраны и функции работают правильно. |
| Измените строку числового формата так, чтобы она содержала три десятичных знака или не содержала ни одного, увеличивая или уменьшая точность. | Визуальный элемент отображается правильно. |

## <a name="performance-testing"></a>Тестирование производительности

Визуальный элемент должен выполняться на приемлемом уровне. Используйте средства разработчика для проверки производительности. Не полагайтесь на визуальные подсказки и журналы консоли.

| Тестовый случай | Ожидаемые результаты
| --------- | ----------------
| Создайте визуальный элемент с большим количеством визуальных элементов. | Визуальный элемент должен хорошо функционировать, не вызывая зависания приложения. В производительности таких элементов как скорость анимации, изменение размера, фильтрация и выбор, не должно возникать проблем.

## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения о процессе публикации см. на странице [Публикация визуализаций Power BI в Центре партнеров](./office-store.md).

Появились дополнительные вопросы? [Спросить в сообществе Power BI](https://community.powerbi.com/)
