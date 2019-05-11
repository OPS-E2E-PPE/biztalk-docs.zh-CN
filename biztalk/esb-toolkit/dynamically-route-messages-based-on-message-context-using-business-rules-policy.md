---
title: 如何：动态路由基于消息上下文中使用业务规则策略的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d3b68de-6b24-46fe-ae0d-91afb630bc19
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e13a2e214622027ee8e28980c4d7cbc97714bd7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306298"
---
# <a name="how-to-dynamically-route-a-message-based-on-message-context-using-a-business-rules-policy"></a><span data-ttu-id="359bb-102">如何：动态路由基于消息上下文中使用业务规则策略的消息</span><span class="sxs-lookup"><span data-stu-id="359bb-102">How to: Dynamically Route a Message Based on Message Context Using a Business Rules Policy</span></span>
## <a name="goal"></a><span data-ttu-id="359bb-103">目的</span><span class="sxs-lookup"><span data-stu-id="359bb-103">Goal</span></span>  
 <span data-ttu-id="359bb-104">本部分演示如何创建路线，其确定消息终结点，基于消息上下文属性，使用 BizTalk Server 业务规则引擎 (BRE) 策略，然后使用 BizTalk Server 文件适配器将消息路由。</span><span class="sxs-lookup"><span data-stu-id="359bb-104">This section demonstrates how to create an itinerary that determines message endpoints, based on message context properties, using a BizTalk Server Business Rules Engine (BRE) policy, and then routes the message using the BizTalk Server FILE adapter.</span></span>  
  
 <span data-ttu-id="359bb-105">在本操作指南主题中，您将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="359bb-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="359bb-106">创建业务规则策略来评估消息类型。</span><span class="sxs-lookup"><span data-stu-id="359bb-106">Create a business rules policy to evaluate message type.</span></span>  
  
-   <span data-ttu-id="359bb-107">创建路线传送名单以动态方式路由使用业务规则策略。</span><span class="sxs-lookup"><span data-stu-id="359bb-107">Create an itinerary routing slip to dynamically route using a business rules policy.</span></span>  
  
-   <span data-ttu-id="359bb-108">测试使用路线测试客户端示例应用程序的路线。</span><span class="sxs-lookup"><span data-stu-id="359bb-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="359bb-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="359bb-109">Prerequisites</span></span>  
 <span data-ttu-id="359bb-110">本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="359bb-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="359bb-111">步骤</span><span class="sxs-lookup"><span data-stu-id="359bb-111">Steps</span></span>  
 <span data-ttu-id="359bb-112">**若要创建使用消息上下文属性将消息路由的 BRE 策略**</span><span class="sxs-lookup"><span data-stu-id="359bb-112">**To create a BRE policy to route a message using message context properties**</span></span>  
  
1. <span data-ttu-id="359bb-113">单击**启动**在任务栏上，依次指向**所有程序**，指向**BizTalk Server**，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="359bb-113">Click **Start** on the taskbar, point to **All Programs**, point to **BizTalk Server**, and then click **Business Rule Composer**.</span></span>  
  
2. <span data-ttu-id="359bb-114">在策略浏览器中右键单击**策略**，然后单击**添加新策略**。</span><span class="sxs-lookup"><span data-stu-id="359bb-114">In Policy Explorer, right-click **Policies**, and then click **Add New Policy**.</span></span> <span data-ttu-id="359bb-115">将策略命名**RouteBasedOnMessageType**。</span><span class="sxs-lookup"><span data-stu-id="359bb-115">Name the policy **RouteBasedOnMessageType**.</span></span>  
  
   <span data-ttu-id="359bb-116">**若要添加的路由规则，北美的订单**</span><span class="sxs-lookup"><span data-stu-id="359bb-116">**To add a routing rule for North American orders**</span></span>  
  
