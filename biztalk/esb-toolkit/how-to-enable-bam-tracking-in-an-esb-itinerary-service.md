---
title: "如何： 启用 BAM 在 ESB 路线服务中跟踪 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58859937-f8d0-4c33-9a7a-62fec8441936
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6245ec69e1c8224ccbe9a39c3c2be9eea9237ee8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-bam-tracking-in-an-esb-itinerary-service"></a><span data-ttu-id="1d843-102">如何： 启用 BAM 在 ESB 路线服务中跟踪</span><span class="sxs-lookup"><span data-stu-id="1d843-102">How to: Enable BAM Tracking in an ESB Itinerary Service</span></span>
## <a name="goal"></a><span data-ttu-id="1d843-103">目的</span><span class="sxs-lookup"><span data-stu-id="1d843-103">Goal</span></span>  
 <span data-ttu-id="1d843-104">本部分演示如何启用业务活动监视 (BAM) 跟踪现有路线。</span><span class="sxs-lookup"><span data-stu-id="1d843-104">This section demonstrates how to enable Business Activity Monitor (BAM) tracking for an existing itinerary.</span></span>  
  
 <span data-ttu-id="1d843-105">在本操作方法主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1d843-105">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="1d843-106">启用用于跟踪使用业务活动监视器的路线服务的属性。</span><span class="sxs-lookup"><span data-stu-id="1d843-106">Enable the property used for tracking Itinerary Services using Business Activity Monitor.</span></span>  
  
-   <span data-ttu-id="1d843-107">测试 BAM 跟踪使用路线测试客户端示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d843-107">Test BAM tracking using the Itinerary Test Client sample application.</span></span>  
  
-   <span data-ttu-id="1d843-108">验证使用 SQL 查询的 BAM 结果。</span><span class="sxs-lookup"><span data-stu-id="1d843-108">Verify the BAM results using a SQL query.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1d843-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="1d843-109">Prerequisites</span></span>  
 <span data-ttu-id="1d843-110">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="1d843-110">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="1d843-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="1d843-111">Before You Begin</span></span>  
 <span data-ttu-id="1d843-112">本操作方法主题中的更高版本执行的步骤之前，请完成以下任务：</span><span class="sxs-lookup"><span data-stu-id="1d843-112">Complete the following tasks before you perform the steps later in this How-to topic:</span></span>  
  
-   <span data-ttu-id="1d843-113">创建一个 ESB 路线域特定语言 (DSL) 模型。</span><span class="sxs-lookup"><span data-stu-id="1d843-113">Create an ESB itinerary domain-specific language (DSL) model.</span></span>  
  
-   <span data-ttu-id="1d843-114">配置路线的属性。</span><span class="sxs-lookup"><span data-stu-id="1d843-114">Configure the properties of the itinerary.</span></span>  
  
-   <span data-ttu-id="1d843-115">定义路线的结构。</span><span class="sxs-lookup"><span data-stu-id="1d843-115">Define the structure of the itinerary.</span></span>  
  
 <span data-ttu-id="1d843-116">下面的过程介绍如何执行其中每个操作。</span><span class="sxs-lookup"><span data-stu-id="1d843-116">The following procedures describe how to do each of these.</span></span>  
  
#### <a name="to-create-an-esb-itinerary-dsl-model"></a><span data-ttu-id="1d843-117">若要创建 ESB 路线 DSL 模型</span><span class="sxs-lookup"><span data-stu-id="1d843-117">To create an ESB itinerary DSL model</span></span>  
  
1.  <span data-ttu-id="1d843-118">在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="1d843-118">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="1d843-119">在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="1d843-119">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="1d843-120">在**添加新项**对话框中，单击**ItineraryDsl**在模板窗格中。</span><span class="sxs-lookup"><span data-stu-id="1d843-120">In the **Add New Item** dialog box, click  **ItineraryDsl** in the Templates pane.</span></span>  
  
