---
title: 将请求映射为在专用流程中的响应 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, maps
- private processes, mapping requests
- private processes, customizing
- orchestrations, adding maps
- maps, adding to orchestrations
- maps, creating
- customizing private processes
- requests, mapping
- requests, private processes
ms.assetid: 5452c0a2-3a9b-43e7-bfa7-713eef0eab3b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd0ec4be1703c81061cf38310a467932a917bca3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283232"
---
# <a name="mapping-a-request-to-a-response-in-a-private-process"></a><span data-ttu-id="3bc2d-102">将请求映射为在专用流程中的响应</span><span class="sxs-lookup"><span data-stu-id="3bc2d-102">Mapping a Request to a Response in a Private Process</span></span>
<span data-ttu-id="3bc2d-103">本主题介绍如何将专用响应方流程收到的请求消息映射 — 从 Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]公用响应方流程，可以发送到的响应消息[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]公用响应方流程。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-103">This topic describes how to map a request message received by the private responder process—from the Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] public responder process, to a response message that can be sent to the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public responder process.</span></span>  
  
 <span data-ttu-id="3bc2d-104">当响应方接收请求消息时，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]到专用业务流程的业务流程，从公用流程，将请求消息路由至业务 (LOB) 程序。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-104">When a responder receives a request message, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] routes the request message from the public-process orchestration, to the private-process orchestration, to the line-of-business (LOB) program.</span></span> <span data-ttu-id="3bc2d-105">响应方需要来自 LOB 程序生成回发起方的 RosettaNet 响应消息的响应服务内容。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-105">The responder requires the response service content from the LOB program to generate a RosettaNet response message back to the initiator.</span></span> <span data-ttu-id="3bc2d-106">许多响应消息中的元素是使用请求消息中的值进行填充。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-106">Many of the elements in the response message are populated using the values from the request message.</span></span> <span data-ttu-id="3bc2d-107">因此，可以将合并在响应方专用流程业务流程，以帮助 LOB 程序生成所需格式的响应服务内容消息映射。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-107">As a result, you can incorporate a map in the responder private-process orchestration to help the LOB program generate the response service-content message in the required format.</span></span>  
  
 <span data-ttu-id="3bc2d-108">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包含将映射添加到响应方专用业务流程时，可以使用以下示例：</span><span class="sxs-lookup"><span data-stu-id="3bc2d-108">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK contains the following samples that you can use when you add a map to a responder private-process:</span></span>  
  
-   [<span data-ttu-id="3bc2d-109">3A2 请求到 3A2 响应映射示例</span><span class="sxs-lookup"><span data-stu-id="3bc2d-109">3A2 Request to 3A2 Response Map Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)  
  
-   [<span data-ttu-id="3bc2d-110">3A4 请求到 3A4 响应映射示例</span><span class="sxs-lookup"><span data-stu-id="3bc2d-110">3A4 Request to 3A4 Response Map Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)  
  
-   [<span data-ttu-id="3bc2d-111">双操作 PIPAutomation 业务流程</span><span class="sxs-lookup"><span data-stu-id="3bc2d-111">Double Action PIPAutomation Orchestration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)  
  
-   [<span data-ttu-id="3bc2d-112">使用业务规则的 3A4 专用响应方业务流程</span><span class="sxs-lookup"><span data-stu-id="3bc2d-112">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)  
  
### <a name="to-create-the-map"></a><span data-ttu-id="3bc2d-113">若要创建映射</span><span class="sxs-lookup"><span data-stu-id="3bc2d-113">To create the map</span></span>  
  
1.  <span data-ttu-id="3bc2d-114">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-114">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="3bc2d-115">上**文件**菜单，依次指向**打开**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-115">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="3bc2d-116">找到包含包含你想要将地图添加专用业务流程的 BizTalk 项目的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-116">Locate the folder that contains the BizTalk project that contains the private-process orchestration to which you want to add the map.</span></span>  
  
4.  <span data-ttu-id="3bc2d-117">在解决方案资源管理器中，右键单击项目，指向“添加”，然后单击“新建项”。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-117">In Solution Explorer, right-click the project, point to **Add**, and then click **New Item**.</span></span>  
  
5.  <span data-ttu-id="3bc2d-118">在添加新项窗口中**类别**窗格中，单击**映射文件**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-118">In the Add New Item window, in the **Categories** pane, click **Map Files**.</span></span> <span data-ttu-id="3bc2d-119">在模板窗格中单击**映射**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-119">In the Templates pane, click **Map**.</span></span> <span data-ttu-id="3bc2d-120">在中**名称**框中，键入映射的名称，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-120">In the **Name** box, type a name for the map, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="3bc2d-121">在源架构窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-121">In the Source Schema pane, click **Open Source Schema**.</span></span>  
  
7.  <span data-ttu-id="3bc2d-122">在 BizTalk 类型选取器窗口中，展开**架构**，选择你想要将映射中，然后单击请求消息的 PIP 架构**确定**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-122">In the BizTalk Type Picker window, expand **Schemas**, select the PIP schema for the request message that you want to map from, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="3bc2d-123">在目标架构窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-123">In the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
9. <span data-ttu-id="3bc2d-124">在 BizTalk 类型选取器窗口中，展开**引用**，展开**Microsoft.Solutions.BTARN.Schemas.RNPIPs**，展开**架构**，选择的 PIP 架构响应消息，你想要将映射，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-124">In the BizTalk Type Picker window, expand **References**, expand **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, expand **Schemas**, select the PIP schema for the response message to which you want to map, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="3bc2d-125">右键单击\<*架构*\>节点的源架构，然后单击**展开树节点**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-125">Right-click the \<*Schema*\> node of the source schema, and then click **Expand Tree Node**.</span></span>  
  
