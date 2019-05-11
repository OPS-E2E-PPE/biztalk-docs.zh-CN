---
title: 如何：解析服务终结点使用 UDDI 绑定密钥搜索 |Microsoft Docs
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
ms.openlocfilehash: d4ce78a9637a09754e5cdb065fb25369b2ccac28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258546"
---
# <a name="how-to-resolve-a-service-endpoint-using-a-uddi-binding-key-search"></a><span data-ttu-id="394cc-102">如何：解析服务终结点使用 UDDI 绑定密钥搜索</span><span class="sxs-lookup"><span data-stu-id="394cc-102">How to: Resolve a Service Endpoint Using a UDDI Binding Key Search</span></span>
## <a name="goal"></a><span data-ttu-id="394cc-103">目的</span><span class="sxs-lookup"><span data-stu-id="394cc-103">Goal</span></span>  
 <span data-ttu-id="394cc-104">本部分演示如何使用 ESB 设计器特定于域的语言 (DSL) 来创建基于路线的传送名单使用通用描述、 发现和集成 (UDDI) 3 冲突解决程序来查找使用绑定键的服务终结点搜索。</span><span class="sxs-lookup"><span data-stu-id="394cc-104">This section demonstrates how to use the ESB Designer domain-specific language (DSL) to create an itinerary-based routing slip that uses the Universal Description, Discovery, and Integration (UDDI) 3 resolver to locate a service endpoint using a binding key search.</span></span> <span data-ttu-id="394cc-105">在此方案中，服务终结点将是在 UDDI 中发布一个文件终结点。</span><span class="sxs-lookup"><span data-stu-id="394cc-105">In this scenario, the service endpoint will be a file endpoint published in UDDI.</span></span>  
  
 <span data-ttu-id="394cc-106">在本操作指南主题中，您将完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="394cc-106">In this How-to topic, you will complete the following steps:</span></span>  
  
-   <span data-ttu-id="394cc-107">创建路线传送名单以解析服务终结点。</span><span class="sxs-lookup"><span data-stu-id="394cc-107">Create an itinerary routing slip to resolve a service endpoint.</span></span>  
  
-   <span data-ttu-id="394cc-108">配置路线以便将消息路由到服务终结点使用 UDDI 3 冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="394cc-108">Configure the itinerary to route the message to a service endpoint using a UDDI 3 resolver.</span></span>  
  
-   <span data-ttu-id="394cc-109">测试使用路线测试客户端示例应用程序的路线。</span><span class="sxs-lookup"><span data-stu-id="394cc-109">Test the itinerary using the Itinerary Test Client sample application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="394cc-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="394cc-110">Prerequisites</span></span>  
 <span data-ttu-id="394cc-111">本操作指南主题中的过程要求在完成[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="394cc-111">The procedures in this How-to topic require the completion of the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md).</span></span>  
  
## <a name="steps"></a><span data-ttu-id="394cc-112">步骤</span><span class="sxs-lookup"><span data-stu-id="394cc-112">Steps</span></span>  
  
#### <a name="to-create-an-itinerary-model"></a><span data-ttu-id="394cc-113">若要创建路线模型</span><span class="sxs-lookup"><span data-stu-id="394cc-113">To create an itinerary model</span></span>  
  
1.  <span data-ttu-id="394cc-114">在 Visual Studio 中，打开 C:\HowTos\Patterns\Patterns.sln。</span><span class="sxs-lookup"><span data-stu-id="394cc-114">In Visual Studio, open C:\HowTos\Patterns\Patterns.sln.</span></span>  
  
2.  <span data-ttu-id="394cc-115">在解决方案资源管理器中右键单击**ItineraryLibrary**项目，指向**添加**，然后单击**新路线**。</span><span class="sxs-lookup"><span data-stu-id="394cc-115">In Solution Explorer, right-click the **ItineraryLibrary** project, point to **Add**, and then click **New Itinerary**.</span></span>  
  
3.  <span data-ttu-id="394cc-116">在中**添加新项**对话框中**名称**框中，键入**UDDI3BindingKeySearch**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="394cc-116">In the **Add New Item** dialog box, in the **Name** box, type **UDDI3BindingKeySearch**, and then click **Add**.</span></span>  
  
#### <a name="to-configure-the-properties-of-the-itinerary"></a><span data-ttu-id="394cc-117">若要配置的路线属性</span><span class="sxs-lookup"><span data-stu-id="394cc-117">To configure the properties of the itinerary</span></span>  
  
