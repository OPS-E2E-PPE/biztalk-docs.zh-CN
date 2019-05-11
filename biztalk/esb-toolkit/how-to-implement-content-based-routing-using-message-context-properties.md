---
title: 如何：实现基于内容的路由使用消息上下文属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 952af792-5762-4b04-9087-980bb3323568
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 200341cb4866806429ee132d07f17b94379a9583
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295821"
---
# <a name="how-to-implement-content-based-routing-using-message-context-properties"></a><span data-ttu-id="965af-102">如何：实现基于内容的路由使用消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="965af-102">How to: Implement Content-Based Routing Using Message Context Properties</span></span>
## <a name="goal"></a><span data-ttu-id="965af-103">目的</span><span class="sxs-lookup"><span data-stu-id="965af-103">Goal</span></span>  
 <span data-ttu-id="965af-104">本部分演示如何使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线设计器创建路线选择消息接收方根据消息上下文属性，然后将消息路由到该收件人使用路线 Broker 消息传递服务。</span><span class="sxs-lookup"><span data-stu-id="965af-104">This section demonstrates how to use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Itinerary Designer to create an itinerary that selects a message recipient based on the message context property and then routes a message to that recipient using the Itinerary Broker messaging service.</span></span>  
  
 <span data-ttu-id="965af-105">在本主题中，您将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="965af-105">In this topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="965af-106">使用路线 broker 和使用静态冲突解决程序的两个路由服务创建路线。</span><span class="sxs-lookup"><span data-stu-id="965af-106">Create an itinerary with an itinerary broker and two routing services with static resolvers.</span></span>  
  
-   <span data-ttu-id="965af-107">测试使用路线测试客户端示例应用程序的路线。</span><span class="sxs-lookup"><span data-stu-id="965af-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="965af-108">当前实现中不提供了任何基于业务流程的 broker 服务。</span><span class="sxs-lookup"><span data-stu-id="965af-108">No orchestration-based broker service is provided in the current implementation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="965af-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="965af-109">Prerequisites</span></span>  
 <span data-ttu-id="965af-110">本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="965af-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="965af-111">步骤</span><span class="sxs-lookup"><span data-stu-id="965af-111">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="965af-112">若要创建的 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="965af-112">To create an ESB Itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="965af-113">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="965af-113">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="965af-114">在解决方案资源管理器中右键单击**ItineraryLibrary**，依次指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="965af-114">In Solution Explorer, right-click **ItineraryLibrary**, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="965af-115">在中**添加新项**对话框中，单击**ItineraryDsl**模板窗格中。</span><span class="sxs-lookup"><span data-stu-id="965af-115">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="965af-116">在中**名称**框中，键入**ChoiceRouter**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="965af-116">In the **Name** box, type **ChoiceRouter**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="965af-117">若要配置的路线属性</span><span class="sxs-lookup"><span data-stu-id="965af-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="965af-118">在 Visual Studio 中，单击的设计图面**ChoiceRouter**路线。</span><span class="sxs-lookup"><span data-stu-id="965af-118">In Visual Studio, click the design surface of the **ChoiceRouter** itinerary.</span></span> <span data-ttu-id="965af-119">在中**ChoiceRouter**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-119">In the **ChoiceRouter** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-120">在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="965af-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="965af-121">在中**扩展器设置**部分中，单击旁边的省略号按钮 （...）**路线 XML 文件**属性。</span><span class="sxs-lookup"><span data-stu-id="965af-121">In the **Extender Settings** section, click the ellipsis button (...) next to the **Itinerary XML file** property.</span></span>  
  
    3.  <span data-ttu-id="965af-122">在中**导出模式**属性下拉列表中，单击**Strict**。</span><span class="sxs-lookup"><span data-stu-id="965af-122">In the **Export Mode** property drop-down list, click **Strict**.</span></span>  
  
    4.  <span data-ttu-id="965af-123">在中**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\ChoiceRouter**中**文件名**框，并单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="965af-123">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\ChoiceRouter** in the **File name** box, and then click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="965af-124">此步骤中，可将路线以 XML 形式导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="965af-124">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="965af-125">通过将一条路线到本地文件的位置，而不导出到行程数据库，您可以测试路线使用 ESB 测试客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="965af-125">By exporting an itinerary to a local file location, instead of to the itinerary database, you can test the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="965af-126">您将完成此过程更高版本的本操作指南主题。</span><span class="sxs-lookup"><span data-stu-id="965af-126">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="965af-127">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="965af-127">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="965af-128">从工具箱拖动**接入点**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-128">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="965af-129">在 OnRamp1 属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-129">In the OnRamp1 Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-130">单击**名称**属性，并键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="965af-130">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="965af-131">在中**Extender**下拉列表中，单击**接入点扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="965af-131">In the **Extender** drop-down list, click **On-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="965af-132">在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="965af-132">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="965af-133">在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="965af-133">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="965af-134">从工具箱拖动**路线 Broker 服务**模型设计器图面，元素，然后将它放到右侧**接入点**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-134">From the Toolbox, drag an **Itinerary Broker Service** model element to the designer surface, and then place it to the right side of the **On-Ramp** model element.</span></span> <span data-ttu-id="965af-135">在中**ItineraryBrokerService1**，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-135">In the **ItineraryBrokerService1**, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-136">单击**名称**属性，并键入**RouteBrokerService**。</span><span class="sxs-lookup"><span data-stu-id="965af-136">Click the **Name** property, and then type **RouteBrokerService**.</span></span>  
  
    2.  <span data-ttu-id="965af-137">在中**Extender**下拉列表中，单击**消息传送中转站扩展器**。</span><span class="sxs-lookup"><span data-stu-id="965af-137">In the **Extender** drop-down list, click **Messaging Broker Extender**.</span></span>  
  
    3.  <span data-ttu-id="965af-138">在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="965af-138">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="965af-139">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**。</span><span class="sxs-lookup"><span data-stu-id="965af-139">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Itinerary.Services.Broker.MessagingBroker**.</span></span>  
  
