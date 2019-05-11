---
title: 对于小型示例体系结构&amp;的中小型公司 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
ms.assetid: fc8c2fdd-bcb1-481c-b351-03092dd48540
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81bde6f78cad46e0c1346ec1ca705f44014d4cb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271070"
---
# <a name="sample-architectures-for-small-amp-medium-sized-companies"></a><span data-ttu-id="827af-102">对于小型示例体系结构&amp;中等规模的公司</span><span class="sxs-lookup"><span data-stu-id="827af-102">Sample Architectures for Small &amp; Medium-Sized Companies</span></span>
<span data-ttu-id="827af-103">本部分提供示例体系结构来部署 Microsoft BizTalk Server，如果想要帮助保护在小型或中型公司中的资产。</span><span class="sxs-lookup"><span data-stu-id="827af-103">This section provides a sample architecture to deploy Microsoft BizTalk Server when you want to help to protect the assets in a small or medium-sized company.</span></span> <span data-ttu-id="827af-104">尽管这些结构鼓励实施深度防御和服务分隔来最小化攻击的影响，它们假定的硬件、 软件和通常也适用于大型公司的人力资源的数量。</span><span class="sxs-lookup"><span data-stu-id="827af-104">While these architectures encourage defense in depth and separation of services to minimize the impact of an attack, they assume quantities of hardware, software, and human resources that are generally available to large companies.</span></span>  
  
 <span data-ttu-id="827af-105">但是，小型和中型公司 （或具有小型 BizTalk Server 部署的大型公司） 还应关注如何保护其环境。</span><span class="sxs-lookup"><span data-stu-id="827af-105">However, small and medium-sized companies (or large companies with small BizTalk Server deployments) should also be concerned with how to protect their environments.</span></span> <span data-ttu-id="827af-106">我们了解了公司如何部署或计划部署后其[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，则我们将派生平衡可用资源与最大可能安全性的小型和中型公司的示例体系结构。</span><span class="sxs-lookup"><span data-stu-id="827af-106">After we looked at how companies deployed or plan to deploy their [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solutions, we derived a sample architecture for small and medium-sized companies that balances available resources with the greatest possible security.</span></span> <span data-ttu-id="827af-107">您应使用本部分中的信息来帮助你规划您自己的部署。</span><span class="sxs-lookup"><span data-stu-id="827af-107">You should use the information in this section to help you plan your own deployment.</span></span> <span data-ttu-id="827af-108">评估您的业务需求和资产后你可能决定在不同的体系结构上的 BizTalk Server 部署。</span><span class="sxs-lookup"><span data-stu-id="827af-108">After you evaluate your business needs and assets you might decide on a different architecture for your BizTalk Server deployment.</span></span>  
  
 <span data-ttu-id="827af-109">若要使其更轻松地查看您的体系结构的外观，本部分提供示例体系结构是基于各种可能在环境中使用的适配器。</span><span class="sxs-lookup"><span data-stu-id="827af-109">To make it easier to see how your architecture would look, this section provides sample architectures based on various adapters that you might use in your environment.</span></span> <span data-ttu-id="827af-110">下图显示您的拓扑的组件是独立于适配器的并在适配器上的哪些组件依赖您在 BizTalk Server 环境中使用。</span><span class="sxs-lookup"><span data-stu-id="827af-110">The figures show you which components of the topology are adapter-independent, and which components depend on the adapter you use in your BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="827af-111">我们还检查根据一些可以使用与 BizTalk Server 适配器的使用方案。</span><span class="sxs-lookup"><span data-stu-id="827af-111">We also examine usage scenarios based on some of the adapters you can use with BizTalk Server.</span></span> <span data-ttu-id="827af-112">若要帮助您规划和设计您自己的体系结构，我们提供此示例结构的威胁模型分析。</span><span class="sxs-lookup"><span data-stu-id="827af-112">To help you as you plan and design your own architecture, we provide a threat model analysis of this sample architecture.</span></span> <span data-ttu-id="827af-113">此分析，您可以深入地了解可能会影响你的公司，具体取决于使用与你的合作伙伴进行通信的适配器的潜在安全问题。</span><span class="sxs-lookup"><span data-stu-id="827af-113">This analysis gives you a deeper look at the potential security issues that might affect your company, depending on the adapters you use to communicate with your partners.</span></span>  
  
 <span data-ttu-id="827af-114">虽然本部分提供信息以帮助您设计安全部署的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，以增加您还应该考虑确保环境中的服务器之间的通信的环境中的安全性。</span><span class="sxs-lookup"><span data-stu-id="827af-114">While this section gives you information to help you design a secure deployment of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], to increase the security in your environment you should also consider securing the communication between the servers in the environment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="827af-115">本部分假设不使用业务活动监视 (BAM)。</span><span class="sxs-lookup"><span data-stu-id="827af-115">This section assumes that you are not using Business Activity Monitoring (BAM).</span></span> <span data-ttu-id="827af-116">此功能需要额外的安全注意事项。</span><span class="sxs-lookup"><span data-stu-id="827af-116">This feature requires additional security considerations.</span></span> <span data-ttu-id="827af-117">中对此进行讨论[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="827af-117">This is discussed in [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="827af-118">有关本文档中未说明的适配器的详细信息，请参阅 BizTalk Server 开发人员中心 ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420)。)</span><span class="sxs-lookup"><span data-stu-id="827af-118">For more information about adapters not described in this document, see the BizTalk Server Developer Center ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420).)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="827af-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="827af-119">In This Section</span></span>  
  
-   [<span data-ttu-id="827af-120">示例体系结构：基本 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="827af-120">Sample Architecture: Base BizTalk Server</span></span>](../core/sample-architecture-base-biztalk-server.md)  
  
-   [<span data-ttu-id="827af-121">示例体系结构：HTTP 和 SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="827af-121">Sample Architecture: HTTP and SOAP Adapters</span></span>](../core/sample-architecture-http-and-soap-adapters.md)  
  
-   [<span data-ttu-id="827af-122">示例体系结构：BizTalk 消息队列</span><span class="sxs-lookup"><span data-stu-id="827af-122">Sample Architecture: BizTalk Message Queuing</span></span>](../core/sample-architecture-biztalk-message-queuing.md)  
  
-   [<span data-ttu-id="827af-123">示例体系结构：FTP Adapter</span><span class="sxs-lookup"><span data-stu-id="827af-123">Sample Architecture: FTP Adapter</span></span>](../core/sample-architecture-ftp-adapter.md)  
  
-   [<span data-ttu-id="827af-124">示例体系结构：文件适配器</span><span class="sxs-lookup"><span data-stu-id="827af-124">Sample Architecture: File Adapter</span></span>](../core/sample-architecture-file-adapter.md)