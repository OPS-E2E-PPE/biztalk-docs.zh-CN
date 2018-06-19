---
title: 服务实现重点介绍面向解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, performance
- performance, service solutions
- service solution tutorial, implementing
ms.assetid: 3dbd8dfd-45b7-4290-ba07-b0c5e6264629
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c593c24c72e5666525001e6a52e2b0bf6eac2de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257749"
---
# <a name="implementation-highlights-of-the-service-oriented-solution"></a><span data-ttu-id="b92c6-102">服务实现重点介绍面向解决方案</span><span class="sxs-lookup"><span data-stu-id="b92c6-102">Implementation Highlights of the Service Oriented Solution</span></span>
<span data-ttu-id="b92c6-103">解决方案用于解决特定环境中的具体问题。</span><span class="sxs-lookup"><span data-stu-id="b92c6-103">A solution solves a particular problem in a specific context.</span></span> <span data-ttu-id="b92c6-104">面向服务的解决方案也不例外和特定于 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和方案。</span><span class="sxs-lookup"><span data-stu-id="b92c6-104">The Service Oriented solution is no exception and is specific to Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the scenario.</span></span> <span data-ttu-id="b92c6-105">Woodgrove Bank 方案有关的详细信息，请参阅[了解服务面向解决方案](../core/understanding-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="b92c6-105">For more information about the Woodgrove Bank scenario, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="b92c6-106">在开发该方案时，有几个方面证明是阻碍将响应时间降低到可接受程度的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="b92c6-106">While developing the scenario, several areas proved to be bottlenecks in reducing response times to an acceptable level.</span></span> <span data-ttu-id="b92c6-107">使用适配器将消息发送到后端系统会导致在获取返回的响应时有明显的延迟。</span><span class="sxs-lookup"><span data-stu-id="b92c6-107">Sending messages to the backend systems using the adapters introduces significant latency in getting back responses.</span></span> <span data-ttu-id="b92c6-108">通常，适配器本身只会造成很短的延迟。</span><span class="sxs-lookup"><span data-stu-id="b92c6-108">In general, adapters by themselves offer very low latency.</span></span> <span data-ttu-id="b92c6-109">但是，BizTalk 的分布式结构要求适配器使用 MessageBox 与业务流程主机实例进行通信。</span><span class="sxs-lookup"><span data-stu-id="b92c6-109">However, the distributed architecture of BizTalk requires adapters to communicate with the orchestration host instances using the message box.</span></span> <span data-ttu-id="b92c6-110">这会导致消息在适配器与该数据库之间往返，从而影响延迟时间。</span><span class="sxs-lookup"><span data-stu-id="b92c6-110">This introduces round trips to the database and affects latency times.</span></span> <span data-ttu-id="b92c6-111">因此，该解决方案的内联版本（速度最快的版本）在业务流程本身中生成直接调用后端系统的适配器功能。</span><span class="sxs-lookup"><span data-stu-id="b92c6-111">For this reason, the inline version of the solution (the fastest version) builds the adapter functionality in the orchestration itself calls the back-end systems directly.</span></span> <span data-ttu-id="b92c6-112">如果有三种不同的后端系统，这意味着可能有三种不同的机制与后端系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="b92c6-112">With three different back-end systems, that means potentially three different mechanisms to communicate with the back-end systems.</span></span>  
  
 <span data-ttu-id="b92c6-113">确认会造成性能问题的另一个方面是从企业单一登录 (SSO) 检索配置数据。</span><span class="sxs-lookup"><span data-stu-id="b92c6-113">Another area that proved a performance problem was retrieving configuration data from Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="b92c6-114">为了在缩短检索时间的同时保持 SSO 的易用性和通用性，该解决方案为配置值使用了本地缓存。</span><span class="sxs-lookup"><span data-stu-id="b92c6-114">To retain the convenience and universality of SSO while speeding up retrieval time, the solution uses a local cache for configuration values.</span></span> <span data-ttu-id="b92c6-115">通过使用 SSO，还可以简化配置数据的管理。</span><span class="sxs-lookup"><span data-stu-id="b92c6-115">Using SSO also allows easier management of the configuration data.</span></span> <span data-ttu-id="b92c6-116">添加其他主机实例以满足延迟和性能要求并不需要更改运行主机实例的服务器的设置。</span><span class="sxs-lookup"><span data-stu-id="b92c6-116">Adding additional host instances to meet latency and performance requirements does not require changing settings on the server running the host instance.</span></span>  
  
 <span data-ttu-id="b92c6-117">该解决方案的另一个不同寻常的方面是直接从代码调用管道。</span><span class="sxs-lookup"><span data-stu-id="b92c6-117">Another unusual element of the solution is calling pipelines directly from code.</span></span> <span data-ttu-id="b92c6-118">这允许重复使用自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="b92c6-118">This allows reuse of the custom pipeline components.</span></span>  
  
 <span data-ttu-id="b92c6-119">最后，还提供了一些可更改的 BizTalk Server 设置，从而可最大限度提高解决方案的速度。</span><span class="sxs-lookup"><span data-stu-id="b92c6-119">Finally, there are several BizTalk Server settings that you can change to squeeze out the last bit of speed from the solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b92c6-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="b92c6-120">In This Section</span></span>  
  
-   [<span data-ttu-id="b92c6-121">内联的后端调用</span><span class="sxs-lookup"><span data-stu-id="b92c6-121">Inlining Back-end Invocation</span></span>](../core/inlining-back-end-invocation.md)  
  
-   [<span data-ttu-id="b92c6-122">在服务中有效地使用 SSO 面向解决方案</span><span class="sxs-lookup"><span data-stu-id="b92c6-122">Using SSO Efficiently in the Service Oriented Solution</span></span>](../core/using-sso-efficiently-in-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="b92c6-123">使用从服务的管道面向解决方案</span><span class="sxs-lookup"><span data-stu-id="b92c6-123">Using Pipelines from the Service Oriented Solution</span></span>](../core/using-pipelines-from-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="b92c6-124">优化服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="b92c6-124">Tuning the Service Oriented Solution</span></span>](../core/tuning-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="b92c6-125">分离传输类型和处理</span><span class="sxs-lookup"><span data-stu-id="b92c6-125">Decoupling Transport Type and Processing</span></span>](../core/decoupling-transport-type-and-processing.md)