---
title: 如何： 转换消息和使用请求-响应消息交换模式的服务终结点的路由 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b1e656fb-6c5f-4b2b-a1b6-4c812b78ee22
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 071227182eb9b5550b23e23463800cc7dd5a22c4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010350"
---
# <a name="how-to-transform-a-message-and-route-to-a-service-endpoint-using-a-request-response-message-exchange-pattern"></a><span data-ttu-id="5a012-102">如何： 转换消息和使用请求-响应消息交换模式的服务终结点的路由</span><span class="sxs-lookup"><span data-stu-id="5a012-102">How to: Transform a Message and Route to a Service Endpoint Using a Request-Response Message Exchange Pattern</span></span>
## <a name="goal"></a><span data-ttu-id="5a012-103">目的</span><span class="sxs-lookup"><span data-stu-id="5a012-103">Goal</span></span>  
 <span data-ttu-id="5a012-104">本部分演示如何使用 ESB 设计器域特定语言 (DSL) 来创建可与双向入口使用请求-响应路线。</span><span class="sxs-lookup"><span data-stu-id="5a012-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create a request-response itinerary that can be used with a two-way on-ramp.</span></span> <span data-ttu-id="5a012-105">你将创建要收到一条消息、 消息转换、 提交到服务，消息和返回到原始消息的提交者的服务的响应消息的路由单。</span><span class="sxs-lookup"><span data-stu-id="5a012-105">You will create a routing slip to receive a message, transform the message, submit the message to a service, and return the service response message to the submitter of the original message.</span></span>  
  
 <span data-ttu-id="5a012-106">在本操作方法主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5a012-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="5a012-107">创建转换路线服务实现 Microsoft BizTalk Server 映射路线的路由滑动。</span><span class="sxs-lookup"><span data-stu-id="5a012-107">Create an itinerary routing slip with a transform itinerary service that implements a Microsoft BizTalk Server map.</span></span>  
  
-   <span data-ttu-id="5a012-108">配置路线将已转换的消息路由到服务终结点。</span><span class="sxs-lookup"><span data-stu-id="5a012-108">Configure the itinerary to route the transformed message to a service endpoint.</span></span>  
  
-   <span data-ttu-id="5a012-109">配置路线以返回到原始发送方的服务响应消息。</span><span class="sxs-lookup"><span data-stu-id="5a012-109">Configure the itinerary to return the service response message to the original sending party.</span></span>  
  
-   <span data-ttu-id="5a012-110">测试路线使用路线测试客户端示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="5a012-110">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5a012-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="5a012-111">Prerequisites</span></span>  
 <span data-ttu-id="5a012-112">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="5a012-112">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="5a012-113">步骤</span><span class="sxs-lookup"><span data-stu-id="5a012-113">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="5a012-114">若要创建 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="5a012-114">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="5a012-115">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="5a012-115">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="5a012-116">在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="5a012-116">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="5a012-117">在**添加新项**对话框中，在**名称**框中，键入**请求响应**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="5a012-117">In the **Add New Item** dialog box, in the **Name** box, type **RequestResponse**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="5a012-118">若要配置路线的属性</span><span class="sxs-lookup"><span data-stu-id="5a012-118">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="5a012-119">在 Visual Studio 中，单击的设计图面**RequestResponse.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="5a012-119">In Visual Studio, click the design surface of **RequestResponse.itinerary**.</span></span> <span data-ttu-id="5a012-120">在**请求响应**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="5a012-120">In the **RequestResponse** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="5a012-121">在**是请求响应**下拉列表中，单击**True**。</span><span class="sxs-lookup"><span data-stu-id="5a012-121">In the **Is Request Response** drop-down list, click **True**.</span></span>  
  
    2.  <span data-ttu-id="5a012-122">在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-122">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    3.  <span data-ttu-id="5a012-123">在**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。</span><span class="sxs-lookup"><span data-stu-id="5a012-123">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    4.  <span data-ttu-id="5a012-124">在**选择 XML 文件**对话框中，在**文件名**框中，键入**C:\HowTos\Itineraries\RequestResponse**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="5a012-124">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\RequestResponse**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5a012-125">此步骤允许您路线作为 XML 导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="5a012-125">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="5a012-126">通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="5a012-126">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="5a012-127">你将完成本操作方法主题中后面此过程。</span><span class="sxs-lookup"><span data-stu-id="5a012-127">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="5a012-128">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="5a012-128">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="5a012-129">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="5a012-129">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="5a012-130">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="5a012-130">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="5a012-131">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="5a012-131">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="5a012-132">在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-132">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="5a012-133">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="5a012-133">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="5a012-134">在**接收端口**下拉列表中，单击**OnRamp.Itinerary.Response**。</span><span class="sxs-lookup"><span data-stu-id="5a012-134">In the **Receive Port** drop-down list, click **OnRamp.Itinerary.Response**.</span></span>  
  