1.  <span data-ttu-id="394cc-118">在 Visual Studio 中，单击的设计图面**UDDI3BindingKeySearch.itinerary**。</span><span class="sxs-lookup"><span data-stu-id="394cc-118">In Visual Studio, click the design surface of **UDDI3BindingKeySearch.itinerary**.</span></span> <span data-ttu-id="394cc-119">在中**UDDI3BindingKeySearch**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="394cc-119">In the **UDDI3BindingKeySearch** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="394cc-120">在中**模型导出程序**下拉列表中，单击**XML 路线导出程序**。</span><span class="sxs-lookup"><span data-stu-id="394cc-120">In the **Model Exporter** drop-down list, click **XML Itinerary Exporter**.</span></span>  
  
    2.  <span data-ttu-id="394cc-121">下**扩展器设置**部分中下, 一步**路线 XML 文件**属性中，单击省略号按钮 （...）。</span><span class="sxs-lookup"><span data-stu-id="394cc-121">Under the **Extender Settings** section, next to the **Itinerary XML file** property, click the ellipsis button (...).</span></span>  
  
    3.  <span data-ttu-id="394cc-122">在中**选择 XML 文件**对话框中，键入**C:\HowTos\Itineraries\UDDI3BindingKeySearch**中**文件名**框中，然后依次**保存**.</span><span class="sxs-lookup"><span data-stu-id="394cc-122">In the **Select XML File** dialog box, type **C:\HowTos\Itineraries\UDDI3BindingKeySearch** in the **File name** box, and then click **Save**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="394cc-123">此步骤中，可将路线以 XML 形式导出到本地文件位置。</span><span class="sxs-lookup"><span data-stu-id="394cc-123">This step enables you to export the itinerary as XML to a local file location.</span></span> <span data-ttu-id="394cc-124">通过为行程数据库，而不导出到本地文件的位置，路线，路线使用 ESB 测试客户端应用程序的测试。</span><span class="sxs-lookup"><span data-stu-id="394cc-124">By exporting an itinerary to a local file location, instead of to the itinerary database, enables testing of the itinerary using the ESB Test Client application.</span></span> <span data-ttu-id="394cc-125">您将完成此过程更高版本的本操作指南主题。</span><span class="sxs-lookup"><span data-stu-id="394cc-125">You will complete this process later in this How-to topic.</span></span>  
  
#### <a name="to-define-the-structure-of-the-itinerary"></a><span data-ttu-id="394cc-126">若要定义路线的结构</span><span class="sxs-lookup"><span data-stu-id="394cc-126">To define the structure of the itinerary</span></span>  
  
1.  <span data-ttu-id="394cc-127">从工具箱拖动**接入点**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="394cc-127">From the Toolbox, drag an **On-Ramp** model element to the design surface.</span></span> <span data-ttu-id="394cc-128">在中**OnRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="394cc-128">In the **OnRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="394cc-129">单击**名称**属性，并键入**ReceiveNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="394cc-129">Click the **Name** property, and then type **ReceiveNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="394cc-130">在中**Extender**下拉列表中，单击**接入点 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="394cc-130">In the **Extender** drop-down list, click **On-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="394cc-131">在中**BizTalk 应用程序**下拉列表中，单击**Microsoft.Practices.ESB**。</span><span class="sxs-lookup"><span data-stu-id="394cc-131">In the **BizTalk Application** drop-down list, click **Microsoft.Practices.ESB**.</span></span>  
  
    4.  <span data-ttu-id="394cc-132">在中**接收端口**下拉列表中，单击**OnRamp.Itinerary**。</span><span class="sxs-lookup"><span data-stu-id="394cc-132">In the **Receive Port** drop-down list, click **OnRamp.Itinerary**.</span></span>  
  
2.  <span data-ttu-id="394cc-133">从工具箱拖动**路线服务**至设计图面上的模型元素。</span><span class="sxs-lookup"><span data-stu-id="394cc-133">From the Toolbox, drag an **Itinerary Service** model element to the design surface.</span></span> <span data-ttu-id="394cc-134">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="394cc-134">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="394cc-135">单击**名称**属性，并键入**BindingKeyRoute**。</span><span class="sxs-lookup"><span data-stu-id="394cc-135">Click the **Name** property, and then type **BindingKeyRoute**.</span></span>  
  
    2.  <span data-ttu-id="394cc-136">在**路线服务 Extender**下拉列表中，单击**消息扩展器**。</span><span class="sxs-lookup"><span data-stu-id="394cc-136">In the **Itinerary Service Extender** drop-down list, click **Messaging Extender**.</span></span>  
  
    3.  <span data-ttu-id="394cc-137">在中**容器**下拉列表中，展开**ReceiveNAOrder**，然后单击**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="394cc-137">In the **Container** drop-down list, expand **ReceiveNAOrder**, and then click **Receive Handlers**.</span></span>  
  
    4.  <span data-ttu-id="394cc-138">在中**服务名称**下拉列表中，单击**Microsoft.Practices.ESB.Services.Routing**。</span><span class="sxs-lookup"><span data-stu-id="394cc-138">In the **Service Name** drop-down list, click **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
