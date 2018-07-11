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
ms.openlocfilehash: 2547be7f7bdadb7f991db54230d4fd791941838d
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2018
ms.locfileid: "37600074"
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

5. Отправьте в службу Power BI файл Power BI Desktop с запросами, в которых сочетаются локальные и облачные источники данных.

6. На странице **Настройки набора данных** для нового набора данных выполните указанные ниже действия.

   - Для локального источника выберите шлюз, связанный с этим источником данных.

   - В разделе **Учетные данные источника данных** при необходимости измените учетные данные облачного источника данных.

     ![Параметры набора данных](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

7. Задав учетные данные облачного источника, можно обновить набор данных с помощью команды **Обновить** или запланировать периодическое обновление.


## <a name="next-steps"></a>Дальнейшие действия

Дополнительные сведения об обновлении данных для шлюзов см. в статье [Использование источника данных для запланированного обновления](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh).