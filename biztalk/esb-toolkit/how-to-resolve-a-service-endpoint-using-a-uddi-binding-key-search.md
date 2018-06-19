---
title: 如何： 解决使用绑定密钥搜索 UDDI 服务终结点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a685641-2beb-4153-a9ba-c766679ce48e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d286f3dd48daa7cc0ddd16f4abda601cf9e8a5f7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010558"
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search"></a><span data-ttu-id="3aae0-102">如何： 解决使用绑定密钥搜索 UDDI 服务终结点</span><span class="sxs-lookup"><span data-stu-id="3aae0-102">How to: Resolve a Service Endpoint Using a UDDI Binding Key Search</span></span>
## <a name="goal"></a><span data-ttu-id="3aae0-103">目的</span><span class="sxs-lookup"><span data-stu-id="3aae0-103">Goal</span></span>  
 <span data-ttu-id="3aae0-104">本部分演示如何使用 ESB 设计器域特定语言 (DSL) 来创建使用的通用的说明，发现，基于路线的路由滑动和集成 (UDDI) 3 冲突解决程序来查找服务终结点使用的绑定密钥搜索。</span><span class="sxs-lookup"><span data-stu-id="3aae0-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary-based routing slip that uses the Universal Description, Discovery, and Integration (UDDI) 3 resolver to locate a service endpoint using a binding key search.</span></span> <span data-ttu-id="3aae0-105">在此方案中，服务终结点将在 UDDI 中发布一个文件终结点。</span><span class="sxs-lookup"><span data-stu-id="3aae0-105">In this scenario, the service endpoint will be a file endpoint published in UDDI.</span></span>  
  
 <span data-ttu-id="3aae0-106">在本操作方法主题中，你将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="3aae0-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="3aae0-107">创建路线的路由滑动，若要解决的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="3aae0-107">Create an itinerary routing slip to resolve a service endpoint.</span></span>  
  
-   <span data-ttu-id="3aae0-108">配置路线后，若要将消息路由到服务终结点使用 UDDI 3 冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="3aae0-108">Configure the itinerary to route the message to a service endpoint using a UDDI 3 resolver.</span></span>  
  
-   <span data-ttu-id="3aae0-109">测试路线使用路线测试客户端示例应用程序。</span><span class="sxs-lookup"><span data-stu-id="3aae0-109">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3aae0-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="3aae0-110">Prerequisites</span></span>  
 <span data-ttu-id="3aae0-111">此操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="3aae0-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="3aae0-112">步骤</span><span class="sxs-lookup"><span data-stu-id="3aae0-112">Steps</span></span>  
  
#### <a name="to-create-an-itinerary-model"></a><span data-ttu-id="3aae0-113">若要创建路线模型</span><span class="sxs-lookup"><span data-stu-id="3aae0-113">To create an itinerary model</span></span>  
  
1.  <span data-ttu-id="3aae0-114">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="3aae0-114">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="3aae0-115">在解决方案资源管理器，右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-115">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="3aae0-116">在**添加新项**对话框中，在**名称**框中，键入**UDDI3BindingKeySearch**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-116">In the **Add New Item** dialog box, in the **Name** box, type **UDDI3BindingKeySearch**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="3aae0-117">若要配置路线的属性</span><span class="sxs-lookup"><span data-stu-id="3aae0-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="3aae0-118">在 Visual Studio 中，单击的设计图面**UDDI3BindingKeySearch.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-118">In Visual Studio, click the design surface of **UDDI3BindingKeySearch.itinerary**.</span></span> <span data-ttu-id="3aae0-119">在**UDDI3BindingKeySearch**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3aae0-119">In the **UDDI3BindingKeySearch** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3aae0-120">在**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="3aae0-121">下**扩展程序设置**部分，旁边**路线 XML 文件**属性，单击省略号按钮 （…）。</span><span class="sxs-lookup"><span data-stu-id="3aae0-121">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="3aae0-122">在**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\UDDI3BindingKeySearch**中**文件名**框中，并依次**保存**.</span><span class="sxs-lookup"><span data-stu-id="3aae0-122">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\UDDI3BindingKeySearch** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3aae0-123">此步骤允许您路线作为 XML 导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="3aae0-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="3aae0-124">通过到路线的数据库，而不导出到本地文件的位置，一条路线使测试路线使用 ESB 测试客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="3aae0-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="3aae0-125">你将完成本操作方法主题中后面此过程。</span><span class="sxs-lookup"><span data-stu-id="3aae0-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="3aae0-126">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="3aae0-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="3aae0-127">从工具箱中，拖动**上负载增加**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="3aae0-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="3aae0-128">在**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3aae0-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3aae0-129">单击**名称**属性，再然后键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3aae0-130">在**扩展程序**下拉列表中，单击**上负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-130">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="3aae0-131">在**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3aae0-132">在**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="3aae0-133">从工具箱中，拖动**路线服务**到设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="3aae0-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="3aae0-134">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3aae0-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3aae0-135">单击**名称**属性，再然后键入**BindingKeyRoute**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-135">Click the **Name** property, and then type **BindingKeyRoute**.</span></span>  
  
    2.  <span data-ttu-id="3aae0-136">在**路线服务扩展程序**下拉列表中，单击**消息传送扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
    3.  <span data-ttu-id="3aae0-137">在**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-137">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="3aae0-138">在**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-138">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="3aae0-139">右键单击**冲突解决程序**集合**BindingKeyRoute**模型元素，并依次**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-139">Right-click the **Resolver** collection of the **BindingKeyRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="3aae0-140">在**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3aae0-140">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3aae0-141">单击**名称**属性，再然后键入**BindingKeySearch**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-141">Click the **Name** property, and then type **BindingKeySearch**.</span></span>  
  
    2.  <span data-ttu-id="3aae0-142">在**解析程序实现**下拉列表中，单击**Uddi3 冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-142">In the **Resolver Implementation** drop-down list, click **Uddi3 Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="3aae0-143">在**冲突解决程序名字对象**下拉列表中，单击**UDDI3**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-143">In the **Resolver Moniker** drop-down list, click **UDDI3**.</span></span>  
  
    4.  <span data-ttu-id="3aae0-144">单击**绑定密钥**属性，再然后键入**uddi:esb:orderfileservicev3.1**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-144">Click the **Binding key** property, and then type **uddi:esb:orderfileservicev3.1**.</span></span>  
  
