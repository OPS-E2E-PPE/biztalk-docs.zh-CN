---
title: 示例基于中心方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- supply chains, examples
- hub-and-spoke systems
- supply chains, hub-and-spoke systems
- examples, supply chains
- trading partners, supply chains
ms.assetid: ee92c24d-a281-4950-a61e-9cb3bd08d291
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b417398786e602379d16d6734a5ed366b9d6f2ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210413"
---
# <a name="sample-hub-based-scenario"></a><span data-ttu-id="ff135-102">示例基于中心的方案</span><span class="sxs-lookup"><span data-stu-id="ff135-102">Sample Hub-Based Scenario</span></span>
<span data-ttu-id="ff135-103">在众多的供应链方案中，公司将与每个贸易合作伙伴合作以建立 RosettaNet 实现框架 (RNIF) 连接。</span><span class="sxs-lookup"><span data-stu-id="ff135-103">In many supply-chain scenarios, a company will work with each of their trading partners to institute a RosettaNet Implementation Framework (RNIF) connection.</span></span> <span data-ttu-id="ff135-104">这是在整个供应链中对通信进行标准化的有效方式。</span><span class="sxs-lookup"><span data-stu-id="ff135-104">This is an effective way to standardize communications throughout the supply chain.</span></span> <span data-ttu-id="ff135-105">此方案中所述[示例提供链方案](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="ff135-105">This scenario is described in [Sample Supply Chain Scenario](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md).</span></span>  
  
 <span data-ttu-id="ff135-106">在整个供应链中自动化交易还有另一种方法，就是公司与另一家公司签署合同，以设置并管理集成系统。</span><span class="sxs-lookup"><span data-stu-id="ff135-106">Another way to automate transactions throughout the supply chain is for the company to contract with another company to set up and manage the integrated system.</span></span> <span data-ttu-id="ff135-107">这是一个有中心的方案。</span><span class="sxs-lookup"><span data-stu-id="ff135-107">This is a hub-based scenario.</span></span>  
  
## <a name="how-a-hub-based-system-works"></a><span data-ttu-id="ff135-108">有中心的系统的工作方式</span><span class="sxs-lookup"><span data-stu-id="ff135-108">How a Hub-Based System Works</span></span>  
 <span data-ttu-id="ff135-109">在有中心的系统中，承购集成系统的公司使用 RNIF 连接与中心公司建立连接。</span><span class="sxs-lookup"><span data-stu-id="ff135-109">In a hub-based system, the company contracting for an integrated system connects to the hub company using an RNIF connection.</span></span> <span data-ttu-id="ff135-110">然后中心使用任意所需类型的电子连接与此公司的所有贸易合作伙伴建立连接。</span><span class="sxs-lookup"><span data-stu-id="ff135-110">The hub then connects to all the company's trading partners using whatever type of electronic connection is required.</span></span> <span data-ttu-id="ff135-111">中心公司提供与连接选项的所有贸易合作伙伴： RNIF 连接、 EDI、 平面文件、 Web 应用程序或不符合标准的、 专用连接。</span><span class="sxs-lookup"><span data-stu-id="ff135-111">The hub company provides all the trading partners with connection options: RNIF connections, EDI, flat file, Web applications, or non-compliant, proprietary connections.</span></span> <span data-ttu-id="ff135-112">通信系统由中心公司负责管理。</span><span class="sxs-lookup"><span data-stu-id="ff135-112">Managing the communications system is the hub company's business.</span></span> <span data-ttu-id="ff135-113">下图显示了此类系统的工作原理。</span><span class="sxs-lookup"><span data-stu-id="ff135-113">The following figure shows how such a system might work.</span></span>  
  
 <span data-ttu-id="ff135-114">![&#60;无更改 &#62;] (../../adapters-and-accelerators/accelerator-rosettanet/media/hub-based-scenario.gif "Hub_Based_Scenario")</span><span class="sxs-lookup"><span data-stu-id="ff135-114">![&#60;No Change&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/hub-based-scenario.gif "Hub_Based_Scenario")</span></span>  
  
 <span data-ttu-id="ff135-115">有中心的系统具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="ff135-115">A hub-based system has many advantages:</span></span>  
  
-   <span data-ttu-id="ff135-116">签署合同的公司不必处理复杂的供应链；中心公司会对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="ff135-116">The contracting company does not have to deal with the complexity of the supply chain; the hub company handles it.</span></span>  
  
-   <span data-ttu-id="ff135-117">签署合同的公司不必维护或升级系统，也不用对停机负责；这些系统维护和停机都由中心公司来负责。</span><span class="sxs-lookup"><span data-stu-id="ff135-117">The contracting company does not have to maintain or upgrade the system, and it is not responsible for downtime; the hub company is responsible for system maintenance and downtime.</span></span>  
  
-   <span data-ttu-id="ff135-118">签署合同的公司可以从 RosettaNet 兼容系统中受益，包括标准化、自动化、节约成本以及可视化。</span><span class="sxs-lookup"><span data-stu-id="ff135-118">The contracting company gains the advantages of a RosettaNet-compliant system, including standardization, automation, cost savings, and visibility.</span></span>  
  
-   <span data-ttu-id="ff135-119">借助各种电子连接，签署合同的公司实现了供应链管理的完全自动化，而这些电子连接也使所有贸易合作伙伴有机会对连接方式进行选择。</span><span class="sxs-lookup"><span data-stu-id="ff135-119">The contracting company has fully automated their supply chain with a variety of electronic connections that give the full array of trading partners a choice of connections.</span></span> <span data-ttu-id="ff135-120">签署合同的公司不必掌握有关各种连接选项的专业技能。</span><span class="sxs-lookup"><span data-stu-id="ff135-120">The contracting company does not have to maintain technological expertise in a variety of connection options.</span></span>  
  
-   <span data-ttu-id="ff135-121">只要中心公司支持，贸易合作伙伴可以继续使用专用连接。</span><span class="sxs-lookup"><span data-stu-id="ff135-121">A trading partner can continue to use a proprietary connection, as long as the hub company supports it.</span></span>  
  
-   <span data-ttu-id="ff135-122">此系统具有很高的灵活性。</span><span class="sxs-lookup"><span data-stu-id="ff135-122">The system is flexible.</span></span> <span data-ttu-id="ff135-123">贸易合作伙伴不必采用 RosettaNet 兼容系统。</span><span class="sxs-lookup"><span data-stu-id="ff135-123">Trading partners do not have to adopt a RosettaNet-compliant system.</span></span> <span data-ttu-id="ff135-124">但是，如果他们采用了此类系统，则将从中受益。</span><span class="sxs-lookup"><span data-stu-id="ff135-124">However, if they do so, they will gain the benefits from such a system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff135-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff135-125">See Also</span></span>  
 <span data-ttu-id="ff135-126">[BizTalk Server 如何解决的业务需要](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md) </span><span class="sxs-lookup"><span data-stu-id="ff135-126">[How BizTalk Server Solves the Business Need](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md) </span></span>  
 <span data-ttu-id="ff135-127">[需贸易合作伙伴集成](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md) </span><span class="sxs-lookup"><span data-stu-id="ff135-127">[The Need for Trading Partner Integration](../../adapters-and-accelerators/accelerator-rosettanet/the-need-for-trading-partner-integration.md) </span></span>  
 <span data-ttu-id="ff135-128">[供应链挑战](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md) </span><span class="sxs-lookup"><span data-stu-id="ff135-128">[The Supply Chain Challenge](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-challenge.md) </span></span>  
 <span data-ttu-id="ff135-129">[供应链解决方案](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md) </span><span class="sxs-lookup"><span data-stu-id="ff135-129">[The Supply Chain Solution](../../adapters-and-accelerators/accelerator-rosettanet/the-supply-chain-solution.md) </span></span>  
 [<span data-ttu-id="ff135-130">示例供应链方案</span><span class="sxs-lookup"><span data-stu-id="ff135-130">Sample Supply Chain Scenario</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/sample-supply-chain-scenario.md)