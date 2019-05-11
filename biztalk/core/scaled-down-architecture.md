---
title: 缩减的体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, small distributions
- architecture, examples
ms.assetid: e25798aa-4a1e-418c-9e0c-db964e8b5a80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 770276aceab5c0de64615f457c20d6d1945a63b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399972"
---
# <a name="scaled-down-architecture"></a><span data-ttu-id="c77c5-102">缩减的体系结构</span><span class="sxs-lookup"><span data-stu-id="c77c5-102">Scaled Down Architecture</span></span>
<span data-ttu-id="c77c5-103">有关完整信息的系统体系结构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="c77c5-103">For complete information about the system architecture for[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="c77c5-104">下图提供了一个示例[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构，可以组合某些域与 BizTalk Server，以减少服务器数量和你的防火墙需要。</span><span class="sxs-lookup"><span data-stu-id="c77c5-104">The following figure provides a sample [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture that combines some of the domains and BizTalk Servers to reduce the number of servers and firewalls you need.</span></span> <span data-ttu-id="c77c5-105">此体系结构，尽管不是最分布式仍将根据其函数 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="c77c5-105">While this architecture is not the most distributed, it still separates the BizTalk Servers based on their function.</span></span>  
  
 <span data-ttu-id="c77c5-106">![缩减的体系结构](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")</span><span class="sxs-lookup"><span data-stu-id="c77c5-106">![Scaled down architecture](../core/media/16ebc4ef-ff64-495b-bcac-5c1fd70ca173.gif "16ebc4ef-ff64-495b-bcac-5c1fd70ca173")</span></span>  
  
        Scaled Down Architecture  
  
 <span data-ttu-id="c77c5-107">在上图中，服务接口域和服务域中的服务器对应于 BizTalk 主机而不是物理服务器。</span><span class="sxs-lookup"><span data-stu-id="c77c5-107">In the previous figure, the servers in the service interfaces and services domain correspond to BizTalk Hosts, and not physical servers.</span></span> <span data-ttu-id="c77c5-108">尽管建议在独立的计算机保持在主密钥服务器和管理工具，可具有实例的跟踪、 处理、 发送和接收多台计算机上运行的主机。</span><span class="sxs-lookup"><span data-stu-id="c77c5-108">While it is recommended to keep the master secret server and the administrative tools in stand-alone computers, you can have host instances for the tracking, processing, send, and receive hosts running on multiple computers.</span></span> <span data-ttu-id="c77c5-109">同样，外围网络中的服务器与逻辑位置相对应。</span><span class="sxs-lookup"><span data-stu-id="c77c5-109">Similarly, the servers in the perimeter network correspond to logical locations.</span></span>  
  
 <span data-ttu-id="c77c5-110">外围网络中的 SMTP、 消息队列、 文件和 SQL 服务器对应于邮件服务器、 队列、 目录或 SQL Server 分别从其 BizTalk 接收和发送主机的处理和服务域中接收和发送消息。</span><span class="sxs-lookup"><span data-stu-id="c77c5-110">The servers in the perimeter network for SMTP, Message Queuing, File, and SQL correspond to the mail servers, queue, directory, or SQL Server respectively from which the BizTalk receive and send hosts in the processing and services domain receive and send messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c77c5-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c77c5-111">See Also</span></span>  
 <span data-ttu-id="c77c5-112">[缩减的具有信息工作者服务的体系结构](../core/scaled-down-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="c77c5-112">[Scaled Down Architecture with Information Worker Services](../core/scaled-down-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="c77c5-113">[大型分布式体系结构](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="c77c5-113">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="c77c5-114">[设计安全的体系结构](../core/designing-a-secure-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="c77c5-114">[Designing a Secure Architecture](../core/designing-a-secure-architecture.md) </span></span>  
 [<span data-ttu-id="c77c5-115">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="c77c5-115">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)