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
# <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a><span data-ttu-id="db51d-102">BizTalk Server 主机实例在 SQL Server 故障转移过程中的操作</span><span class="sxs-lookup"><span data-stu-id="db51d-102">Behavior of BizTalk Server Host Instances during SQL Server Failover</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="db51d-103">位于 Microsoft 的群集实例上的数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]暂时不可用如果的群集的实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]遇到故障转移。</span><span class="sxs-lookup"><span data-stu-id="db51d-103"> databases housed on a clustered instance of Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are temporarily unavailable if the clustered instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] experiences a failover.</span></span> <span data-ttu-id="db51d-104">本节介绍与关联的主机实例的行为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库不可用。</span><span class="sxs-lookup"><span data-stu-id="db51d-104">This section documents the behavior of the host instances associated with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] when the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable.</span></span>  
  
## <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a><span data-ttu-id="db51d-105">SQL Server 故障转移期间进程内主机实例的行为</span><span class="sxs-lookup"><span data-stu-id="db51d-105">Behavior of In-Process Host Instances during SQL Server Failover</span></span>  
 <span data-ttu-id="db51d-106">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据不可用，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机的进程内实例将被回收，直至到 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的连接还原为止。</span><span class="sxs-lookup"><span data-stu-id="db51d-106">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable, then an in-process instance of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host will be recycled until the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is restored.</span></span> <span data-ttu-id="db51d-107">到 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 数据库的连接还原后，会继续正常进行文档处理。</span><span class="sxs-lookup"><span data-stu-id="db51d-107">Once the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases is restored, document processing resumes normally.</span></span>  
  
## <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a><span data-ttu-id="db51d-108">SQL Server 故障转移期间独立主机实例的行为</span><span class="sxs-lookup"><span data-stu-id="db51d-108">Behavior of Isolated Host Instances During SQL Server Failover</span></span>  
 <span data-ttu-id="db51d-109">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据不可用，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 主机的独立实例将暂停，并在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序日志中生成类似以下的错误：</span><span class="sxs-lookup"><span data-stu-id="db51d-109">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable, then an isolated instance of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host will pause and an error similar to the following will be generated in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application log:</span></span>  
  
```  
All receive locations are being temporarily disabled because either   
the MessageBox or Configuration database is not available.   
When these databases become available, the receive locations will be automatically enabled.  
```  
  
 <span data-ttu-id="db51d-110">一次连接到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库还原类似于以下一条信息性消息写入到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序日志和文档通常处理继续：</span><span class="sxs-lookup"><span data-stu-id="db51d-110">Once the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases is restored an informational message similar to the following is written to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application log and document processing resumes normally:</span></span>  
  
```  
All receive locations are being enabled because both the MessageBox and Configuration databases are back online.  
```  
  
## <a name="see-also"></a><span data-ttu-id="db51d-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db51d-111">See Also</span></span>  
 [<span data-ttu-id="db51d-112">主机</span><span class="sxs-lookup"><span data-stu-id="db51d-112">Hosts</span></span>](../core/hosts.md)