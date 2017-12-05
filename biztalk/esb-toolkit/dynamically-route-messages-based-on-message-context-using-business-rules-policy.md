---
title: "如何： 动态路由根据消息上下文使用业务规则策略消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d3b68de-6b24-46fe-ae0d-91afb630bc19
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0d36df10b271d83b1e77f4d7f57d357f4b22033
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-dynamically-route-a-message-based-on-message-context-using-a-business-rules-policy"></a><span data-ttu-id="b0cca-102">如何： 动态路由基于消息上下文使用业务规则策略在一条消息</span><span class="sxs-lookup"><span data-stu-id="b0cca-102">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>
## <a name="goal"></a><span data-ttu-id="b0cca-103">目的</span><span class="sxs-lookup"><span data-stu-id="b0cca-103">Goal</span></span>  
 <span data-ttu-id="b0cca-104">本部分演示如何创建一条路线，并将确定消息终结点，根据消息上下文属性，使用 BizTalk Server 业务规则引擎 (BRE) 策略，然后将路由使用 BizTalk Server 文件适配器的消息。</span><span class="sxs-lookup"><span data-stu-id="b0cca-104">This section demonstrates how to create an itinerary that determines message endpoints, based on message context properties, using a BizTalk Server Business Rules Engine (BRE) policy, and then routes the message using the BizTalk Server FILE adapter.</span></span>  
  
 <span data-ttu-id="b0cca-105">在本操作方法主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="b0cca-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="b0cca-106">创建业务规则策略来评估消息类型。</span><span class="sxs-lookup"><span data-stu-id="b0cca-106">Create a business rules policy to evaluate message type.</span></span>  
  
-   <span data-ttu-id="b0cca-107">创建动态路由使用业务规则策略路线路由滑动。</span><span class="sxs-lookup"><span data-stu-id="b0cca-107">Create an itinerary routing slip to dynamically route using a business rules policy.</span></span>  
  
-   <span data-ttu-id="b0cca-108">测试路线使用路线测试客户端示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="b0cca-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b0cca-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="b0cca-109">Prerequisites</span></span>  
 <span data-ttu-id="b0cca-110">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="b0cca-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="b0cca-111">步骤</span><span class="sxs-lookup"><span data-stu-id="b0cca-111">Steps</span></span>  
 <span data-ttu-id="b0cca-112">**若要创建使用消息上下文属性将消息路由 BRE 策略**</span><span class="sxs-lookup"><span data-stu-id="b0cca-112">**To create a BRE policy to route a message using message context properties**</span></span>  
  
1.  <span data-ttu-id="b0cca-113">单击**启动**在任务栏中，指向**所有程序**，指向**BizTalk Server**，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-113">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="b0cca-114">在策略资源管理器中，右键单击**策略**，然后单击**添加新策略**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-114">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="b0cca-115">命名策略时**RouteBasedOnMessageType**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-115">Name the policy **RouteBasedOnMessageType**.</span></span>  
  
 <span data-ttu-id="b0cca-116">**若要添加的北美订单的路由规则**</span><span class="sxs-lookup"><span data-stu-id="b0cca-116">**To add a routing rule for North American orders**</span></span>  
  
1.  <span data-ttu-id="b0cca-117">在**RouteBasedOnMessageType**策略，右键单击**（不保存） 1.0 版**，然后单击**添加新规则**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-117">In the **RouteBasedOnMessageType** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="b0cca-118">命名规则**SetNAOrderEndpoint**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-118">Name the rule **SetNAOrderEndpoint**.</span></span>  
  
