---
title: 如何： 启用 BAM 跟踪在 ESB 路线服务中 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 58859937-f8d0-4c33-9a7a-62fec8441936
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27d0338ad56daa342fce1d339b9e7aa43fd7e25e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991542"
---
# <a name="how-to-enable-bam-tracking-in-an-esb-itinerary-service"></a><span data-ttu-id="a035b-102">如何： 启用 BAM 跟踪在 ESB 路线服务</span><span class="sxs-lookup"><span data-stu-id="a035b-102">How to: Enable BAM Tracking in an ESB Itinerary Service</span></span>
## <a name="goal"></a><span data-ttu-id="a035b-103">目的</span><span class="sxs-lookup"><span data-stu-id="a035b-103">Goal</span></span>  
 <span data-ttu-id="a035b-104">本部分演示如何启用业务活动监视 (BAM) 跟踪现有路线。</span><span class="sxs-lookup"><span data-stu-id="a035b-104">This section demonstrates how to enable Business Activity Monitor (BAM) tracking for an existing itinerary.</span></span>  
  
 <span data-ttu-id="a035b-105">在本操作指南主题中，您将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="a035b-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="a035b-106">启用用于跟踪使用业务活动监视的路线服务的属性。</span><span class="sxs-lookup"><span data-stu-id="a035b-106">Enable the property used for tracking Itinerary Services using Business Activity Monitor.</span></span>  
  
-   <span data-ttu-id="a035b-107">测试使用路线测试客户端示例应用程序的 BAM 跟踪。</span><span class="sxs-lookup"><span data-stu-id="a035b-107">Test BAM tracking using the Itinerary Test Client sample application.</span></span>  
  
-   <span data-ttu-id="a035b-108">验证 BAM 结果使用 SQL 查询。</span><span class="sxs-lookup"><span data-stu-id="a035b-108">Verify the BAM results using a SQL query.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a035b-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="a035b-109">Prerequisites</span></span>  
 <span data-ttu-id="a035b-110">本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="a035b-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="a035b-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="a035b-111">Before You Begin</span></span>  
 <span data-ttu-id="a035b-112">在本操作指南主题的后面部分执行的步骤之前，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="a035b-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
- <span data-ttu-id="a035b-113">创建的 ESB 路线域特定语言 (DSL) 模型。</span><span class="sxs-lookup"><span data-stu-id="a035b-113">Create an ESB itinerary domain-specific language (DSL) model.</span></span>  
  
- <span data-ttu-id="a035b-114">配置路线的属性。</span><span class="sxs-lookup"><span data-stu-id="a035b-114">Configure the properties of the itinerary.</span></span>  
  
- <span data-ttu-id="a035b-115">定义路线的结构。</span><span class="sxs-lookup"><span data-stu-id="a035b-115">Define the structure of the itinerary.</span></span>  
  
  <span data-ttu-id="a035b-116">以下过程介绍如何执行其中每项功能。</span><span class="sxs-lookup"><span data-stu-id="a035b-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="a035b-117">若要创建的 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="a035b-117">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="a035b-118">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="a035b-118">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="a035b-119">在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="a035b-119">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="a035b-120">在中**添加新项**对话框中，单击**ItineraryDsl**模板窗格中。</span><span class="sxs-lookup"><span data-stu-id="a035b-120">In the **Add New Item** dialog box, click  **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="a035b-121">在中**名称**框中，键入**BamTracking**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="a035b-121">In the **Name** box, type **BamTracking**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="a035b-122">若要配置的路线属性</span><span class="sxs-lookup"><span data-stu-id="a035b-122">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="a035b-123">在 Visual Studio 中，单击的设计图面**BamTracking.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="a035b-123">In Visual Studio, click the design surface of **BamTracking.itinerary**.</span></span> <span data-ttu-id="a035b-124">在中**BamTracking**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a035b-124">In the **BamTracking** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a035b-125">在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="a035b-125">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="a035b-126">在中**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="a035b-126">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="a035b-127">在中**选择 XML 文件**对话框中**文件名**框中，键入**C:\HowTos\Itineraries\BamTracking** ，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="a035b-127">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\BamTracking** and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a035b-128">此步骤中，可将路线以 XML 形式导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="a035b-128">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="a035b-129">通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。</span><span class="sxs-lookup"><span data-stu-id="a035b-129">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="a035b-130">您将完成此过程更高版本的本操作指南主题。</span><span class="sxs-lookup"><span data-stu-id="a035b-130">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="a035b-131">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="a035b-131">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="a035b-132">从工具箱拖动**接入点**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="a035b-132">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="a035b-133">在中**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a035b-133">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a035b-134">单击**名称**属性，并键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="a035b-134">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="a035b-135">在中**Extender**下拉列表中，单击**接入点 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="a035b-135">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="a035b-136">在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="a035b-136">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="a035b-137">在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="a035b-137">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="a035b-138">从工具箱拖动**路线服务**模型元素到设计图面，然后将它放到右侧**接入点**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a035b-138">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="a035b-139">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a035b-139">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a035b-140">单击**名称**属性，并键入**MapNAOrderToCNOrder**。</span><span class="sxs-lookup"><span data-stu-id="a035b-140">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="a035b-141">在**路线服务 Extender**下拉列表中，单击**Messaging 路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="a035b-141">In the **Itinerary Service Extender** drop-down list, click **Messaging Itinerary Service Extension**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a035b-142">此属性定义，过程将花费 （消息传送） 管道中的位置。</span><span class="sxs-lookup"><span data-stu-id="a035b-142">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="a035b-143">或者，如果该过程会发生在业务流程中，设置**路线服务 Extender**属性设置为**业务流程路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="a035b-143">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="a035b-144">在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="a035b-144">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="a035b-145">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="a035b-145">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="a035b-146">右键单击**冲突解决程序**系列**MapNAOrderToCNOrder**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="a035b-146">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="a035b-147">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a035b-147">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a035b-148">单击**名称**属性，并键入**StaticallySpecifyTheMap**。</span><span class="sxs-lookup"><span data-stu-id="a035b-148">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="a035b-149">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="a035b-149">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="a035b-150">在中**转换的类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。</span><span class="sxs-lookup"><span data-stu-id="a035b-150">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
    4.  <span data-ttu-id="a035b-151">在中**TransportName**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="a035b-151">In the **TransportName** drop-down list, click **FILE**.</span></span>  
  
