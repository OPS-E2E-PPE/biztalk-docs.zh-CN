---
title: "有关路线 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d34632f-8652-49dd-97b7-2513aacc1bd7
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66a9a759a6afdd55c3c1646d02c480aa193261aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="about-itineraries"></a><span data-ttu-id="d05d7-102">有关路线</span><span class="sxs-lookup"><span data-stu-id="d05d7-102">About Itineraries</span></span>
<span data-ttu-id="d05d7-103">一条路线是的表示形式执行的处理指令基于序列的 ESB 中介策略[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]可扩展格式。</span><span class="sxs-lookup"><span data-stu-id="d05d7-103">An itinerary is a representation of an ESB mediation policy for executing a sequence of processing instructions based on the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extensible format.</span></span> <span data-ttu-id="d05d7-104">一条路线可被视为描述一系列由配置是与中介组件关联的声明性路线服务的高级中介语言[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心引擎。</span><span class="sxs-lookup"><span data-stu-id="d05d7-104">An itinerary can be viewed as a high-level mediation language that describes a sequence of declarative itinerary services that are associated with mediation components by configuration of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core engine.</span></span> <span data-ttu-id="d05d7-105">你可以设计中介流来描述应如何处理消息，而且您可以组织 visual 绘制整个流中。</span><span class="sxs-lookup"><span data-stu-id="d05d7-105">You can design mediation flows to describe how messages should be processed, and you can organize the entire flow as a visual drawing.</span></span> <span data-ttu-id="d05d7-106">在运行时，[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]核心引擎执行路线设计器生成的路线。</span><span class="sxs-lookup"><span data-stu-id="d05d7-106">At run time, the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core engine executes the itinerary produced by Itinerary Designer.</span></span>  
  
## <a name="the-itinerary-designer-surface"></a><span data-ttu-id="d05d7-107">路线设计器图面</span><span class="sxs-lookup"><span data-stu-id="d05d7-107">The Itinerary Designer Surface</span></span>  
 <span data-ttu-id="d05d7-108">路线设计器图面是可视化设计器中用于创建[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线并将这些路线导出到运行时间格式。</span><span class="sxs-lookup"><span data-stu-id="d05d7-108">The Itinerary Designer surface is a visual designer that is used to create [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itineraries and to export these itineraries into run-time format.</span></span> <span data-ttu-id="d05d7-109">它是指可拖动的项从工具箱中，一个画布，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="d05d7-109">It is a canvas to which you can drag items from the Toolbox, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="d05d7-110">![路线设计器](../esb-toolkit/media/ch5-itinerarydesigner.gif "Ch5 ItineraryDesigner")</span><span class="sxs-lookup"><span data-stu-id="d05d7-110">![Itinerary Designer](../esb-toolkit/media/ch5-itinerarydesigner.gif "Ch5-ItineraryDesigner")</span></span>  
  
 <span data-ttu-id="d05d7-111">**图 1**</span><span class="sxs-lookup"><span data-stu-id="d05d7-111">**Figure 1**</span></span>  
  
 <span data-ttu-id="d05d7-112">**路线设计器图面**</span><span class="sxs-lookup"><span data-stu-id="d05d7-112">**Itinerary Designer surface**</span></span>  
  
 <span data-ttu-id="d05d7-113">路线的名称显示在路线设计器和 Microsoft Visual Studio 标题栏中，顶部选项卡。</span><span class="sxs-lookup"><span data-stu-id="d05d7-113">The name of the itinerary is displayed on the top tab of the Itinerary Designer and in the Microsoft Visual Studio title bar.</span></span> <span data-ttu-id="d05d7-114">设计图面本身是单个区域，包含描述的路线实际的消息流的模型元素。</span><span class="sxs-lookup"><span data-stu-id="d05d7-114">The design surface itself is a single area and contains model elements that describe the actual message flow of the itinerary.</span></span> <span data-ttu-id="d05d7-115">ItineraryDSL 使您可以修改使用 Visual Studio 属性窗口的模型元素属性。</span><span class="sxs-lookup"><span data-stu-id="d05d7-115">The ItineraryDSL enables you to modify the model element properties using the Visual Studio Properties window.</span></span>  
  
## <a name="itinerary-designer-toolbox"></a><span data-ttu-id="d05d7-116">路线设计器工具箱</span><span class="sxs-lookup"><span data-stu-id="d05d7-116">Itinerary Designer Toolbox</span></span>  
 <span data-ttu-id="d05d7-117">Visual Studio 工具箱中包含表示的工具集的选项卡。</span><span class="sxs-lookup"><span data-stu-id="d05d7-117">The Visual Studio Toolbox contains tabs, which represent sets of tools.</span></span> <span data-ttu-id="d05d7-118">当你打开使用路线设计器的 Visual Studio 项目时，该工具箱中包含两个选项卡：**常规**选项卡和**ItineraryDsl**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d05d7-118">When you open a Visual Studio project that uses Itinerary Designer, the Toolbox contains two tabs: the **General** tab and the **ItineraryDsl** tabs.</span></span> <span data-ttu-id="d05d7-119">**ItineraryDsl**选项卡包含以下工具：</span><span class="sxs-lookup"><span data-stu-id="d05d7-119">The **ItineraryDsl** tab contains the following tools:</span></span>  
  
-   <span data-ttu-id="d05d7-120">**路线服务工具**。</span><span class="sxs-lookup"><span data-stu-id="d05d7-120">**Itinerary Service tool**.</span></span> <span data-ttu-id="d05d7-121">此模型元素对应于路线中介服务，而表示一条处理指令。</span><span class="sxs-lookup"><span data-stu-id="d05d7-121">This model element corresponds to the itinerary mediation service and represents a processing instruction.</span></span>  
  
-   <span data-ttu-id="d05d7-122">**连接器工具**。</span><span class="sxs-lookup"><span data-stu-id="d05d7-122">**Connector tool**.</span></span> <span data-ttu-id="d05d7-123">此模型元素定义在路线设计器图面上的单个模型元素之间的关系。</span><span class="sxs-lookup"><span data-stu-id="d05d7-123">This model element defines the relationship between individual model elements on the Itinerary Designer surface.</span></span>  
  
-   <span data-ttu-id="d05d7-124">**关闭负载增加工具**。</span><span class="sxs-lookup"><span data-stu-id="d05d7-124">**Off-Ramp tool**.</span></span> <span data-ttu-id="d05d7-125">此模型元素对应于出口发送消息。</span><span class="sxs-lookup"><span data-stu-id="d05d7-125">This model element corresponds to the off-ramp that sends a message.</span></span> <span data-ttu-id="d05d7-126">路线设计器允许多个关闭的渐变每个模型。</span><span class="sxs-lookup"><span data-stu-id="d05d7-126">The Itinerary Designer allows multiple off-ramps per model.</span></span>  
  
-   <span data-ttu-id="d05d7-127">**在负载增加工具**。</span><span class="sxs-lookup"><span data-stu-id="d05d7-127">**On-Ramp tool**.</span></span> <span data-ttu-id="d05d7-128">此模型元素对应于入口接收消息。</span><span class="sxs-lookup"><span data-stu-id="d05d7-128">This model element corresponds to an on-ramp that receives a message.</span></span> <span data-ttu-id="d05d7-129">路线设计器，只有一个上的负载增加每个模型。</span><span class="sxs-lookup"><span data-stu-id="d05d7-129">The Itinerary Designer allows only one on-ramp per model.</span></span>  
  
-   <span data-ttu-id="d05d7-130">**路线 Broker 服务工具**。</span><span class="sxs-lookup"><span data-stu-id="d05d7-130">**Itinerary Broker Service tool**.</span></span> <span data-ttu-id="d05d7-131">此模型元素对应于路线中介服务，允许具有多个输入和多个输出的定义的消息流。</span><span class="sxs-lookup"><span data-stu-id="d05d7-131">This model element corresponds to the itinerary mediation service that allows defined message flow with multiple inputs and multiple outputs.</span></span>  
  
-   <span data-ttu-id="d05d7-132">**路线 Broker 输出端口**。</span><span class="sxs-lookup"><span data-stu-id="d05d7-132">**Itinerary Broker Output port**.</span></span> <span data-ttu-id="d05d7-133">此模型元素对应于路线 Broker 服务的单个输出端口。</span><span class="sxs-lookup"><span data-stu-id="d05d7-133">This model element corresponds to the single output port of the Itinerary Broker Service.</span></span> <span data-ttu-id="d05d7-134">路线 Broker 服务模型元素允许多个输出端口。</span><span class="sxs-lookup"><span data-stu-id="d05d7-134">The Itinerary Broker Service model element allows multiple output ports.</span></span>  
  
## <a name="steps-in-itinerary-development"></a><span data-ttu-id="d05d7-135">路线开发中的步骤</span><span class="sxs-lookup"><span data-stu-id="d05d7-135">Steps in Itinerary Development</span></span>  
 <span data-ttu-id="d05d7-136">若要开发路线，它表示 ESB 中介流，通常应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d05d7-136">To develop an itinerary, which represents ESB mediation flow, you should typically perform the following actions:</span></span>  
  
-   <span data-ttu-id="d05d7-137">添加模型元素来表示的消息处理您的路线的步骤。</span><span class="sxs-lookup"><span data-stu-id="d05d7-137">Add model elements to represent the message processing steps for your itinerary.</span></span> <span data-ttu-id="d05d7-138">路线设计器提供包含用来表示不同的操作或关键抽象形状的工具箱。</span><span class="sxs-lookup"><span data-stu-id="d05d7-138">The Itinerary Designer provides a toolbox that contains shapes used to represent different actions or key abstractions.</span></span>  
  
-   <span data-ttu-id="d05d7-139">指定路线模型属性，其中包括 Microsoft BizTalk Server 管理数据库和模型导出程序配置的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="d05d7-139">Specify itinerary model properties, which include a connection string to the Microsoft BizTalk Server management database and model exporter configuration.</span></span>  
  
-   <span data-ttu-id="d05d7-140">绑定入口和出口模型元素到物理 BizTalk 接收位置和发送端口通过使用相应技术扩展器将这些模型元素相关联。</span><span class="sxs-lookup"><span data-stu-id="d05d7-140">Bind on-ramp and off-ramp model elements to physical BizTalk receive locations and send ports by associating these model elements with corresponding technology extenders.</span></span>  
  
-   <span data-ttu-id="d05d7-141">扩展程序相关联路线服务模型元素和定义所需的扩展程序的特定于技术的属性。</span><span class="sxs-lookup"><span data-stu-id="d05d7-141">Associate itinerary services model elements with extenders and define technology-specific properties required by an extender.</span></span> <span data-ttu-id="d05d7-142">为特定类型的扩展程序; 这些属性可能会有所不同它们可以表示路线中介服务属性和其运行时组件和项目与关联的 BizTalk 特定属性。</span><span class="sxs-lookup"><span data-stu-id="d05d7-142">These properties may vary for a particular type of the extender; they can represent itinerary mediation service properties and BizTalk-specific properties associated with its run-time components and artifacts.</span></span>  
  
-   <span data-ttu-id="d05d7-143">标识你可能想要作为路线中介服务引用的自定义组件。</span><span class="sxs-lookup"><span data-stu-id="d05d7-143">Identify custom components that you might want to reference as itinerary mediation services.</span></span> <span data-ttu-id="d05d7-144">例如，你可以开发作为路线服务业务流程。</span><span class="sxs-lookup"><span data-stu-id="d05d7-144">For example, you may develop an orchestration as the itinerary service.</span></span>  
  
-   <span data-ttu-id="d05d7-145">验证冲突解决程序针对的模型元素设置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]通过调用设计器图面中的解析程序服务的运行时配置。</span><span class="sxs-lookup"><span data-stu-id="d05d7-145">Verify resolver model element settings against [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] run-time configuration by invoking resolver service from the designer surface.</span></span>  
  
-   <span data-ttu-id="d05d7-146">验证和导出路线使用导出程序的运行时策略。</span><span class="sxs-lookup"><span data-stu-id="d05d7-146">Validate and export the itinerary run-time policy using an exporter.</span></span> <span data-ttu-id="d05d7-147">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]与路线设计器提供两个导出程序： 文件导出程序和数据库导出程序。</span><span class="sxs-lookup"><span data-stu-id="d05d7-147">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides two exporters with the Itinerary Designer: file exporter and database exporter.</span></span> <span data-ttu-id="d05d7-148">或者，你可以实现自定义的导出程序。</span><span class="sxs-lookup"><span data-stu-id="d05d7-148">Alternatively, you can implement a custom exporter.</span></span>  
  
-   <span data-ttu-id="d05d7-149">测试使用测试客户端应用程序或 BizUnit framework 你路线。</span><span class="sxs-lookup"><span data-stu-id="d05d7-149">Test your itinerary using test client applications or BizUnit framework.</span></span>  
  
## <a name="security-considerations-for-developing-itineraries"></a><span data-ttu-id="d05d7-150">有关开发路线的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="d05d7-150">Security Considerations for Developing Itineraries</span></span>  
 <span data-ttu-id="d05d7-151">当您设计路线时，应考虑潜在的安全问题：</span><span class="sxs-lookup"><span data-stu-id="d05d7-151">When you design itineraries, you should consider potential security issues:</span></span>  
  
-   <span data-ttu-id="d05d7-152">避免在不使用来自模型属性的证书的情况下指定用户凭据。</span><span class="sxs-lookup"><span data-stu-id="d05d7-152">Avoid specifying user credentials without using a certificate from the model properties.</span></span>  
  
-   <span data-ttu-id="d05d7-153">不引用 BizTalk 接收端口与接收允许匿名访问的位置。</span><span class="sxs-lookup"><span data-stu-id="d05d7-153">Do not refer to BizTalk receive ports with receive locations that allow anonymous access.</span></span>  
  
-   <span data-ttu-id="d05d7-154">如果路线消息包含敏感数据，请保护消息或传输通道。</span><span class="sxs-lookup"><span data-stu-id="d05d7-154">Protect the message or transport channel if the itinerary message contains sensitive data.</span></span>  
  
-   <span data-ttu-id="d05d7-155">如果消息包含需要在传输过程中保护的敏感数据，请保护带管道组件的消息框中的消息。</span><span class="sxs-lookup"><span data-stu-id="d05d7-155">Protect messages in the Message box with a pipeline component if the messages contain sensitive data that needs to be protected while in transit.</span></span>