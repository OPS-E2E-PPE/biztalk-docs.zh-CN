---
title: 如何：转换消息并使用请求-响应消息交换模式的服务终结点的路由 |Microsoft Docs
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
ms.openlocfilehash: e7bea07435e4d9bf10df8e47fda319a0fd106ed9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399648"
---
# <a name="how-to-transform-a-message-and-route-to-a-service-endpoint-using-a-request-response-message-exchange-pattern"></a><span data-ttu-id="a790f-102">如何：转换消息并使用请求-响应消息交换模式的服务终结点的路由</span><span class="sxs-lookup"><span data-stu-id="a790f-102">How to: Transform a Message and Route to a Service Endpoint Using a Request-Response Message Exchange Pattern</span></span>
## <a name="goal"></a><span data-ttu-id="a790f-103">目的</span><span class="sxs-lookup"><span data-stu-id="a790f-103">Goal</span></span>  
 <span data-ttu-id="a790f-104">本部分演示如何使用 ESB 设计器特定于域的语言 (DSL) 来创建可用于双向接入点请求-响应路线。</span><span class="sxs-lookup"><span data-stu-id="a790f-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create a request-response itinerary that can be used with a two-way on-ramp.</span></span> <span data-ttu-id="a790f-105">您将创建一个传送名单收到一条消息、 将消息转换、 提交到服务，消息和服务响应消息返回到原始消息的提交者。</span><span class="sxs-lookup"><span data-stu-id="a790f-105">You will create a routing slip to receive a message, transform the message, submit the message to a service, and return the service response message to the submitter of the original message.</span></span>  
  
 <span data-ttu-id="a790f-106">在本操作指南主题中，您将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a790f-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="a790f-107">使用实现了一个 Microsoft BizTalk Server 映射转换路线服务创建路线传送名单。</span><span class="sxs-lookup"><span data-stu-id="a790f-107">Create an itinerary routing slip with a transform itinerary service that implements a Microsoft BizTalk Server map.</span></span>  
  
-   <span data-ttu-id="a790f-108">配置路线以便将转换后的消息路由到服务终结点。</span><span class="sxs-lookup"><span data-stu-id="a790f-108">Configure the itinerary to route the transformed message to a service endpoint.</span></span>  
  
-   <span data-ttu-id="a790f-109">配置路线服务响应消息返回到原始发送方。</span><span class="sxs-lookup"><span data-stu-id="a790f-109">Configure the itinerary to return the service response message to the original sending party.</span></span>  
  
-   <span data-ttu-id="a790f-110">测试使用路线测试客户端示例应用程序的路线。</span><span class="sxs-lookup"><span data-stu-id="a790f-110">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a790f-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="a790f-111">Prerequisites</span></span>  
 <span data-ttu-id="a790f-112">本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="a790f-112">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="a790f-113">步骤</span><span class="sxs-lookup"><span data-stu-id="a790f-113">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="a790f-114">若要创建的 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="a790f-114">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="a790f-115">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="a790f-115">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="a790f-116">在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="a790f-116">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="a790f-117">在中**添加新项**对话框中**名称**框中，键入**RequestResponse**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="a790f-117">In the **Add New Item** dialog box, in the **Name** box, type **RequestResponse**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="a790f-118">若要配置的路线属性</span><span class="sxs-lookup"><span data-stu-id="a790f-118">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="a790f-119">在 Visual Studio 中，单击的设计图面**RequestResponse.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="a790f-119">In Visual Studio, click the design surface of **RequestResponse.itinerary**.</span></span> <span data-ttu-id="a790f-120">在中**RequestResponse**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a790f-120">In the **RequestResponse** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a790f-121">在中**是请求响应**下拉列表中，单击**True**。</span><span class="sxs-lookup"><span data-stu-id="a790f-121">In the **Is Request Response** drop-down list, click **True**.</span></span>  
  
    2.  <span data-ttu-id="a790f-122">在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="a790f-122">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    3.  <span data-ttu-id="a790f-123">在中**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="a790f-123">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    4.  <span data-ttu-id="a790f-124">在中**选择 XML 文件**对话框中**文件名**框中，键入**C:\HowTos\Itineraries\RequestResponse**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="a790f-124">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\RequestResponse**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a790f-125">此步骤中，可将路线以 XML 形式导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="a790f-125">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="a790f-126">通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。</span><span class="sxs-lookup"><span data-stu-id="a790f-126">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="a790f-127">您将完成此过程更高版本的本操作指南主题。</span><span class="sxs-lookup"><span data-stu-id="a790f-127">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="a790f-128">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="a790f-128">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="a790f-129">从工具箱拖动**接入点**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="a790f-129">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="a790f-130">在中**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a790f-130">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a790f-131">单击**名称**属性，并键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="a790f-131">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="a790f-132">在中**Extender**下拉列表中，单击**接入点 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="a790f-132">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="a790f-133">在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="a790f-133">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="a790f-134">在中**接收端口**下拉列表中，单击**OnRamp.Itinerary.Response**。</span><span class="sxs-lookup"><span data-stu-id="a790f-134">In the **Receive Port** drop-down list, click **OnRamp.Itinerary.Response**.</span></span>  
  
