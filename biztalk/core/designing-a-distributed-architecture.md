---
title: 设计分布式体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- clustering, SQL Servers
- SQL Server, clustering
ms.assetid: 8a8f1710-4d53-42bf-b5e5-2be3b43813b4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3e495fd45074398fbdedec2e4b8e3fb544f9e55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389721"
---
# <a name="designing-a-distributed-architecture"></a><span data-ttu-id="876c9-102">设计分布式体系结构</span><span class="sxs-lookup"><span data-stu-id="876c9-102">Designing a Distributed Architecture</span></span>
<span data-ttu-id="876c9-103">有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="876c9-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="876c9-104">中的主题提供的体系结构[大型分布式体系结构](../core/large-distributed-architecture.md)解决很多 BizTalk 环境是易受攻击的潜在安全威胁。</span><span class="sxs-lookup"><span data-stu-id="876c9-104">The architecture presented in the topic [Large Distributed Architecture](../core/large-distributed-architecture.md) addresses many of the potential security threats to which a BizTalk environment is vulnerable.</span></span> <span data-ttu-id="876c9-105">虽然设计您的体系结构时，安全性应是高优先级的列表，有一些在分布式环境中，例如高可用性、 可伸缩性和性能的其他注意事项。</span><span class="sxs-lookup"><span data-stu-id="876c9-105">While security should be high on your list of priorities when designing your architecture, there are additional considerations in a distributed environment, such as high-availability, scalability, and performance.</span></span> <span data-ttu-id="876c9-106">本部分提供设计时可考虑的其他选项在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构。</span><span class="sxs-lookup"><span data-stu-id="876c9-106">This section provides additional options you can consider when designing your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture.</span></span>  
  
## <a name="domains"></a><span data-ttu-id="876c9-107">域</span><span class="sxs-lookup"><span data-stu-id="876c9-107">Domains</span></span>  
 <span data-ttu-id="876c9-108">如果您所在公司执行主要面向 Internet 的通信，你可以从公司域中删除 intranet 服务。</span><span class="sxs-lookup"><span data-stu-id="876c9-108">If your company performs mostly Internet-facing communications, you can remove the intranet services from the corporate domain.</span></span> <span data-ttu-id="876c9-109">相反，如果使用 BizTalk Server 要连接到其他应用程序或通过 intranet 连接的业务合作伙伴，您可以删除外围网络。</span><span class="sxs-lookup"><span data-stu-id="876c9-109">Conversely, if you use BizTalk Server to connect to other applications or business partners that connect through the intranet, you can remove the perimeter network.</span></span> <span data-ttu-id="876c9-110">如果你的公司与少量的合作伙伴进行 Internet 和面向 intranet 的通信，则可以考虑将 intranet 服务和外围网络相结合。</span><span class="sxs-lookup"><span data-stu-id="876c9-110">If your company does both Internet and intranet-facing communications with a small number of partners, you may consider combining the intranet services and the perimeter network.</span></span>  
  
 <span data-ttu-id="876c9-111">如果你想要最大程度减少延迟时间以处理服务器和数据域中的 SQL 服务器之间的通信和安全问题，例如网络探查、 篡改数据包和主机欺骗内部网络中不考虑，则可以删除的处理和数据域之间的防火墙，然后合并这些域。</span><span class="sxs-lookup"><span data-stu-id="876c9-111">If you want to minimize the latency in the communication between the processing servers and the SQL Servers in the data domain, and security issues such as network sniffing, tampering of packets, and host spoofing in the internal network are not a concern, you can remove the firewall between the processing and data domain, and merge these domains.</span></span> <span data-ttu-id="876c9-112">建议您然后使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 来保护数据时对其从一台服务器到另一个。</span><span class="sxs-lookup"><span data-stu-id="876c9-112">It is recommended you then use Internet Protocol security (IPSec) or Secure Sockets Layer (SSL) to protect the data as it goes from one server to another.</span></span>  
  
## <a name="sql-server-clustering"></a><span data-ttu-id="876c9-113">SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="876c9-113">SQL Server clustering</span></span>  
 <span data-ttu-id="876c9-114">尽管不在本部分中的详细信息中所述，我们强烈建议您群集数据库故障转移保护。</span><span class="sxs-lookup"><span data-stu-id="876c9-114">Although not described in detail in this section, we strongly recommend clustering your databases for failover protection.</span></span> <span data-ttu-id="876c9-115">有关 SQL Server 2008 故障转移群集的详细信息，请参阅 Microsoft MSDN 网站上的[ http://go.microsoft.com/fwlink/?LinkId=131016 ](http://go.microsoft.com/fwlink/?LinkId=131016)。</span><span class="sxs-lookup"><span data-stu-id="876c9-115">For more information about SQL Server 2008 failover clustering, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=131016](http://go.microsoft.com/fwlink/?LinkId=131016).</span></span>  
  
## <a name="messagebox-database"></a><span data-ttu-id="876c9-116">MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="876c9-116">MessageBox database</span></span>  
 <span data-ttu-id="876c9-117">具体取决于你的公司的消息吞吐量要求，可能需要添加 （或删除） MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="876c9-117">Depending on the message throughput requirements for your company, you may need to add (or remove) MessageBox databases.</span></span> <span data-ttu-id="876c9-118">有关多个 messagebox 的详细信息，请参阅[Scaled-Out 数据库](../core/scaled-out-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="876c9-118">For more information about multiple messagebox, see [Scaled-Out Databases](../core/scaled-out-databases.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="876c9-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="876c9-119">See Also</span></span>  
 <span data-ttu-id="876c9-120">[设计安全的体系结构](../core/designing-a-secure-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="876c9-120">[Designing a Secure Architecture](../core/designing-a-secure-architecture.md) </span></span>  
 <span data-ttu-id="876c9-121">[规划高可用性](../core/planning-for-high-availability3.md) </span><span class="sxs-lookup"><span data-stu-id="876c9-121">[Planning for High Availability](../core/planning-for-high-availability3.md) </span></span>  
 <span data-ttu-id="876c9-122">[规划可持续性能](../core/planning-for-sustained-performance.md) </span><span class="sxs-lookup"><span data-stu-id="876c9-122">[Planning for Sustained Performance](../core/planning-for-sustained-performance.md) </span></span>  
 <span data-ttu-id="876c9-123">[为 BizTalk Server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="876c9-123">[Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span></span>  
 [<span data-ttu-id="876c9-124">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="876c9-124">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)