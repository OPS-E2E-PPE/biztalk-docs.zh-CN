---
title: 设计安全的体系结构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- firewalls
- architecture, security
- installation, firewalls
- installation, security
ms.assetid: 93df6a3f-396c-4767-99c8-2145bddf8fdf
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 157c11477efb9dec455e9ac2de81736cd4ea72ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239445"
---
# <a name="designing-a-secure-architecture"></a><span data-ttu-id="4072d-102">设计安全结构</span><span class="sxs-lookup"><span data-stu-id="4072d-102">Designing a Secure Architecture</span></span>
<span data-ttu-id="4072d-103">有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="4072d-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="4072d-104">主题中提供的体系结构[大型分布式体系结构](../core/large-distributed-architecture.md)消除了许多潜在的安全威胁到 BizTalk 环境的易受攻击。</span><span class="sxs-lookup"><span data-stu-id="4072d-104">The architecture presented in the topic [Large Distributed Architecture](../core/large-distributed-architecture.md) addresses many of the potential security threats to which a BizTalk environment is vulnerable.</span></span> <span data-ttu-id="4072d-105">不过，你需要评估你的业务资产、与你的业务相关的威胁以及可用于保护资产和缓解潜在威胁的资源，以确定适合你的最佳结构。</span><span class="sxs-lookup"><span data-stu-id="4072d-105">However, you need to evaluate your business assets, the threats that are a concern for your business, and the resources you have available to protect your assets and mitigate your potential threats to determine what the best architecture is for you.</span></span> <span data-ttu-id="4072d-106">此部分提供其他安全选项，您可以在设计时考虑你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构。</span><span class="sxs-lookup"><span data-stu-id="4072d-106">This section provides additional security options you can consider when designing your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture.</span></span>  
  
## <a name="firewalls"></a><span data-ttu-id="4072d-107">防火墙</span><span class="sxs-lookup"><span data-stu-id="4072d-107">Firewalls</span></span>  
 <span data-ttu-id="4072d-108">可以使用物理（硬件）或软件防火墙来限制对环境中资源的访问。</span><span class="sxs-lookup"><span data-stu-id="4072d-108">You can use physical (hardware) or software firewalls to restrict access to the resources in your environment.</span></span> <span data-ttu-id="4072d-109">尽管主题[大型分布式体系结构](../core/large-distributed-architecture.md)使用 Forefront Threat Management Gateway (TMG) 2010年服务器，你可以创建相似的体系结构通过使用硬件或第三方软件防火墙、，只要您打开和配置不同的 BizTalk Server 组件之间的通信所需的端口。</span><span class="sxs-lookup"><span data-stu-id="4072d-109">While the topic [Large Distributed Architecture](../core/large-distributed-architecture.md) uses Forefront Threat Management Gateway (TMG) 2010 server, you can create a similar architecture by using hardware or third-party software firewalls, as long as you open and configure the ports required for communication between the different BizTalk Server components.</span></span> <span data-ttu-id="4072d-110">BizTalk Server 使用的端口的详细信息，请参阅[的 BizTalk Server 所需端口](../core/required-ports-for-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="4072d-110">For more information about the ports BizTalk Server uses, see [Required Ports for BizTalk Server](../core/required-ports-for-biztalk-server.md).</span></span>  
  
## <a name="active-directory"></a><span data-ttu-id="4072d-111">Active Directory</span><span class="sxs-lookup"><span data-stu-id="4072d-111">Active Directory</span></span>  
 <span data-ttu-id="4072d-112">在示例部署中，用于创建严格的安全边界的服务器的每个组周围 Active Directory® 目录服务。</span><span class="sxs-lookup"><span data-stu-id="4072d-112">In the sample deployment, Active Directory® directory service is used to create a hard security boundary around each group of servers.</span></span> <span data-ttu-id="4072d-113">使用单向信任，你可以进一步保护 BizTalk Server 环境不会因处理服务器上运行的其他非 BizTalk Server 应用程序中的缺陷而遭受攻击，因为 BizTalk Server 应用程序在数据域中创建的帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="4072d-113">With the one-way trusts, you can further protect the BizTalk Server environment from attacks due to flaws in other non-BizTalk Server applications running on the processing servers, as the BizTalk Server applications run under accounts created in the data domain.</span></span> <span data-ttu-id="4072d-114">由于数据域不信任其他任何域中的任何帐户，因此，如果其他域中的帐户受到威胁，也不会危及 BizTalk Server 环境。</span><span class="sxs-lookup"><span data-stu-id="4072d-114">Because the data domain does not trust any accounts in any other domain, a compromise of an account in another domain keeps the BizTalk Server environment from being compromised.</span></span>  
  
## <a name="ipsec-and-ssl"></a><span data-ttu-id="4072d-115">IPSec 和 SSL</span><span class="sxs-lookup"><span data-stu-id="4072d-115">IPSec and SSL</span></span>  
 <span data-ttu-id="4072d-116">如果你的环境未造成需要防火墙所提供安全级别的关键威胁，但没有从物理上保护连接数据域、处理域和服务域的网络段免受各种网络攻击（例如，数据包探查或篡改），则你仍需要在服务器间传递数据时对其进行保护。</span><span class="sxs-lookup"><span data-stu-id="4072d-116">If your environment does not pose critical threats that require the level of security firewalls provide, but the network segments that connect the data, processing, and services domains are not physically secure from various network attacks (for example packet sniffing or tampering), you still need to protect the data as it goes from one server to another.</span></span> <span data-ttu-id="4072d-117">在这种情况下，可使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 对服务器之间的通信进行加密。</span><span class="sxs-lookup"><span data-stu-id="4072d-117">In this case, you can use Internet Protocol security (IPSec) or Secure Sockets Layer (SSL) to encrypt traffic from one server to another.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4072d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4072d-118">See Also</span></span>  
 <span data-ttu-id="4072d-119">[设计分布式体系结构](../core/designing-a-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="4072d-119">[Designing a Distributed Architecture](../core/designing-a-distributed-architecture.md) </span></span>  
 <span data-ttu-id="4072d-120">[规划安全性](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="4072d-120">[Planning for Security](../core/planning-for-security.md) </span></span>  
 <span data-ttu-id="4072d-121">[BizTalk server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="4072d-121">[Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span></span>  
 [<span data-ttu-id="4072d-122">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="4072d-122">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)