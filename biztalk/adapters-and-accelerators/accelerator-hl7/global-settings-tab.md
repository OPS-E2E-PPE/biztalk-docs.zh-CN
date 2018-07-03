---
title: 全局设置选项卡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.globalsettings
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- Global Settings tab [Configuration Explorer]
- auditing, configuring
ms.assetid: 057189f7-9072-4841-950f-371ba1f73a15
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c19cfb387ba3cce61d21c467c1c91674204d4c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998678"
---
# <a name="global-settings-tab"></a>全局设置选项卡
您使用**全局设置**选项卡可配置使用的日志记录存储区[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]。  

 在中**BTAHL7 配置资源管理器**对话框中，在**全局设置**选项卡上，执行以下操作：  


|     使用此选项      |                                                                                                                                                执行的操作                                                                                                                                                |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **WMI**      |                                                                 选择此选项，如果你想要生成[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]BTAHL7 的 Management Instrumentation (WMI) 通知。                                                                  |
|      **SQL**      | 选择此选项，如果你想要使用 Microsoft[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]作为 BTAHL7 的日志记录存储。 **注意：** BTAHL7 将自动创建所需的日志记录，如果不存在的表。 |
|  **SQL Server**   |            类型[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名称。 这是必需的当您选择**SQL**选项。 允许的最大长度为 64 个字符。<br /><br /> 默认服务器和数据库名称为配置的 BTAHL7 数据库。            |
| **数据库名称** |                                                 类型[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库名称。 这是必需的当您选择**SQL**选项。 允许的最大长度为 128 个字符。                                                 |
|   **事件日志**   |                选择此选项，如果你想要使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]作为 BTAHL7 的日志记录存储的事件日志。 您使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件查看器查看事件消息。                 |