3. <span data-ttu-id="359bb-117">在中**RouteBasedOnMessageType**策略中，右键单击**版本 1.0 （未保存）**，然后单击**添加新规则**。</span><span class="sxs-lookup"><span data-stu-id="359bb-117">In the **RouteBasedOnMessageType** policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span> <span data-ttu-id="359bb-118">命名规则**SetNAOrderEndpoint**。</span><span class="sxs-lookup"><span data-stu-id="359bb-118">Name the rule **SetNAOrderEndpoint**.</span></span>  
  
4. <span data-ttu-id="359bb-119">在规则窗口中，右键单击**条件**，依次指向**谓词**，然后单击**相等**。</span><span class="sxs-lookup"><span data-stu-id="359bb-119">In the Rule window, right-click **Conditions**, point to **Predicates**, and then click **Equal**.</span></span>  
  
5. <span data-ttu-id="359bb-120">在事实浏览器中展开**ESB。ContextInfo**词汇，展开**版本 1.0**，然后将拖**上下文消息类型**事实**argument1**节点下的**条件**。</span><span class="sxs-lookup"><span data-stu-id="359bb-120">In Facts Explorer, expand the **ESB.ContextInfo** vocabulary, expand **Version 1.0**, and then drag the **Context Message Type** fact to the **argument1** node under **Conditions**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="359bb-121">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括几个可用于创建规则的词汇。</span><span class="sxs-lookup"><span data-stu-id="359bb-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes several vocabularies that can be used for creating rules.</span></span> <span data-ttu-id="359bb-122">其中一些应替换或扩充了自己的词汇。</span><span class="sxs-lookup"><span data-stu-id="359bb-122">Some of these should be replaced or augmented with your own vocabularies.</span></span> <span data-ttu-id="359bb-123">例如， **DynamicRunTimeMaptypes**策略具有定义中提供的映射**GlobalBank**示例。</span><span class="sxs-lookup"><span data-stu-id="359bb-123">For example, the **DynamicRunTimeMaptypes** policy has definitions for the maps provided in the **GlobalBank** samples.</span></span>  
  
6. <span data-ttu-id="359bb-124">单击**argument2**节点，并键入 **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**</span><span class="sxs-lookup"><span data-stu-id="359bb-124">Click the **argument2** node, and then type **http://globalbank.esb.dynamicresolution.com/northamericanservices/#OrderDoc**</span></span>  
  
7. <span data-ttu-id="359bb-125">在事实浏览器中展开**ESB。EndPointInfo**词汇，展开**版本 1.0**，然后将拖**设置终结点出站传输位置**定义**操作**。</span><span class="sxs-lookup"><span data-stu-id="359bb-125">In Facts Explorer, expand the **ESB.EndPointInfo** vocabulary, expand **Version 1.0**, and then drag the **Set End Point Outbound Transport Location** definition to **Actions**.</span></span>  
  
8. <span data-ttu-id="359bb-126">单击**\<空字符串\>**，然后键入**C:\HowTos\Out\NorthAmerica%MessageID%.xml**</span><span class="sxs-lookup"><span data-stu-id="359bb-126">Click **\<empty string\>**, and then type **C:\HowTos\Out\NorthAmerica%MessageID%.xml**</span></span>  
  
9. <span data-ttu-id="359bb-127">从事实浏览器中，将**设置终结点出站传输类型**定义**操作**。</span><span class="sxs-lookup"><span data-stu-id="359bb-127">From Facts Explorer, drag the **Set End Point Outbound Transport Type** definition to **Actions**.</span></span>  
  
10. <span data-ttu-id="359bb-128">在事实浏览器中展开**ESB。TansportTypes**词汇，展开**版本 1.0**，然后将拖**适配器提供程序**定义**\<空字符串\>**.</span><span class="sxs-lookup"><span data-stu-id="359bb-128">In Facts Explorer, expand the **ESB.TansportTypes** vocabulary, expand **Version 1.0**, and then drag the **Adaptor Providers** definition to **\<empty string\>**.</span></span>  
  