2.  <span data-ttu-id="b0cca-119">在规则窗口中，右键单击**条件**，指向**谓词**，然后单击**相等**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-119">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
3.  <span data-ttu-id="b0cca-120">在事实数据资源管理器中，展开**ESB。ContextInfo**词汇，展开**版本 1.0**，然后拖动**上下文消息类型**事实**argument1**节点下的**条件**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-120">In Facts Explorer, expand the **ESB.ContextInfo** vocabulary, expand **Version 1.0**, and then drag the **Context Message Type** fact to the **argument1** node under **Conditions**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0cca-121">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括可用于创建规则的多个词汇。</span><span class="sxs-lookup"><span data-stu-id="b0cca-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several vocabularies that can be used for creating rules.</span></span> <span data-ttu-id="b0cca-122">其中一些应替换或扩充自己词汇。</span><span class="sxs-lookup"><span data-stu-id="b0cca-122">Some of these should be replaced or augmented with your own vocabularies.</span></span> <span data-ttu-id="b0cca-123">例如， **DynamicRunTimeMaptypes**策略拥有中提供的映射用于定义**GlobalBank**示例。</span><span class="sxs-lookup"><span data-stu-id="b0cca-123">For example, the **DynamicRunTimeMaptypes** policy has definitions for the maps provided in the **GlobalBank** samples.</span></span>  
  
4.  <span data-ttu-id="b0cca-124">单击**argument2**节点，并键入**http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**</span><span class="sxs-lookup"><span data-stu-id="b0cca-124">Click the **argument2** node, and then type **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**</span></span>  
  
5.  <span data-ttu-id="b0cca-125">在事实数据资源管理器中，展开**ESB。EndPointInfo**词汇，展开**版本 1.0**，然后拖动**设置终结点出站传输位置**定义与**操作**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-125">In Facts Explorer, expand the **ESB.EndPointInfo** vocabulary, expand **Version 1.0**, and then drag the **Set End Point Outbound Transport Location** definition to **Actions**.</span></span>  
  
6.  <span data-ttu-id="b0cca-126">单击**\<空字符串\>**，然后键入**C:\HowTos\Out\NorthAmerica%MessageID%.xml**</span><span class="sxs-lookup"><span data-stu-id="b0cca-126">Click **\<empty string\>**, and then type **C:\HowTos\Out\NorthAmerica%MessageID%.xml**</span></span>  
  
7.  <span data-ttu-id="b0cca-127">从事实数据资源管理器拖动**设置终结点出站传输类型**定义与**操作**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-127">From Facts Explorer, drag the **Set End Point Outbound Transport Type** definition to **Actions**.</span></span>  
  
8.  <span data-ttu-id="b0cca-128">在事实数据资源管理器中，展开**ESB。TansportTypes**词汇，展开**版本 1.0**，然后拖动**适配器提供程序**定义与**\<空字符串\>**.</span><span class="sxs-lookup"><span data-stu-id="b0cca-128">In Facts Explorer, expand the **ESB.TansportTypes** vocabulary, expand **Version 1.0**, and then drag the **Adaptor Providers** definition to **\<empty string\>**.</span></span>  
  
9. <span data-ttu-id="b0cca-129">在操作窗格中，展开**适配器提供程序**下拉列表，然后单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-129">In the Actions pane, expand the **Adaptor Providers** drop-down list, and then click **FILE**.</span></span>  
  
 <span data-ttu-id="b0cca-130">**若要发布和部署策略**</span><span class="sxs-lookup"><span data-stu-id="b0cca-130">**To publish and deploy the policy**</span></span>  
  
1.  <span data-ttu-id="b0cca-131">在策略资源管理器下**RouteBasedOnMessageType**策略中，右击**（不保存） 1.0 版**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-131">In Policy Explorer, under the **RouteBasedOnMessageType** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
2.  <span data-ttu-id="b0cca-132">在策略资源管理器下**RouteBasedOnMessageType**策略中，右击**版本 1.0-发布**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-132">In Policy Explorer, under the **RouteBasedOnMessageType** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
 <span data-ttu-id="b0cca-133">**若要创建 ESB 路线域特定语言 (DSL) 模型**</span><span class="sxs-lookup"><span data-stu-id="b0cca-133">**To create an ESB itinerary domain-specific language (DSL) model**</span></span>  
  
1.  <span data-ttu-id="b0cca-134">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="b0cca-134">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="b0cca-135">在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-135">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="b0cca-136">在**名称**框中，键入**MessageType**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-136">In the **Name** box, type **MessageType**, and then click **Add**.</span></span>  
  
 <span data-ttu-id="b0cca-137">**若要配置路线的属性**</span><span class="sxs-lookup"><span data-stu-id="b0cca-137">**To configure the properties of the itinerary**</span></span>  
  
