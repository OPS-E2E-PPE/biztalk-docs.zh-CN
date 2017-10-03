---
title: "如何： 实现基于内容的路由使用消息上下文属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 952af792-5762-4b04-9087-980bb3323568
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e47235978960ac89f4ea276c4c4a60c8ddf16e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-implement-content-based-routing-using-message-context-properties"></a><span data-ttu-id="f19cd-102">如何： 实现基于内容的路由使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="f19cd-102">How to: Implement Content-Based Routing Using Message Context Properties</span></span>
## <a name="goal"></a><span data-ttu-id="f19cd-103">目的</span><span class="sxs-lookup"><span data-stu-id="f19cd-103">Goal</span></span>  
 <span data-ttu-id="f19cd-104">本部分演示如何使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线设计器来创建一条路线选择消息接收方根据消息上下文属性，然后将消息路由到此收件人使用路线 Broker 消息传递服务。</span><span class="sxs-lookup"><span data-stu-id="f19cd-104">This section demonstrates how to use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Itinerary Designer to create an itinerary that selects a message recipient based on the message context property and then routes a message to that recipient using the Itinerary Broker messaging service.</span></span>  
  
 <span data-ttu-id="f19cd-105">在本主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f19cd-105">In this topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="f19cd-106">使用路线 broker 和使用静态解析程序的两个路由服务创建一条路线。</span><span class="sxs-lookup"><span data-stu-id="f19cd-106">Create an itinerary with an itinerary broker and two routing services with static resolvers.</span></span>  
  
-   <span data-ttu-id="f19cd-107">测试路线使用路线测试客户端示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="f19cd-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f19cd-108">在当前实现中提供了不基于业务流程的 broker 服务。</span><span class="sxs-lookup"><span data-stu-id="f19cd-108">No orchestration-based broker service is provided in the current implementation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f19cd-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="f19cd-109">Prerequisites</span></span>  
 <span data-ttu-id="f19cd-110">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="f19cd-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="f19cd-111">步骤</span><span class="sxs-lookup"><span data-stu-id="f19cd-111">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="f19cd-112">若要创建 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="f19cd-112">To create an ESB Itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="f19cd-113">在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="f19cd-113">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="f19cd-114">在解决方案资源管理器，右键单击**ItineraryLibrary**，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-114">In Solution Explorer, right-click **ItineraryLibrary**, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="f19cd-115">在**添加新项**对话框中，单击**ItineraryDsl**在模板窗格中。</span><span class="sxs-lookup"><span data-stu-id="f19cd-115">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="f19cd-116">在**名称**框中，键入**ChoiceRouter**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-116">In the **Name** box, type **ChoiceRouter**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="f19cd-117">若要配置路线的属性</span><span class="sxs-lookup"><span data-stu-id="f19cd-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="f19cd-118">在 Visual Studio 中，单击的设计图面**ChoiceRouter**路线。</span><span class="sxs-lookup"><span data-stu-id="f19cd-118">In Visual Studio, click the design surface of the **ChoiceRouter** itinerary.</span></span> <span data-ttu-id="f19cd-119">在**ChoiceRouter**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-119">In the **ChoiceRouter** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-120">在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-121">在**扩展程序设置**部分中，单击旁边的省略号按钮 （...）**路线 XML 文件**属性。</span><span class="sxs-lookup"><span data-stu-id="f19cd-121">In the **Extender Settings** section, click the ellipsis button (...) next to the **Itinerary XML file** property.</span></span>  
  
    3.  <span data-ttu-id="f19cd-122">在**导出模式**属性下拉列表中，单击**Strict**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-122">In the **Export Mode** property drop-down list, click **Strict**.</span></span>  
  
    4.  <span data-ttu-id="f19cd-123">在**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\ChoiceRouter**中**文件名**框中，并依次**保存**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-123">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\ChoiceRouter** in the **File name** box, and then click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f19cd-124">此步骤允许您路线作为 XML 导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="f19cd-124">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="f19cd-125">通过将一条路线到本地文件的位置，而不导出到路线的数据库中，你可以测试路线使用 ESB 测试客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="f19cd-125">By exporting an itinerary to a local file location, instead of to the itinerary database, you can test the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="f19cd-126">你将完成本操作方法主题中后面此过程。</span><span class="sxs-lookup"><span data-stu-id="f19cd-126">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="f19cd-127">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="f19cd-127">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="f19cd-128">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-128">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="f19cd-129">在 OnRamp1 属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-129">In the OnRamp1 Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-130">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-130">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-131">在**扩展程序**下拉列表中，单击**上负载增加扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-131">In the **Extender** drop-down list, click **On-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-132">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-132">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="f19cd-133">在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-133">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="f19cd-134">从工具箱中，拖动**路线 Broker 服务**模型元素到设计器图面，然后将其放到右侧**上负载增加**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-134">From the Toolbox, drag an **Itinerary Broker Service** model element to the designer surface, and then place it to the right side of the **On-Ramp** model element.</span></span> <span data-ttu-id="f19cd-135">在**ItineraryBrokerService1**，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-135">In the **ItineraryBrokerService1**, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-136">单击**名称**属性，再然后键入**RouteBrokerService**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-136">Click the **Name** property, and then type **RouteBrokerService**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-137">在**扩展程序**下拉列表中，单击**消息传递代理扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-137">In the **Extender** drop-down list, click **Messaging Broker Extender**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-138">在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-138">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="f19cd-139">在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-139">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**.</span></span>  
  