2.  <span data-ttu-id="5a012-135">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**上负载增加**模型元素。</span><span class="sxs-lookup"><span data-stu-id="5a012-135">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="5a012-136">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="5a012-136">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="5a012-137">单击**名称**属性，再然后键入**MapNAOrderToCNOrder**。</span><span class="sxs-lookup"><span data-stu-id="5a012-137">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="5a012-138">在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-138">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5a012-139">此属性定义的过程将需要在管道 （消息传送） 中的位置。</span><span class="sxs-lookup"><span data-stu-id="5a012-139">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="5a012-140">或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-140">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="5a012-141">在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-141">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="5a012-142">在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="5a012-142">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="5a012-143">右键单击**冲突解决程序**集合**MapNAOrderToCNOrder**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-143">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="5a012-144">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="5a012-144">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="5a012-145">单击**名称**属性，再然后键入**StaticallySpecifyTheMap**。</span><span class="sxs-lookup"><span data-stu-id="5a012-145">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="5a012-146">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="5a012-146">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="5a012-147">在**转换类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。</span><span class="sxs-lookup"><span data-stu-id="5a012-147">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
4.  <span data-ttu-id="5a012-148">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="5a012-148">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="5a012-149">将从连接**ReceiveNAOrder**到模型元素**MapNAOrderToCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="5a012-149">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="5a012-150">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**MapNAOrderToCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="5a012-150">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="5a012-151">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="5a012-151">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="5a012-152">单击**名称**属性，再然后键入**RouteToCNService**。</span><span class="sxs-lookup"><span data-stu-id="5a012-152">Click the **Name** property, and then type **RouteToCNService**.</span></span>  
  
    2.  <span data-ttu-id="5a012-153">在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-153">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5a012-154">此属性定义的过程将需要在管道 （消息传送） 中的位置。</span><span class="sxs-lookup"><span data-stu-id="5a012-154">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="5a012-155">或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-155">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="5a012-156">在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-156">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="5a012-157">在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="5a012-157">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
6.  <span data-ttu-id="5a012-158">右键单击**冲突解决程序**集合**RouteToCNService**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-158">Right-click the **Resolver** collection of the **RouteToCNService** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="5a012-159">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="5a012-159">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="5a012-160">单击**名称**属性，再然后键入**StaticallySpecifyTheService**。</span><span class="sxs-lookup"><span data-stu-id="5a012-160">Click the **Name** property, and then type **StaticallySpecifyTheService**.</span></span>  
  
    2.  <span data-ttu-id="5a012-161">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="5a012-161">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="5a012-162">在**传输名称**下拉列表中，单击**WCF BasicHttp**。</span><span class="sxs-lookup"><span data-stu-id="5a012-162">In the **Transport Name** drop-down list, click **WCF-BasicHttp**.</span></span>  
  
    4.  <span data-ttu-id="5a012-163">单击**传输位置**属性，再然后键入**http://localhost/ESB.CanadianServices/SubmitPOService.asmx**。</span><span class="sxs-lookup"><span data-stu-id="5a012-163">Click the **Transport Location** property, and then type **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.</span></span>  
  
    5.  <span data-ttu-id="5a012-164">单击**目标 Namespace**属性，再然后键入**http://globalbank.esb.dynamicresolution.com/canadianservices**。</span><span class="sxs-lookup"><span data-stu-id="5a012-164">Click the **Target Namespace** property, and then type **http://globalbank.esb.dynamicresolution.com/canadianservices**.</span></span>  
  
    6.  <span data-ttu-id="5a012-165">单击**操作**属性，再然后键入**将订单**。</span><span class="sxs-lookup"><span data-stu-id="5a012-165">Click the **Action** property, and then type **submitOrder**.</span></span>  
  
7.  <span data-ttu-id="5a012-166">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="5a012-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="5a012-167">将从连接**MapNAOrderToCNOrder**到模型元素**RouteToCNService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="5a012-167">Drag a connection from the **MapNAOrderToCNOrder** model element to the **RouteToCNService** model element.</span></span>  
  
8.  <span data-ttu-id="5a012-168">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**RouteToCNService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="5a012-168">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToCNService** model element.</span></span> <span data-ttu-id="5a012-169">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="5a012-169">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="5a012-170">单击**名称**属性，再然后键入**InvokeCNService**。</span><span class="sxs-lookup"><span data-stu-id="5a012-170">Click the **Name** property, and then type **InvokeCNService**.</span></span>  
  
    2.  <span data-ttu-id="5a012-171">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-171">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="5a012-172">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="5a012-172">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="5a012-173">在**发送端口**下拉列表中，单击**DynamicResolutionSolicitResp**。</span><span class="sxs-lookup"><span data-stu-id="5a012-173">In the **Send Port** drop-down list, click **DynamicResolutionSolicitResp**.</span></span>  
  