4.  <span data-ttu-id="a035b-152">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="a035b-152">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a035b-153">将从连接**ReceiveNAOrder**到模型元素**MapNAOrderToCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a035b-153">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="a035b-154">从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**MapNAOrderToCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a035b-154">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="a035b-155">在中**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a035b-155">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a035b-156">单击**名称**属性，并键入**SendCNOrder**。</span><span class="sxs-lookup"><span data-stu-id="a035b-156">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="a035b-157">在中**Extender**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="a035b-157">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="a035b-158">在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="a035b-158">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="a035b-159">在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="a035b-159">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="a035b-160">从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**MapNAOrderToCNOrder**模型元素和**SendCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a035b-160">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **MapNAOrderToCNOrder** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="a035b-161">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a035b-161">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a035b-162">单击**名称**属性，并键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="a035b-162">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="a035b-163">在**路线服务 Extender**下拉列表中，单击**接入点关闭路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="a035b-163">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="a035b-164">在中**关闭负载增加**下拉列表中，展开**SendCNOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="a035b-164">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="a035b-165">右键单击**冲突解决程序**系列**SendPortFilter**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="a035b-165">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="a035b-166">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="a035b-166">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="a035b-167">单击**名称**属性，并键入**ConfigureFolderSettings**。</span><span class="sxs-lookup"><span data-stu-id="a035b-167">Click the **Name** property, and then type **ConfigureFolderSettings**.</span></span>  
  
    2.  <span data-ttu-id="a035b-168">在中**解析程序实现**下拉列表中，单击**静态解析程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="a035b-168">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="a035b-169">在中**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="a035b-169">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="a035b-170">单击**传输位置**属性，并键入**C:\HowTos\Out\BAM%MessageID%.xml**</span><span class="sxs-lookup"><span data-stu-id="a035b-170">Click the **Transport Location** property, and then type **C:\HowTos\Out\BAM%MessageID%.xml**</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a035b-171">每个关闭接入点将具有与之; 关联的路线服务路线服务属性和关闭负载增加的属性的组合定义的动态发送端口的订阅。</span><span class="sxs-lookup"><span data-stu-id="a035b-171">Each off-ramp will have an itinerary service associated with it; the combination of the itinerary service properties and the properties of the off-ramp define the subscription of the dynamic send port.</span></span>  
  
8.  <span data-ttu-id="a035b-172">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="a035b-172">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a035b-173">将从连接**MapNAOrderToCNOrder**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a035b-173">Drag a connection from the **MapNAOrderToCNOrder** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="a035b-174">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="a035b-174">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="a035b-175">将从连接**SendPortFilter**到模型元素**SendCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="a035b-175">Drag a connection from the **SendPortFilter** model element to the **SendCNOrder** model element.</span></span>  
  
10. <span data-ttu-id="a035b-176">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="a035b-176">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="a035b-177">步骤</span><span class="sxs-lookup"><span data-stu-id="a035b-177">Steps</span></span>  
  