3.  <span data-ttu-id="f19cd-140">右键单击**筛选器**集合，，然后单击**添加新的筛选器**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-140">Right-click the **Filter** collection, and then click **Add new Filter**.</span></span> <span data-ttu-id="f19cd-141">在**Filter1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-141">In the **Filter1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-142">单击**名称**属性，再然后键入**ASMXFilter**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-142">Click the **Name** property, and then type **ASMXFilter**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-143">单击**筛选器**实现下拉列表，然后单击**XPath 筛选器**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-143">Click the **Filter** Implementation drop-down list, and then click **XPath Filter**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-144">单击**表达式**属性，再然后键入**计数 (/ ContextProperties/属性 [@name= InboundTransportLocation] [包含 (。，ProcessItinerary.asmx)]) > 0**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-144">Click the **Expression** property, and then type **count(/ContextProperties/Property[@name='InboundTransportLocation'][contains(., 'ProcessItinerary.asmx')]) > 0**.</span></span>  
  
4.  <span data-ttu-id="f19cd-145">右键单击**筛选器**集合，，然后单击**添加新的筛选器**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-145">Right-click the **Filter** collection, and then click **Add new Filter**.</span></span> <span data-ttu-id="f19cd-146">在**Filter1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-146">In the **Filter1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-147">单击**名称**属性，再然后键入**WCFFilter**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-147">Click the **Name** property, and then type **WCFFilter**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-148">单击**筛选器实现**下拉列表中，然后单击**XPath 筛选器**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-148">Click the **Filter Implementation** drop-down list, and click **XPath Filter**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-149">单击**表达式**属性，再然后键入**计数 (/ ContextProperties/属性 [@name= InboundTransportLocation] [包含 (。，ESB。ItineraryServices.WCF')]) > 0**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-149">Click the **Expression** property, and then type **count(/ContextProperties/Property[@name='InboundTransportLocation'][contains(., 'ESB.ItineraryServices.WCF')]) > 0**.</span></span>  
  
5.  <span data-ttu-id="f19cd-150">右键单击**冲突解决程序**集合**RouteBrokerService**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-150">Right-click the **Resolver** collection of the **RouteBrokerService** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="f19cd-151">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-151">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-152">单击**名称**属性，再然后键入**ResolverBrokerRoute**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-152">Click the **Name** property, and then type **ResolverBrokerRoute**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-153">在**解析程序实现**下拉列表中，单击**MessageContext 冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-153">In the **Resolver Implementation** drop-down list, click **MessageContext Resolver Extension**.</span></span>  
  
6.  <span data-ttu-id="f19cd-154">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-154">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f19cd-155">将从连接**ReceiveNAOrder**到模型元素**RouteBrokerService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-155">Drag a connection from the **ReceiveNAOrder** model element to the **RouteBrokerService** model element.</span></span>  
  
