---
title: Роли рабочей области Power BI
description: Таблица ролей рабочей области Power BI
services: powerbi
author: maggiesMSFT
ms.service: powerbi
ms.topic: include
ms.date: 04/23/2020
ms.author: maggies
ms.custom: include file
ms.openlocfilehash: 9a6ca5abf3c26af876666ef45fe7ae192e69f2a3
ms.sourcegitcommit: 9ec2c608b90bf651df613f0714addd251a885039
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2020
ms.locfileid: "82120365"
---
Ниже перечислены возможности четырех ролей: администраторов, членов, участников и зрителей. Для использования всех этих возможностей, за исключением просмотра и взаимодействия, требуется лицензия Power BI Pro.

|Возможность   | Администратор  | Участник  | Участник  | Зритель |
|---|---|---|---|---|
| Обновлять и удалять рабочую область.  | X  |   |   |   | 
| Добавлять и удалять пользователей, включая других администраторов.  | X  |   |   |   |
| Добавлять членов или других пользователей с разрешениями более низкого уровня.  |  X | X  |   |   |
| Публиковать и обновлять приложение. |  X | X  |   |   |
| Предоставлять общий доступ к элементу или приложению.<sup>1</sup> |  X | X  |   |   |
| Разрешать другим пользователям повторно предоставлять совместный доступ к элементам.<sup>1</sup> |  X | X  |   |   |
| Добавлять приложения в подборку на главной странице коллег |  X | X  |   |   |
| Добавлять панели мониторинга и отчеты в подборку на главной странице коллег |  X | X  | X |   |
| Создавать, редактировать и удалять содержимое в рабочей области.  |  X | X  | X  |   |
| Публиковать отчеты в рабочей области, удалять содержимое.  |  X | X  | X  |   |
| Создавать в другой рабочей области отчет на основе набора данных из текущей области<sup>1</sup>. |  X | X  | X  |   |
| Копировать отчет.<sup>2</sup> | X | X | X |  |
| Просматривать элемент и взаимодействовать с ним.<sup>3</sup> |  X | X  | X  | X  |
| Читать данные, хранящиеся в потоках данных рабочей области. | X | X | X | X |

1. Участники и зрители могут совместно использовать элементы в рабочей области, если у них есть разрешения на повторное предоставление общего доступа.
2. Чтобы скопировать отчет или создать в другой рабочей области новый отчет на основе набора данных из текущей области, требуется разрешение на создание набора данных. При использовании наборов данных из этой рабочей области пользователям с ролями администратора, члена или участника предоставляются разрешения на создание в рамках роли рабочей области.
3. Даже если у вас нет лицензии Power BI Pro, вы можете просматривать элементы и взаимодействовать с ними в службе Power BI, если они находятся в рабочей области в емкости Premium.
