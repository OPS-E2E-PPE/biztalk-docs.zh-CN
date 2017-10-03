---
title: "按比例缩小体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
ms.assetid: e25798aa-4a1e-418c-9e0c-db964e8b5a80
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a112f3f737a1a5aec0cfac16b7689d3dada1e8ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scaled-down-architecture"></a><span data-ttu-id="70035-102">精简规模结构</span><span class="sxs-lookup"><span data-stu-id="70035-102">Scaled Down Architecture</span></span>
<span data-ttu-id="70035-103">有关系统体系结构的完整信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="70035-103">For complete information about the system architecture for[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="70035-104">下图提供了一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 示例结构，该结构将某些域与 BizTalk Server 组合在一起以减少所需的服务器和防火墙的数量。</span><span class="sxs-lookup"><span data-stu-id="70035-104">The following figure provides a sample [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture that combines some of the domains and BizTalk Servers to reduce the number of servers and firewalls you need.</span></span> <span data-ttu-id="70035-105">尽管此结构不具备最强的分布式性能，但它仍然按服务器功能来分隔不同的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="70035-105">While this architecture is not the most distributed, it still separates the BizTalk Servers based on their function.</span></span>  
  
 <span data-ttu-id="70035-106">![按比例缩小体系结构](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")</span><span class="sxs-lookup"><span data-stu-id="70035-106">![Scaled down architecture](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")</span></span>  
  
        Scaled Down Architecture  
  
 <span data-ttu-id="70035-107">在上图中，服务接口和服务域中的服务器与 BizTalk 主机而不是物理服务器相对应。</span><span class="sxs-lookup"><span data-stu-id="70035-107">In the previous figure, the servers in the service interfaces and services domain correspond to BizTalk Hosts, and not physical servers.</span></span> <span data-ttu-id="70035-108">虽然建议您将主密钥服务器和管理工具置于独立的计算机中，但您仍会具有与多台计算机上运行的跟踪、处理、发送和接收主机相对应的实例。</span><span class="sxs-lookup"><span data-stu-id="70035-108">While it is recommended to keep the master secret server and the administrative tools in stand-alone computers, you can have host instances for the tracking, processing, send, and receive hosts running on multiple computers.</span></span> <span data-ttu-id="70035-109">同样，外围网络中的服务器与逻辑位置相对应。</span><span class="sxs-lookup"><span data-stu-id="70035-109">Similarly, the servers in the perimeter network correspond to logical locations.</span></span>  
  
 <span data-ttu-id="70035-110">外围网络中的 SMTP 服务器、消息队列服务器、文件服务器和 SQL Server 分别与邮件服务器、队列、目录或 SQL Server 相对应，处理和服务域中的 BizTalk 接收主机与发送主机从这些逻辑位置接收和发送消息。</span><span class="sxs-lookup"><span data-stu-id="70035-110">The servers in the perimeter network for SMTP, Message Queuing, File, and SQL correspond to the mail servers, queue, directory, or SQL Server respectively from which the BizTalk receive and send hosts in the processing and services domain receive and send messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70035-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="70035-111">See Also</span></span>  
 <span data-ttu-id="70035-112">[按比例缩小使用信息辅助服务的体系结构](../core/scaled-down-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="70035-112">[Scaled Down Architecture with Information Worker Services](../core/scaled-down-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="70035-113">[大型分布式体系结构](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="70035-113">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="70035-114">[设计安全的体系结构](../core/designing-a-secure-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="70035-114">[Designing a Secure Architecture](../core/designing-a-secure-architecture.md) </span></span>  
 [<span data-ttu-id="70035-115">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="70035-115">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)