7.  <span data-ttu-id="f19cd-156">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其在**RouteBrokerService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-156">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it under the **RouteBrokerService** model element.</span></span> <span data-ttu-id="f19cd-157">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-157">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-158">单击**名称**属性，再然后键入**RouteToFileFromASMX**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-158">Click the **Name** property, and then type **RouteToFileFromASMX**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-159">在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-159">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f19cd-160">此属性定义的过程将需要在管道 （消息传送） 中的位置。</span><span class="sxs-lookup"><span data-stu-id="f19cd-160">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="f19cd-161">或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-161">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-162">在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-162">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="f19cd-163">在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-163">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
8.  <span data-ttu-id="f19cd-164">右键单击**冲突解决程序**集合**RouteToFileFromASMX**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-164">Right-click the **Resolver** collection of the **RouteToFileFromASMX** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="f19cd-165">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-165">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-166">单击**名称**属性，再然后键入**ResolverFromAsmx**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-166">Click the **Name** property, and then type **ResolverFromAsmx**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-167">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-167">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-168">在**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-168">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="f19cd-169">单击**传输位置**属性，再然后键入**c:\howtos\out\asmx%MessageId%.xml**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-169">Click the **Transport Location** property, and then type **c:\howtos\out\asmx%MessageId%.xml**.</span></span>  
  
9. <span data-ttu-id="f19cd-170">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**RouteToFileFromASMX**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-170">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToFileFromASMX** model element.</span></span> <span data-ttu-id="f19cd-171">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-171">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-172">单击**名称**属性，再然后键入**SendASMXOrder**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-172">Click the **Name** property, and then type **SendASMXOrder**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-173">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-173">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-174">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-174">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="f19cd-175">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-175">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
10. <span data-ttu-id="f19cd-176">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**RouteToFileFromASMX**模型元素和**SendASMXOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-176">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToFileFromASMX** model element and the **SendASMXOrder** model element.</span></span> <span data-ttu-id="f19cd-177">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-177">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-178">单击**名称**属性，再然后键入**SendPortFilterASMX**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-178">Click the **Name** property, and then type **SendPortFilterASMX**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-179">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-179">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-180">在**关闭负载增加**下拉列表中，展开**SendASMXOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-180">In the **Off-Ramp** drop-down list, expand **SendASMXOrder**, and then click **Send Handlers**.</span></span>  
  
11. <span data-ttu-id="f19cd-181">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f19cd-182">将从连接**RouteToFileFromASMX**到模型元素**SendPortFilterASMX**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-182">Drag a connection from the **RouteToFileFromASMX** model element to the **SendPortFilterASMX** model element.</span></span>  
  
12. <span data-ttu-id="f19cd-183">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-183">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f19cd-184">将从连接**SendPortFilterASMX**到模型元素**SendASMXOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-184">Drag a connection from the **SendPortFilterASMX** model element to the **SendASMXOrder** model element.</span></span>  
  
13. <span data-ttu-id="f19cd-185">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**RouteBrokerService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-185">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of **RouteBrokerService** model element.</span></span> <span data-ttu-id="f19cd-186">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-186">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-187">单击**名称**属性，再然后键入**RouteToFileFromWCF**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-187">Click the **Name** property, and then type **RouteToFileFromWCF**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-188">在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-188">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f19cd-189">此属性定义的过程将需要在管道 （消息传送） 中的位置。</span><span class="sxs-lookup"><span data-stu-id="f19cd-189">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="f19cd-190">或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-190">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-191">在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-191">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="f19cd-192">在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-192">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
14. <span data-ttu-id="f19cd-193">右键单击**冲突解决程序**集合**RouteToFileFromWCF**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-193">Right-click the **Resolver** collection of the **RouteToFileFromWCF** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="f19cd-194">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-194">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-195">单击**名称**属性，再然后键入**ResolverFromWCF**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-195">Click the **Name** property, and then type **ResolverFromWCF**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-196">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-196">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-197">在**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-197">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="f19cd-198">单击**传输位置**属性，再然后键入**c:\howtos\out\wcf%MessageId%.xml**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-198">Click the **Transport Location** property, and then type **c:\howtos\out\wcf%MessageId%.xml**.</span></span>  
  
15. <span data-ttu-id="f19cd-199">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**RouteToFileFromWCF**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-199">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToFileFromWCF** model element.</span></span> <span data-ttu-id="f19cd-200">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-200">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-201">单击**名称**属性，再然后键入**SendWCFOrder**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-201">Click the **Name** property, and then type **SendWCFOrder**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-202">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-202">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-203">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-203">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="f19cd-204">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-204">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
16. <span data-ttu-id="f19cd-205">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**RouteToFileFromWCF**模型元素和**SendWCFOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-205">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToFileFromWCF** model element and the **SendWCFOrder** model element.</span></span> <span data-ttu-id="f19cd-206">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-206">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-207">单击**名称**属性，再然后键入**SendPortFilterWCF**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-207">Click the **Name** property, and then type **SendPortFilterWCF**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-208">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-208">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-209">在**关闭负载增加**下拉列表中，展开**SendWCFOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-209">In the **Off-Ramp** drop-down list, expand **SendWCFOrder**, and then click **Send Handlers**.</span></span>  
  
