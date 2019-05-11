---
title: 如何：转换消息并将生成的消息路由到使用路线传送名单的文件位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c27749ba-c228-4cd4-827e-e8009a0c999d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e671e48ea2da80783b714a8be6c503b80b95f27
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399664"
---
# <a name="how-to-transform-a-message-and-route-the-resulting-message-to-a-file-location-using-an-itinerary-routing-slip"></a><span data-ttu-id="c03d3-102">如何：转换消息并将生成的消息路由到使用路线传送名单的文件位置</span><span class="sxs-lookup"><span data-stu-id="c03d3-102">How to: Transform a Message and Route the Resulting Message to a File Location Using an Itinerary Routing Slip</span></span>
## <a name="goal"></a><span data-ttu-id="c03d3-103">目的</span><span class="sxs-lookup"><span data-stu-id="c03d3-103">Goal</span></span>  
 <span data-ttu-id="c03d3-104">本部分演示如何使用 ESB 设计器特定于域的语言 (DSL) 来创建路线通过调用 BizTalk 映射时，实现消息转换，然后使用消息路由[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]文件适配器。</span><span class="sxs-lookup"><span data-stu-id="c03d3-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary that implements message transformation by invoking a BizTalk map, and then it routes the messages using the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] FILE adapter.</span></span>  
  
 <span data-ttu-id="c03d3-105">在本操作指南主题中，您将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c03d3-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="c03d3-106">使用实现了一个 BizTalk 映射转换路线服务创建路线传送名单。</span><span class="sxs-lookup"><span data-stu-id="c03d3-106">Create an itinerary routing slip with a transform itinerary service that implements a BizTalk map.</span></span>  
  
-   <span data-ttu-id="c03d3-107">配置路线以便将转换后的消息路由到某个文件位置。</span><span class="sxs-lookup"><span data-stu-id="c03d3-107">Configure the itinerary to route the transformed message to a file location.</span></span>  
  
-   <span data-ttu-id="c03d3-108">测试使用路线测试客户端示例应用程序的路线。</span><span class="sxs-lookup"><span data-stu-id="c03d3-108">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c03d3-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="c03d3-109">Prerequisites</span></span>  
 <span data-ttu-id="c03d3-110">本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="c03d3-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="c03d3-111">步骤</span><span class="sxs-lookup"><span data-stu-id="c03d3-111">Steps</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="c03d3-112">若要创建的 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="c03d3-112">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="c03d3-113">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="c03d3-113">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="c03d3-114">在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-114">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="c03d3-115">在中**添加新项**对话框中，单击**ItineraryDsl**模板窗格中。</span><span class="sxs-lookup"><span data-stu-id="c03d3-115">In the **Add New Item** dialog box, click **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="c03d3-116">在中**名称**框中，键入**DataModelTransformation**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-116">In the **Name** box, type **DataModelTransformation**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="c03d3-117">若要配置的路线属性</span><span class="sxs-lookup"><span data-stu-id="c03d3-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="c03d3-118">在 Visual Studio 中，单击的设计图面**DataModelTransformation.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-118">In Visual Studio, click the design surface of **DataModelTransformation.itinerary**.</span></span> <span data-ttu-id="c03d3-119">在中**DataModelTransformation**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="c03d3-119">In the **DataModelTransformation** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="c03d3-120">在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="c03d3-121">在中**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="c03d3-121">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="c03d3-122">在中**选择 XML 文件**对话框中**文件名**框中，键入**C:\HowTos\Itineraries\DataModelTransformation**，然后单击**保存**.</span><span class="sxs-lookup"><span data-stu-id="c03d3-122">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\DataModelTransformation**, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c03d3-123">此步骤中，可将路线以 XML 形式导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="c03d3-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="c03d3-124">通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。</span><span class="sxs-lookup"><span data-stu-id="c03d3-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="c03d3-125">您将完成此过程更高版本的本操作指南主题。</span><span class="sxs-lookup"><span data-stu-id="c03d3-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="c03d3-126">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="c03d3-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="c03d3-127">从工具箱拖动**接入点**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="c03d3-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="c03d3-128">在中**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="c03d3-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="c03d3-129">单击**名称**属性，并键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="c03d3-130">在中**Extender**下拉列表中，单击**接入点 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-130">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="c03d3-131">在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="c03d3-132">在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="c03d3-133">从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**接入点**模型元素。</span><span class="sxs-lookup"><span data-stu-id="c03d3-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="c03d3-134">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="c03d3-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="c03d3-135">单击**名称**属性，并键入**MapNAOrderToCNOrder**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-135">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="c03d3-136">在**路线服务 Extender**下拉列表中，单击**消息扩展器**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c03d3-137">此属性定义，过程将花费 （消息传送） 管道中的位置。</span><span class="sxs-lookup"><span data-stu-id="c03d3-137">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="c03d3-138">或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程扩展器**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-138">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Extender**.</span></span>  
  
    3.  <span data-ttu-id="c03d3-139">在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-139">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="c03d3-140">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-140">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="c03d3-141">右键单击**冲突解决程序**系列**MapNAOrderToCNOrder**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-141">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="c03d3-142">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="c03d3-142">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="c03d3-143">单击**名称**属性，并键入**StaticallySpecifyTheMap**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-143">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="c03d3-144">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-144">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="c03d3-145">在中**转换的类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-145">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
    4.  <span data-ttu-id="c03d3-146">在中**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-146">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