11. <span data-ttu-id="359bb-129">在操作窗格中，展开**适配器提供程序**下拉列表，再单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="359bb-129">In the Actions pane, expand the **Adaptor Providers** drop-down list, and then click **FILE**.</span></span>  
  
    <span data-ttu-id="359bb-130">**若要发布和部署策略**</span><span class="sxs-lookup"><span data-stu-id="359bb-130">**To publish and deploy the policy**</span></span>  
  
12. <span data-ttu-id="359bb-131">在策略浏览器下**RouteBasedOnMessageType**策略中，右键单击**版本 1.0 （未保存）**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="359bb-131">In Policy Explorer, under the **RouteBasedOnMessageType** policy, right click **Version 1.0 (not saved)**, and then click **Publish**.</span></span>  
  
13. <span data-ttu-id="359bb-132">在策略浏览器下**RouteBasedOnMessageType**策略中，右键单击**版本 1.0-已发布**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="359bb-132">In Policy Explorer, under the **RouteBasedOnMessageType** policy, right click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  
  
    <span data-ttu-id="359bb-133">**若要创建的 ESB 路线域特定语言 (DSL) 模型**</span><span class="sxs-lookup"><span data-stu-id="359bb-133">**To create an ESB itinerary domain-specific language (DSL) model**</span></span>  
  
14. <span data-ttu-id="359bb-134">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="359bb-134">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
15. <span data-ttu-id="359bb-135">在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="359bb-135">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
16. <span data-ttu-id="359bb-136">在中**名称**框中，键入**MessageType**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="359bb-136">In the **Name** box, type **MessageType**, and then click **Add**.</span></span>  
  
    <span data-ttu-id="359bb-137">**若要配置的路线属性**</span><span class="sxs-lookup"><span data-stu-id="359bb-137">**To configure the properties of the itinerary**</span></span>  
  
17. <span data-ttu-id="359bb-138">在 Visual Studio 中，单击的设计图面**MessageType.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="359bb-138">In Visual Studio, click the design surface of **MessageType.itinerary**.</span></span> <span data-ttu-id="359bb-139">在中**MessageType**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="359bb-139">In the **MessageType** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="359bb-140">在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="359bb-140">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="359bb-141">在中**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="359bb-141">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="359bb-142">在中**选择 XML 文件**对话框中**文件名**框中，键入**C:\HowTos\Itineraries\MessageType**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="359bb-142">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\MessageType**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="359bb-143">此步骤中，可将路线以 XML 形式导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="359bb-143">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="359bb-144">为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。</span><span class="sxs-lookup"><span data-stu-id="359bb-144">Exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="359bb-145">您将完成此过程更高版本的本操作指南主题。</span><span class="sxs-lookup"><span data-stu-id="359bb-145">You will complete this process later in this How-to topic.</span></span>  
  
    <span data-ttu-id="359bb-146">**若要定义路线的结构**</span><span class="sxs-lookup"><span data-stu-id="359bb-146">**To define the structure of the itinerary**</span></span>  
  
18. <span data-ttu-id="359bb-147">从工具箱拖动**接入点**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="359bb-147">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="359bb-148">在中**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="359bb-148">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="359bb-149">单击**名称**属性，并键入**ReceiveOrders**。</span><span class="sxs-lookup"><span data-stu-id="359bb-149">Click the **Name** property, and then type **ReceiveOrders**.</span></span>  
  
    2.  <span data-ttu-id="359bb-150">在中**Extender**下拉列表中，单击**接入点 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="359bb-150">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="359bb-151">在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="359bb-151">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="359bb-152">在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="359bb-152">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
