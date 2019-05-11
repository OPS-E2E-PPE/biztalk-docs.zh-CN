---
title: 使用动态转换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1e4aac7-242a-41b6-8df4-4881371f44d1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81476c0bdcdbcf3d5647dd7bc83b37a70d6e7557
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396445"
---
# <a name="using-dynamic-transformation"></a><span data-ttu-id="e9f13-102">使用动态转换</span><span class="sxs-lookup"><span data-stu-id="e9f13-102">Using Dynamic Transformation</span></span>
## <a name="overview"></a><span data-ttu-id="e9f13-103">概述</span><span class="sxs-lookup"><span data-stu-id="e9f13-103">Overview</span></span>  
 <span data-ttu-id="e9f13-104">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]动态转换为支持三种机制：</span><span class="sxs-lookup"><span data-stu-id="e9f13-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports three mechanisms for dynamic transformation:</span></span>  
  
- <span data-ttu-id="e9f13-105">作为业务流程实现了动态转换代理</span><span class="sxs-lookup"><span data-stu-id="e9f13-105">A dynamic transformation agent implemented as an orchestration</span></span>  
  
- <span data-ttu-id="e9f13-106">动态转换核心 Web 服务中包含的 Web 服务</span><span class="sxs-lookup"><span data-stu-id="e9f13-106">A dynamic transformation Web service included with the core Web services</span></span>  
  
