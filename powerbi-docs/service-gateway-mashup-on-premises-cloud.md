---
title: Объединение и добавление локальных и облачных источников данных
description: Используйте локальный шлюз данных для объединения или добавления локальных и облачных источников данных в одном запросе.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 06/06/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 3550a3fc0cfc51b61e1d7e51a50c2a36325f2388
ms.sourcegitcommit: 49570ab8f5b5cd5bab4cd388f4281b1372bcb80b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2018
ms.locfileid: "35250654"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>Объединение и добавление локальных и облачных источников данных

Локальный шлюз данных позволяет объединять или добавлять локальные и облачные источники данных в одном запросе. Это полезно, если нужно комбинировать данные из нескольких источников, не используя отдельные запросы.

## <a name="prerequisites"></a>Предварительные требования

- [Шлюз, установленный](service-gateway-install.md) на локальном компьютере.
- Файл Power BI Desktop с запросами, в которых сочетаются локальные и облачные источники данных.

1. В службе Power BI в правом верхнем углу экрана щелкните значок шестеренки ![Значок параметров](media/service-gateway-mashup-on-premises-cloud/icon-gear.png) > **Управление шлюзами**.

    ![Управление шлюзами](media/service-gateway-mashup-on-premises-cloud/manage-gateways.png)

2. Выберите шлюз, который нужно настроить.

3. В разделе **Параметры кластера шлюза** выберите **Разрешите облачные источники данных пользователя, чтобы обновлять их через этот кластер шлюза** > **Применить**.

    ![Обновление через этот кластер шлюза](media/service-gateway-mashup-on-premises-cloud/refresh-gateway-cluster.png)

4. В кластере шлюза добавьте [локальные источники данных](service-gateway-enterprise-manage-scheduled-refresh.md#add-a-data-source), используемые в запросах. Добавлять здесь облачные источники данных не требуется.

4. Отправьте в службу Power BI файл Power BI Desktop с запросами, в которых сочетаются локальные и облачные источники данных.

5. На странице **Настройки набора данных** для нового набора данных выполните указанные ниже действия.

    - Для локального источника выберите шлюз, связанный с этим источником данных.

    - В разделе **Учетные данные источника данных** при необходимости измените учетные данные облачного источника данных.

    ![Параметры набора данных](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

6. Задав учетные данные облачного источника, можно обновить набор данных с помощью команды **Обновить** или запланировать периодическое обновление.


## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения об обновлении данных для шлюзов см. в статье [Использование источника данных для запланированного обновления](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh).