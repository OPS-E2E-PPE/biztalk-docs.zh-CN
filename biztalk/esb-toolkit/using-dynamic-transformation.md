---
title: "使用动态转换 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1e4aac7-242a-41b6-8df4-4881371f44d1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d7f6bc57d009e558188950d9bcb0387f808f835
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-dynamic-transformation"></a><span data-ttu-id="7e9d1-102">使用动态转换</span><span class="sxs-lookup"><span data-stu-id="7e9d1-102">Using Dynamic Transformation</span></span>
## <a name="overview"></a><span data-ttu-id="7e9d1-103">概述</span><span class="sxs-lookup"><span data-stu-id="7e9d1-103">Overview</span></span>  
 <span data-ttu-id="7e9d1-104">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态转换支持三种机制：</span><span class="sxs-lookup"><span data-stu-id="7e9d1-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports three mechanisms for dynamic transformation:</span></span>  
  
-   <span data-ttu-id="7e9d1-105">作为业务流程实现动态转换代理</span><span class="sxs-lookup"><span data-stu-id="7e9d1-105">A dynamic transformation agent implemented as an orchestration</span></span>  
  
-   <span data-ttu-id="7e9d1-106">动态转换核心 Web 服务中包含的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="7e9d1-106">A dynamic transformation Web service included with the core Web services</span></span>  
  
-   <span data-ttu-id="7e9d1-107">由 ESB 管道组件执行的转换</span><span class="sxs-lookup"><span data-stu-id="7e9d1-107">Transformations executed by ESB pipeline components</span></span>  
  
 <span data-ttu-id="7e9d1-108">本部分重点介绍实现按业务流程的转换代理。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-108">This section focuses on the transformation agent implemented as an orchestration.</span></span> <span data-ttu-id="7e9d1-109">有关转换 Web 服务的信息，请参阅[使用 BizTalk ESB 工具包 Web 服务](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-109">For information about the transformation Web service, see [Using the BizTalk ESB Toolkit Web Services](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md).</span></span> <span data-ttu-id="7e9d1-110">有关 ESB 调度程序管道组件的信息，请参阅[使用管道支持组件](../esb-toolkit/using-the-pipeline-support-components.md)。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-110">For information about the ESB Dispatcher pipeline components, see [Using the Pipeline Support Components](../esb-toolkit/using-the-pipeline-support-components.md).</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="7e9d1-111">它是如何工作</span><span class="sxs-lookup"><span data-stu-id="7e9d1-111">How It Works</span></span>  
 <span data-ttu-id="7e9d1-112">转换传递代理是订阅的消息的业务流程其中**名称**属性的当前**服务实例**路线中的元素是**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-112">The transformation delivery agent is an orchestration that subscribes to messages where the **Name** attribute of the current **ServiceInstance** element in the itinerary is **Microsoft.Practices.ESB.Services.Transform**.</span></span> <span data-ttu-id="7e9d1-113">代理可执行以下操作序列：</span><span class="sxs-lookup"><span data-stu-id="7e9d1-113">The agent performs the following sequence of operations:</span></span>  
  
1.  <span data-ttu-id="7e9d1-114">接收非类型化的消息 (System.Xml.XmlDocument)。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-114">It receives an un-typed message (System.Xml.XmlDocument).</span></span>  
  
2.  <span data-ttu-id="7e9d1-115">如果为路线中的静态值可用映射的名称，代理将尝试解析映射使用解析程序管理器的名称。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-115">If the name of the map is available as a static value in the itinerary, the agent attempts to resolve the name of the map using the resolver manager.</span></span>  
  
3.  <span data-ttu-id="7e9d1-116">它适用于入站的源消息的适当的映射。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-116">It applies the appropriate map to the inbound source message.</span></span>  
  
4.  <span data-ttu-id="7e9d1-117">它将映射表输出发布到 BizTalk 消息框数据库。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-117">It publishes the map output to the BizTalk Message Box database.</span></span>  
  
## <a name="how-to-configure-dynamic-transformation"></a><span data-ttu-id="7e9d1-118">如何配置动态转换</span><span class="sxs-lookup"><span data-stu-id="7e9d1-118">How to Configure Dynamic Transformation</span></span>  
 <span data-ttu-id="7e9d1-119">有关如何配置使用路线设计器的动态转换的详细信息，请参阅[创建路线使用路线设计器](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-119">For more information about how to configure Dynamic Transformation using Itinerary Designer, see [Creating Itineraries Using Itinerary Designer](../esb-toolkit/creating-itineraries-using-itinerary-designer.md).</span></span>  
  
## <a name="dynamic-transformation-errors"></a><span data-ttu-id="7e9d1-120">动态转换错误</span><span class="sxs-lookup"><span data-stu-id="7e9d1-120">Dynamic Transformation Errors</span></span>  
 <span data-ttu-id="7e9d1-121">动态转换机制将创建并在以下情况下发布 ESB 错误消息：</span><span class="sxs-lookup"><span data-stu-id="7e9d1-121">The dynamic transformation mechanism will create and publish an ESB fault message in the following cases:</span></span>  
  
-   <span data-ttu-id="7e9d1-122">无法确定冲突解决程序组件，它们将分别映射。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-122">The resolver component cannot determine which map to apply.</span></span>  
  
-   <span data-ttu-id="7e9d1-123">指定的地图不可用 （例如，你指定为不正确的地图类型或地图尚未部署 BizTalk Server 2009 年）。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-123">The specified map is not available (for example, you specified an incorrect map type or a map not yet deployed in BizTalk Server 2009).</span></span>  
  
-   <span data-ttu-id="7e9d1-124">映射过程中出现故障 （例如，源文档的不是正确的源类型或自定义函数的外部程序集中未部署到 BizTalk 映射引用）。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-124">A failure occurs during mapping (for example, the source document is not of the correct source type or the map references a custom function in an external assembly is not deployed to BizTalk).</span></span>  
  
-   <span data-ttu-id="7e9d1-125">映射类型的解析 — 在实时 (JIT) 过程中发生异常。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-125">An exception occurs during just-in-time (JIT) resolution of the map type.</span></span>  
  
-   <span data-ttu-id="7e9d1-126">没有任何订户存在输出消息。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-126">No subscriber exists for the output message.</span></span>  
  
-   <span data-ttu-id="7e9d1-127">会发生任何系统异常。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-127">Any system exception occurs.</span></span>  
  
 <span data-ttu-id="7e9d1-128">它由开发人员负责提供用来填充异常消息和创建处理程序来响应该异常的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-128">It is the developer's responsibility to provide the context information used to populate the exception messages and create handlers to react to the exception.</span></span> <span data-ttu-id="7e9d1-129">某些数据会自动提供，和泛型处理程序会选取异常消息，如果没有目标处理指定了或可用。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-129">Some of the data is automatically available, and a generic handler will pick up the exception message if no target handler is specified or available.</span></span> <span data-ttu-id="7e9d1-130">有关处理动态转换异常的详细信息，请参阅[使用 ESB 异常管理](../esb-toolkit/using-esb-exception-management.md)。</span><span class="sxs-lookup"><span data-stu-id="7e9d1-130">For more information about handling dynamic transformation exceptions, see [Using ESB Exception Management](../esb-toolkit/using-esb-exception-management.md).</span></span>