2.  <span data-ttu-id="a790f-135">从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**接入点**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a790f-135">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="a790f-136">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a790f-136">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a790f-137">单击**名称**属性，并键入**MapNAOrderToCNOrder**。</span><span class="sxs-lookup"><span data-stu-id="a790f-137">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="a790f-138">在**路线服务 Extender**下拉列表中，单击**消息扩展器**。</span><span class="sxs-lookup"><span data-stu-id="a790f-138">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a790f-139">此属性定义，过程将花费 （消息传送） 管道中的位置。</span><span class="sxs-lookup"><span data-stu-id="a790f-139">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="a790f-140">或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。</span><span class="sxs-lookup"><span data-stu-id="a790f-140">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="a790f-141">在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="a790f-141">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="a790f-142">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="a790f-142">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="a790f-143">右键单击**冲突解决程序**系列**MapNAOrderToCNOrder**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="a790f-143">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="a790f-144">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a790f-144">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a790f-145">单击**名称**属性，并键入**StaticallySpecifyTheMap**。</span><span class="sxs-lookup"><span data-stu-id="a790f-145">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="a790f-146">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="a790f-146">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="a790f-147">在中**转换的类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。</span><span class="sxs-lookup"><span data-stu-id="a790f-147">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
4.  <span data-ttu-id="a790f-148">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="a790f-148">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a790f-149">将从连接**ReceiveNAOrder**到模型元素**MapNAOrderToCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a790f-149">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="a790f-150">从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**MapNAOrderToCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a790f-150">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="a790f-151">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a790f-151">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a790f-152">单击**名称**属性，并键入**RouteToCNService**。</span><span class="sxs-lookup"><span data-stu-id="a790f-152">Click the **Name** property, and then type **RouteToCNService**.</span></span>  
  
    2.  <span data-ttu-id="a790f-153">在**路线服务 Extender**下拉列表中，单击**消息扩展器**。</span><span class="sxs-lookup"><span data-stu-id="a790f-153">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a790f-154">此属性定义，过程将花费 （消息传送） 管道中的位置。</span><span class="sxs-lookup"><span data-stu-id="a790f-154">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="a790f-155">或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。</span><span class="sxs-lookup"><span data-stu-id="a790f-155">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="a790f-156">在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="a790f-156">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="a790f-157">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="a790f-157">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
