---
title: 如何：将一条消息路由到多个收件人使用路线传送名单 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 42c30493-4fe1-4fd5-8bc7-af091535b091
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9eb1118850c46215ebd57f25956ce3581eee844
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395895"
---
# <a name="how-to-route-a-single-message-to-multiple-recipients-using-an-itinerary-routing-slip"></a><span data-ttu-id="d6270-102">如何：将一条消息路由到多个收件人使用路线传送名单</span><span class="sxs-lookup"><span data-stu-id="d6270-102">How to: Route a Single Message to Multiple Recipients Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="d6270-103">目的</span><span class="sxs-lookup"><span data-stu-id="d6270-103">Goal</span></span>  
 <span data-ttu-id="d6270-104">本部分演示如何使用设计器特定于域的语言 (DSL) 来创建路线，将消息路由到使用静态的冲突解决程序和 BizTalk Server 文件适配器的三个不同的收件人。</span><span class="sxs-lookup"><span data-stu-id="d6270-104">This section demonstrates how to use the Designer domain-specific language (DSL) to create an itinerary that routes a message to three distinct recipients using a static resolver and the BizTalk Server FILE adapter.</span></span>  
  
 <span data-ttu-id="d6270-105">在本操作指南主题中，您将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="d6270-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="d6270-106">使用三个静态冲突解决程序将消息路由到多个收件人创建一条路线。</span><span class="sxs-lookup"><span data-stu-id="d6270-106">Create an itinerary with three static resolvers to route messages to multiple recipients.</span></span>  
  
-   <span data-ttu-id="d6270-107">测试使用路线测试客户端示例应用程序的路线。</span><span class="sxs-lookup"><span data-stu-id="d6270-107">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d6270-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="d6270-108">Prerequisites</span></span>  
 <span data-ttu-id="d6270-109">本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="d6270-109">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="d6270-110">步骤</span><span class="sxs-lookup"><span data-stu-id="d6270-110">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="d6270-111">若要创建的 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="d6270-111">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="d6270-112">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="d6270-112">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="d6270-113">在解决方案资源管理器中右键单击**ItineraryLibrary**，依次指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="d6270-113">In Solution Explorer, right-click **ItineraryLibrary**, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="d6270-114">在中**添加新项**对话框中，单击**ItineraryDsl**模板窗格中。</span><span class="sxs-lookup"><span data-stu-id="d6270-114">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="d6270-115">在中**名称**框中，键入**RecipientList**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d6270-115">In the **Name** box, type **RecipientList**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="d6270-116">若要配置的路线属性</span><span class="sxs-lookup"><span data-stu-id="d6270-116">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="d6270-117">在 Visual Studio 中，单击 RecipientList.itinerary 的设计图面。</span><span class="sxs-lookup"><span data-stu-id="d6270-117">In Visual Studio, click the design surface of RecipientList.itinerary.</span></span> <span data-ttu-id="d6270-118">在 RecipientList 属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="d6270-118">In the RecipientList Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d6270-119">在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="d6270-119">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="d6270-120">在中**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="d6270-120">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="d6270-121">在中**选择 XML 文件**对话框中**文件名**框中，键入**C:\HowTos\Itineraries\RecipientList**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="d6270-121">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\RecipientList**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d6270-122">此步骤中，可将路线以 XML 形式导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="d6270-122">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="d6270-123">通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。</span><span class="sxs-lookup"><span data-stu-id="d6270-123">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="d6270-124">您将完成此过程更高版本的本操作指南主题。</span><span class="sxs-lookup"><span data-stu-id="d6270-124">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="d6270-125">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="d6270-125">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="d6270-126">从工具箱拖动**接入点**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="d6270-126">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="d6270-127">在中**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="d6270-127">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d6270-128">单击**名称**属性，并键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="d6270-128">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="d6270-129">在中**Extender**下拉列表中，单击**接入点扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="d6270-129">In the **Extender** drop-down list, click **On-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="d6270-130">在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="d6270-130">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="d6270-131">在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="d6270-131">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="d6270-132">从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**接入点**模型元素。</span><span class="sxs-lookup"><span data-stu-id="d6270-132">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="d6270-133">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="d6270-133">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d6270-134">单击**名称**属性，并键入**RouteToThreeRecipients**。</span><span class="sxs-lookup"><span data-stu-id="d6270-134">Click the **Name** property, and then type **RouteToThreeRecipients**.</span></span>  
  
    2.  <span data-ttu-id="d6270-135">在**路线服务 Extender**下拉列表中，单击**消息扩展器**。</span><span class="sxs-lookup"><span data-stu-id="d6270-135">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d6270-136">此属性定义，过程将花费 （消息传送） 管道中的位置。</span><span class="sxs-lookup"><span data-stu-id="d6270-136">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="d6270-137">或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。</span><span class="sxs-lookup"><span data-stu-id="d6270-137">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="d6270-138">在中**容器**下拉列表中，展开**ReceiveNaOrderDoc**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="d6270-138">In the **Container** drop-down list, expand **ReceiveNaOrderDoc**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="d6270-139">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="d6270-139">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="d6270-140">右键单击**冲突解决程序**系列**RouteToThreeRecipients**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="d6270-140">Right-click the **Resolver** collection of the **RouteToThreeRecipients** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="d6270-141">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="d6270-141">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d6270-142">单击**名称**属性，并键入**FirstResolver**。</span><span class="sxs-lookup"><span data-stu-id="d6270-142">Click the **Name** property, and then type **FirstResolver**.</span></span>  
  
    2.  <span data-ttu-id="d6270-143">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="d6270-143">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="d6270-144">在中**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="d6270-144">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="d6270-145">单击**传输位置**属性，并键入**C:\HowTos\Out\First%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="d6270-145">Click the **Transport Location** property, and then type **C:\HowTos\Out\First%MessageID%.xml**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="d6270-146">已添加此路线服务的三个冲突解决程序的第一个。</span><span class="sxs-lookup"><span data-stu-id="d6270-146">You have added the first of three resolvers for this itinerary service.</span></span> <span data-ttu-id="d6270-147">现在，您将添加两个更多的解析程序来将消息路由到其他收件人。</span><span class="sxs-lookup"><span data-stu-id="d6270-147">You will now add two more resolvers to route the message to additional recipients.</span></span>  
  