19. <span data-ttu-id="359bb-153">从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**接入点**模型元素。</span><span class="sxs-lookup"><span data-stu-id="359bb-153">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="359bb-154">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="359bb-154">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="359bb-155">单击**名称**属性，并键入**BreRoute**。</span><span class="sxs-lookup"><span data-stu-id="359bb-155">Click the **Name** property, and then type **BreRoute**.</span></span>  
  
    2.  <span data-ttu-id="359bb-156">在**路线服务 Extender**下拉列表中，单击**消息扩展器**。</span><span class="sxs-lookup"><span data-stu-id="359bb-156">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="359bb-157">此属性定义，过程将花费 （消息传送） 管道中的位置。</span><span class="sxs-lookup"><span data-stu-id="359bb-157">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="359bb-158">或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。</span><span class="sxs-lookup"><span data-stu-id="359bb-158">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="359bb-159">在中**容器**下拉列表中，展开**ReceiveOrders**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="359bb-159">In the **Container** drop-down list, expand **ReceiveOrders**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="359bb-160">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="359bb-160">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
20. <span data-ttu-id="359bb-161">右键单击**冲突解决程序**系列**BreRoute**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="359bb-161">Right-click the **Resolver** collection of the **BreRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="359bb-162">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="359bb-162">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="359bb-163">单击**名称**属性，并键入**ByMessageType**。</span><span class="sxs-lookup"><span data-stu-id="359bb-163">Click the **Name** property, and then type **ByMessageType**.</span></span>  
  
    2.  <span data-ttu-id="359bb-164">在中**解析程序实现**下拉列表中，单击**Bre 冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="359bb-164">In the **Resolver Implementation** drop-down list, click **Bre Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="359bb-165">在中**策略**下拉列表中，单击**RouteBasedOnMessageType v 1.0**。</span><span class="sxs-lookup"><span data-stu-id="359bb-165">In the **Policy** drop-down list, click **RouteBasedOnMessageType v 1.0**.</span></span>  
  
21. <span data-ttu-id="359bb-166">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="359bb-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="359bb-167">将从连接**ReceiveOrders**到模型元素**BreRoute**模型元素。</span><span class="sxs-lookup"><span data-stu-id="359bb-167">Drag a connection from the **ReceiveOrders** model element to the **BreRoute** model element.</span></span>  
  
22. <span data-ttu-id="359bb-168">从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**BreRoute**模型元素。</span><span class="sxs-lookup"><span data-stu-id="359bb-168">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BreRoute** model element.</span></span> <span data-ttu-id="359bb-169">在中**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="359bb-169">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="359bb-170">单击**名称**属性，并键入**SendBasedOnType**。</span><span class="sxs-lookup"><span data-stu-id="359bb-170">Click the **Name** property, and then type **SendBasedOnType**.</span></span>  
  
    2.  <span data-ttu-id="359bb-171">在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="359bb-171">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="359bb-172">在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="359bb-172">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="359bb-173">在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="359bb-173">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
23. <span data-ttu-id="359bb-174">从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**BreRoute**模型元素和**SendBasedOnType**模型元素。</span><span class="sxs-lookup"><span data-stu-id="359bb-174">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BreRoute** model element and the **SendBasedOnType** model element.</span></span> <span data-ttu-id="359bb-175">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="359bb-175">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="359bb-176">单击**名称**属性，并键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="359bb-176">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="359bb-177">在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。</span><span class="sxs-lookup"><span data-stu-id="359bb-177">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="359bb-178">在中**关闭负载增加**下拉列表中，展开**SendBasedOnType**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="359bb-178">In the **Off-Ramp** drop-down list, expand **SendBasedOnType**, and then click **Send Handlers**.</span></span>  
  
24. <span data-ttu-id="359bb-179">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="359bb-179">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="359bb-180">将从连接**BreRoute**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="359bb-180">Drag a connection from the **BreRoute** model element to the **SendPortFilter** model element.</span></span>  
  