9. <span data-ttu-id="5a012-174">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**RouteToCNService**模型元素和**InvokeCNService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="5a012-174">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToCNService** model element and the **InvokeCNService** model element.</span></span> <span data-ttu-id="5a012-175">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="5a012-175">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="5a012-176">单击**名称**属性，再然后键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="5a012-176">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="5a012-177">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-177">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="5a012-178">在**关闭负载增加**下拉列表中，展开**InvokeCNService**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="5a012-178">In the **Off-Ramp** drop-down list, expand **InvokeCNService**, and then click **Send Handlers**.</span></span>  
  
10. <span data-ttu-id="5a012-179">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="5a012-179">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="5a012-180">将从连接**RouteToCNService**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="5a012-180">Drag a connection from the **RouteToCNService** model element to the **SendPortFilter** model element.</span></span>  
  
11. <span data-ttu-id="5a012-181">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="5a012-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="5a012-182">将从连接**SendPortFilter**到模型元素**InvokeCNService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="5a012-182">Drag a connection from the **SendPortFilter** model element to the **InvokeCNService** model element.</span></span>  
  
12. <span data-ttu-id="5a012-183">右键单击设计图面上，并依次**验证**。</span><span class="sxs-lookup"><span data-stu-id="5a012-183">Right-click the design surface, and then click **Validate**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5a012-184">路线验证;不需要返回到上负载增加连接关闭负载增加，以将响应消息发送回请求方。</span><span class="sxs-lookup"><span data-stu-id="5a012-184">The itinerary validates; it is not necessary to connect the off-ramp back to the on-ramp in order to send the response message back to the requesting party.</span></span> <span data-ttu-id="5a012-185">通过使用双向入口，最后一条消息将自动返回给请求方。</span><span class="sxs-lookup"><span data-stu-id="5a012-185">By using a two-way on-ramp, the final message is automatically returned to the requesting party.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="5a012-186">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="5a012-186">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="5a012-187">在 Visual Studio 中，右键单击的设计图面**请求响应**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="5a012-187">In Visual Studio, right-click the design surface of the **RequestResponse** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5a012-188">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="5a012-188">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="5a012-189">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="5a012-189">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="5a012-190">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="5a012-190">In Windows Explorer, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="5a012-191">请注意你路线 XML (RequestResponse.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="5a012-191">Notice the creation of your itinerary XML (RequestResponse.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="5a012-192">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="5a012-192">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="5a012-193">打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="5a012-193">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="5a012-194">在路线测试客户端中，清除**使用 WCF 服务**复选框。</span><span class="sxs-lookup"><span data-stu-id="5a012-194">In the Itinerary Test Client, clear the **Use WCF Service** check box.</span></span>  
  
3.  <span data-ttu-id="5a012-195">在**Web 服务选项**部分中，选择**两个方式服务**复选框，并依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="5a012-195">In the **Web Service Options** section, select the **Two Way Service** check box, and then click **Load Itinerary**.</span></span>  
  
4.  <span data-ttu-id="5a012-196">在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="5a012-196">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="5a012-197">选择**RequestResponse.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="5a012-197">Select **RequestResponse.xml**, and then click **Open** to load the itinerary.</span></span>  
  
5.  <span data-ttu-id="5a012-198">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="5a012-198">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
6.  <span data-ttu-id="5a012-199">在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="5a012-199">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
7.  <span data-ttu-id="5a012-200">在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="5a012-200">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="5a012-201">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="5a012-201">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
8.  <span data-ttu-id="5a012-202">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="5a012-202">Click the **Submit Request** button.</span></span> <span data-ttu-id="5a012-203">在测试完成后，单击**确定**关闭出现的确认。</span><span class="sxs-lookup"><span data-stu-id="5a012-203">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
9. <span data-ttu-id="5a012-204">在**结果**框中，注意到消息的根节点是**submitOrderResponse**的默认命名空间和...**canadianservices**。</span><span class="sxs-lookup"><span data-stu-id="5a012-204">In the **Results** box, notice the message's root node is **submitOrderResponse** and the default namespace is ... **canadianservices**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5a012-205">如果响应消息响应发送到请求方之前需要其他转换，则必须使用包含 ESB 转发器组件的管道。</span><span class="sxs-lookup"><span data-stu-id="5a012-205">If the response message requires additional transformation before the response is sent to the requesting party, you must use a pipeline that contains the ESB Forwarder component.</span></span> <span data-ttu-id="5a012-206">有关此功能的示例，请参阅[安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="5a012-206">For an example of this functionality, see the [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="5a012-207">其他资源</span><span class="sxs-lookup"><span data-stu-id="5a012-207">Additional Resources</span></span>  
 <span data-ttu-id="5a012-208">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="5a012-208">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="5a012-209">如何：转换消息并使用路线传送名单将生成的消息路由至文件位置</span><span class="sxs-lookup"><span data-stu-id="5a012-209">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="5a012-210">开发活动</span><span class="sxs-lookup"><span data-stu-id="5a012-210">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="5a012-211">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="5a012-211">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="5a012-212">安装和运行多个 Web 服务示例</span><span class="sxs-lookup"><span data-stu-id="5a012-212">Installing and Running the Multiple Web Services Sample</span></span>](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)