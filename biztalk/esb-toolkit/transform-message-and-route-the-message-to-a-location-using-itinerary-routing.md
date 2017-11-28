---
title: "如何： 转换一条消息，并将生成的消息路由到使用路线的路由滑动某个文件位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c27749ba-c228-4cd4-827e-e8009a0c999d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18caef7d7c60fa7aa129baa787c746b3b797c808
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-transform-a-message-and-route-the-resulting-message-to-a-file-location-using-an-itinerary-routing-slip"></a><span data-ttu-id="f0de6-102">如何： 转换一条消息，并将生成的消息路由到使用路线的路由滑动某个文件位置</span><span class="sxs-lookup"><span data-stu-id="f0de6-102">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="f0de6-103">目的</span><span class="sxs-lookup"><span data-stu-id="f0de6-103">Goal</span></span>  
 <span data-ttu-id="f0de6-104">本部分演示如何使用 ESB 设计器域特定语言 (DSL) 来创建一条路线实现消息转换通过调用 BizTalk 映射，并随后它将路由使用的消息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]文件适配器。</span><span class="sxs-lookup"><span data-stu-id="f0de6-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary that implements message transformation by invoking a BizTalk map, and then it routes the messages using the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] FILE adapter.</span></span>  
  
 <span data-ttu-id="f0de6-105">在本操作方法主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f0de6-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="f0de6-106">使用实现 BizTalk 映射转换路线服务创建路线的路由滑动。</span><span class="sxs-lookup"><span data-stu-id="f0de6-106">Create an itinerary routing slip with a transform itinerary service that implements a BizTalk map.</span></span>  
  
-   <span data-ttu-id="f0de6-107">配置路线将已转换的消息路由到的文件位置。</span><span class="sxs-lookup"><span data-stu-id="f0de6-107">Configure the itinerary to route the transformed message to a file location.</span></span>  
  
-   <span data-ttu-id="f0de6-108">测试路线使用路线测试客户端示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0de6-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f0de6-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="f0de6-109">Prerequisites</span></span>  
 <span data-ttu-id="f0de6-110">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="f0de6-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="f0de6-111">步骤</span><span class="sxs-lookup"><span data-stu-id="f0de6-111">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="f0de6-112">若要创建 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="f0de6-112">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="f0de6-113">在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="f0de6-113">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="f0de6-114">在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-114">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="f0de6-115">在**添加新项**对话框中，单击**ItineraryDsl**在模板窗格中。</span><span class="sxs-lookup"><span data-stu-id="f0de6-115">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="f0de6-116">在**名称**框中，键入**DataModelTransformation**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-116">In the **Name** box, type **DataModelTransformation**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="f0de6-117">若要配置路线的属性</span><span class="sxs-lookup"><span data-stu-id="f0de6-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="f0de6-118">在 Visual Studio 中，单击的设计图面**DataModelTransformation.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-118">In Visual Studio, click the design surface of **DataModelTransformation.itinerary**.</span></span> <span data-ttu-id="f0de6-119">在**DataModelTransformation**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f0de6-119">In the **DataModelTransformation** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f0de6-120">在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="f0de6-121">在**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。</span><span class="sxs-lookup"><span data-stu-id="f0de6-121">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="f0de6-122">在**选择 XML 文件**对话框中，在**文件名**框中，键入**C:\HowTos\Itineraries\DataModelTransformation**，然后单击**保存**.</span><span class="sxs-lookup"><span data-stu-id="f0de6-122">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\DataModelTransformation**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f0de6-123">此步骤允许您路线作为 XML 导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="f0de6-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="f0de6-124">通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0de6-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="f0de6-125">你将完成本操作方法主题中后面此过程。</span><span class="sxs-lookup"><span data-stu-id="f0de6-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="f0de6-126">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="f0de6-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="f0de6-127">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="f0de6-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="f0de6-128">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f0de6-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f0de6-129">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="f0de6-130">在**扩展程序**下拉列表中，单击**上负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-130">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="f0de6-131">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="f0de6-132">在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="f0de6-133">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**上负载增加**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f0de6-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="f0de6-134">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f0de6-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f0de6-135">单击**名称**属性，再然后键入**MapNAOrderToCNOrder**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-135">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="f0de6-136">在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f0de6-137">此属性定义的过程将需要在管道 （消息传送） 中的位置。</span><span class="sxs-lookup"><span data-stu-id="f0de6-137">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="f0de6-138">或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-138">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="f0de6-139">在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-139">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="f0de6-140">在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-140">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="f0de6-141">右键单击**冲突解决程序**集合**MapNAOrderToCNOrder**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-141">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="f0de6-142">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f0de6-142">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f0de6-143">单击**名称**属性，再然后键入**StaticallySpecifyTheMap**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-143">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="f0de6-144">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-144">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="f0de6-145">在**转换类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-145">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
    4.  <span data-ttu-id="f0de6-146">在**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-146">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
