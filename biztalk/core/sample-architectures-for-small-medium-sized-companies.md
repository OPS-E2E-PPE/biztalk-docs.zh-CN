---
title: "对于小型示例体系结构&amp;中等规模的公司 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: architecture, examples
ms.assetid: fc8c2fdd-bcb1-481c-b351-03092dd48540
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa7911b7b2da942d559f2c85ad32e896c79d174
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architectures-for-small-amp-medium-sized-companies"></a><span data-ttu-id="89223-102">对于小型示例体系结构&amp;中等规模的公司</span><span class="sxs-lookup"><span data-stu-id="89223-102">Sample Architectures for Small &amp; Medium-Sized Companies</span></span>
<span data-ttu-id="89223-103">本部分介绍了部署 Microsoft BizTalk Server 以帮助保护中小型公司内的资产的示例结构。</span><span class="sxs-lookup"><span data-stu-id="89223-103">This section provides a sample architecture to deploy Microsoft BizTalk Server when you want to help to protect the assets in a small or medium-sized company.</span></span> <span data-ttu-id="89223-104">尽管这些结构鼓励实施深度防御和服务分隔来最大限度地降低攻击的影响，但其假定的硬件、软件和人力资源的数量通常也适用于大型公司。</span><span class="sxs-lookup"><span data-stu-id="89223-104">While these architectures encourage defense in depth and separation of services to minimize the impact of an attack, they assume quantities of hardware, software, and human resources that are generally available to large companies.</span></span>  
  
 <span data-ttu-id="89223-105">不过，中小型公司（或者具有小规模 BizTalk Server 部署的大型公司）还应关注如何保护其环境。</span><span class="sxs-lookup"><span data-stu-id="89223-105">However, small and medium-sized companies (or large companies with small BizTalk Server deployments) should also be concerned with how to protect their environments.</span></span> <span data-ttu-id="89223-106">我们查看公司如何部署或计划部署后其[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案，则我们将派生平衡与最大限度的安全性的可用资源的小型和中型公司的示例体系结构。</span><span class="sxs-lookup"><span data-stu-id="89223-106">After we looked at how companies deployed or plan to deploy their [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solutions, we derived a sample architecture for small and medium-sized companies that balances available resources with the greatest possible security.</span></span> <span data-ttu-id="89223-107">使用本部分中的信息将有助于您规划您自己的部署。</span><span class="sxs-lookup"><span data-stu-id="89223-107">You should use the information in this section to help you plan your own deployment.</span></span> <span data-ttu-id="89223-108">在评估您的业务需求和资产后，您也可能决定为 BizTalk Server 部署采用其他结构。</span><span class="sxs-lookup"><span data-stu-id="89223-108">After you evaluate your business needs and assets you might decide on a different architecture for your BizTalk Server deployment.</span></span>  
  
 <span data-ttu-id="89223-109">为了更方便地展示结构的外观，本部分根据您可能在环境中使用的各种适配器提供了不同的示例结构。</span><span class="sxs-lookup"><span data-stu-id="89223-109">To make it easier to see how your architecture would look, this section provides sample architectures based on various adapters that you might use in your environment.</span></span> <span data-ttu-id="89223-110">这些图中显示了拓扑结构的哪些组件与适配器无关，以及哪些组件需要依赖 BizTalk Server 环境中所使用的适配器。</span><span class="sxs-lookup"><span data-stu-id="89223-110">The figures show you which components of the topology are adapter-independent, and which components depend on the adapter you use in your BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="89223-111">我们还根据可与 BizTalk Server 一起使用的一些适配器来划分不同的使用方案。</span><span class="sxs-lookup"><span data-stu-id="89223-111">We also examine usage scenarios based on some of the adapters you can use with BizTalk Server.</span></span> <span data-ttu-id="89223-112">为帮助您规划和设计自己的结构，我们对此示例结构进行了威胁模型分析。</span><span class="sxs-lookup"><span data-stu-id="89223-112">To help you as you plan and design your own architecture, we provide a threat model analysis of this sample architecture.</span></span> <span data-ttu-id="89223-113">通过此分析，您可以更深入地了解可能会影响您的公司的潜在安全问题。根据您与合作伙伴进行通信所用的适配器的不同，这些问题也会有所不同。</span><span class="sxs-lookup"><span data-stu-id="89223-113">This analysis gives you a deeper look at the potential security issues that might affect your company, depending on the adapters you use to communicate with your partners.</span></span>  
  
 <span data-ttu-id="89223-114">虽然本部分提供信息来帮助你设计的安全部署[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，来提高您还应考虑保护环境中的服务器之间的通信的环境中的安全性。</span><span class="sxs-lookup"><span data-stu-id="89223-114">While this section gives you information to help you design a secure deployment of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], to increase the security in your environment you should also consider securing the communication between the servers in the environment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="89223-115">本部分假定您没有使用业务活动监视 (BAM)。</span><span class="sxs-lookup"><span data-stu-id="89223-115">This section assumes that you are not using Business Activity Monitoring (BAM).</span></span> <span data-ttu-id="89223-116">使用该功能还需要遵循其他安全注意事项。</span><span class="sxs-lookup"><span data-stu-id="89223-116">This feature requires additional security considerations.</span></span> <span data-ttu-id="89223-117">对此进行讨论[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="89223-117">This is discussed in [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="89223-118">有关在本文档中未涉及的适配器的详细信息，请参阅 BizTalk Server 开发人员中心 ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420)。)</span><span class="sxs-lookup"><span data-stu-id="89223-118">For more information about adapters not described in this document, see the BizTalk Server Developer Center ([http://go.microsoft.com/fwlink/?LinkId=46420](http://go.microsoft.com/fwlink/?LinkId=46420).)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89223-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="89223-119">In This Section</span></span>  
  
-   [<span data-ttu-id="89223-120">示例体系结构： 基 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="89223-120">Sample Architecture: Base BizTalk Server</span></span>](../core/sample-architecture-base-biztalk-server.md)  
  
-   [<span data-ttu-id="89223-121">示例体系结构： HTTP 和 SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="89223-121">Sample Architecture: HTTP and SOAP Adapters</span></span>](../core/sample-architecture-http-and-soap-adapters.md)  
  
-   [<span data-ttu-id="89223-122">示例体系结构： BizTalk 消息队列</span><span class="sxs-lookup"><span data-stu-id="89223-122">Sample Architecture: BizTalk Message Queuing</span></span>](../core/sample-architecture-biztalk-message-queuing.md)  
  
-   [<span data-ttu-id="89223-123">示例体系结构： FTP 适配器</span><span class="sxs-lookup"><span data-stu-id="89223-123">Sample Architecture: FTP Adapter</span></span>](../core/sample-architecture-ftp-adapter.md)  
  
-   [<span data-ttu-id="89223-124">示例体系结构： 文件适配器</span><span class="sxs-lookup"><span data-stu-id="89223-124">Sample Architecture: File Adapter</span></span>](../core/sample-architecture-file-adapter.md)