6.  <span data-ttu-id="a790f-158">右键单击**冲突解决程序**系列**RouteToCNService**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="a790f-158">Right-click the **Resolver** collection of the **RouteToCNService** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="a790f-159">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a790f-159">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a790f-160">单击**名称**属性，并键入**StaticallySpecifyTheService**。</span><span class="sxs-lookup"><span data-stu-id="a790f-160">Click the **Name** property, and then type **StaticallySpecifyTheService**.</span></span>  
  
    2.  <span data-ttu-id="a790f-161">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="a790f-161">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="a790f-162">在中**传输名称**下拉列表中，单击**Wcf-basichttp**。</span><span class="sxs-lookup"><span data-stu-id="a790f-162">In the **Transport Name** drop-down list, click **WCF-BasicHttp**.</span></span>  
  
    4.  <span data-ttu-id="a790f-163">单击**传输位置**属性，并键入**http://localhost/ESB.CanadianServices/SubmitPOService.asmx**。</span><span class="sxs-lookup"><span data-stu-id="a790f-163">Click the **Transport Location** property, and then type **http://localhost/ESB.CanadianServices/SubmitPOService.asmx**.</span></span>  
  
    5.  <span data-ttu-id="a790f-164">单击**目标 Namespace**属性，并键入**http://globalbank.esb.dynamicresolution.com/canadianservices**。</span><span class="sxs-lookup"><span data-stu-id="a790f-164">Click the **Target Namespace** property, and then type **http://globalbank.esb.dynamicresolution.com/canadianservices**.</span></span>  
  
    6.  <span data-ttu-id="a790f-165">单击**操作**属性，并键入**submitOrder**。</span><span class="sxs-lookup"><span data-stu-id="a790f-165">Click the **Action** property, and then type **submitOrder**.</span></span>  
  
7.  <span data-ttu-id="a790f-166">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="a790f-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a790f-167">将从连接**MapNAOrderToCNOrder**到模型元素**RouteToCNService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a790f-167">Drag a connection from the **MapNAOrderToCNOrder** model element to the **RouteToCNService** model element.</span></span>  
  
8.  <span data-ttu-id="a790f-168">从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**RouteToCNService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a790f-168">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToCNService** model element.</span></span> <span data-ttu-id="a790f-169">在中**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a790f-169">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a790f-170">单击**名称**属性，并键入**InvokeCNService**。</span><span class="sxs-lookup"><span data-stu-id="a790f-170">Click the **Name** property, and then type **InvokeCNService**.</span></span>  
  
    2.  <span data-ttu-id="a790f-171">在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="a790f-171">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="a790f-172">在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="a790f-172">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="a790f-173">在中**发送端口**下拉列表中，单击**DynamicResolutionSolicitResp**。</span><span class="sxs-lookup"><span data-stu-id="a790f-173">In the **Send Port** drop-down list, click **DynamicResolutionSolicitResp**.</span></span>  
  
9. <span data-ttu-id="a790f-174">从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**RouteToCNService**模型元素和**InvokeCNService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a790f-174">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToCNService** model element and the **InvokeCNService** model element.</span></span> <span data-ttu-id="a790f-175">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a790f-175">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a790f-176">单击**名称**属性，并键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="a790f-176">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="a790f-177">在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。</span><span class="sxs-lookup"><span data-stu-id="a790f-177">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="a790f-178">在中**关闭负载增加**下拉列表中，展开**InvokeCNService**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="a790f-178">In the **Off-Ramp** drop-down list, expand **InvokeCNService**, and then click **Send Handlers**.</span></span>  
  
10. <span data-ttu-id="a790f-179">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="a790f-179">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a790f-180">将从连接**RouteToCNService**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a790f-180">Drag a connection from the **RouteToCNService** model element to the **SendPortFilter** model element.</span></span>  
  
11. <span data-ttu-id="a790f-181">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="a790f-181">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a790f-182">将从连接**SendPortFilter**到模型元素**InvokeCNService**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a790f-182">Drag a connection from the **SendPortFilter** model element to the **InvokeCNService** model element.</span></span>  
  