4.  <span data-ttu-id="c03d3-147">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-147">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="c03d3-148">将从连接**ReceiveNAOrder**到模型元素**MapNAOrderToCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="c03d3-148">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="c03d3-149">从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**MapNAOrderToCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="c03d3-149">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="c03d3-150">在中**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="c03d3-150">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="c03d3-151">单击**名称**属性，并键入**SendCNOrder**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-151">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="c03d3-152">在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-152">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="c03d3-153">在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-153">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="c03d3-154">在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-154">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="c03d3-155">从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**MapNAOrderToCNOrder**模型元素和**SendCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="c03d3-155">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **MapNAOrderToCNOrder** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="c03d3-156">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="c03d3-156">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="c03d3-157">单击**名称**属性，并键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-157">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="c03d3-158">在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-158">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="c03d3-159">在中**关闭负载增加**下拉列表中，展开**SendCNOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-159">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="c03d3-160">右键单击**冲突解决程序**系列**SendPortFilter**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-160">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="c03d3-161">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="c03d3-161">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="c03d3-162">单击**名称**属性，并键入**ConfigureFolderSettings**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-162">Click the **Name** property, and then type **ConfigureFolderSettings**.</span></span>  
  
    2.  <span data-ttu-id="c03d3-163">在中**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-163">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    3.  <span data-ttu-id="c03d3-164">单击**传输位置**属性，并键入**C:\HowTos\Out\\%MessageID%.xml**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-164">Click the **Transport Location** property, and then type **C:\HowTos\Out\\%MessageID%.xml**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c03d3-165">每个关闭接入点将具有与它; 关联的路线服务路线服务属性和关闭负载增加的属性的组合定义的动态发送端口的订阅。</span><span class="sxs-lookup"><span data-stu-id="c03d3-165">Each off-ramp will have an Itinerary Service associated with it; the combination of the Itinerary Service properties and the properties of the off-ramp define the subscription of the dynamic send port.</span></span>  
  
8.  <span data-ttu-id="c03d3-166">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-166">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="c03d3-167">将从连接**MapNAOrderToCNOrder**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="c03d3-167">Drag a connection from the **MapNAOrderToCNOrder** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="c03d3-168">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-168">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="c03d3-169">将从连接**SendPortFilter**到模型元素**SendCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="c03d3-169">Drag a connection from the **SendPortFilter** model element to the **SendCNOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="c03d3-170">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="c03d3-170">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="c03d3-171">在 Visual Studio 中，右键单击设计图面的**DataModelTransformation**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-171">In Visual Studio, right-click the design surface of the **DataModelTransformation** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c03d3-172">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="c03d3-172">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="c03d3-173">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="c03d3-173">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="c03d3-174">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries 并请注意，您的路线 XML (DataModelTransformation.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="c03d3-174">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (DataModelTransformation.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="c03d3-175">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="c03d3-175">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="c03d3-176">打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="c03d3-176">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="c03d3-177">在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="c03d3-177">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="c03d3-178">在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="c03d3-178">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="c03d3-179">选择**DataModelTransformation.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="c03d3-179">Select **DataModelTransformation.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="c03d3-180">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="c03d3-180">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="c03d3-181">在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="c03d3-181">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="c03d3-182">在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="c03d3-182">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="c03d3-183">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="c03d3-183">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="c03d3-184">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="c03d3-184">Click the **Submit Request** button.</span></span> <span data-ttu-id="c03d3-185">测试完成后，单击**确定**若要消除出现的确认。</span><span class="sxs-lookup"><span data-stu-id="c03d3-185">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="c03d3-186">在 Windows 资源管理器，浏览到 C:\HowTos\Out。确认 **%MessageID%.xml**消息已写入到的目录。</span><span class="sxs-lookup"><span data-stu-id="c03d3-186">In Windows Explorer, browse to C:\HowTos\Out. Verify that the **%MessageID%.xml** message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="c03d3-187">其他资源</span><span class="sxs-lookup"><span data-stu-id="c03d3-187">Additional Resources</span></span>  
 <span data-ttu-id="c03d3-188">有关详细信息，请参阅以下相关主题：</span><span class="sxs-lookup"><span data-stu-id="c03d3-188">For more information, see these related topics:</span></span>  
  
1.  [<span data-ttu-id="c03d3-189">如何：将某个交换拆分，并将结果的消息路由到多个使用不同的路线的文件位置</span><span class="sxs-lookup"><span data-stu-id="c03d3-189">How to: Split an Interchange and Route the Resulting Messages to Multiple File Locations Using Distinct Itineraries</span></span>](../esb-toolkit/split-an-interchange-and-route-messages-to-multiple-locations-using-itineraries.md)  
  
2.  [<span data-ttu-id="c03d3-190">开发活动</span><span class="sxs-lookup"><span data-stu-id="c03d3-190">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
3.  [<span data-ttu-id="c03d3-191">消息转换模式</span><span class="sxs-lookup"><span data-stu-id="c03d3-191">Message Transformation Patterns</span></span>](../esb-toolkit/message-transformation-patterns.md)