3.  <span data-ttu-id="965af-140">右键单击**筛选器**集合，并单击**添加新的筛选器**。</span><span class="sxs-lookup"><span data-stu-id="965af-140">Right-click the **Filter** collection, and then click **Add new Filter**.</span></span> <span data-ttu-id="965af-141">在中**Filter1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-141">In the **Filter1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-142">单击**名称**属性，并键入**ASMXFilter**。</span><span class="sxs-lookup"><span data-stu-id="965af-142">Click the **Name** property, and then type **ASMXFilter**.</span></span>  
  
    2.  <span data-ttu-id="965af-143">单击**筛选器**实现下拉列表，再单击**XPath 筛选器**。</span><span class="sxs-lookup"><span data-stu-id="965af-143">Click the **Filter** Implementation drop-down list, and then click **XPath Filter**.</span></span>  
  
    3.  <span data-ttu-id="965af-144">单击**表达式**属性，并键入**计数 (/ ContextProperties/属性 [@name= InboundTransportLocation] [包含 (。，ProcessItinerary.asmx')]) > 0**。</span><span class="sxs-lookup"><span data-stu-id="965af-144">Click the **Expression** property, and then type **count(/ContextProperties/Property[@name='InboundTransportLocation'][contains(., 'ProcessItinerary.asmx')]) > 0**.</span></span>  
  
4.  <span data-ttu-id="965af-145">右键单击**筛选器**集合，并单击**添加新的筛选器**。</span><span class="sxs-lookup"><span data-stu-id="965af-145">Right-click the **Filter** collection, and then click **Add new Filter**.</span></span> <span data-ttu-id="965af-146">在中**Filter1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-146">In the **Filter1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-147">单击**名称**属性，并键入**WCFFilter**。</span><span class="sxs-lookup"><span data-stu-id="965af-147">Click the **Name** property, and then type **WCFFilter**.</span></span>  
  
    2.  <span data-ttu-id="965af-148">单击**筛选器实现**下拉列表中，然后单击**XPath 筛选器**。</span><span class="sxs-lookup"><span data-stu-id="965af-148">Click the **Filter Implementation** drop-down list, and click **XPath Filter**.</span></span>  
  
    3.  <span data-ttu-id="965af-149">单击**表达式**属性，并键入**计数 (/ ContextProperties/属性 [@name= InboundTransportLocation] [包含 (。，ESB。ItineraryServices.WCF')]) > 0**。</span><span class="sxs-lookup"><span data-stu-id="965af-149">Click the **Expression** property, and then type **count(/ContextProperties/Property[@name='InboundTransportLocation'][contains(., 'ESB.ItineraryServices.WCF')]) > 0**.</span></span>  
  
5.  <span data-ttu-id="965af-150">右键单击**冲突解决程序**系列**RouteBrokerService**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="965af-150">Right-click the **Resolver** collection of the **RouteBrokerService** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="965af-151">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-151">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-152">单击**名称**属性，并键入**ResolverBrokerRoute**。</span><span class="sxs-lookup"><span data-stu-id="965af-152">Click the **Name** property, and then type **ResolverBrokerRoute**.</span></span>  
  
    2.  <span data-ttu-id="965af-153">在中**解析程序实现**下拉列表中，单击**MessageContext 冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="965af-153">In the **Resolver Implementation** drop-down list, click **MessageContext Resolver Extension**.</span></span>  
  
6.  <span data-ttu-id="965af-154">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="965af-154">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="965af-155">将从连接**ReceiveNAOrder**到模型元素**RouteBrokerService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-155">Drag a connection from the **ReceiveNAOrder** model element to the **RouteBrokerService** model element.</span></span>  
  
7.  <span data-ttu-id="965af-156">从工具箱拖动**路线服务**模型元素到设计图面，然后将其下放置**RouteBrokerService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-156">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it under the **RouteBrokerService** model element.</span></span> <span data-ttu-id="965af-157">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-157">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-158">单击**名称**属性，并键入**RouteToFileFromASMX**。</span><span class="sxs-lookup"><span data-stu-id="965af-158">Click the **Name** property, and then type **RouteToFileFromASMX**.</span></span>  
  
    2.  <span data-ttu-id="965af-159">在**路线服务 Extender**下拉列表中，单击**消息扩展器**。</span><span class="sxs-lookup"><span data-stu-id="965af-159">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="965af-160">此属性定义，过程将花费 （消息传送） 管道中的位置。</span><span class="sxs-lookup"><span data-stu-id="965af-160">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="965af-161">或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。</span><span class="sxs-lookup"><span data-stu-id="965af-161">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="965af-162">在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="965af-162">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="965af-163">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="965af-163">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
8.  <span data-ttu-id="965af-164">右键单击**冲突解决程序**系列**RouteToFileFromASMX**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="965af-164">Right-click the **Resolver** collection of the **RouteToFileFromASMX** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="965af-165">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-165">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-166">单击**名称**属性，并键入**ResolverFromAsmx**。</span><span class="sxs-lookup"><span data-stu-id="965af-166">Click the **Name** property, and then type **ResolverFromAsmx**.</span></span>  
  
    2.  <span data-ttu-id="965af-167">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="965af-167">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="965af-168">在中**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="965af-168">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="965af-169">单击**传输位置**属性，并键入**c:\howtos\out\asmx%MessageId%.xml**。</span><span class="sxs-lookup"><span data-stu-id="965af-169">Click the **Transport Location** property, and then type **c:\howtos\out\asmx%MessageId%.xml**.</span></span>  
  
9. <span data-ttu-id="965af-170">从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**RouteToFileFromASMX**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-170">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToFileFromASMX** model element.</span></span> <span data-ttu-id="965af-171">在中**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-171">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-172">单击**名称**属性，并键入**SendASMXOrder**。</span><span class="sxs-lookup"><span data-stu-id="965af-172">Click the **Name** property, and then type **SendASMXOrder**.</span></span>  
  
    2.  <span data-ttu-id="965af-173">在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="965af-173">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="965af-174">在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="965af-174">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="965af-175">在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="965af-175">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
10. <span data-ttu-id="965af-176">从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**RouteToFileFromASMX**模型元素和**SendASMXOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-176">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToFileFromASMX** model element and the **SendASMXOrder** model element.</span></span> <span data-ttu-id="965af-177">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-177">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-178">单击**名称**属性，并键入**SendPortFilterASMX**。</span><span class="sxs-lookup"><span data-stu-id="965af-178">Click the **Name** property, and then type **SendPortFilterASMX**.</span></span>  
  
    2.  <span data-ttu-id="965af-179">在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。</span><span class="sxs-lookup"><span data-stu-id="965af-179">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="965af-180">在中**关闭负载增加**下拉列表中，展开**SendASMXOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="965af-180">In the **Off-Ramp** drop-down list, expand **SendASMXOrder**, and then click **Send Handlers**.</span></span>  
  
11. <span data-ttu-id="965af-181">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="965af-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="965af-182">将从连接**RouteToFileFromASMX**到模型元素**SendPortFilterASMX**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-182">Drag a connection from the **RouteToFileFromASMX** model element to the **SendPortFilterASMX** model element.</span></span>  
  
12. <span data-ttu-id="965af-183">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="965af-183">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="965af-184">将从连接**SendPortFilterASMX**到模型元素**SendASMXOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-184">Drag a connection from the **SendPortFilterASMX** model element to the **SendASMXOrder** model element.</span></span>  
  
13. <span data-ttu-id="965af-185">从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**RouteBrokerService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-185">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of **RouteBrokerService** model element.</span></span> <span data-ttu-id="965af-186">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-186">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-187">单击**名称**属性，并键入**RouteToFileFromWCF**。</span><span class="sxs-lookup"><span data-stu-id="965af-187">Click the **Name** property, and then type **RouteToFileFromWCF**.</span></span>  
  
    2.  <span data-ttu-id="965af-188">在**路线服务 Extender**下拉列表中，单击**消息扩展器**。</span><span class="sxs-lookup"><span data-stu-id="965af-188">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="965af-189">此属性定义，过程将花费 （消息传送） 管道中的位置。</span><span class="sxs-lookup"><span data-stu-id="965af-189">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="965af-190">或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。</span><span class="sxs-lookup"><span data-stu-id="965af-190">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="965af-191">在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="965af-191">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="965af-192">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="965af-192">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
14. <span data-ttu-id="965af-193">右键单击**冲突解决程序**系列**RouteToFileFromWCF**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="965af-193">Right-click the **Resolver** collection of the **RouteToFileFromWCF** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="965af-194">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-194">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-195">单击**名称**属性，并键入**ResolverFromWCF**。</span><span class="sxs-lookup"><span data-stu-id="965af-195">Click the **Name** property, and then type **ResolverFromWCF**.</span></span>  
  
    2.  <span data-ttu-id="965af-196">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="965af-196">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="965af-197">在中**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="965af-197">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="965af-198">单击**传输位置**属性，并键入**c:\howtos\out\wcf%MessageId%.xml**。</span><span class="sxs-lookup"><span data-stu-id="965af-198">Click the **Transport Location** property, and then type **c:\howtos\out\wcf%MessageId%.xml**.</span></span>  
  
15. <span data-ttu-id="965af-199">从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**RouteToFileFromWCF**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-199">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToFileFromWCF** model element.</span></span> <span data-ttu-id="965af-200">在中**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-200">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-201">单击**名称**属性，并键入**SendWCFOrder**。</span><span class="sxs-lookup"><span data-stu-id="965af-201">Click the **Name** property, and then type **SendWCFOrder**.</span></span>  
  
    2.  <span data-ttu-id="965af-202">在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="965af-202">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="965af-203">在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="965af-203">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="965af-204">在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="965af-204">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
16. <span data-ttu-id="965af-205">从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**RouteToFileFromWCF**模型元素和**SendWCFOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-205">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToFileFromWCF** model element and the **SendWCFOrder** model element.</span></span> <span data-ttu-id="965af-206">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-206">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-207">单击**名称**属性，并键入**SendPortFilterWCF**。</span><span class="sxs-lookup"><span data-stu-id="965af-207">Click the **Name** property, and then type **SendPortFilterWCF**.</span></span>  
  
    2.  <span data-ttu-id="965af-208">在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。</span><span class="sxs-lookup"><span data-stu-id="965af-208">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="965af-209">在中**关闭负载增加**下拉列表中，展开**SendWCFOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="965af-209">In the **Off-Ramp** drop-down list, expand **SendWCFOrder**, and then click **Send Handlers**.</span></span>  
  
17. <span data-ttu-id="965af-210">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="965af-210">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="965af-211">将从连接**RouteToFileFromWCF**到模型元素**SendPortFilterWCF**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-211">Drag a connection from the **RouteToFileFromWCF** model element to the **SendPortFilterWCF** model element.</span></span>  
  
18. <span data-ttu-id="965af-212">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="965af-212">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="965af-213">将从连接**SendPortFilterWCF**到模型元素**SendWCFOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-213">Drag a connection from the **SendPortFilterWCF** model element to the **SendWCFOrder** model element.</span></span>  
  
19. <span data-ttu-id="965af-214">从工具箱拖动**路线 Outport**右边框的模型元素**RouteBrokerService**。</span><span class="sxs-lookup"><span data-stu-id="965af-214">From the Toolbox, drag an **Itinerary Outport** model element to right border of **RouteBrokerService**.</span></span> <span data-ttu-id="965af-215">在中**ItineraryBrokerOutPort1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-215">In the **ItineraryBrokerOutPort1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-216">单击**名称**属性，并键入**WCF 端口**。</span><span class="sxs-lookup"><span data-stu-id="965af-216">Click the **Name** property, and then type **WCF Port**.</span></span>  
  
    2.  <span data-ttu-id="965af-217">在中**筛选器**下拉列表中，单击**WCFFilter**。</span><span class="sxs-lookup"><span data-stu-id="965af-217">In the **Filter** drop-down list, click **WCFFilter**.</span></span>  
  
    3.  <span data-ttu-id="965af-218">在中**冲突解决程序**下拉列表中，单击**ResolverBrokerRoute**。</span><span class="sxs-lookup"><span data-stu-id="965af-218">In the **Resolver** drop-down list, click **ResolverBrokerRoute**.</span></span>  
  
20. <span data-ttu-id="965af-219">从工具箱拖动**路线 Outport**模型元素的下边框**RouteBrokerService**。</span><span class="sxs-lookup"><span data-stu-id="965af-219">From the Toolbox, drag an **Itinerary Outport** model element to the bottom border of **RouteBrokerService**.</span></span> <span data-ttu-id="965af-220">在中**ItineraryBrokerOutPort1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="965af-220">In the **ItineraryBrokerOutPort1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="965af-221">单击**名称**属性，并键入**ASMX 端口**。</span><span class="sxs-lookup"><span data-stu-id="965af-221">Click the **Name** property, and then type **ASMX Port**.</span></span>  
  
    2.  <span data-ttu-id="965af-222">在中**筛选器**下拉列表中，单击**ASMXFilter**。</span><span class="sxs-lookup"><span data-stu-id="965af-222">In the **Filter** drop-down list, click **ASMXFilter**.</span></span>  
  
    3.  <span data-ttu-id="965af-223">在中**冲突解决程序**下拉列表中，单击**ResolverBrokerRoute**。</span><span class="sxs-lookup"><span data-stu-id="965af-223">In the **Resolver** drop-down list, click **ResolverBrokerRoute**.</span></span>  
  
21. <span data-ttu-id="965af-224">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="965af-224">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="965af-225">将从连接**WCF 端口**到模型元素**RouteToFileFromWCF**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-225">Drag a connection from the **WCF Port** model element to the **RouteToFileFromWCF** model element.</span></span>  
  
22. <span data-ttu-id="965af-226">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="965af-226">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="965af-227">将从连接**ASMX 端口**到模型元素**RouteToFileFromASMX**模型元素。</span><span class="sxs-lookup"><span data-stu-id="965af-227">Drag a connection from the **ASMX Port** model element to the **RouteToFileFromASMX** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="965af-228">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="965af-228">To export the model for use with the Itinerary Test Client</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="965af-229">将需要两次导出路线： 在 XML 中一次，另一个时间到数据库来测试通过代理路由。</span><span class="sxs-lookup"><span data-stu-id="965af-229">You will need to export the itinerary twice: one time in XML and one time to the database to test the routing through the broker.</span></span>  
  
1.  <span data-ttu-id="965af-230">在 Visual Studio 中，右键单击设计图面的**ChoiceRouter**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="965af-230">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="965af-231">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="965af-231">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="965af-232">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，，然后请注意，您的路线 XML (ChoiceRouter.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="965af-232">In Windows Explorer, browse to C:\HowTos\Itineraries, and then notice the creation of your itinerary XML (ChoiceRouter.xml).</span></span>  
  
3.  <span data-ttu-id="965af-233">在 Visual Studio 中，右键单击设计图面的**ChoiceRouter**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="965af-233">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
4.  <span data-ttu-id="965af-234">在属性窗口中，单击**数据库路线导出程序**中**模型导出程序**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="965af-234">In the Properties window, click **Database Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
5.  <span data-ttu-id="965af-235">在属性窗口中设置**行程数据库**属性以指向路线的数据库的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="965af-235">In the Properties window, set the **Itinerary Database** property connection string to point to the itinerary database.</span></span>  
  
6.  <span data-ttu-id="965af-236">在中**路线状态**属性下拉列表中，选择**已部署**。</span><span class="sxs-lookup"><span data-stu-id="965af-236">In the **Itinerary Status** property drop-down list select **Deployed**.</span></span>  
  
7.  <span data-ttu-id="965af-237">在 Visual Studio 中，右键单击设计图面的**ChoiceRouter**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="965af-237">In Visual Studio, right-click the design surface of the **ChoiceRouter** itinerary, and then click **Export Model**.</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="965af-238">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="965af-238">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="965af-239">打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="965af-239">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="965af-240">在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="965af-240">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="965af-241">在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="965af-241">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="965af-242">选择**ChoiceRouter.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="965af-242">Select **ChoiceRouter.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="965af-243">单击**确定**以关闭"路线加载成功"消息。</span><span class="sxs-lookup"><span data-stu-id="965af-243">Click **OK** to close the "Itinerary Loaded Successfully" message.</span></span>  
  
5.  <span data-ttu-id="965af-244">在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="965af-244">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="965af-245">在中**选择要加载 XML 文档**对话框中，浏览到 C:\Patterns\HowTos。</span><span class="sxs-lookup"><span data-stu-id="965af-245">In the **Select XML Document to load** dialog box, browse to C:\Patterns\HowTos.</span></span> <span data-ttu-id="965af-246">选择 NAOrderDoc.xml，，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="965af-246">Select NAOrderDoc.xml, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="965af-247">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="965af-247">Click the **Submit Request** button.</span></span> <span data-ttu-id="965af-248">测试完成后，单击**确定**关闭出现的确认消息。</span><span class="sxs-lookup"><span data-stu-id="965af-248">When the test completes, click **OK** to close the confirmation message that appears.</span></span>  
  
8.  <span data-ttu-id="965af-249">在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证已将 ASMX%MessageID%.xml 消息写入到此目录。</span><span class="sxs-lookup"><span data-stu-id="965af-249">In Windows Explorer, browse to C:\HowTos\Out. Verify that the ASMX%MessageID%.xml messages have been written to this directory.</span></span>  
  
9. <span data-ttu-id="965af-250">单击路线测试客户端**使用 WCF 服务**复选框。</span><span class="sxs-lookup"><span data-stu-id="965af-250">Click the Itinerary Test client **Use WCF Service** check box.</span></span> <span data-ttu-id="965af-251">在中**路线名称**框中，键入**ChoiceRouter**，然后单击**提交申请**按钮。</span><span class="sxs-lookup"><span data-stu-id="965af-251">In the **Itinerary Name** box, type **ChoiceRouter**, and then click the **Submit Request** button.</span></span> <span data-ttu-id="965af-252">测试完成后，单击**确定**关闭确认消息。</span><span class="sxs-lookup"><span data-stu-id="965af-252">When the test completes, click **OK** to close the confirmation message.</span></span>  
  
10. <span data-ttu-id="965af-253">在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证已将 WCF%MessageID%.xml 消息写入到此目录。</span><span class="sxs-lookup"><span data-stu-id="965af-253">In Windows Explorer, browse to C:\HowTos\Out. Verify that the WCF%MessageID%.xml messages have been written to this directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="965af-254">其他资源</span><span class="sxs-lookup"><span data-stu-id="965af-254">Additional Resources</span></span>  
 <span data-ttu-id="965af-255">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="965af-255">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="965af-256">如何：选择使用业务规则策略路线</span><span class="sxs-lookup"><span data-stu-id="965af-256">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="965af-257">如何：动态路由基于消息上下文中使用业务规则策略的消息</span><span class="sxs-lookup"><span data-stu-id="965af-257">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>](../esb-toolkit/dynamically-route-messages-based-on-message-context-using-business-rules-policy.md)  
  
-   [<span data-ttu-id="965af-258">开发活动</span><span class="sxs-lookup"><span data-stu-id="965af-258">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="965af-259">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="965af-259">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)