- <span data-ttu-id="e9f13-107">ESB 管道组件执行的转换</span><span class="sxs-lookup"><span data-stu-id="e9f13-107">Transformations executed by ESB pipeline components</span></span>  
  
  <span data-ttu-id="e9f13-108">本部分重点介绍作为业务流程实现的转换代理。</span><span class="sxs-lookup"><span data-stu-id="e9f13-108">This section focuses on the transformation agent implemented as an orchestration.</span></span> <span data-ttu-id="e9f13-109">有关转换 Web 服务的信息，请参阅[使用 BizTalk ESB 工具包 Web 服务](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f13-109">For information about the transformation Web service, see [Using the BizTalk ESB Toolkit Web Services](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md).</span></span> <span data-ttu-id="e9f13-110">ESB 调度程序管道组件的信息，请参阅[使用管道支持组件](../esb-toolkit/using-the-pipeline-support-components.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f13-110">For information about the ESB Dispatcher pipeline components, see [Using the Pipeline Support Components](../esb-toolkit/using-the-pipeline-support-components.md).</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="e9f13-111">其工作原理</span><span class="sxs-lookup"><span data-stu-id="e9f13-111">How It Works</span></span>  
 <span data-ttu-id="e9f13-112">转换传递代理是指业务流程订阅消息的位置**名称**属性的当前**ServiceInstance**路线中的元素是**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="e9f13-112">The transformation delivery agent is an orchestration that subscribes to messages where the **Name** attribute of the current **ServiceInstance** element in the itinerary is **Microsoft.Practices.ESB.Services.Transform**.</span></span> <span data-ttu-id="e9f13-113">代理将执行以下一系列操作：</span><span class="sxs-lookup"><span data-stu-id="e9f13-113">The agent performs the following sequence of operations:</span></span>  
  
1.  <span data-ttu-id="e9f13-114">收到非类型化的消息 (System.Xml.XmlDocument)。</span><span class="sxs-lookup"><span data-stu-id="e9f13-114">It receives an un-typed message (System.Xml.XmlDocument).</span></span>  
  
2.  <span data-ttu-id="e9f13-115">如果可用作路线中的静态值的映射的名称，代理将尝试解析使用冲突解决程序管理器的映射的名称。</span><span class="sxs-lookup"><span data-stu-id="e9f13-115">If the name of the map is available as a static value in the itinerary, the agent attempts to resolve the name of the map using the resolver manager.</span></span>  
  
3.  <span data-ttu-id="e9f13-116">它适用于入站的源消息的适当的映射。</span><span class="sxs-lookup"><span data-stu-id="e9f13-116">It applies the appropriate map to the inbound source message.</span></span>  
  
4.  <span data-ttu-id="e9f13-117">它将映射表输出发布到 BizTalk Messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="e9f13-117">It publishes the map output to the BizTalk Message Box database.</span></span>  
  
## <a name="how-to-configure-dynamic-transformation"></a><span data-ttu-id="e9f13-118">如何配置动态转换</span><span class="sxs-lookup"><span data-stu-id="e9f13-118">How to Configure Dynamic Transformation</span></span>  
 <span data-ttu-id="e9f13-119">有关如何配置使用路线设计器的动态转换的详细信息，请参阅[路线使用路线设计器创建](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f13-119">For more information about how to configure Dynamic Transformation using Itinerary Designer, see [Creating Itineraries Using Itinerary Designer](../esb-toolkit/creating-itineraries-using-itinerary-designer.md).</span></span>  
  
## <a name="dynamic-transformation-errors"></a><span data-ttu-id="e9f13-120">动态转换错误</span><span class="sxs-lookup"><span data-stu-id="e9f13-120">Dynamic Transformation Errors</span></span>  
 <span data-ttu-id="e9f13-121">动态转换机制将创建并在以下情况下发布到 ESB 的错误消息：</span><span class="sxs-lookup"><span data-stu-id="e9f13-121">The dynamic transformation mechanism will create and publish an ESB fault message in the following cases:</span></span>  
  
- <span data-ttu-id="e9f13-122">冲突解决程序组件无法确定要应用的映射。</span><span class="sxs-lookup"><span data-stu-id="e9f13-122">The resolver component cannot determine which map to apply.</span></span>  
  
- <span data-ttu-id="e9f13-123">指定的映射不可用 （例如，您指定不正确的映射类型或映射在 BizTalk Server 2009 中尚不支持部署）。</span><span class="sxs-lookup"><span data-stu-id="e9f13-123">The specified map is not available (for example, you specified an incorrect map type or a map not yet deployed in BizTalk Server 2009).</span></span>  
  
- <span data-ttu-id="e9f13-124">在映射期间发生故障 （例如，源文档不是正确的源类型或自定义函数中的外部程序集未部署到 BizTalk 映射引用的）。</span><span class="sxs-lookup"><span data-stu-id="e9f13-124">A failure occurs during mapping (for example, the source document is not of the correct source type or the map references a custom function in an external assembly is not deployed to BizTalk).</span></span>  
  
- <span data-ttu-id="e9f13-125">在实时 (JIT) 解析映射类型的过程中发生异常。</span><span class="sxs-lookup"><span data-stu-id="e9f13-125">An exception occurs during just-in-time (JIT) resolution of the map type.</span></span>  
  
- <span data-ttu-id="e9f13-126">没有订阅服务器上存在的输出消息。</span><span class="sxs-lookup"><span data-stu-id="e9f13-126">No subscriber exists for the output message.</span></span>  
  
- <span data-ttu-id="e9f13-127">会发生任何系统异常。</span><span class="sxs-lookup"><span data-stu-id="e9f13-127">Any system exception occurs.</span></span>  
  
  <span data-ttu-id="e9f13-128">它是开发人员负责提供用来填充异常消息和创建处理程序来对异常做出反应的上下文信息。</span><span class="sxs-lookup"><span data-stu-id="e9f13-128">It is the developer's responsibility to provide the context information used to populate the exception messages and create handlers to react to the exception.</span></span> <span data-ttu-id="e9f13-129">一些数据自动可用，并且一般处理程序将选取异常消息，如果没有目标处理程序指定了或可用。</span><span class="sxs-lookup"><span data-stu-id="e9f13-129">Some of the data is automatically available, and a generic handler will pick up the exception message if no target handler is specified or available.</span></span> <span data-ttu-id="e9f13-130">有关处理动态转换异常的详细信息，请参阅[使用 ESB 异常管理](../esb-toolkit/using-esb-exception-management.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f13-130">For more information about handling dynamic transformation exceptions, see [Using ESB Exception Management](../esb-toolkit/using-esb-exception-management.md).</span></span>