---
title: 监视 SQL Server 代理作业和数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2eb5f318-10d3-4f43-991d-9bff2ebc20e2
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2a0b770ded2bef9ccf28a763f63f053c0b3c89e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024307"
---
# <a name="monitoring-sql-server-agent-jobs-and-databases"></a>监视 SQL Server 代理作业和数据库
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包含多个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]执行重要功能，以使服务器正常操作和运行的代理作业。 您应该监视这些作业的运行状况，确保它们无错运行。 在 Microsoft[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]管理包包含用于监视 SQL 数据库等项目的规则和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业。 应配置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]适用于所有的全面的监视管理包[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包包括用于监视的两个最重要的 BizTalk 运行状况的两个已禁用的规则[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业：  
  
- 严重错误： BizTalk SQL Server 代理作业失败-备份 BizTalk Server  
  
- 严重错误： BizTalk SQL Server 代理作业失败 – 跟踪消息复制  
  
  若要监视所有 BizTalk Server[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]代理作业中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包，必须启用这些规则并创建为你想要使用以下过程都监视其他作业的其他规则。  
  
- 在 Operations Manager 管理员控制台中，创建两个上述规则中的任何一个的副本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]核心规则组，并相应地重命名规则。  
  
- 规则在条件部分中的通配符比较参数 1 的相应更改。  
  
- 在某些情况下，作业名称是依赖于数据库的名称创建用户，例如，MessageBox 数据库的名称。  
  
- 可以针对你的规则是针对作业与单个 MessageBox 或所有 Messagebox。  
  
## <a name="see-also"></a>请参阅  
 [如何启动 SQL Server 代理](../technical-guides/how-to-start-the-sql-server-agent.md)