25. <span data-ttu-id="359bb-181">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="359bb-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="359bb-182">将从连接**SendPortFilter**到模型元素**SendBasedOnType**模型元素。</span><span class="sxs-lookup"><span data-stu-id="359bb-182">Drag a connection from the **SendPortFilter** model element to the **SendBasedOnType** model element.</span></span>  
  
    <span data-ttu-id="359bb-183">**若要导出与路线测试客户端一起使用的模型**</span><span class="sxs-lookup"><span data-stu-id="359bb-183">**To export the model for use with the Itinerary Test Client**</span></span>  
  
26. <span data-ttu-id="359bb-184">在 Visual Studio 中，右键单击设计图面的**MessageType**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="359bb-184">In Visual Studio, right-click the design surface of the **MessageType** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="359bb-185">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="359bb-185">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
27. <span data-ttu-id="359bb-186">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="359bb-186">Save all project artifacts.</span></span>  
  
28. <span data-ttu-id="359bb-187">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries 并请注意，您的路线 XML (MessageType.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="359bb-187">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (MessageType.xml).</span></span>  
  
    <span data-ttu-id="359bb-188">**若要测试路线**</span><span class="sxs-lookup"><span data-stu-id="359bb-188">**To test the itinerary**</span></span>  
  
29. <span data-ttu-id="359bb-189">打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="359bb-189">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
30. <span data-ttu-id="359bb-190">在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="359bb-190">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
31. <span data-ttu-id="359bb-191">在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="359bb-191">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="359bb-192">选择**MessageType.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="359bb-192">Select **MessageType.xml**, and then click **Open** to load the itinerary.</span></span>  
  
32. <span data-ttu-id="359bb-193">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="359bb-193">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
33. <span data-ttu-id="359bb-194">在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="359bb-194">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
34. <span data-ttu-id="359bb-195">在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="359bb-195">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="359bb-196">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="359bb-196">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
35. <span data-ttu-id="359bb-197">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="359bb-197">Click the **Submit Request** button.</span></span> <span data-ttu-id="359bb-198">测试完成后，单击**确定**若要消除出现的确认。</span><span class="sxs-lookup"><span data-stu-id="359bb-198">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
36. <span data-ttu-id="359bb-199">在 Windows 资源管理器，浏览到 C:\HowTos\Out\\。</span><span class="sxs-lookup"><span data-stu-id="359bb-199">In Windows Explorer, browse to C:\HowTos\Out\\.</span></span> <span data-ttu-id="359bb-200">验证 NorthAmerica%MessageID%.xml 消息已写入到目录。</span><span class="sxs-lookup"><span data-stu-id="359bb-200">Verify that the NorthAmerica%MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="359bb-201">其他资源</span><span class="sxs-lookup"><span data-stu-id="359bb-201">Additional Resources</span></span>  
 <span data-ttu-id="359bb-202">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="359bb-202">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="359bb-203">如何：选择使用业务规则策略路线</span><span class="sxs-lookup"><span data-stu-id="359bb-203">How to: Select an Itinerary Using a Business Rules Policy</span></span>](../esb-toolkit/how-to-select-an-itinerary-using-a-business-rules-policy.md)  
  
-   [<span data-ttu-id="359bb-204">如何：转换消息并将生成的消息路由到使用路线传送名单的文件位置</span><span class="sxs-lookup"><span data-stu-id="359bb-204">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="359bb-205">如何：实现基于内容的路由使用业务规则策略为已知的消息类型</span><span class="sxs-lookup"><span data-stu-id="359bb-205">How to: Implement Content-Based Routing Using a Business Rules Policy for a Known Message Type</span></span>](../esb-toolkit/apply-content-based-routing-using-business-rules-policy-for-known-message-type.md)  
  
-   [<span data-ttu-id="359bb-206">开发活动</span><span class="sxs-lookup"><span data-stu-id="359bb-206">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="359bb-207">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="359bb-207">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="359bb-208">使用动态解析和路由</span><span class="sxs-lookup"><span data-stu-id="359bb-208">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)