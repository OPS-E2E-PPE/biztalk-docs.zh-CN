---
title: "动态解析和路由概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a9a32491-132b-4b25-ac8c-4a927052f0be
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 341b8389530ac85fdc459816f5691f3b814fbd56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-resolution-and-routing-overview"></a><span data-ttu-id="8dd39-102">动态解析和路由概述</span><span class="sxs-lookup"><span data-stu-id="8dd39-102">Dynamic Resolution and Routing Overview</span></span>
<span data-ttu-id="8dd39-103">ESB 解析程序类支持以下运行时解决方法：</span><span class="sxs-lookup"><span data-stu-id="8dd39-103">The ESB Resolver classes support run-time resolution of the following:</span></span>  
  
-   <span data-ttu-id="8dd39-104">消息传递终结点</span><span class="sxs-lookup"><span data-stu-id="8dd39-104">Message delivery endpoints</span></span>  
  
-   <span data-ttu-id="8dd39-105">转换的的映射</span><span class="sxs-lookup"><span data-stu-id="8dd39-105">Maps for transformation</span></span>  
  
-   <span data-ttu-id="8dd39-106">终结点配置</span><span class="sxs-lookup"><span data-stu-id="8dd39-106">Endpoint configuration</span></span>  
  
-   <span data-ttu-id="8dd39-107">自定义的服务元数据</span><span class="sxs-lookup"><span data-stu-id="8dd39-107">Custom service metadata</span></span>  
  
-   <span data-ttu-id="8dd39-108">服务器端路线</span><span class="sxs-lookup"><span data-stu-id="8dd39-108">Server-side itineraries</span></span>  
  
 <span data-ttu-id="8dd39-109">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用解析程序连接字符串以在消息到达时尝试解析地图以及终结点。</span><span class="sxs-lookup"><span data-stu-id="8dd39-109">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses resolver connection strings to attempt resolution of maps and endpoints when messages arrive.</span></span> <span data-ttu-id="8dd39-110">这些连接字符串中可能存在路线的 SOAP 标头的消息到达时，或它们可能在使用一个以下管道组件的自定义管道中设置时： ESB 路线选择器、 ESB 调度程序或 ESB 调度程序反汇编。</span><span class="sxs-lookup"><span data-stu-id="8dd39-110">These connections strings may exist in the itinerary SOAP header of messages when they arrive, or they may be set in a custom pipeline using one of the following pipeline components: ESB Itinerary Selector, ESB Dispatcher, or ESB Dispatcher Disassemble.</span></span> <span data-ttu-id="8dd39-111">解决方法是更高版本在使用 ESB 解析程序和适配器提供程序框架组件的"实时"(JIT) 解析功能处理生命周期中。</span><span class="sxs-lookup"><span data-stu-id="8dd39-111">Resolution occurs later in the processing life cycle using the "just-in-time" (JIT) resolution capabilities of the ESB Resolver and Adapter Provider Framework components.</span></span>  
  
 <span data-ttu-id="8dd39-112">例如，如果动态转换代理收到一条消息必须映射，但尚未确定映射名称，它将尝试使用关联的冲突解决程序执行解析。</span><span class="sxs-lookup"><span data-stu-id="8dd39-112">For example, if the dynamic transformation agent receives a message that it must map, but the map name has not yet been determined, it will attempt to use the associated resolver to perform the resolution.</span></span> <span data-ttu-id="8dd39-113">如果 JIT 解析失败，这划分为错误，系统将生成一条异常消息。</span><span class="sxs-lookup"><span data-stu-id="8dd39-113">If JIT resolution fails, which is classed as an error, the system generates an exception message.</span></span>  
  
 <span data-ttu-id="8dd39-114">以下数据存储区或解析机制，可以查询中的冲突解决程序和适配器提供程序框架：</span><span class="sxs-lookup"><span data-stu-id="8dd39-114">The Resolver and Adapter Provider Framework can query the following data stores or resolution mechanisms:</span></span>  
  
-   <span data-ttu-id="8dd39-115">硬编码的地图或终结点，在其中案例动态解决不会发生</span><span class="sxs-lookup"><span data-stu-id="8dd39-115">Hard-coded maps or endpoints, in which case dynamic resolution does not occur</span></span>  
  
-   <span data-ttu-id="8dd39-116">业务规则引擎 (BRE) 策略</span><span class="sxs-lookup"><span data-stu-id="8dd39-116">A Business Rules Engine (BRE) policy</span></span>  
  
-   <span data-ttu-id="8dd39-117">实现自定义程序集**IResolveProvider**接口</span><span class="sxs-lookup"><span data-stu-id="8dd39-117">A custom assembly implementing the **IResolveProvider** interface</span></span>  
  
-   <span data-ttu-id="8dd39-118">在消息上 XPath 查询</span><span class="sxs-lookup"><span data-stu-id="8dd39-118">An XPath query over the message</span></span>  
  
-   <span data-ttu-id="8dd39-119">通用、 描述、 发现和集成 (UDDI) 查找</span><span class="sxs-lookup"><span data-stu-id="8dd39-119">A Universal Description, Discovery, and Integration (UDDI) lookup</span></span>