17. <span data-ttu-id="f19cd-210">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-210">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f19cd-211">将从连接**RouteToFileFromWCF**到模型元素**SendPortFilterWCF**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-211">Drag a connection from the **RouteToFileFromWCF** model element to the **SendPortFilterWCF** model element.</span></span>  
  
18. <span data-ttu-id="f19cd-212">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-212">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f19cd-213">将从连接**SendPortFilterWCF**到模型元素**SendWCFOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-213">Drag a connection from the **SendPortFilterWCF** model element to the **SendWCFOrder** model element.</span></span>  
  
19. <span data-ttu-id="f19cd-214">从工具箱中，拖动**路线 Outport**到右边框的模型元素**RouteBrokerService**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-214">From the Toolbox, drag an **Itinerary Outport** model element to right border of **RouteBrokerService**.</span></span> <span data-ttu-id="f19cd-215">在**ItineraryBrokerOutPort1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-215">In the **ItineraryBrokerOutPort1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-216">单击**名称**属性，再然后键入**WCF 端口**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-216">Click the **Name** property, and then type **WCF Port**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-217">在**筛选器**下拉列表中，单击**WCFFilter**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-217">In the **Filter** drop-down list, click **WCFFilter**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-218">在**冲突解决程序**下拉列表中，单击**ResolverBrokerRoute**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-218">In the **Resolver** drop-down list, click **ResolverBrokerRoute**.</span></span>  
  
20. <span data-ttu-id="f19cd-219">从工具箱中，拖动**路线 Outport**到下边框的模型元素**RouteBrokerService**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-219">From the Toolbox, drag an **Itinerary Outport** model element to the bottom border of **RouteBrokerService**.</span></span> <span data-ttu-id="f19cd-220">在**ItineraryBrokerOutPort1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f19cd-220">In the **ItineraryBrokerOutPort1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f19cd-221">单击**名称**属性，再然后键入**ASMX 端口**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-221">Click the **Name** property, and then type **ASMX Port**.</span></span>  
  
    2.  <span data-ttu-id="f19cd-222">在**筛选器**下拉列表中，单击**ASMXFilter**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-222">In the **Filter** drop-down list, click **ASMXFilter**.</span></span>  
  
    3.  <span data-ttu-id="f19cd-223">在**冲突解决程序**下拉列表中，单击**ResolverBrokerRoute**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-223">In the **Resolver** drop-down list, click **ResolverBrokerRoute**.</span></span>  
  
21. <span data-ttu-id="f19cd-224">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-224">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f19cd-225">将从连接**WCF 端口**到模型元素**RouteToFileFromWCF**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-225">Drag a connection from the **WCF Port** model element to the **RouteToFileFromWCF** model element.</span></span>  
  
22. <span data-ttu-id="f19cd-226">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-226">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f19cd-227">将从连接**ASMX 端口**到模型元素**RouteToFileFromASMX**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f19cd-227">Drag a connection from the **ASMX Port** model element to the **RouteToFileFromASMX** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="f19cd-228">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="f19cd-228">To export the model for use with the Itinerary Test Client</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f19cd-229">你将需要两次导出路线： 在 XML 中一次，另一个时间到数据库来测试通过代理路由。</span><span class="sxs-lookup"><span data-stu-id="f19cd-229">You will need to export the itinerary twice: one time in XML and one time to the database to test the routing through the broker.</span></span>  
  
