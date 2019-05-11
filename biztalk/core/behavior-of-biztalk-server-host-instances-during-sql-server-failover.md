---
title: SQL Server 故障转移期间 BizTalk Server 主机实例的行为 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5642417-d27f-4539-a369-5fa11bec4a4f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cd4f60d37ecf994b258991bb1b0947c2f28d7bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358218"
---
# <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a><span data-ttu-id="5fa2e-102">SQL Server 故障转移期间 BizTalk Server 主机实例的行为</span><span class="sxs-lookup"><span data-stu-id="5fa2e-102">Behavior of BizTalk Server Host Instances during SQL Server Failover</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5fa2e-103">数据库存储在 Microsoft 的群集实例上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]暂时不可用如果的群集的实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]发生故障转移。</span><span class="sxs-lookup"><span data-stu-id="5fa2e-103">databases housed on a clustered instance of Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are temporarily unavailable if the clustered instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] experiences a failover.</span></span> <span data-ttu-id="5fa2e-104">本部分介绍与关联的主机实例的行为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库都不可用。</span><span class="sxs-lookup"><span data-stu-id="5fa2e-104">This section documents the behavior of the host instances associated with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] when the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable.</span></span>  
  
## <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a><span data-ttu-id="5fa2e-105">SQL Server 故障转移期间进程内主机实例的行为</span><span class="sxs-lookup"><span data-stu-id="5fa2e-105">Behavior of In-Process Host Instances during SQL Server Failover</span></span>  
 <span data-ttu-id="5fa2e-106">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据不可用，则进程内实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]之前连接到主机将被回收[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]还原。</span><span class="sxs-lookup"><span data-stu-id="5fa2e-106">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable, then an in-process instance of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host will be recycled until the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is restored.</span></span> <span data-ttu-id="5fa2e-107">一次连接到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]还原数据库、 文档处理正常恢复。</span><span class="sxs-lookup"><span data-stu-id="5fa2e-107">Once the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases is restored, document processing resumes normally.</span></span>  
  
## <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a><span data-ttu-id="5fa2e-108">SQL Server 故障转移期间独立主机实例的行为</span><span class="sxs-lookup"><span data-stu-id="5fa2e-108">Behavior of Isolated Host Instances During SQL Server Failover</span></span>  
 <span data-ttu-id="5fa2e-109">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据不可用，则的独立的实例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机将暂停，并将在其中生成类似于以下的错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序日志：</span><span class="sxs-lookup"><span data-stu-id="5fa2e-109">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are unavailable, then an isolated instance of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host will pause and an error similar to the following will be generated in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application log:</span></span>  
  
```  
All receive locations are being temporarily disabled because either   
the MessageBox or Configuration database is not available.   
When these databases become available, the receive locations will be automatically enabled.  
```  
  
 <span data-ttu-id="5fa2e-110">一次连接到[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库还原类似于以下的信息性消息写入到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序日志和正常处理简历的文档：</span><span class="sxs-lookup"><span data-stu-id="5fa2e-110">Once the connection to the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases is restored an informational message similar to the following is written to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application log and document processing resumes normally:</span></span>  
  
```  
All receive locations are being enabled because both the MessageBox and Configuration databases are back online.  
```  
  
## <a name="see-also"></a><span data-ttu-id="5fa2e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fa2e-111">See Also</span></span>  
 [<span data-ttu-id="5fa2e-112">主机</span><span class="sxs-lookup"><span data-stu-id="5fa2e-112">Hosts</span></span>](../core/hosts.md)