4.  <span data-ttu-id="3aae0-145">右键单击**BindingKeySearch**冲突解决程序，，然后单击**测试解析程序配置**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-145">Right-click the **BindingKeySearch** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3aae0-146">验证显示在输出窗口中的输出。</span><span class="sxs-lookup"><span data-stu-id="3aae0-146">Verify the output displayed in the Output window.</span></span>  
  
5.  <span data-ttu-id="3aae0-147">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-147">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3aae0-148">将从连接**ReceiveNAOrder**到模型元素**BindingKeyRoute**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3aae0-148">Drag a connection from the **ReceiveNAOrder** model element to the **BindingKeyRoute** model element.</span></span>  
  
6.  <span data-ttu-id="3aae0-149">从工具箱中，拖动**关闭负载增加**模型元素到设计图面，然后将其放到右侧**BindingKeyRoute**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3aae0-149">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BindingKeyRoute** model element.</span></span> <span data-ttu-id="3aae0-150">在**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3aae0-150">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3aae0-151">单击**名称**属性，再然后键入**SendNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-151">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="3aae0-152">在**扩展程序**下拉列表中，单击**关闭负载增加 ESB 扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-152">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="3aae0-153">在**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-153">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="3aae0-154">在**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-154">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
7.  <span data-ttu-id="3aae0-155">从工具箱中，拖动**路线服务**模型元素到设计图面，然后将它之间**BindingKeyRoute**模型元素和**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3aae0-155">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BindingKeyRoute** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="3aae0-156">在**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="3aae0-156">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="3aae0-157">单击**名称**属性，再然后键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-157">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="3aae0-158">在**路线服务扩展程序**下拉列表中，单击**关闭负载增加扩展程序**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-158">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="3aae0-159">在**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-159">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
8.  <span data-ttu-id="3aae0-160">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-160">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3aae0-161">将从连接**BindingKeyRoute**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3aae0-161">Drag a connection from the **BindingKeyRoute** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="3aae0-162">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-162">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="3aae0-163">将从连接**SendPortFilter**到模型元素**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="3aae0-163">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="3aae0-164">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="3aae0-164">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="3aae0-165">在 Visual Studio 中，右键单击的设计图面**UDDI3BindingKeySearch**路线，，然后单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-165">In Visual Studio, right-click the design surface of the **UDDI3BindingKeySearch** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3aae0-166">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="3aae0-166">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="3aae0-167">保存所有项目。</span><span class="sxs-lookup"><span data-stu-id="3aae0-167">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="3aae0-168">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries，并注意你路线 XML (UDDI3BindingKeySearch.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="3aae0-168">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (UDDI3BindingKeySearch.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="3aae0-169">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="3aae0-169">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="3aae0-170">打开路线测试客户端示例应用程序使用期间创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="3aae0-170">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="3aae0-171">在路线测试客户端中，清除**使用 WCF 服务**复选框，并依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="3aae0-171">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="3aae0-172">在打开路线文件对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="3aae0-172">In the Open Itinerary File dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="3aae0-173">选择 UDDI3BindingKeySearch.xml，，然后单击打开加载路线。</span><span class="sxs-lookup"><span data-stu-id="3aae0-173">Select UDDI3BindingKeySearch.xml, and then click Open to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="3aae0-174">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="3aae0-174">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="3aae0-175">在路线测试客户端上，单击旁边的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="3aae0-175">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="3aae0-176">在**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="3aae0-176">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="3aae0-177">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="3aae0-177">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="3aae0-178">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="3aae0-178">Click the **Submit Request** button.</span></span> <span data-ttu-id="3aae0-179">在测试完成后，单击**确定**关闭出现的确认。</span><span class="sxs-lookup"><span data-stu-id="3aae0-179">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="3aae0-180">在 Windows 资源管理器，浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out。验证 %MessageID%.xml 消息已写入到目录。</span><span class="sxs-lookup"><span data-stu-id="3aae0-180">In Windows Explorer, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out. Verify that the %MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="3aae0-181">其他资源</span><span class="sxs-lookup"><span data-stu-id="3aae0-181">Additional Resources</span></span>  
 <span data-ttu-id="3aae0-182">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="3aae0-182">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="3aae0-183">如何：使用 UDDI 类别搜索解析服务终结点</span><span class="sxs-lookup"><span data-stu-id="3aae0-183">How to: Resolve a Service Endpoint Using a UDDI Category Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [<span data-ttu-id="3aae0-184">开发活动</span><span class="sxs-lookup"><span data-stu-id="3aae0-184">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="3aae0-185">使用动态解析和路由</span><span class="sxs-lookup"><span data-stu-id="3aae0-185">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)