4.  <span data-ttu-id="d6270-148">右键单击**冲突解决程序**系列**RouteToThreeRecipients**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="d6270-148">Right-click the **Resolver** collection of the **RouteToThreeRecipients** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="d6270-149">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="d6270-149">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d6270-150">单击**名称**属性，并键入**SecondResolver**。</span><span class="sxs-lookup"><span data-stu-id="d6270-150">Click the **Name** property, and then type **SecondResolver**.</span></span>  
  
    2.  <span data-ttu-id="d6270-151">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="d6270-151">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="d6270-152">在中**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="d6270-152">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="d6270-153">单击**传输位置**属性，并键入**C:\HowTos\Out\Second%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="d6270-153">Click the **Transport Location** property, and then type **C:\HowTos\Out\Second%MessageID%.xml**.</span></span>  
  
5.  <span data-ttu-id="d6270-154">右键单击**冲突解决程序**系列**RouteToThreeRecipients**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="d6270-154">Right-click the **Resolver** collection of the **RouteToThreeRecipients** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="d6270-155">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="d6270-155">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d6270-156">单击**名称**属性，并键入**ThirdResolver**。</span><span class="sxs-lookup"><span data-stu-id="d6270-156">Click the **Name** property, and then type **ThirdResolver**.</span></span>  
  
    2.  <span data-ttu-id="d6270-157">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="d6270-157">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="d6270-158">在中**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="d6270-158">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="d6270-159">单击**传输位置**属性，并键入**C:\HowTos\Out\Third%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="d6270-159">Click the **Transport Location** property, and then type **C:\HowTos\Out\Third%MessageID%.xml**.</span></span>  
  
6.  <span data-ttu-id="d6270-160">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="d6270-160">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="d6270-161">将从连接**ReceiveNAOrder**到模型元素**RouteToThreeRecipients**模型元素。</span><span class="sxs-lookup"><span data-stu-id="d6270-161">Drag a connection from the **ReceiveNAOrder** model element to the **RouteToThreeRecipients** model element.</span></span>  
  
7.  <span data-ttu-id="d6270-162">从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**RouteToThreeRecipients**模型元素。</span><span class="sxs-lookup"><span data-stu-id="d6270-162">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **RouteToThreeRecipients** model element.</span></span> <span data-ttu-id="d6270-163">在中**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="d6270-163">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d6270-164">单击**名称**属性，并键入**SendThreeMessages**。</span><span class="sxs-lookup"><span data-stu-id="d6270-164">Click the **Name** property, and then type **SendThreeMessages**.</span></span>  
  
    2.  <span data-ttu-id="d6270-165">在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="d6270-165">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="d6270-166">在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="d6270-166">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="d6270-167">在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="d6270-167">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