3.  <span data-ttu-id="394cc-139">右键单击**冲突解决程序**系列**BindingKeyRoute**模型元素，然后单击**添加新解析程序**。</span><span class="sxs-lookup"><span data-stu-id="394cc-139">Right-click the **Resolver** collection of the **BindingKeyRoute** model element, and then click **Add new Resolver**.</span></span> <span data-ttu-id="394cc-140">在中**Resolver1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="394cc-140">In the **Resolver1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="394cc-141">单击**名称**属性，并键入**BindingKeySearch**。</span><span class="sxs-lookup"><span data-stu-id="394cc-141">Click the **Name** property, and then type **BindingKeySearch**.</span></span>  
  
    2.  <span data-ttu-id="394cc-142">在中**解析程序实现**下拉列表中，单击**Uddi3 冲突解决程序扩展**。</span><span class="sxs-lookup"><span data-stu-id="394cc-142">In the **Resolver Implementation** drop-down list, click **Uddi3 Resolver Extension**.</span></span>  
  
    3.  <span data-ttu-id="394cc-143">在中**冲突解决程序名字对象**下拉列表中，单击**UDDI3**。</span><span class="sxs-lookup"><span data-stu-id="394cc-143">In the **Resolver Moniker** drop-down list, click **UDDI3**.</span></span>  
  
    4.  <span data-ttu-id="394cc-144">单击**绑定键**属性，并键入**uddi:esb:orderfileservicev3.1**。</span><span class="sxs-lookup"><span data-stu-id="394cc-144">Click the **Binding key** property, and then type **uddi:esb:orderfileservicev3.1**.</span></span>  
  
4.  <span data-ttu-id="394cc-145">右键单击**BindingKeySearch**冲突解决程序，并单击**测试解析程序配置**。</span><span class="sxs-lookup"><span data-stu-id="394cc-145">Right-click the **BindingKeySearch** resolver, and then click **Test Resolver Configuration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="394cc-146">验证显示在输出窗口中的输出。</span><span class="sxs-lookup"><span data-stu-id="394cc-146">Verify the output displayed in the Output window.</span></span>  
  
5.  <span data-ttu-id="394cc-147">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="394cc-147">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="394cc-148">将从连接**ReceiveNAOrder**到模型元素**BindingKeyRoute**模型元素。</span><span class="sxs-lookup"><span data-stu-id="394cc-148">Drag a connection from the **ReceiveNAOrder** model element to the **BindingKeyRoute** model element.</span></span>  
  
6.  <span data-ttu-id="394cc-149">从工具箱拖动**关闭负载增加**模型元素到设计图面，然后将它放到右侧**BindingKeyRoute**模型元素。</span><span class="sxs-lookup"><span data-stu-id="394cc-149">From the Toolbox, drag an **Off-Ramp** model element to the design surface, and then place it to the right of the **BindingKeyRoute** model element.</span></span> <span data-ttu-id="394cc-150">在中**OffRamp1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="394cc-150">In the **OffRamp1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="394cc-151">单击**名称**属性，并键入**SendNAOrder**。</span><span class="sxs-lookup"><span data-stu-id="394cc-151">Click the **Name** property, and then type **SendNAOrder**.</span></span>  
  
    2.  <span data-ttu-id="394cc-152">在**Extender**下拉列表中，单击**关闭负载增加 ESB 扩展器**。</span><span class="sxs-lookup"><span data-stu-id="394cc-152">In the **Extender** drop-down list, click **Off-Ramp ESB Extender**.</span></span>  
  
    3.  <span data-ttu-id="394cc-153">在中**BizTalk 应用程序**下拉列表中，单击**GlobalBank.ESB**。</span><span class="sxs-lookup"><span data-stu-id="394cc-153">In the **BizTalk Application** drop-down list, click **GlobalBank.ESB**.</span></span>  
  
    4.  <span data-ttu-id="394cc-154">在中**发送端口**下拉列表中，单击**DynamicResolutionOneWay**。</span><span class="sxs-lookup"><span data-stu-id="394cc-154">In the **Send Port** drop-down list, click **DynamicResolutionOneWay**.</span></span>  
  
