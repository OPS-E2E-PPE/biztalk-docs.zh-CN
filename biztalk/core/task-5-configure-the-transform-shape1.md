---
title: 任务 5：配置转换形状 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a73fd2-0f34-4681-8aed-7d54d69c86d3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cf1be22c9a42da6cb82cb4d2303bcbc45038180
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299841"
---
# <a name="task-5-configure-the-transform-shape"></a><span data-ttu-id="bd64a-102">任务 5：配置转换形状</span><span class="sxs-lookup"><span data-stu-id="bd64a-102">Task 5: Configure the Transform Shape</span></span>
<span data-ttu-id="bd64a-103">使用以下过程来配置转换形状。</span><span class="sxs-lookup"><span data-stu-id="bd64a-103">Use the following procedure to configure the Transform shape.</span></span>  
  
### <a name="to-configure-the-transform-shape"></a><span data-ttu-id="bd64a-104">若要配置转换形状</span><span class="sxs-lookup"><span data-stu-id="bd64a-104">To configure the Transform shape</span></span>  
  
1. <span data-ttu-id="bd64a-105">将构造消息形状拖至 ReceiveBeginDocResponse 后。</span><span class="sxs-lookup"><span data-stu-id="bd64a-105">Drag a Construct Message shape after ReceiveBeginDocResponse.</span></span>  
  
   - <span data-ttu-id="bd64a-106">**构造的消息：** EditLineMsg</span><span class="sxs-lookup"><span data-stu-id="bd64a-106">**Messages Constructed:** EditLineMsg</span></span>  
  
   - <span data-ttu-id="bd64a-107">**名称：** ConstructEditLineMessageWithData</span><span class="sxs-lookup"><span data-stu-id="bd64a-107">**Name:** ConstructEditLineMessageWithData</span></span>  
  
     <span data-ttu-id="bd64a-108">在中间，选择右击**插入形状**，然后选择**转换**。</span><span class="sxs-lookup"><span data-stu-id="bd64a-108">Right-click in the middle, select **Insert Shape**, and then select **Transform**.</span></span>  
  
     <span data-ttu-id="bd64a-109">![](../core/media/jde-insert-shape-transform.gif "JDE_insert_shape_transform")</span><span class="sxs-lookup"><span data-stu-id="bd64a-109">![](../core/media/jde-insert-shape-transform.gif "JDE_insert_shape_transform")</span></span>  
  
     <span data-ttu-id="bd64a-110">使用转换，将数据从发送到发送的数据的数据的映射。</span><span class="sxs-lookup"><span data-stu-id="bd64a-110">Using Transform, map data from the data you are sending to the data that is sent.</span></span>  
  
     <span data-ttu-id="bd64a-111">为你的工作环境将文档发送 （而不是 BeginDoc) 的所有值可能允许您构造所有可能的消息、 BeginDoc、 EditLine 和 EndDoc。</span><span class="sxs-lookup"><span data-stu-id="bd64a-111">For your work environment you would send a document (instead of BeginDoc) with all values possible allowing you to construct all possible messages, BeginDoc, EditLine, and EndDoc.</span></span> <span data-ttu-id="bd64a-112">对于此示例中，但是，没有仅硬编码的数据。</span><span class="sxs-lookup"><span data-stu-id="bd64a-112">For this example, however, there is only hard coded data.</span></span>  
  
2. <span data-ttu-id="bd64a-113">双击**Transform_1**打开。</span><span class="sxs-lookup"><span data-stu-id="bd64a-113">Double-click **Transform_1** to open.</span></span>  
  
   1.  <span data-ttu-id="bd64a-114">选择源，然后单击下方的添加行**变量名**，然后选择**BeginDocResponseMsg**。</span><span class="sxs-lookup"><span data-stu-id="bd64a-114">Select Source and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
        <span data-ttu-id="bd64a-115">![](../core/media/jde-transform-source.gif "JDE_transform_source")</span><span class="sxs-lookup"><span data-stu-id="bd64a-115">![](../core/media/jde-transform-source.gif "JDE_transform_source")</span></span>  
  
   2.  <span data-ttu-id="bd64a-116">选择**目标**下方的添加行中单击**变量的名称**，选择**EditLineMsg**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bd64a-116">Select **Destination** and click in the Add row under **Variable Name**, select **EditLineMsg**, and click **OK**.</span></span>  
  
        <span data-ttu-id="bd64a-117">![](../core/media/jde-transform-destination.gif "JDE_transform_destination")</span><span class="sxs-lookup"><span data-stu-id="bd64a-117">![](../core/media/jde-transform-destination.gif "JDE_transform_destination")</span></span>  
  