8.  <span data-ttu-id="d6270-168">从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**RouteToThreeRecipients**模型元素和**SendThreeMessages**模型元素。</span><span class="sxs-lookup"><span data-stu-id="d6270-168">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **RouteToThreeRecipients** model element and the **SendThreeMessages** model element.</span></span> <span data-ttu-id="d6270-169">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="d6270-169">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="d6270-170">单击**名称**属性，并键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="d6270-170">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="d6270-171">在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。</span><span class="sxs-lookup"><span data-stu-id="d6270-171">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="d6270-172">在中**关闭负载增加**下拉列表中，展开**SendThreeMessages**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="d6270-172">In the **Off-Ramp** drop-down list, expand **SendThreeMessages**, and then click **Send Handlers**.</span></span>  
  
9. <span data-ttu-id="d6270-173">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="d6270-173">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="d6270-174">将从连接**RouteToThreeRecipients**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="d6270-174">Drag a connection from the **RouteToThreeRecipients** model element to the **SendPortFilter** model element.</span></span>  
  
10. <span data-ttu-id="d6270-175">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="d6270-175">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="d6270-176">将从连接**SendPortFilter**到模型元素**SendThreeMessages**模型元素。</span><span class="sxs-lookup"><span data-stu-id="d6270-176">Drag a connection from the **SendPortFilter** model element to the **SendThreeMessages** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="d6270-177">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="d6270-177">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="d6270-178">在 Visual Studio 中，右键单击设计图面的**RecipientList**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="d6270-178">In Visual Studio, right-click the design surface of the **RecipientList** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d6270-179">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="d6270-179">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d6270-180">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="d6270-180">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="d6270-181">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，，然后请注意，您的路线 XML (RecipientList.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="d6270-181">In Windows Explorer, browse to C:\HowTos\Itineraries, and then notice the creation of your itinerary XML (RecipientList.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="d6270-182">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="d6270-182">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="d6270-183">打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="d6270-183">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="d6270-184">在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="d6270-184">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="d6270-185">在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="d6270-185">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="d6270-186">选择**RecipientList.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="d6270-186">Select **RecipientList.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="d6270-187">单击**确定**以清除"行程成功加载： 消息。</span><span class="sxs-lookup"><span data-stu-id="d6270-187">Click **OK** to clear the "Itinerary Loaded Successfully: message.</span></span>  
  
5.  <span data-ttu-id="d6270-188">在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="d6270-188">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="d6270-189">在中**选择要加载 XML 文档**对话框中，浏览到 C:\Patterns。</span><span class="sxs-lookup"><span data-stu-id="d6270-189">In the **Select XML Document to load** dialog box, browse to C:\Patterns.</span></span> <span data-ttu-id="d6270-190">选择 NAOrderDoc.xml，，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="d6270-190">Select NAOrderDoc.xml, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="d6270-191">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="d6270-191">Click the **Submit Request** button.</span></span> <span data-ttu-id="d6270-192">测试完成后，单击**确定**若要消除出现的确认。</span><span class="sxs-lookup"><span data-stu-id="d6270-192">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="d6270-193">在 Windows 资源管理器，浏览到 C:\HowTos\Out\\。</span><span class="sxs-lookup"><span data-stu-id="d6270-193">In Windows Explorer, browse to C:\HowTos\Out\\.</span></span> <span data-ttu-id="d6270-194">验证已将以下消息写入到目录：</span><span class="sxs-lookup"><span data-stu-id="d6270-194">Verify that the following messages have been written to the directory:</span></span>  
  
    -   <span data-ttu-id="d6270-195">First%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="d6270-195">First%MessageID%.xml</span></span>  
  
    -   <span data-ttu-id="d6270-196">Second%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="d6270-196">Second%MessageID%.xml</span></span>  
  
    -   <span data-ttu-id="d6270-197">Third%MessageID%.xml</span><span class="sxs-lookup"><span data-stu-id="d6270-197">Third%MessageID%.xml</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="d6270-198">其他资源</span><span class="sxs-lookup"><span data-stu-id="d6270-198">Additional Resources</span></span>  
 <span data-ttu-id="d6270-199">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="d6270-199">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="d6270-200">开发活动</span><span class="sxs-lookup"><span data-stu-id="d6270-200">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="d6270-201">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="d6270-201">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="d6270-202">使用动态解析和路由</span><span class="sxs-lookup"><span data-stu-id="d6270-202">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)