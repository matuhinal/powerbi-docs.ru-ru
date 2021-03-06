---
title: Мониторинг емкостей Power BI Premium с помощью портала администрирования
description: Используйте портал администрирования Power BI для мониторинга емкостей Premium.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-premium
ms.topic: how-to
ms.date: 05/11/2020
LocalizationGroup: Premium
ms.openlocfilehash: 3948cca3a7e274c22ac1ea5cc80773edd0d5e451
ms.sourcegitcommit: 51b965954377884bef7af16ef3031bf10323845f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2020
ms.locfileid: "91599788"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>Мониторинг емкостей на портале администрирования

Вкладка **Работоспособность** в области **Параметры емкости** на портале администрирования содержит сводку метрик о емкости и включенных рабочих нагрузках.  

![Вкладка "Работоспособность емкости" на портале](media/service-admin-premium-monitor-portal/admin-portal-health.png)

Если вам нужны более полные метрики, используйте [Метрики емкости Power BI Premium](service-admin-premium-monitor-capacity.md). Приложение обеспечивает детализацию и фильтрацию, а также наиболее детализированные метрики практически для всех аспектов, влияющих на производительность емкости. Дополнительные сведения см. в разделе [Мониторинг емкостей Premium в приложении](service-admin-premium-monitor-capacity.md).

> [!IMPORTANT]
> Если емкость Power BI Premium подвергается большой нагрузке, из-за которой могут возникать проблемы с производительностью или надежностью, вы можете получать по электронной почте уведомления, чтобы устранять эти проблемы. Это может упростить устранение неполадок, связанных с перегрузкой емкостей. Дополнительные сведения см. в статье [Уведомления о емкости и надежности](service-interruption-notifications.md#capacity-and-reliability-notifications).


## <a name="system-metrics"></a>Метрики системы

На вкладке **Работоспособность** на высшем уровне, загрузка ЦП и использование памяти позволяют быстро просмотреть наиболее важные метрики для емкости. Эти метрики представляют совокупное число, включая все включенные рабочие нагрузки для емкости.

| **Метрика** | **Описание** |
| --- | --- |
| ЗАГРУЗКА ЦП | Средняя загрузка ЦП в процентах от общего доступного ЦП. |
| ИСПОЛЬЗОВАНИЕ ПАМЯТИ | Среднее использование памяти в гигабайтах (ГБ).|

## <a name="workload-metrics"></a>Метрики рабочей нагрузки

Для каждой рабочей нагрузки, включенной для этой емкости. Отображаются сведения об использовании ЦП и памяти.

| **Метрика** | **Описание** |
| --- | --- |
| ЗАГРУЗКА ЦП | Средняя загрузка ЦП в процентах от общего доступного ЦП. |
| ИСПОЛЬЗОВАНИЕ ПАМЯТИ | Среднее использование памяти в гигабайтах (ГБ).|

### <a name="detailed-workload-metrics"></a>Подробные метрики рабочей нагрузки

Каждая рабочая нагрузка имеет дополнительные метрики. Тип отображаемых метрик зависит от рабочей нагрузки. Чтобы просмотреть подробные метрики рабочей нагрузки, щелкните стрелку раскрытия (вниз).

![Развертывание работоспособности рабочей нагрузки](media/service-admin-premium-monitor-portal/admin-portal-health-expand.png)

#### <a name="dataflows"></a>Потоки данных

##### <a name="dataflow-operations"></a>Операции потока данных

| **Метрика** | **Описание** |
| --- | --- |
| Общее число | количество обновлений для каждого потока данных. |
| Число успехов | Общее число успешных обновлений для каждого потока данных.|
| Средняя длительность (мин) | средняя длительность обновления для потока данных (в минутах) |
| Максимальная длительность (мин) | максимальное время обновления для потока данных в минутах. |
| Среднее время ожидания (мин) | средняя задержка между запланированным временем и фактическим началом обновления потока данных в минутах. |
| Максимальное время ожидания (мин) | максимальное время ожидания для потока данных в минутах.  |

#### <a name="datasets"></a>Наборы данных

##### <a name="refresh"></a>Обновить

| **Метрика** | **Описание** |
| --- | --- |
| Общее число | общее количество обновлений для каждого набора данных. |
| Число успехов | Общее число успешных обновлений для каждого набора данных. |
| Число сбоев | Общее число неудачных обновлений для каждого набора данных. |
| Частота успешных выполнений  | Количество успешных обновлений, разделенное на общее количество обновлений для измерения. надежности. |
| Средняя длительность (мин) | средняя длительность обновления для набора данных в минутах.  |
| Максимальная длительность (мин) | максимальная длительность обновления для набора данных в минутах. |
| Среднее время ожидания (мин) | средняя задержка между запланированным временем и фактическим началом обновления набора данных в минутах. |
| Максимальное время ожидания (мин) | максимальное время ожидания для набора данных в минутах. |

##### <a name="query"></a>Запрос

| **Метрика** | **Описание** |
| --- | --- |
| Общее число | общее количество запросов, выполненных для набора данных. |
| Средняя длительность (мс) |средняя продолжительность запросов для набора данных (в миллисекундах)|
| Максимальная длительность (мс) |максимальная длительность запроса, выполненного для набора данных в миллисекундах. |
| Среднее время ожидания (мс) |средняя продолжительность ожидания запросов для набора данных в миллисекундах. |
| Максимальное время ожидания (мс) |длительность максимального ожидания запроса для набора данных в миллисекундах. |

##### <a name="eviction"></a>вытеснение

| **Метрика** | **Описание** |
| --- | --- |
| Количество моделей | Общее количество вытеснений наборов данных для этой емкости. При нехватке памяти узел вытесняет один или несколько наборов данных из памяти. Наборы данных в неактивном состоянии (для которых не выполняются запросы или обновление) вытесняются в первую очередь. Для них применяется порядок "недавно использовавшиеся" (LRU). |

#### <a name="paginated-reports"></a>Отчеты с разбивкой на страницы

##### <a name="report-execution"></a>Выполнение отчета

| **Метрика** | **Описание** |
| --- | --- |
| Счетчик выполнения  | Количество просмотров и выполнений отчета пользователями.|

##### <a name="report-usage"></a>Использование отчета

| **Метрика** | **Описание** |
| --- | --- |
| Число успехов | количество просмотров отчета пользователем. |
| Число сбоев |количество просмотров отчета пользователем.|
| Число строк |количество строк данных в отчете. |
| Длительность получения данных (мс) |средняя продолжительность получения данных для отчета (в миллисекундах). Высокая продолжительность может указывать на плохую оптимизацию запросов или другие проблемы с источником данных.  |
| Длительность обработки (мс) |средняя продолжительность обработки данных для отчета в миллисекундах. |
| Длительность отрисовки (мс) |средняя продолжительность отображения отчета в окне браузера в миллисекундах. |

> [!NOTE]
> Подробные метрики для рабочей нагрузки **AI** пока недоступны.

## <a name="next-steps"></a>Дальнейшие действия

Теперь, когда вы понимаете, как выполнять мониторинг емкостей Power BI Premium, узнайте больше об их оптимизации.

> [!div class="nextstepaction"]
> [Оптимизация емкостей Power BI Premium](service-premium-capacity-optimize.md)