4.  <span data-ttu-id="1d843-121">在**名称**框中，键入**BamTracking**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="1d843-121">In the **Name** box, type **BamTracking**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="1d843-122">若要配置路线的属性</span><span class="sxs-lookup"><span data-stu-id="1d843-122">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="1d843-123">在 Visual Studio 中，单击的设计图面**BamTracking.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="1d843-123">In Visual Studio, click the design surface of **BamTracking.itinerary**.</span></span> <span data-ttu-id="1d843-124">在**BamTracking**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="1d843-124">In the **BamTracking** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1d843-125">在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="1d843-125">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="1d843-126">在**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。</span><span class="sxs-lookup"><span data-stu-id="1d843-126">In the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="1d843-127">在**选择 XML 文件**对话框中，在**文件名**框中，键入**C:\HowTos\Itineraries\BamTracking** ，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="1d843-127">In the **Select XML File** dialog box, in the **File name** box, type **C:\HowTos\Itineraries\BamTracking** and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1d843-128">此步骤允许您路线作为 XML 导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="1d843-128">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="1d843-129">通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d843-129">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="1d843-130">你将完成本操作方法主题中后面此过程。</span><span class="sxs-lookup"><span data-stu-id="1d843-130">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="1d843-131">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="1d843-131">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="1d843-132">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="1d843-132">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="1d843-133">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="1d843-133">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1d843-134">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="1d843-134">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="1d843-135">在**扩展程序**下拉列表中，单击**上负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="1d843-135">In the **Extender** drop-down list, click **On-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="1d843-136">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="1d843-136">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="1d843-137">在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="1d843-137">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="1d843-138">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将其放到右侧**上负载增加**模型元素。</span><span class="sxs-lookup"><span data-stu-id="1d843-138">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it to the right of the **On-Ramp** model element.</span></span> <span data-ttu-id="1d843-139">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="1d843-139">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1d843-140">单击**名称**属性，再然后键入**MapNAOrderToCNOrder**。</span><span class="sxs-lookup"><span data-stu-id="1d843-140">Click the **Name** property, and then type **MapNAOrderToCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="1d843-141">在**路线服务扩展程序**下拉列表中，单击**Messaging 路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="1d843-141">In the **Itinerary Service Extender** drop-down list, click **Messaging Itinerary Service Extension**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1d843-142">此属性定义的过程将需要在管道 （消息传送） 中的位置。</span><span class="sxs-lookup"><span data-stu-id="1d843-142">This property defines that the process will take place in a pipeline (messaging).</span></span> <span data-ttu-id="1d843-143">或者，如果过程将需要一个业务流程中的位置，则设置**路线服务扩展程序**属性**Orchestration 路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="1d843-143">Alternately, if the process will take place in an orchestration, set the **Itinerary Service Extender** property to **Orchestration Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="1d843-144">在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="1d843-144">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="1d843-145">在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Transform**。</span><span class="sxs-lookup"><span data-stu-id="1d843-145">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
3.  <span data-ttu-id="1d843-146">右键单击**冲突解决程序**集合**MapNAOrderToCNOrder**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="1d843-146">Right-click the **Resolver** collection of the **MapNAOrderToCNOrder** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="1d843-147">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="1d843-147">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1d843-148">单击**名称**属性，再然后键入**StaticallySpecifyTheMap**。</span><span class="sxs-lookup"><span data-stu-id="1d843-148">Click the **Name** property, and then type **StaticallySpecifyTheMap**.</span></span>  
  
    2.  <span data-ttu-id="1d843-149">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="1d843-149">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="1d843-150">在**转换类型**下拉列表中，单击**GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**。</span><span class="sxs-lookup"><span data-stu-id="1d843-150">In the **Transform Type** drop-down list, click **GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN**.</span></span>  
  
    4.  <span data-ttu-id="1d843-151">在**TransportName**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="1d843-151">In the **TransportName** drop-down list, click **FILE**.</span></span>  
  
4.  <span data-ttu-id="1d843-152">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="1d843-152">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1d843-153">将从连接**ReceiveNAOrder**到模型元素**MapNAOrderToCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="1d843-153">Drag a connection from the **ReceiveNAOrder** model element to the **MapNAOrderToCNOrder** model element.</span></span>  
  
5.  <span data-ttu-id="1d843-154">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**MapNAOrderToCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="1d843-154">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **MapNAOrderToCNOrder** model element.</span></span> <span data-ttu-id="1d843-155">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="1d843-155">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1d843-156">单击**名称**属性，再然后键入**SendCNOrder**。</span><span class="sxs-lookup"><span data-stu-id="1d843-156">Click the **Name** property, and then type **SendCNOrder**.</span></span>  
  
    2.  <span data-ttu-id="1d843-157">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="1d843-157">In the **Extender** drop-down list, click **Off-Ramp ESB Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="1d843-158">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="1d843-158">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="1d843-159">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="1d843-159">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