1.  <span data-ttu-id="b0cca-138">在 Visual Studio 中，单击的设计图面**MessageType.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-138">In Visual Studio, click the design surface of **MessageType.itinerary**.</span></span> <span data-ttu-id="b0cca-139">在**MessageType**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="b0cca-139">In the **MessageType** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b0cca-140">在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-140">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="b0cca-141">在**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。</span><span class="sxs-lookup"><span data-stu-id="b0cca-141">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="b0cca-142">在**选择 XML 文件**对话框中，在**文件名**框中，键入**C:\HowTos\Itineraries\MessageType**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-142">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\MessageType**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b0cca-143">此步骤允许您路线作为 XML 导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="b0cca-143">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="b0cca-144">到路线的数据库，而不导出到本地文件的位置，一条路线使路线使用 ESB 测试客户端应用程序的测试。</span><span class="sxs-lookup"><span data-stu-id="b0cca-144">Exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="b0cca-145">你将完成本操作方法主题中后面此过程。</span><span class="sxs-lookup"><span data-stu-id="b0cca-145">You will complete this process later in this How-to topic.</span></span>  
  
 <span data-ttu-id="b0cca-146">**若要定义路线的结构**</span><span class="sxs-lookup"><span data-stu-id="b0cca-146">**To define the structure of the itinerary**</span></span>  
  
1.  <span data-ttu-id="b0cca-147">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="b0cca-147">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="b0cca-148">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="b0cca-148">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b0cca-149">单击**名称**属性，再然后键入**ReceiveOrders**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-149">Click the **Name** property, and then type **ReceiveOrders**.</span></span>  
  
    2.  <span data-ttu-id="b0cca-150">在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-150">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="b0cca-151">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-151">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="b0cca-152">在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-152">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="b0cca-153">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**上负载增加**模型元素。</span><span class="sxs-lookup"><span data-stu-id="b0cca-153">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="b0cca-154">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="b0cca-154">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b0cca-155">单击**名称**属性，再然后键入**BreRoute**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-155">Click the **Name** property, and then type **BreRoute**.</span></span>  
  
    2.  <span data-ttu-id="b0cca-156">在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-156">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="b0cca-157">此属性定义的过程将需要在管道 （消息传送） 中的位置。</span><span class="sxs-lookup"><span data-stu-id="b0cca-157">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="b0cca-158">或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-158">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="b0cca-159">在**容器**下拉列表中，展开**ReceiveOrders**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-159">In the **Container** drop-down list, expand **ReceiveOrders**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="b0cca-160">在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-160">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="b0cca-161">右键单击**冲突解决程序**集合**BreRoute**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-161">Right-click the **Resolver** collection of the **BreRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="b0cca-162">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="b0cca-162">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b0cca-163">单击**名称**属性，再然后键入**ByMessageType**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-163">Click the **Name** property, and then type **ByMessageType**.</span></span>  
  
    2.  <span data-ttu-id="b0cca-164">在**解析程序实现**下拉列表中，单击**Bre 冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-164">In the **Resolver Implementation** drop-down list, click **Bre Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="b0cca-165">在**策略**下拉列表中，单击**RouteBasedOnMessageType v 1.0**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-165">In the **Policy** drop-down list, click **RouteBasedOnMessageType v 1.0**.</span></span>  
  
4.  <span data-ttu-id="b0cca-166">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="b0cca-167">将从连接**ReceiveOrders**到模型元素**BreRoute**模型元素。</span><span class="sxs-lookup"><span data-stu-id="b0cca-167">Drag a connection from the **ReceiveOrders** model element to the **BreRoute** model element.</span></span>  
  