7.  <span data-ttu-id="394cc-155">从工具箱拖动**路线服务**模型元素到设计图面，然后将其之间放置**BindingKeyRoute**模型元素和**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="394cc-155">From the Toolbox, drag an **Itinerary Service** model element to the design surface, and then place it between the **BindingKeyRoute** model element and the **SendNAOrder** model element.</span></span> <span data-ttu-id="394cc-156">在中**ItineraryService1**属性窗口中，配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="394cc-156">In the **ItineraryService1** Properties window, configure the following properties:</span></span>  
  
    1.  <span data-ttu-id="394cc-157">单击**名称**属性，并键入**SendPortFilter**。</span><span class="sxs-lookup"><span data-stu-id="394cc-157">Click the **Name** property, and then type **SendPortFilter**.</span></span>  
  
    2.  <span data-ttu-id="394cc-158">在**路线服务 Extender**下拉列表中，单击**接入点关闭扩展器**。</span><span class="sxs-lookup"><span data-stu-id="394cc-158">In the **Itinerary Service Extender** drop-down list, click **Off-Ramp Extender**.</span></span>  
  
    3.  <span data-ttu-id="394cc-159">在中**关闭负载增加**下拉列表中，展开**SendNAOrder**，然后单击**发送处理程序**。</span><span class="sxs-lookup"><span data-stu-id="394cc-159">In the **Off-Ramp** drop-down list, expand **SendNAOrder**, and then click **Send Handlers**.</span></span>  
  
8.  <span data-ttu-id="394cc-160">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="394cc-160">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="394cc-161">将从连接**BindingKeyRoute**到模型元素**SendPortFilter**模型元素。</span><span class="sxs-lookup"><span data-stu-id="394cc-161">Drag a connection from the **BindingKeyRoute** model element to the **SendPortFilter** model element.</span></span>  
  
9. <span data-ttu-id="394cc-162">在工具箱中，单击**连接器**。</span><span class="sxs-lookup"><span data-stu-id="394cc-162">In the Toolbox, click **Connector**.</span></span> <span data-ttu-id="394cc-163">将从连接**SendPortFilter**到模型元素**SendNAOrder**模型元素。</span><span class="sxs-lookup"><span data-stu-id="394cc-163">Drag a connection from the **SendPortFilter** model element to the **SendNAOrder** model element.</span></span>  
  
#### <a name="to-export-the-model-for-use-with-the-itinerary-test-client"></a><span data-ttu-id="394cc-164">若要导出与路线测试客户端一起使用的模型</span><span class="sxs-lookup"><span data-stu-id="394cc-164">To export the model for use with the Itinerary Test Client</span></span>  
  
1.  <span data-ttu-id="394cc-165">在 Visual Studio 中，右键单击设计图面的**UDDI3BindingKeySearch**路线，并单击**导出模型**。</span><span class="sxs-lookup"><span data-stu-id="394cc-165">In Visual Studio, right-click the design surface of the **UDDI3BindingKeySearch** itinerary, and then click **Export Model**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="394cc-166">在 Visual Studio 中打开的 XML 版本的路线。</span><span class="sxs-lookup"><span data-stu-id="394cc-166">The XML version of the itinerary opens in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="394cc-167">保存项目的所有项目。</span><span class="sxs-lookup"><span data-stu-id="394cc-167">Save all project artifacts.</span></span>  
  
3.  <span data-ttu-id="394cc-168">在 Windows 资源管理器，浏览到 C:\HowTos\Itineraries 并请注意，您的路线 XML (UDDI3BindingKeySearch.xml) 创建。</span><span class="sxs-lookup"><span data-stu-id="394cc-168">In Windows Explorer, browse to C:\HowTos\Itineraries and notice the creation of your itinerary XML (UDDI3BindingKeySearch.xml).</span></span>  
  
#### <a name="to-test-the-itinerary"></a><span data-ttu-id="394cc-169">若要测试路线</span><span class="sxs-lookup"><span data-stu-id="394cc-169">To test the itinerary</span></span>  
  