6.  <span data-ttu-id="1d843-160">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**MapNAOrderToCNOrder**模型元素和**SendCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="1d843-160">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **MapNAOrderToCNOrder** model element and the **SendCNOrder** model element.</span></span> <span data-ttu-id="1d843-161">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="1d843-161">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1d843-162">单击**名称**属性，再然后键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="1d843-162">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="1d843-163">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加路线服务扩展**。</span><span class="sxs-lookup"><span data-stu-id="1d843-163">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Itinerary Service Extension**.</span></span>  
  
    3.  <span data-ttu-id="1d843-164">在**关闭负载增加**下拉列表中，展开**SendCNOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="1d843-164">In the **Off-Ramp** drop-down list, expand **SendCNOrder**, and then click **Send Handlers**.</span></span>  
  
7.  <span data-ttu-id="1d843-165">右键单击**冲突解决程序**集合**SendPortFilter**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="1d843-165">Right-click the **Resolver** collection of the **SendPortFilter** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="1d843-166">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="1d843-166">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="1d843-167">单击**名称**属性，再然后键入**ConfigureFolderSettings**。</span><span class="sxs-lookup"><span data-stu-id="1d843-167">Click the **Name** property, and then type **ConfigureFolderSettings**.</span></span>  
  
    2.  <span data-ttu-id="1d843-168">在**解析程序实现**下拉列表中，单击**静态冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="1d843-168">In the **Resolver Implementation** drop-down list, click **Static Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="1d843-169">在**传输名称**下拉列表中，单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="1d843-169">In the **Transport Name** drop-down list, click **FILE**.</span></span>  
  
    4.  <span data-ttu-id="1d843-170">单击**传输位置**属性，再然后键入**C:\HowTos\Out\BAM%MessageID%.xml**</span><span class="sxs-lookup"><span data-stu-id="1d843-170">Click the **Transport Location** property, and then type **C:\HowTos\Out\BAM%MessageID%.xml**</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="1d843-171">每个关闭提升将具有与之; 关联的路线服务路线服务属性和关闭负载增加的属性的组合定义动态发送端口的订阅。</span><span class="sxs-lookup"><span data-stu-id="1d843-171">Each off-ramp will have an itinerary service associated with it; the combination of the itinerary service properties and the properties of the off-ramp define the subscription of the dynamic send port.</span></span>  
  
8.  <span data-ttu-id="1d843-172">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="1d843-172">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1d843-173">将从连接**MapNAOrderToCNOrder**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="1d843-173">Drag a connection from the **MapNAOrderToCNOrder** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="1d843-174">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="1d843-174">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="1d843-175">将从连接**SendPortFilter**到模型元素**SendCNOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="1d843-175">Drag a connection from the **SendPortFilter** model element to the **SendCNOrder** model element.</span></span>  
  
10. <span data-ttu-id="1d843-176">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="1d843-176">Save all project artifacts.</span></span>  
  
## <a name="steps"></a><span data-ttu-id="1d843-177">步骤</span><span class="sxs-lookup"><span data-stu-id="1d843-177">Steps</span></span>  
  
#### <a name="to-modify-the-itinerary"></a><span data-ttu-id="1d843-178">若要修改路线</span><span class="sxs-lookup"><span data-stu-id="1d843-178">To modify the itinerary</span></span>  
  
1.  <span data-ttu-id="1d843-179">在[!INCLUDE[vs2010](../includes/vs2010-md.md)]，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="1d843-179">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="1d843-180">在解决方案资源管理器中，双击**BamTracking.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="1d843-180">In Solution Explorer, double-click **BamTracking.itinerary**.</span></span>  
  
3.  <span data-ttu-id="1d843-181">单击**MapNAOrderToCNOrder**路线服务元素。</span><span class="sxs-lookup"><span data-stu-id="1d843-181">Click the **MapNAOrderToCNOrder** itinerary service element.</span></span>  
  
4.  <span data-ttu-id="1d843-182">在**MapNAOrderToCNOrder**属性窗口中，单击**True**中**启用跟踪**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="1d843-182">In the **MapNAOrderToCNOrder** Properties window, click **True** in the **Tracking Enabled** drop-down list.</span></span>  
  