#### <a name="to-modify-the-itinerary"></a><span data-ttu-id="a035b-178">若要修改路线</span><span class="sxs-lookup"><span data-stu-id="a035b-178">To modify the itinerary</span></span>  
  
1.  <span data-ttu-id="a035b-179">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="a035b-179">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="a035b-180">在解决方案资源管理器中双击**BamTracking.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="a035b-180">In Solution Explorer, double-click **BamTracking.itinerary**.</span></span>  
  
3.  <span data-ttu-id="a035b-181">单击**MapNAOrderToCNOrder**路线服务元素。</span><span class="sxs-lookup"><span data-stu-id="a035b-181">Click the **MapNAOrderToCNOrder** itinerary service element.</span></span>  
  
4.  <span data-ttu-id="a035b-182">在中**MapNAOrderToCNOrder**属性窗口中，单击**True**中**启用跟踪**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a035b-182">In the **MapNAOrderToCNOrder** Properties window, click **True** in the **Tracking Enabled** drop-down list.</span></span>  
  
5.  <span data-ttu-id="a035b-183">单击**SendPortFilter**路线服务元素。</span><span class="sxs-lookup"><span data-stu-id="a035b-183">Click the **SendPortFilter** itinerary service element.</span></span>  
  
6.  <span data-ttu-id="a035b-184">在中**SendPortFilter**属性窗口中，单击**True**中**启用跟踪**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a035b-184">In the **SendPortFilter** Properties window, click **True** in the **Tracking Enabled** drop-down list.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="a035b-185">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="a035b-185">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="a035b-186">在 Visual Studio 中，右键单击设计图面的**BamTracking**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="a035b-186">In Visual Studio, right-click the design surface of the **BamTracking** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a035b-187">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="a035b-187">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="a035b-188">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="a035b-188">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="a035b-189">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries 并请注意，您的路线 XML (BamTracking.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="a035b-189">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (BamTracking.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="a035b-190">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="a035b-190">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="a035b-191">打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="a035b-191">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="a035b-192">在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="a035b-192">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="a035b-193">在中**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="a035b-193">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="a035b-194">选择**BamTracking.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="a035b-194">Select **BamTracking.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="a035b-195">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="a035b-195">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="a035b-196">在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="a035b-196">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="a035b-197">在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="a035b-197">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="a035b-198">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="a035b-198">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="a035b-199">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="a035b-199">Click the **Submit Request** button.</span></span> <span data-ttu-id="a035b-200">测试完成后，单击**确定**若要消除出现的确认。</span><span class="sxs-lookup"><span data-stu-id="a035b-200">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="a035b-201">在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 BAM%MessageID%.xml 消息已写入到目录。</span><span class="sxs-lookup"><span data-stu-id="a035b-201">In Windows Explorer, browse to C:\HowTos\Out. Verify that the BAM%MessageID%.xml message has been written to the directory.</span></span>  
  
#### <a name="to-verify-message-tracking"></a><span data-ttu-id="a035b-202">若要验证消息跟踪</span><span class="sxs-lookup"><span data-stu-id="a035b-202">To verify message tracking</span></span>  
  
1. <span data-ttu-id="a035b-203">单击**启动**在任务栏上，依次指向**所有程序**，指向[!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="a035b-203">Click **Start** on the taskbar, point to **All Programs**, point to [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="a035b-204">单击 **“新建查询”**。</span><span class="sxs-lookup"><span data-stu-id="a035b-204">Click **New Query**.</span></span>  
  
3. <span data-ttu-id="a035b-205">在查询窗格中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="a035b-205">In the query pane, type the following:</span></span>  
  
   ```  
   SELECT *  
   FROM [BAMPrimaryImport].[dbo].[bam_ItineraryServiceActivity_Completed]  
   GO  
   ```  
  
4. <span data-ttu-id="a035b-206">单击 **“执行”**。</span><span class="sxs-lookup"><span data-stu-id="a035b-206">Click **Execute**.</span></span>  
  
5. <span data-ttu-id="a035b-207">在结果窗格中，使用**时间戳**列来查找最新条目。</span><span class="sxs-lookup"><span data-stu-id="a035b-207">In the Results pane, use the **TimeStamp** column to locate the most recent entry.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="a035b-208">其他资源</span><span class="sxs-lookup"><span data-stu-id="a035b-208">Additional Resources</span></span>  
 <span data-ttu-id="a035b-209">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="a035b-209">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="a035b-210">开发活动</span><span class="sxs-lookup"><span data-stu-id="a035b-210">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="a035b-211">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="a035b-211">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="a035b-212">使用动态解析和路由</span><span class="sxs-lookup"><span data-stu-id="a035b-212">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)