---
title: 设计分布式体系结构 |Microsoft 文档
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
ms.openlocfilehash: 156c7107abfd0fd140a5e7b07f06d00eabf7c961
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239421"
---
# <a name="designing-a-distributed-architecture"></a><span data-ttu-id="2f472-102">设计分布式结构</span><span class="sxs-lookup"><span data-stu-id="2f472-102">Designing a Distributed Architecture</span></span>
<span data-ttu-id="2f472-103">有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="2f472-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="2f472-104">主题中提供的体系结构[大型分布式体系结构](../core/large-distributed-architecture.md)消除了许多潜在的安全威胁到 BizTalk 环境的易受攻击。</span><span class="sxs-lookup"><span data-stu-id="2f472-104">The architecture presented in the topic [Large Distributed Architecture](../core/large-distributed-architecture.md) addresses many of the potential security threats to which a BizTalk environment is vulnerable.</span></span> <span data-ttu-id="2f472-105">设计结构时，应优先考虑安全性；在分布式环境中还有其他注意事项，例如高可用性、可伸缩性和性能。</span><span class="sxs-lookup"><span data-stu-id="2f472-105">While security should be high on your list of priorities when designing your architecture, there are additional considerations in a distributed environment, such as high-availability, scalability, and performance.</span></span> <span data-ttu-id="2f472-106">本节提供您可以在设计时考虑的其他选项你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构。</span><span class="sxs-lookup"><span data-stu-id="2f472-106">This section provides additional options you can consider when designing your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture.</span></span>  
  
## <a name="domains"></a><span data-ttu-id="2f472-107">域</span><span class="sxs-lookup"><span data-stu-id="2f472-107">Domains</span></span>  
 <span data-ttu-id="2f472-108">如果您所在公司执行主要面向 Internet 的通信，您可以将 Intranet 服务从公司域中删除。</span><span class="sxs-lookup"><span data-stu-id="2f472-108">If your company performs mostly Internet-facing communications, you can remove the intranet services from the corporate domain.</span></span> <span data-ttu-id="2f472-109">相反，如果使用 BizTalk Server 与其他通过 Intranet 连接的应用程序或业务合作伙伴相连接，则您可以删除外围网络。</span><span class="sxs-lookup"><span data-stu-id="2f472-109">Conversely, if you use BizTalk Server to connect to other applications or business partners that connect through the intranet, you can remove the perimeter network.</span></span> <span data-ttu-id="2f472-110">如果你的公司限制较少的合作伙伴 Internet 和面向 intranet 的通信，你可以考虑组合的 intranet 服务和外围网络。</span><span class="sxs-lookup"><span data-stu-id="2f472-110">If your company does both Internet and intranet-facing communications with a small number of partners, you may consider combining the intranet services and the perimeter network.</span></span>  
  
 <span data-ttu-id="2f472-111">若要将数据域中的处理服务器与 SQL Server 之间进行通信的延迟时间降至最短，在不考虑内部网络中的安全问题（例如网络探查、篡改数据包和主机欺骗）的情况下，您可以删除处理域与数据域之间的防火墙并合并这些域。</span><span class="sxs-lookup"><span data-stu-id="2f472-111">If you want to minimize the latency in the communication between the processing servers and the SQL Servers in the data domain, and security issues such as network sniffing, tampering of packets, and host spoofing in the internal network are not a concern, you can remove the firewall between the processing and data domain, and merge these domains.</span></span> <span data-ttu-id="2f472-112">建议您随后使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 以便在数据从一台服务器传递到另一台服务器时对其进行保护。</span><span class="sxs-lookup"><span data-stu-id="2f472-112">It is recommended you then use Internet Protocol security (IPSec) or Secure Sockets Layer (SSL) to protect the data as it goes from one server to another.</span></span>  
  
## <a name="sql-server-clustering"></a><span data-ttu-id="2f472-113">SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="2f472-113">SQL Server clustering</span></span>  
 <span data-ttu-id="2f472-114">尽管本部分中没有详细介绍，但还是强烈建议您群集数据库以进行故障转移保护。</span><span class="sxs-lookup"><span data-stu-id="2f472-114">Although not described in detail in this section, we strongly recommend clustering your databases for failover protection.</span></span> <span data-ttu-id="2f472-115">有关 SQL Server 2008 故障转移群集的详细信息，请参阅 Microsoft MSDN 网站在[http://go.microsoft.com/fwlink/?LinkId=131016](http://go.microsoft.com/fwlink/?LinkId=131016)。</span><span class="sxs-lookup"><span data-stu-id="2f472-115">For more information about SQL Server 2008 failover clustering, see the Microsoft MSDN Web site at [http://go.microsoft.com/fwlink/?LinkId=131016](http://go.microsoft.com/fwlink/?LinkId=131016).</span></span>  
  
## <a name="messagebox-database"></a><span data-ttu-id="2f472-116">MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="2f472-116">MessageBox database</span></span>  
 <span data-ttu-id="2f472-117">根据您所在公司的消息吞吐量要求的不同，您可能需要添加（或删除）MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="2f472-117">Depending on the message throughput requirements for your company, you may need to add (or remove) MessageBox databases.</span></span> <span data-ttu-id="2f472-118">有关多个消息框的详细信息，请参阅[Scaled-Out 数据库](../core/scaled-out-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="2f472-118">For more information about multiple messagebox, see [Scaled-Out Databases](../core/scaled-out-databases.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f472-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f472-119">See Also</span></span>  
 <span data-ttu-id="2f472-120">[设计安全的体系结构](../core/designing-a-secure-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="2f472-120">[Designing a Secure Architecture](../core/designing-a-secure-architecture.md) </span></span>  
 <span data-ttu-id="2f472-121">[高可用性规划](../core/planning-for-high-availability3.md) </span><span class="sxs-lookup"><span data-stu-id="2f472-121">[Planning for High Availability](../core/planning-for-high-availability3.md) </span></span>  
 <span data-ttu-id="2f472-122">[为持续性能规划](../core/planning-for-sustained-performance.md) </span><span class="sxs-lookup"><span data-stu-id="2f472-122">[Planning for Sustained Performance](../core/planning-for-sustained-performance.md) </span></span>  
 <span data-ttu-id="2f472-123">[BizTalk server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="2f472-123">[Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span></span>  
 [<span data-ttu-id="2f472-124">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="2f472-124">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)