1.  <span data-ttu-id="f19cd-230">在 Visual Studio 中，右键单击的设计图面**ChoiceRouter**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-230">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f19cd-231">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="f19cd-231">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="f19cd-232">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，，然后记下你路线 XML (ChoiceRouter.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="f19cd-232">In Windows Explorer, browse to C:\HowTos\Itineraries, and then notice the creation of your itinerary XML (ChoiceRouter.xml).</span></span>  
  
3.  <span data-ttu-id="f19cd-233">在 Visual Studio 中，右键单击的设计图面**ChoiceRouter**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-233">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
4.  <span data-ttu-id="f19cd-234">在属性窗口中，单击**数据库路线导出程序**中**模型导出程序**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="f19cd-234">In the Properties window, click **Database Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
5.  <span data-ttu-id="f19cd-235">在属性窗口中，设置**路线数据库**属性连接字符串以指向路线的数据库。</span><span class="sxs-lookup"><span data-stu-id="f19cd-235">In the Properties window, set the **Itinerary Database** property connection string to point to the itinerary database.</span></span>  
  
6.  <span data-ttu-id="f19cd-236">在**路线状态**属性下拉列表中，选择**已部署**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-236">In the **Itinerary Status** property drop-down list select **Deployed**.</span></span>  
  
7.  <span data-ttu-id="f19cd-237">在 Visual Studio 中，右键单击的设计图面**ChoiceRouter**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-237">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="f19cd-238">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="f19cd-238">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="f19cd-239">打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="f19cd-239">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="f19cd-240">在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="f19cd-240">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="f19cd-241">在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="f19cd-241">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="f19cd-242">选择**ChoiceRouter.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="f19cd-242">Select **ChoiceRouter.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="f19cd-243">单击**确定**以关闭"路线加载成功"消息。</span><span class="sxs-lookup"><span data-stu-id="f19cd-243">Click **OK** to close the "Itinerary Loaded Successfully" message.</span></span>  
  
5.  <span data-ttu-id="f19cd-244">在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="f19cd-244">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="f19cd-245">在**选择要加载 XML 文档**对话框中，浏览到 C:\Patterns\HowTos。</span><span class="sxs-lookup"><span data-stu-id="f19cd-245">In the **Select XML Document to load** dialog box, browse to C:\Patterns\HowTos.</span></span> <span data-ttu-id="f19cd-246">选择 NAOrderDoc.xml，，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="f19cd-246">Select NAOrderDoc.xml, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="f19cd-247">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="f19cd-247">Click the **Submit Request** button.</span></span> <span data-ttu-id="f19cd-248">在测试完成后，单击**确定**关闭显示的确认消息。</span><span class="sxs-lookup"><span data-stu-id="f19cd-248">When the test completes, click **OK** to close the confirmation message that appears.</span></span>  
  
8.  <span data-ttu-id="f19cd-249">在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证此目录中已写的 ASMX%MessageID%.xml 消息。</span><span class="sxs-lookup"><span data-stu-id="f19cd-249">In Windows Explorer, browse to C:\HowTos\Out. Verify that the ASMX%MessageID%.xml messages have been written to this directory.</span></span>  
  
9. <span data-ttu-id="f19cd-250">单击路线测试客户端**使用 WCF 服务**复选框。</span><span class="sxs-lookup"><span data-stu-id="f19cd-250">Click the Itinerary Test client **Use WCF Service** check box.</span></span> <span data-ttu-id="f19cd-251">在**路线名称**框中，键入**ChoiceRouter**，然后单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="f19cd-251">In the **Itinerary Name** box, type **ChoiceRouter**, and then click the **Submit Request** button.</span></span> <span data-ttu-id="f19cd-252">在测试完成后，单击**确定**关闭确认消息。</span><span class="sxs-lookup"><span data-stu-id="f19cd-252">When the test completes, click **OK** to close the confirmation message.</span></span>  
  
10. <span data-ttu-id="f19cd-253">在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证此目录中已写的 WCF%MessageID%.xml 消息。</span><span class="sxs-lookup"><span data-stu-id="f19cd-253">In Windows Explorer, browse to C:\HowTos\Out. Verify that the WCF%MessageID%.xml messages have been written to this directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="f19cd-254">其他资源</span><span class="sxs-lookup"><span data-stu-id="f19cd-254">Additional Resources</span></span>  
 <span data-ttu-id="f19cd-255">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="f19cd-255">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="f19cd-256">如何： 选择使用业务规则策略路线</span><span class="sxs-lookup"><span data-stu-id="f19cd-256">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="f19cd-257">如何： 动态路由基于消息上下文使用业务规则策略在一条消息</span><span class="sxs-lookup"><span data-stu-id="f19cd-257">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [<span data-ttu-id="f19cd-258">开发活动</span><span class="sxs-lookup"><span data-stu-id="f19cd-258">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="f19cd-259">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="f19cd-259">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)