12. <span data-ttu-id="a790f-183">右键单击设计图面上，然后依次**验证**。</span><span class="sxs-lookup"><span data-stu-id="a790f-183">Right-click the design surface, and then click **Validate**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a790f-184">路线验证;不需要关闭负载增加重新连接到了的途径，若要将响应消息发送回请求方。</span><span class="sxs-lookup"><span data-stu-id="a790f-184">The itinerary validates; it is not necessary to connect the off-ramp back to the on-ramp in order to send the response message back to the requesting party.</span></span> <span data-ttu-id="a790f-185">通过使用双向接入点，最后一条消息自动返回到请求方。</span><span class="sxs-lookup"><span data-stu-id="a790f-185">By using a two-way on-ramp, the final message is automatically returned to the requesting party.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="a790f-186">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="a790f-186">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="a790f-187">在 Visual Studio 中，右键单击设计图面的**RequestResponse**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="a790f-187">In Visual Studio, right-click the design surface of the **RequestResponse** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a790f-188">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="a790f-188">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a790f-189">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="a790f-189">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="a790f-190">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="a790f-190">In Windows Explorer, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="a790f-191">请注意，您的路线 XML (RequestResponse.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="a790f-191">Notice the creation of your itinerary XML (RequestResponse.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="a790f-192">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="a790f-192">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="a790f-193">打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="a790f-193">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="a790f-194">在路线测试客户端，清除**使用 WCF 服务**复选框。</span><span class="sxs-lookup"><span data-stu-id="a790f-194">In the Itinerary Test Client, clear the **Use WCF Service** check box.</span></span>  
  
3.  <span data-ttu-id="a790f-195">在中**Web 服务选项**部分中，选择**两种方式服务**复选框，然后依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="a790f-195">In the **Web Service Options** section, select the **Two Way Service** check box, and then click **Load Itinerary**.</span></span>  
  
4.  <span data-ttu-id="a790f-196">在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="a790f-196">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="a790f-197">选择**RequestResponse.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="a790f-197">Select **RequestResponse.xml**, and then click **Open** to load the itinerary.</span></span>  
  
5.  <span data-ttu-id="a790f-198">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="a790f-198">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
6.  <span data-ttu-id="a790f-199">在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="a790f-199">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
7.  <span data-ttu-id="a790f-200">在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="a790f-200">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="a790f-201">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="a790f-201">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
8.  <span data-ttu-id="a790f-202">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="a790f-202">Click the **Submit Request** button.</span></span> <span data-ttu-id="a790f-203">测试完成后，单击**确定**若要消除出现的确认。</span><span class="sxs-lookup"><span data-stu-id="a790f-203">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
9. <span data-ttu-id="a790f-204">在中**结果**框中，请注意，消息的根节点是**submitOrderResponse**和默认命名空间是...**canadianservices**。</span><span class="sxs-lookup"><span data-stu-id="a790f-204">In the **Results** box, notice the message's root node is **submitOrderResponse** and the default namespace is ... **canadianservices**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a790f-205">如果响应消息响应发送到请求方之前需要其他转换，则必须使用包含 ESB 转发器组件的管道。</span><span class="sxs-lookup"><span data-stu-id="a790f-205">If the response message requires additional transformation before the response is sent to the requesting party, you must use a pipeline that contains the ESB Forwarder component.</span></span> <span data-ttu-id="a790f-206">有关此功能的示例，请参阅[安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="a790f-206">For an example of this functionality, see the [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="a790f-207">其他资源</span><span class="sxs-lookup"><span data-stu-id="a790f-207">Additional Resources</span></span>  
 <span data-ttu-id="a790f-208">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="a790f-208">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="a790f-209">如何：转换消息并将生成的消息路由到使用路线传送名单的文件位置</span><span class="sxs-lookup"><span data-stu-id="a790f-209">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>](../esb-toolkit/transform-message-and-route-the-message-to-a-location-using-itinerary-routing.md)  
  
-   [<span data-ttu-id="a790f-210">开发活动</span><span class="sxs-lookup"><span data-stu-id="a790f-210">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="a790f-211">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="a790f-211">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="a790f-212">安装和运行多个 Web 服务示例</span><span class="sxs-lookup"><span data-stu-id="a790f-212">Installing and Running the Multiple Web Services Sample</span></span>](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)