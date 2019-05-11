---
title: 设计安全的体系结构 |Microsoft Docs
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
ms.openlocfilehash: cacd6bf8414ac91e2fb6d7846fd3b650c90b6912
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351676"
---
# <a name="designing-a-secure-architecture"></a><span data-ttu-id="57484-102">设计安全的体系结构</span><span class="sxs-lookup"><span data-stu-id="57484-102">Designing a Secure Architecture</span></span>
<span data-ttu-id="57484-103">有关 BizTalk Server 部署的系统体系结构的完整信息，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="57484-103">For complete information about the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="57484-104">中的主题提供的体系结构[大型分布式体系结构](../core/large-distributed-architecture.md)解决很多 BizTalk 环境是易受攻击的潜在安全威胁。</span><span class="sxs-lookup"><span data-stu-id="57484-104">The architecture presented in the topic [Large Distributed Architecture](../core/large-distributed-architecture.md) addresses many of the potential security threats to which a BizTalk environment is vulnerable.</span></span> <span data-ttu-id="57484-105">但是，您需要评估你的业务资产，需考虑您的业务，并可用于保护你的资产和缓解潜在威胁来确定最佳体系结构是为你的资源的威胁。</span><span class="sxs-lookup"><span data-stu-id="57484-105">However, you need to evaluate your business assets, the threats that are a concern for your business, and the resources you have available to protect your assets and mitigate your potential threats to determine what the best architecture is for you.</span></span> <span data-ttu-id="57484-106">此部分提供了可以考虑在设计时额外的安全选项在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构。</span><span class="sxs-lookup"><span data-stu-id="57484-106">This section provides additional security options you can consider when designing your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architecture.</span></span>  
  
## <a name="firewalls"></a><span data-ttu-id="57484-107">防火墙</span><span class="sxs-lookup"><span data-stu-id="57484-107">Firewalls</span></span>  
 <span data-ttu-id="57484-108">可以使用物理 （硬件） 或软件防火墙来限制对资源的访问，您的环境中。</span><span class="sxs-lookup"><span data-stu-id="57484-108">You can use physical (hardware) or software firewalls to restrict access to the resources in your environment.</span></span> <span data-ttu-id="57484-109">尽管本主题[大型分布式体系结构](../core/large-distributed-architecture.md)使用 Forefront Threat Management Gateway (TMG) 2010年服务器，您可以创建相似的体系结构使用硬件或第三方软件防火墙，只要您打开和配置不同的 BizTalk Server 组件之间进行通信所需的端口。</span><span class="sxs-lookup"><span data-stu-id="57484-109">While the topic [Large Distributed Architecture](../core/large-distributed-architecture.md) uses Forefront Threat Management Gateway (TMG) 2010 server, you can create a similar architecture by using hardware or third-party software firewalls, as long as you open and configure the ports required for communication between the different BizTalk Server components.</span></span> <span data-ttu-id="57484-110">有关 BizTalk Server 所使用的端口的详细信息，请参阅[的 BizTalk Server 所需端口](../core/required-ports-for-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="57484-110">For more information about the ports BizTalk Server uses, see [Required Ports for BizTalk Server](../core/required-ports-for-biztalk-server.md).</span></span>  
  
## <a name="active-directory"></a><span data-ttu-id="57484-111">Active Directory</span><span class="sxs-lookup"><span data-stu-id="57484-111">Active Directory</span></span>  
 <span data-ttu-id="57484-112">在示例部署中，Active Directory® 目录服务用于创建服务器的每个组周围的严格的安全边界。</span><span class="sxs-lookup"><span data-stu-id="57484-112">In the sample deployment, Active Directory® directory service is used to create a hard security boundary around each group of servers.</span></span> <span data-ttu-id="57484-113">使用单向信任，可以进一步保护 BizTalk Server 环境免受由于作为应用程序数据域中创建的帐户下运行的 BizTalk Server 处理服务器上运行其他非 BizTalk Server 应用程序中的漏洞的攻击。</span><span class="sxs-lookup"><span data-stu-id="57484-113">With the one-way trusts, you can further protect the BizTalk Server environment from attacks due to flaws in other non-BizTalk Server applications running on the processing servers, as the BizTalk Server applications run under accounts created in the data domain.</span></span> <span data-ttu-id="57484-114">数据域不信任其他任何域中的任何帐户，因为另一个域中的帐户的安全威胁使 BizTalk Server 环境不会受到攻击。</span><span class="sxs-lookup"><span data-stu-id="57484-114">Because the data domain does not trust any accounts in any other domain, a compromise of an account in another domain keeps the BizTalk Server environment from being compromised.</span></span>  
  
## <a name="ipsec-and-ssl"></a><span data-ttu-id="57484-115">IPSec 和 SSL</span><span class="sxs-lookup"><span data-stu-id="57484-115">IPSec and SSL</span></span>  
 <span data-ttu-id="57484-116">如果你的环境未造成严重提供需要的安全防火墙级别的威胁，但网络段连接的数据，处理，并且服务域不是物理上安全免受各种网络攻击 （例如，数据包探查或篡改），仍需要保护的数据，随着从一台服务器添加到另一个。</span><span class="sxs-lookup"><span data-stu-id="57484-116">If your environment does not pose critical threats that require the level of security firewalls provide, but the network segments that connect the data, processing, and services domains are not physically secure from various network attacks (for example packet sniffing or tampering), you still need to protect the data as it goes from one server to another.</span></span> <span data-ttu-id="57484-117">在这种情况下，您可以使用 Internet 协议安全性 (IPSec) 或安全套接字层 (SSL) 从一台服务器之间的通信进行加密。</span><span class="sxs-lookup"><span data-stu-id="57484-117">In this case, you can use Internet Protocol security (IPSec) or Secure Sockets Layer (SSL) to encrypt traffic from one server to another.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57484-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="57484-118">See Also</span></span>  
 <span data-ttu-id="57484-119">[设计分布式体系结构](../core/designing-a-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="57484-119">[Designing a Distributed Architecture](../core/designing-a-distributed-architecture.md) </span></span>  
 <span data-ttu-id="57484-120">[规划安全性](../core/planning-for-security.md) </span><span class="sxs-lookup"><span data-stu-id="57484-120">[Planning for Security](../core/planning-for-security.md) </span></span>  
 <span data-ttu-id="57484-121">[为 BizTalk Server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="57484-121">[Designing the System Architectures for BizTalk Server](../core/designing-the-system-architectures-for-biztalk-server.md) </span></span>  
 [<span data-ttu-id="57484-122">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="57484-122">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)