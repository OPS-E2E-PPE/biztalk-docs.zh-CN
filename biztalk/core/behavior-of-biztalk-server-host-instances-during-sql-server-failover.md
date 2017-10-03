---
title: "在 SQL Server 故障转移期间的 BizTalk Server 主机实例行为 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5642417-d27f-4539-a369-5fa11bec4a4f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f244ce0fe00fe05f73db5f43ec867254b7a61fb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a>BizTalk Server 主机实例在 SQL Server 故障转移过程中的操作
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]位于 Microsoft 的群集实例上的数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]暂时不可用如果的群集的实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]遇到故障转移。 本节介绍与关联的主机实例的行为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库不可用。  
  
## <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a>SQL Server 故障转移期间进程内主机实例的行为  
 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据不可用，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机的进程内实例将被回收，直至到 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的连接还原为止。 到 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 数据库的连接还原后，会继续正常进行文档处理。  
  
## <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a>SQL Server 故障转移期间独立主机实例的行为  
 如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据不可用，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机的独立实例将暂停，并在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序日志中生成类似以下的错误：  
  
```  
All receive locations are being temporarily disabled because either   
the MessageBox or Configuration database is not available.   
When these databases become available, the receive locations will be automatically enabled.  
```  
  
 一次连接到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库还原类似于以下一条信息性消息写入到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序日志和文档通常处理继续：  
  
```  
All receive locations are being enabled because both the MessageBox and Configuration databases are back online.  
```  
  
## <a name="see-also"></a>另请参阅  
 [主机](../core/hosts.md)