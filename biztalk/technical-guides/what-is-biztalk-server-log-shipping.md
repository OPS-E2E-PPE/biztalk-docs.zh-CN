---
title: 什么 BizTalk Server 日志传送概述 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 79a2088a-ff36-4590-97c9-51d5bb245486
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27885498dab635ebd8cb1923932c274b468e1d76
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301686"
---
# <a name="what-is-biztalk-server-log-shipping"></a>什么 BizTalk Server 日志传送概述
BizTalk Server 灾难恢复过程围绕 BizTalk 日志传送。 BizTalk 日志传送通过连续将事务日志更新应用于灾难恢复站点数据库，简化了发生灾难时数据库还原。  
  
 尽管的 BizTalk 日志传送依赖于使用类似做法准则也作为[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]日志传送[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]不支持日志传送[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为备份 BizTalk Server SQL 代理作业的一部分备份的数据库。  
  
## <a name="how-does-biztalk-log-shipping-work"></a>原理 BizTalk 日志传送的工作是什么？  
 BizTalk 日志传送功能的方式类似于[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]日志传送。 生产[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组配置为备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]UNC 位置的数据库。 默认情况下，备份 BizTalk SQL 代理作业执行完整备份每隔一小时和日志备份每隔 15 分钟。 备份 BizTalk Server 作业实现逻辑来自动启动完整备份，如果检测到备份失败。  
  
 当灾难恢复[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例配置为 BizTalk 日志传送备份 BizTalk Server SQL 代理作业会还原灾难恢复站点上每隔 15 分钟默认情况下创建的备份文件。 通过 SQL 还原命令，通过网络复制的备份文件。 仅在以下情况下复制完整备份的文件：  
  
- 需要先配置时 BizTalk 日志传送  
  
- 当新的数据库添加到备份 BizTalk Server 作业。  
  
- 在灾难恢复站点发生还原故障  
  
  每个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例在灾难恢复站点单独进行配置的 BizTalk 日志传送还原数据库托管在生产一部分[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库实例。 当[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例配置为 BizTalk Server 日志传送和**BTS 日志传送还原数据库**启用作业， **BTS 日志传送还原数据库**作业将连接到在生产上的 BizTalk 管理数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  
  
  如上文所述，当首次配置目标服务器的完整数据库备份还原到目标服务器。 大多数情况下仅日志被还原时**BTS 日志传送还原数据库**作业将运行。  
  
  查看灾难恢复时[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例与[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio 中，数据库将显示在"加载"状态。 这是因为永远不会自动还原在备份集中的最后一个日志。 一旦新的日志不可用，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送还原到最后一个日志的下一步。 当发生灾难恢复事件和灾难恢复站点必须处于联机状态、 的最后一个日志会恢复使用 STOPATMARK 命令可将数据库恢复，数据库将不再显示为处于"正在加载"状态。