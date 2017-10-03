---
title: "监视 SQL Server 代理作业和数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2eb5f318-10d3-4f43-991d-9bff2ebc20e2
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c9991e7ebd61c72bbeb6a090b0497244da63e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-sql-server-agent-jobs-and-databases"></a>监视 SQL Server 代理作业和数据库
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含多个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]执行重要的功能使你的服务器操作和正常运行的代理作业。 您应该监视这些作业的运行状况，确保它们无错运行。 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理包包含用于监视 SQL 数据库之类的项的规则和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业。 你应配置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]用于全面监视的所有管理包[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包中包括两个禁用的规则，用于监视的运行状况的两个最重要的 BizTalk[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业：  
  
-   严重错误： BizTalk SQL Server 代理作业失败-备份 BizTalk Server  
  
-   严重错误： BizTalk SQL Server 代理作业失败 – 跟踪消息副本  
  
 若要监视所有 BizTalk 服务器[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业从内[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包，您必须启用这些规则并创建为你想要都监视使用以下过程的其他作业的其他规则。  
  
-   在 Operations Manager 管理员控制台中，创建一份在两个前面的规则任一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]核心规则组，然后相应地重命名规则。  
  
-   针对规则的条件部分中的通配符比较参数 1 相应变化。  
  
-   在某些情况下，作业名称是依赖于数据库名称的用户创建，例如，MessageBox 数据库的名称。  
  
-   可以针对你的规则是针对作业与单个 MessageBox 或所有 MessageBoxes。  
  
## <a name="see-also"></a>另请参阅  
 [如何启动 SQL Server 代理](../technical-guides/how-to-start-the-sql-server-agent.md)