1.  <span data-ttu-id="394cc-170">打开路线测试客户端示例应用程序使用过程中创建的快捷方式[开发活动的先决条件](../esb-toolkit/prerequisites-for-the-development-activities.md)(C:\HowTos\ESB。Itinerary.Test.exe-快捷方式)。</span><span class="sxs-lookup"><span data-stu-id="394cc-170">Open the Itinerary Test Client sample application using the shortcut created during the [Prerequisites for the Development Activities](../esb-toolkit/prerequisites-for-the-development-activities.md) (C:\HowTos\ESB.Itinerary.Test.exe - Shortcut).</span></span>  
  
2.  <span data-ttu-id="394cc-171">在路线测试客户端，清除**使用 WCF 服务**复选框，然后依次**负载路线**。</span><span class="sxs-lookup"><span data-stu-id="394cc-171">In the Itinerary Test Client, clear the **Use WCF Service** check box, and then click **Load Itinerary**.</span></span>  
  
3.  <span data-ttu-id="394cc-172">在打开路线文件对话框中，浏览到 C:\HowTos\Itineraries。</span><span class="sxs-lookup"><span data-stu-id="394cc-172">In the Open Itinerary File dialog box, browse to C:\HowTos\Itineraries.</span></span> <span data-ttu-id="394cc-173">选择 UDDI3BindingKeySearch.xml，，然后单击打开加载路线。</span><span class="sxs-lookup"><span data-stu-id="394cc-173">Select UDDI3BindingKeySearch.xml, and then click Open to load the itinerary.</span></span>  
  
4.  <span data-ttu-id="394cc-174">单击**确定**清除**成功加载路线**消息。</span><span class="sxs-lookup"><span data-stu-id="394cc-174">Click **OK** to clear the **Itinerary Loaded Successfully** message.</span></span>  
  
5.  <span data-ttu-id="394cc-175">在路线测试客户端，单击下一步的省略号按钮 （...）**负载消息**框。</span><span class="sxs-lookup"><span data-stu-id="394cc-175">In the Itinerary Test Client, click the ellipsis button (...) next to the **Load Message** box.</span></span>  
  
6.  <span data-ttu-id="394cc-176">在中**选择要加载 XML 文档**对话框中，浏览到 C:\HowTos。</span><span class="sxs-lookup"><span data-stu-id="394cc-176">In the **Select XML Document to load** dialog box, browse to C:\HowTos.</span></span> <span data-ttu-id="394cc-177">选择**NAOrderDoc.xml**，然后单击**打开**加载测试消息。</span><span class="sxs-lookup"><span data-stu-id="394cc-177">Select **NAOrderDoc.xml**, and then click **Open** to load the test message.</span></span>  
  
7.  <span data-ttu-id="394cc-178">单击**提交请求**按钮。</span><span class="sxs-lookup"><span data-stu-id="394cc-178">Click the **Submit Request** button.</span></span> <span data-ttu-id="394cc-179">测试完成后，单击**确定**若要消除出现的确认。</span><span class="sxs-lookup"><span data-stu-id="394cc-179">When the test completes, click **OK** to dismiss the confirmation that appears.</span></span>  
  
8.  <span data-ttu-id="394cc-180">在 Windows 资源管理器，浏览到 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out。验证 %MessageID%.xml 消息已写入到目录。</span><span class="sxs-lookup"><span data-stu-id="394cc-180">In Windows Explorer, browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out. Verify that the %MessageID%.xml message has been written to the directory.</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="394cc-181">其他资源</span><span class="sxs-lookup"><span data-stu-id="394cc-181">Additional Resources</span></span>  
 <span data-ttu-id="394cc-182">有关详细信息，请参阅下列相关主题：</span><span class="sxs-lookup"><span data-stu-id="394cc-182">For more information, see the following related topics:</span></span>  
  
-   [<span data-ttu-id="394cc-183">如何：解析服务终结点使用 UDDI 类别搜索</span><span class="sxs-lookup"><span data-stu-id="394cc-183">How to: Resolve a Service Endpoint Using a UDDI Category Search</span></span>](../esb-toolkit/how-to-resolve-a-service-endpoint-using-a-uddi-category-search.md)  
  
-   [<span data-ttu-id="394cc-184">开发活动</span><span class="sxs-lookup"><span data-stu-id="394cc-184">Development Activities</span></span>](../esb-toolkit/development-activities.md)  
  
-   [<span data-ttu-id="394cc-185">使用动态解析和路由</span><span class="sxs-lookup"><span data-stu-id="394cc-185">Using Dynamic Resolution and Routing</span></span>](../esb-toolkit/using-dynamic-resolution-and-routing.md)