5.  <span data-ttu-id="b0cca-168">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**BreRoute**模型元素。</span><span class="sxs-lookup"><span data-stu-id="b0cca-168">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BreRoute** model element.</span></span> <span data-ttu-id="b0cca-169">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="b0cca-169">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b0cca-170">单击**名称**属性，再然后键入**SendBasedOnType**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-170">Click the **Name** property, and then type **SendBasedOnType**.</span></span>  
  
    2.  <span data-ttu-id="b0cca-171">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-171">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="b0cca-172">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-172">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="b0cca-173">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-173">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="b0cca-174">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**BreRoute**模型元素和**SendBasedOnType**模型元素。</span><span class="sxs-lookup"><span data-stu-id="b0cca-174">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BreRoute** model element and the **SendBasedOnType** model element.</span></span> <span data-ttu-id="b0cca-175">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="b0cca-175">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="b0cca-176">单击**名称**属性，再然后键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-176">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="b0cca-177">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-177">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="b0cca-178">在**关闭负载增加**下拉列表中，展开**SendBasedOnType**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-178">In the **Off-Ramp** drop-down list, expand **SendBasedOnType**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="b0cca-179">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-179">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="b0cca-180">将从连接**BreRoute**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="b0cca-180">Drag a connection from the **BreRoute** model element to the **SendPortFilter** model element.</span></span>  
  
8.  <span data-ttu-id="b0cca-181">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="b0cca-182">将从连接**SendPortFilter**到模型元素**SendBasedOnType**模型元素。</span><span class="sxs-lookup"><span data-stu-id="b0cca-182">Drag a connection from the **SendPortFilter** model element to the **SendBasedOnType** model element.</span></span>  
  
 <span data-ttu-id="b0cca-183">**若要导出与路线测试客户端一起使用的模型**</span><span class="sxs-lookup"><span data-stu-id="b0cca-183">**To export the model for use with the Itinerary Test Client**</span></span>  
  
1.  <span data-ttu-id="b0cca-184">在 Visual Studio 中，右键单击的设计图面**MessageType**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-184">In Visual Studio, right-click the design surface of the **MessageType** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0cca-185">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="b0cca-185">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="b0cca-186">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="b0cca-186">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="b0cca-187">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (MessageType.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="b0cca-187">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (MessageType.xml).</span></span>  
  
 <span data-ttu-id="b0cca-188">**若要测试路线**</span><span class="sxs-lookup"><span data-stu-id="b0cca-188">**To test the itinerary**</span></span>  
  
1.  <span data-ttu-id="b0cca-189">打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="b0cca-189">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="b0cca-190">在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="b0cca-190">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="b0cca-191">在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="b0cca-191">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="b0cca-192">选择**MessageType.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="b0cca-192">Select **MessageType.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="b0cca-193">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="b0cca-193">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="b0cca-194">在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="b0cca-194">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="b0cca-195">在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="b0cca-195">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="b0cca-196">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="b0cca-196">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="b0cca-197">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="b0cca-197">Click the **Submit Request** button.</span></span> <span data-ttu-id="b0cca-198">在测试完成后，单击**确定**关闭出现的确认。</span><span class="sxs-lookup"><span data-stu-id="b0cca-198">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="b0cca-199">在 Windows 资源管理器，浏览到 C:\HowTos\Out\\。</span><span class="sxs-lookup"><span data-stu-id="b0cca-199">In Windows Explorer, browse to C:\HowTos\Out\\.</span></span> <span data-ttu-id="b0cca-200">验证 NorthAmerica%MessageID%.xml 消息已写入到目录。</span><span class="sxs-lookup"><span data-stu-id="b0cca-200">Verify that the NorthAmerica%MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="b0cca-201">其他资源</span><span class="sxs-lookup"><span data-stu-id="b0cca-201">Additional Resources</span></span>  
 <span data-ttu-id="b0cca-202">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="b0cca-202">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="b0cca-203">如何：使用业务规则策略选择路线</span><span class="sxs-lookup"><span data-stu-id="b0cca-203">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="b0cca-204">如何：转换消息并使用路线传送名单将生成的消息路由至文件位置</span><span class="sxs-lookup"><span data-stu-id="b0cca-204">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="b0cca-205">如何：使用已知消息类型的业务规则策略实现基于内容的路由</span><span class="sxs-lookup"><span data-stu-id="b0cca-205">How to: Implement Content-Based Routing Using a Business Rules Policy for a Known Message Type</span></span>](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [<span data-ttu-id="b0cca-206">开发活动</span><span class="sxs-lookup"><span data-stu-id="b0cca-206">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="b0cca-207">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="b0cca-207">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="b0cca-208">使用动态解析和路由</span><span class="sxs-lookup"><span data-stu-id="b0cca-208">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)