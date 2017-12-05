---
title: "什么 BizTalk Server 日志传送？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 79a2088a-ff36-4590-97c9-51d5bb245486
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3b20589229b1e3868f23c3823d2a26decc56081
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="what-is-biztalk-server-log-shipping"></a>什么 BizTalk Server 日志传送？
BizTalk Server 灾难恢复过程围绕 BizTalk 日志传送。 BizTalk 日志传送通过连续将事务日志更新应用于的灾难恢复站点数据库，简化了发生灾难时的数据库还原。  
  
 而的 BizTalk 日志传送依赖于使用类似的准则[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]日志传送，[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]不支持日志传送[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份作为备份 BizTalk Server SQL 代理作业的一部分。  
  
## <a name="how-does-biztalk-log-shipping-work"></a>BizTalk 日志传送工作方式是怎样的？  
 BizTalk 中的日志传送函数方式类似于[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]日志传送。 生产[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组配置为备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库到 UNC 位置。 默认情况下，备份 BizTalk SQL 代理作业执行完整备份每隔一小时和每隔 15 分钟的日志备份。 备份 BizTalk Server 作业实现逻辑以自动启动完整备份，如果检测到备份失败。  
  
 当灾难恢复[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例所配置的 BizTalk 日志传送，由备份 BizTalk Server SQL 代理作业还原在灾难恢复站点上每隔 15 分钟默认情况下创建的备份文件。 备份文件将通过网络复制 SQL 还原命令。 在以下情况下仅复制完整备份文件：  
  
-   BizTalk 登录时首次配置传送  
  
-   当新数据库添加到备份 BizTalk Server 作业。  
  
-   在灾难恢复站点时还原失败  
  
 每个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在灾难恢复站点的实例作为 BizTalk 日志传送还原生产上承载数据库的一部分单独配置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库实例。 当[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例配置为 BizTalk Server 日志传送和**BTS 日志传送还原数据库**作业是否已启用， **BTS 日志传送还原数据库**作业将连接到对生产 BizTalk 管理数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  
  
 如上面所述，当首次配置目标服务器的完整数据库备份还原到目标服务器。 大多数情况下还原仅日志时**BTS 日志传送还原数据库**作业运行。  
  
 查看灾难恢复时[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio 中，数据库将显示在"加载"状态。 这是因为备份集中的最后一个日志永远不会自动还原。 一旦新的日志不可用，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送还原到最新日志的下一步。 当发生了灾难恢复事件和灾难恢复站点必须处于联机状态、 使用 STOPATMARK 命令将数据库恢复还原最后一个日志和数据库将不再显示为处于"加载"状态。