3. <span data-ttu-id="bd64a-118">在解决方案资源管理器，双击**Transform_1.btm**以打开映射工具。</span><span class="sxs-lookup"><span data-stu-id="bd64a-118">In the Solution Explorer, double-click **Transform_1.btm** to open the mapping tool.</span></span> <span data-ttu-id="bd64a-119">链接以下四个项：</span><span class="sxs-lookup"><span data-stu-id="bd64a-119">Link the following four items:</span></span>  
  
   - <span data-ttu-id="bd64a-120">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="bd64a-120">mnCMJobNo</span></span>  
  
   - <span data-ttu-id="bd64a-121">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="bd64a-121">szCMComputerID</span></span>  
  
   - <span data-ttu-id="bd64a-122">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="bd64a-122">mnProcessID</span></span>  
  
   - <span data-ttu-id="bd64a-123">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="bd64a-123">mnTransactionID</span></span>  
  
     <span data-ttu-id="bd64a-124">![](../core/media/jde-example-transformmapping.gif "JDE_example_transformmapping")</span><span class="sxs-lookup"><span data-stu-id="bd64a-124">![](../core/media/jde-example-transformmapping.gif "JDE_example_transformmapping")</span></span>  
  
     <span data-ttu-id="bd64a-125">为了方便使用，此示例具有硬编码值。</span><span class="sxs-lookup"><span data-stu-id="bd64a-125">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="bd64a-126">单击目标架构中的项并设置以下值。</span><span class="sxs-lookup"><span data-stu-id="bd64a-126">Click the item in the Destination Schema and set the following Value.</span></span>  
  
     <span data-ttu-id="bd64a-127">![](../core/media/jde-hardcoded-mapping-example.gif "JDE_hardcoded_mapping_example")</span><span class="sxs-lookup"><span data-stu-id="bd64a-127">![](../core/media/jde-hardcoded-mapping-example.gif "JDE_hardcoded_mapping_example")</span></span>  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:F4211FSEditLine xmlns:ns0="http://schemas.microsoft.com/  
         [JDE://CSALES/B4200310]">  
      <ns0:cCMLineAction>A</ns0:cCMLineAction>  
      <ns0:cCMProcessEdits>1</ns0:cCMProcessEdits>  
      <ns0:cCMWriteToWFFlag>2</ns0:cCMWriteToWFFlag>  
      <ns0:szItemNo>210</ns0:szItemNo>  
      <ns0:mnQtyOrdered>1</ns0:mnQtyOrdered>  
      <ns0:cSalesTaxableYN>N</ns0:cSalesTaxableYN>  
      <ns0:szTransactionUOM>EA</ns0:szTransactionUOM>  
      <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
      <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
   </ns0:F4211FSEditLine>  
   ```  
  
4. <span data-ttu-id="bd64a-128">将构造消息拖至 ReceiveEditLine 后。</span><span class="sxs-lookup"><span data-stu-id="bd64a-128">Drag a Construct Message after ReceiveEditLine.</span></span>  
  
   - <span data-ttu-id="bd64a-129">**构造的消息：** EndDocMsg</span><span class="sxs-lookup"><span data-stu-id="bd64a-129">**Messages Constructed:** EndDocMsg</span></span>  
  
   - <span data-ttu-id="bd64a-130">**名称：** ConstructEndDocMessageWithData</span><span class="sxs-lookup"><span data-stu-id="bd64a-130">**Name:** ConstructEndDocMessageWithData</span></span>  
  
     <span data-ttu-id="bd64a-131">右键单击中部，选择**插入形状**，然后选择**转换**。</span><span class="sxs-lookup"><span data-stu-id="bd64a-131">Right-click in the middle and select **Insert Shape**, and then select **Transform**.</span></span>  
  
5. <span data-ttu-id="bd64a-132">双击**Transform_2**打开。</span><span class="sxs-lookup"><span data-stu-id="bd64a-132">Double-click **Transform_2** to open.</span></span>  
  
   1.  <span data-ttu-id="bd64a-133">选择**源**下方的添加行中单击**变量的名称**，然后选择**BeginDocResponseMsg**。</span><span class="sxs-lookup"><span data-stu-id="bd64a-133">Select **Source** and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
   2.  <span data-ttu-id="bd64a-134">选择**目标**下方的添加行中单击**变量的名称**，选择**EndDocMsg**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="bd64a-134">Select **Destination** and click in the Add row under **Variable Name**, select **EndDocMsg**, and click **OK**.</span></span>  
  
6. <span data-ttu-id="bd64a-135">在解决方案资源管理器，双击**Transform_2.btm**以打开映射工具。</span><span class="sxs-lookup"><span data-stu-id="bd64a-135">In the Solution Explorer, double-click **Transform_2.btm** to open the mapping tool.</span></span> <span data-ttu-id="bd64a-136">链接以下四个项：</span><span class="sxs-lookup"><span data-stu-id="bd64a-136">Link the following four items:</span></span>  
  
   - <span data-ttu-id="bd64a-137">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="bd64a-137">mnCMJobNo</span></span>  
  
   - <span data-ttu-id="bd64a-138">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="bd64a-138">szCMComputerID</span></span>  
  
   - <span data-ttu-id="bd64a-139">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="bd64a-139">mnProcessID</span></span>  
  
   - <span data-ttu-id="bd64a-140">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="bd64a-140">mnTransactionID</span></span>  
  
     <span data-ttu-id="bd64a-141">为了方便使用，此示例具有硬编码值。</span><span class="sxs-lookup"><span data-stu-id="bd64a-141">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="bd64a-142">单击目标架构中的项并设置以下值。</span><span class="sxs-lookup"><span data-stu-id="bd64a-142">Click the item in the Destination Schema and set the following Value.</span></span>  
  
   ```  
   <?xml version="1.0" encoding="utf-8"?>  
   <ns0:F4211FSEndDoc xmlns:ns0="http://schemas.microsoft.com/  
       [JDE://CSALES/B4200310]">  
      <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
      <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
      <ns0:cCMUseWorkFiles>2</ns0:cCMUseWorkFiles>  
   </ns0:F4211FSEndDoc>  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="bd64a-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd64a-143">See Also</span></span>  
 <span data-ttu-id="bd64a-144">[任务 1:创建端口](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="bd64a-144">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="bd64a-145">[任务 2:创建消息](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="bd64a-145">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="bd64a-146">[任务 3:配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="bd64a-146">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 [<span data-ttu-id="bd64a-147">任务 4:配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="bd64a-147">Task 4: Configure the Construct Message Shape</span></span>](../core/task-4-configure-the-construct-message-shape2.md)