4.  <span data-ttu-id="f0de6-147">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-147">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f0de6-148">将从连接**ReceiveNAOrder**到模型元素**MapNAOrderToCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f0de6-148">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="f0de6-149">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**MapNAOrderToCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f0de6-149">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="f0de6-150">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f0de6-150">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f0de6-151">单击**名称**属性，再然后键入**SendCNOrder**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-151">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="f0de6-152">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-152">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="f0de6-153">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-153">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="f0de6-154">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-154">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="f0de6-155">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**MapNAOrderToCNOrder**模型元素和**SendCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f0de6-155">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **MapNAOrderToCNOrder** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="f0de6-156">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f0de6-156">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f0de6-157">单击**名称**属性，再然后键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-157">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="f0de6-158">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-158">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="f0de6-159">在**关闭负载增加**下拉列表中，展开**SendCNOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-159">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="f0de6-160">右键单击**冲突解决程序**集合**SendPortFilter**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-160">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="f0de6-161">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="f0de6-161">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="f0de6-162">单击**名称**属性，再然后键入**ConfigureFolderSettings**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-162">Click the **Name** property, and then type **ConfigureFolderSettings**.</span></span>  
  
    2.  <span data-ttu-id="f0de6-163">在**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-163">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    3.  <span data-ttu-id="f0de6-164">单击**传输位置**属性，再然后键入**C:\HowTos\Out\\%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-164">Click the **Transport Location** property, and then type **C:\HowTos\Out\\%MessageID%.xml**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f0de6-165">每个关闭提升将会获得与它; 路线服务路线服务属性和关闭负载增加的属性的组合定义动态发送端口的订阅。</span><span class="sxs-lookup"><span data-stu-id="f0de6-165">Each off-ramp will have an Itinerary Service associated with it; the combination of the Itinerary Service properties and the properties of the off-ramp define the subscription of the dynamic send port.</span></span>  
  
8.  <span data-ttu-id="f0de6-166">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f0de6-167">将从连接**MapNAOrderToCNOrder**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f0de6-167">Drag a connection from the **MapNAOrderToCNOrder** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="f0de6-168">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-168">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="f0de6-169">将从连接**SendPortFilter**到模型元素**SendCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="f0de6-169">Drag a connection from the **SendPortFilter** model element to the **SendCNOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="f0de6-170">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="f0de6-170">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="f0de6-171">在 Visual Studio 中，右键单击的设计图面**DataModelTransformation**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-171">In Visual Studio, right-click the design surface of the **DataModelTransformation** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f0de6-172">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="f0de6-172">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="f0de6-173">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="f0de6-173">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="f0de6-174">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (DataModelTransformation.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="f0de6-174">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (DataModelTransformation.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="f0de6-175">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="f0de6-175">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="f0de6-176">打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="f0de6-176">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="f0de6-177">在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="f0de6-177">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="f0de6-178">在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="f0de6-178">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="f0de6-179">选择**DataModelTransformation.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="f0de6-179">Select **DataModelTransformation.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="f0de6-180">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="f0de6-180">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="f0de6-181">在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="f0de6-181">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="f0de6-182">在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="f0de6-182">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="f0de6-183">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="f0de6-183">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="f0de6-184">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="f0de6-184">Click the **Submit Request** button.</span></span> <span data-ttu-id="f0de6-185">在测试完成后，单击**确定**关闭出现的确认。</span><span class="sxs-lookup"><span data-stu-id="f0de6-185">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="f0de6-186">在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证**%MessageID%.xml**消息已写入到的目录。</span><span class="sxs-lookup"><span data-stu-id="f0de6-186">In Windows Explorer, browse to C:\HowTos\Out. Verify that the **%MessageID%.xml** message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="f0de6-187">其他资源</span><span class="sxs-lookup"><span data-stu-id="f0de6-187">Additional Resources</span></span>  
 <span data-ttu-id="f0de6-188">有关详细信息，请参阅这些相关主题：</span><span class="sxs-lookup"><span data-stu-id="f0de6-188">For more information, see these related topics:</span></span>  
  
1.  [<span data-ttu-id="f0de6-189">如何： 拆分将交换，并将生成的消息路由到多个使用不同路线的文件位置</span><span class="sxs-lookup"><span data-stu-id="f0de6-189">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
2.  [<span data-ttu-id="f0de6-190">开发活动</span><span class="sxs-lookup"><span data-stu-id="f0de6-190">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
3.  [<span data-ttu-id="f0de6-191">消息转换模式</span><span class="sxs-lookup"><span data-stu-id="f0de6-191">Message Transformation Patterns</span></span>](../esb-toolkit/message-transformation-patterns.md)