11. <span data-ttu-id="3bc2d-126">对于目标架构中重复步骤 10。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-126">Repeat step 10 for the destination schema.</span></span>  
  
12. <span data-ttu-id="3bc2d-127">在源架构窗格中，单击并按住你想要将映射到目标架构中的字段的字段。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-127">In the Source Schema pane, click and hold on a field that you want to map to a field in the destination schema.</span></span> <span data-ttu-id="3bc2d-128">将拖至目标架构窗格中的相应节点。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-128">Drag to the corresponding node in the Destination Schema pane.</span></span>  
  
13. <span data-ttu-id="3bc2d-129">对于具有两个架构之间进行映射的所有字段重复步骤 12。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-129">Repeat step 12 for all fields that you have to map between the two schemas.</span></span>  
  
14. <span data-ttu-id="3bc2d-130">验证和测试映射。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-130">Validate and test the map.</span></span> <span data-ttu-id="3bc2d-131">有关详细信息，请参阅 BizTalk Server 帮助中的"编译和测试映射"主题。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-131">For more information, see the "Compiling and Testing Maps" topic in BizTalk Server Help.</span></span>  
  
### <a name="to-add-the-map-to-the-orchestration"></a><span data-ttu-id="3bc2d-132">若要将地图添加到业务流程</span><span class="sxs-lookup"><span data-stu-id="3bc2d-132">To add the map to the orchestration</span></span>  
  
1.  <span data-ttu-id="3bc2d-133">在解决方案资源管理器，双击专用业务流程。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-133">In Solution Explorer, double-click the private-process orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bc2d-134">请确保该业务流程具有对包含架构的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-134">Make sure that the orchestration has references to the assemblies that contain the schemas.</span></span>  
  
2.  <span data-ttu-id="3bc2d-135">在工具箱中，单击**转换**形状，并将其拖到业务流程具有将转换为响应消息的请求消息中的点。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-135">In the Toolbox, click the **Transform** shape, and drag it to the point in the orchestration at which you have to transform the request message into the response message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bc2d-136">有关示例的位置**转换**形状中，请参阅 PIP3A4PrivateResponder.odx 业务流程。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-136">For an example of the placement of the **Transform** shape, see the PIP3A4PrivateResponder.odx orchestration.</span></span> <span data-ttu-id="3bc2d-137">该文件位于\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for rosettanet\sdk\pipautomation\3a4\pr。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-137">It is located in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4\PR.</span></span> <span data-ttu-id="3bc2d-138">此示例会将**转换**立即形状下**放在 IsActivityDoubleAction**形状。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-138">This sample puts the **Transform** shape immediately under the **IsActivityDoubleAction** shape.</span></span> <span data-ttu-id="3bc2d-139">有关详细信息，请参阅[3A4 专用响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-139">For more information, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3bc2d-140">有关如何将多个映射合并多个 Pip 的示例，请参阅[双操作 PIPAutomation 业务流程](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-140">For an example of how you can incorporate multiple maps for multiple PIPs, see [Double Action PIPAutomation Orchestration](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md).</span></span>  
  
3.  <span data-ttu-id="3bc2d-141">在业务流程设计图面上，单击**揅 constructmessage1**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-141">On the orchestration design surface, click **ConstructMessage1**.</span></span> <span data-ttu-id="3bc2d-142">在属性窗口中，键入该形状的名称和要构造的消息的名称。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-142">In the Properties window, type a name for the shape, and a name for the message to be constructed.</span></span>  
  
4.  <span data-ttu-id="3bc2d-143">在业务流程设计图面上，单击**转换**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-143">On the orchestration design surface, click **Transform**.</span></span> <span data-ttu-id="3bc2d-144">在属性窗口中，单击省略号按钮 (**...**) 旁边**映射名称**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-144">In the Properties window, click the ellipsis button (**...**) next to **Map Name**.</span></span>  
  
5.  <span data-ttu-id="3bc2d-145">在转换配置窗口中，单击**现有的映射**，然后在**完全限定的映射名称**，单击刚创建的映射。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-145">In the Transform Configuration window, click **Existing Map**, and in **Fully Qualified Map Name**, click the map that you just created.</span></span>  
  
6.  <span data-ttu-id="3bc2d-146">下**转换**，单击**源**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-146">Under **Transform**, click **Source**.</span></span> <span data-ttu-id="3bc2d-147">单击变量下的空框，并从下拉列表中选择请求消息的名称。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-147">Click the empty box under variable, and select the name of the request message from the drop-down list.</span></span>  
  
7.  <span data-ttu-id="3bc2d-148">下**转换**，单击**目标**。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-148">Under **Transform**, click **Destination**.</span></span> <span data-ttu-id="3bc2d-149">单击变量下的空框，然后从下拉列表中选择响应消息的名称。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-149">Click the empty box under variable, and select the name of the response message from the drop-down list.</span></span>  
  
8.  <span data-ttu-id="3bc2d-150">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="3bc2d-150">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bc2d-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bc2d-151">See Also</span></span>  
 [<span data-ttu-id="3bc2d-152">编程指南</span><span class="sxs-lookup"><span data-stu-id="3bc2d-152">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)