---
title: 面向服务的实现重点推荐的解决方案 |Microsoft Docs
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
ms.openlocfilehash: 47cc270e442964d46307a81c097df18085696107
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332497"
---
# <a name="implementation-highlights-of-the-service-oriented-solution"></a><span data-ttu-id="b6bd1-102">面向服务的实现重点推荐的解决方案</span><span class="sxs-lookup"><span data-stu-id="b6bd1-102">Implementation Highlights of the Service Oriented Solution</span></span>
<span data-ttu-id="b6bd1-103">解决方案用于解决特定的上下文中的特定问题。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-103">A solution solves a particular problem in a specific context.</span></span> <span data-ttu-id="b6bd1-104">面向服务的解决方案也不例外，特定于 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和方案。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-104">The Service Oriented solution is no exception and is specific to Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and the scenario.</span></span> <span data-ttu-id="b6bd1-105">有关 Woodgrove Bank 方案的详细信息，请参阅[了解面向服务的解决方案](../core/understanding-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-105">For more information about the Woodgrove Bank scenario, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md).</span></span>  
  
 <span data-ttu-id="b6bd1-106">在开发该方案，几个方面被证明是响应时间降低到可接受级别的瓶颈。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-106">While developing the scenario, several areas proved to be bottlenecks in reducing response times to an acceptable level.</span></span> <span data-ttu-id="b6bd1-107">将消息发送到后端系统使用的适配器有明显的延迟在获取响应。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-107">Sending messages to the backend systems using the adapters introduces significant latency in getting back responses.</span></span> <span data-ttu-id="b6bd1-108">一般情况下，适配器本身提供延迟非常低。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-108">In general, adapters by themselves offer very low latency.</span></span> <span data-ttu-id="b6bd1-109">但是，BizTalk 的分布式的结构要求适配器与使用 messagebox 的业务流程主机实例进行通信。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-109">However, the distributed architecture of BizTalk requires adapters to communicate with the orchestration host instances using the message box.</span></span> <span data-ttu-id="b6bd1-110">这给数据库带来了往返行程，从而影响延迟时间。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-110">This introduces round trips to the database and affects latency times.</span></span> <span data-ttu-id="b6bd1-111">出于此原因，解决方案 （最快的版本） 生成的内联版本中的业务流程本身的适配器功能的后端系统直接调用。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-111">For this reason, the inline version of the solution (the fastest version) builds the adapter functionality in the orchestration itself calls the back-end systems directly.</span></span> <span data-ttu-id="b6bd1-112">使用三个不同的后端系统，这意味着可能三个不同的机制与后端系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-112">With three different back-end systems, that means potentially three different mechanisms to communicate with the back-end systems.</span></span>  
  
 <span data-ttu-id="b6bd1-113">事实证明，性能问题的另一个区域从企业单一登录 (SSO) 检索配置数据。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-113">Another area that proved a performance problem was retrieving configuration data from Enterprise Single Sign-On (SSO).</span></span> <span data-ttu-id="b6bd1-114">若要在缩短检索时间的同时保留方便使用和 SSO 的通用性，该解决方案时，可使用本地缓存的配置值。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-114">To retain the convenience and universality of SSO while speeding up retrieval time, the solution uses a local cache for configuration values.</span></span> <span data-ttu-id="b6bd1-115">使用 SSO 还允许更方便地管理配置数据。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-115">Using SSO also allows easier management of the configuration data.</span></span> <span data-ttu-id="b6bd1-116">添加其他主机实例以满足延迟和性能要求不需要更改运行主机实例的服务器上的设置。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-116">Adding additional host instances to meet latency and performance requirements does not require changing settings on the server running the host instance.</span></span>  
  
 <span data-ttu-id="b6bd1-117">另一个不同寻常的解决方案直接从代码调用管道。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-117">Another unusual element of the solution is calling pipelines directly from code.</span></span> <span data-ttu-id="b6bd1-118">这允许重复使用的自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-118">This allows reuse of the custom pipeline components.</span></span>  
  
 <span data-ttu-id="b6bd1-119">最后，有多个 BizTalk Server 设置，可以更改最大限度的最后一从解决方案的速度。</span><span class="sxs-lookup"><span data-stu-id="b6bd1-119">Finally, there are several BizTalk Server settings that you can change to squeeze out the last bit of speed from the solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b6bd1-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="b6bd1-120">In This Section</span></span>  
  
-   [<span data-ttu-id="b6bd1-121">内联后端调用</span><span class="sxs-lookup"><span data-stu-id="b6bd1-121">Inlining Back-end Invocation</span></span>](../core/inlining-back-end-invocation.md)  
  
-   [<span data-ttu-id="b6bd1-122">在服务中有效使用 SSO 面向解决方案</span><span class="sxs-lookup"><span data-stu-id="b6bd1-122">Using SSO Efficiently in the Service Oriented Solution</span></span>](../core/using-sso-efficiently-in-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="b6bd1-123">使用该服务中的管道面向解决方案</span><span class="sxs-lookup"><span data-stu-id="b6bd1-123">Using Pipelines from the Service Oriented Solution</span></span>](../core/using-pipelines-from-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="b6bd1-124">优化面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="b6bd1-124">Tuning the Service Oriented Solution</span></span>](../core/tuning-the-service-oriented-solution.md)  
  
-   [<span data-ttu-id="b6bd1-125">分离传输类型和处理</span><span class="sxs-lookup"><span data-stu-id="b6bd1-125">Decoupling Transport Type and Processing</span></span>](../core/decoupling-transport-type-and-processing.md)