5.  <span data-ttu-id="1d843-183">单击**SendPortFilter**路线服务元素。</span><span class="sxs-lookup"><span data-stu-id="1d843-183">Click the **SendPortFilter** itinerary service element.</span></span>  
  
6.  <span data-ttu-id="1d843-184">在**SendPortFilter**属性窗口中，单击**True**中**启用跟踪**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="1d843-184">In the **SendPortFilter** Properties window, click **True** in the **Tracking Enabled** drop-down list.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="1d843-185">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="1d843-185">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="1d843-186">在 Visual Studio 中，右键单击的设计图面**BamTracking**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="1d843-186">In Visual Studio, right-click the design surface of the **BamTracking** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1d843-187">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="1d843-187">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="1d843-188">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="1d843-188">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="1d843-189">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (BamTracking.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="1d843-189">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (BamTracking.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="1d843-190">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="1d843-190">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="1d843-191">打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="1d843-191">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="1d843-192">在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="1d843-192">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="1d843-193">在**打开路线文件**对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="1d843-193">In the **Open Itinerary File** dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="1d843-194">选择**BamTracking.xml**，然后单击**打开**加载路线。</span><span class="sxs-lookup"><span data-stu-id="1d843-194">Select **BamTracking.xml**, and then click **Open** to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="1d843-195">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="1d843-195">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="1d843-196">在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="1d843-196">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="1d843-197">在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="1d843-197">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="1d843-198">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="1d843-198">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="1d843-199">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="1d843-199">Click the **Submit Request** button.</span></span> <span data-ttu-id="1d843-200">在测试完成后，单击**确定**关闭出现的确认。</span><span class="sxs-lookup"><span data-stu-id="1d843-200">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="1d843-201">在 Windows 资源管理器，浏览到 C:\HowTos\Out。验证 BAM%MessageID%.xml 消息已写入到目录。</span><span class="sxs-lookup"><span data-stu-id="1d843-201">In Windows Explorer, browse to C:\HowTos\Out. Verify that the BAM%MessageID%.xml message has been written to the directory.</span></span>  
  
#### <a name="to-verify-message-tracking"></a><span data-ttu-id="1d843-202">若要验证邮件跟踪</span><span class="sxs-lookup"><span data-stu-id="1d843-202">To verify message tracking</span></span>  
  
1.  <span data-ttu-id="1d843-203">单击**启动**在任务栏中，指向**所有程序**，指向[!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)]，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="1d843-203">Click **Start** on the taskbar, point to **All Programs**, point to [!INCLUDE[SQLServer2008or2005](../includes/sqlserver2008or2005-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="1d843-204">单击 **“新建查询”**。</span><span class="sxs-lookup"><span data-stu-id="1d843-204">Click **New Query**.</span></span>  
  
3.  <span data-ttu-id="1d843-205">在查询窗格中，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="1d843-205">In the query pane, type the following:</span></span>  
  
    ```  
    SELECT *  
    FROM [BAMPrimaryImport].[dbo].[bam_ItineraryServiceActivity_Completed]  
    GO  
    ```  
  
4.  <span data-ttu-id="1d843-206">单击 **“执行”**。</span><span class="sxs-lookup"><span data-stu-id="1d843-206">Click **Execute**.</span></span>  
  
5.  <span data-ttu-id="1d843-207">在结果窗格中，使用**时间戳**列找到最新条目。</span><span class="sxs-lookup"><span data-stu-id="1d843-207">In the Results pane, use the **TimeStamp** column to locate the most recent entry.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="1d843-208">其他资源</span><span class="sxs-lookup"><span data-stu-id="1d843-208">Additional Resources</span></span>  
 <span data-ttu-id="1d843-209">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="1d843-209">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="1d843-210">开发活动</span><span class="sxs-lookup"><span data-stu-id="1d843-210">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="1d843-211">消息路由模式</span><span class="sxs-lookup"><span data-stu-id="1d843-211">Message Routing Patterns</span></span>](../esb-toolkit/message-routing-patterns.md)  
  
-   [<span data-ttu-id="1d843-212">使用动态解析和路由</span><span class="sxs-lookup"><span data-stu-id="1d843-212">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)