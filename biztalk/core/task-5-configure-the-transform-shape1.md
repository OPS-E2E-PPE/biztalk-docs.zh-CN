---
title: "任务 5： 配置转换 Shape1 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93a73fd2-0f34-4681-8aed-7d54d69c86d3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e76313ca87ad3138da83480b46a38a802d89ff15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="task-5-configure-the-transform-shape"></a><span data-ttu-id="10e3f-102">任务 5： 配置转换形状</span><span class="sxs-lookup"><span data-stu-id="10e3f-102">Task 5: Configure the Transform Shape</span></span>
<span data-ttu-id="10e3f-103">使用以下过程可配置转换形状。</span><span class="sxs-lookup"><span data-stu-id="10e3f-103">Use the following procedure to configure the Transform shape.</span></span>  
  
### <a name="to-configure-the-transform-shape"></a><span data-ttu-id="10e3f-104">若要配置转换形状</span><span class="sxs-lookup"><span data-stu-id="10e3f-104">To configure the Transform shape</span></span>  
  
1.  <span data-ttu-id="10e3f-105">将构造消息形状拖至 ReceiveBeginDocResponse 后。</span><span class="sxs-lookup"><span data-stu-id="10e3f-105">Drag a Construct Message shape after ReceiveBeginDocResponse.</span></span>  
  
    -   <span data-ttu-id="10e3f-106">**构造的消息：** EditLineMsg</span><span class="sxs-lookup"><span data-stu-id="10e3f-106">**Messages Constructed:** EditLineMsg</span></span>  
  
    -   <span data-ttu-id="10e3f-107">**名称：** ConstructEditLineMessageWithData</span><span class="sxs-lookup"><span data-stu-id="10e3f-107">**Name:** ConstructEditLineMessageWithData</span></span>  
  
     <span data-ttu-id="10e3f-108">在中间，选择中右击**插入形状**，然后选择**转换**。</span><span class="sxs-lookup"><span data-stu-id="10e3f-108">Right-click in the middle, select **Insert Shape**, and then select **Transform**.</span></span>  
  
     ![](../core/media/jde-insert-shape-transform.gif "JDE_insert_shape_transform")  
  
     <span data-ttu-id="10e3f-109">使用“转换”，将数据从正在发送的数据映射到发送的数据。</span><span class="sxs-lookup"><span data-stu-id="10e3f-109">Using Transform, map data from the data you are sending to the data that is sent.</span></span>  
  
     <span data-ttu-id="10e3f-110">对于将发送具有所有可能值的文档（而不是 BeginDoc）的工作环境，允许您构造所有可能的消息 BeginDoc、EditLine 和 EndDoc。</span><span class="sxs-lookup"><span data-stu-id="10e3f-110">For your work environment you would send a document (instead of BeginDoc) with all values possible allowing you to construct all possible messages, BeginDoc, EditLine, and EndDoc.</span></span> <span data-ttu-id="10e3f-111">然而，对于该示例，只有硬编码数据。</span><span class="sxs-lookup"><span data-stu-id="10e3f-111">For this example, however, there is only hard coded data.</span></span>  
  
2.  <span data-ttu-id="10e3f-112">双击**Transform_1**以打开。</span><span class="sxs-lookup"><span data-stu-id="10e3f-112">Double-click **Transform_1** to open.</span></span>  
  
    1.  <span data-ttu-id="10e3f-113">选择源并单击在添加行**变量名称**和选择**BeginDocResponseMsg**。</span><span class="sxs-lookup"><span data-stu-id="10e3f-113">Select Source and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
         ![](../core/media/jde-transform-source.gif "JDE_transform_source")  
  
    2.  <span data-ttu-id="10e3f-114">选择**目标**在添加行单击**变量名称**，选择**EditLineMsg**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="10e3f-114">Select **Destination** and click in the Add row under **Variable Name**, select **EditLineMsg**, and click **OK**.</span></span>  
  
         ![](../core/media/jde-transform-destination.gif "JDE_transform_destination")  
  
3.  <span data-ttu-id="10e3f-115">在解决方案资源管理器中，双击**Transform_1.btm**若要打开的映射工具。</span><span class="sxs-lookup"><span data-stu-id="10e3f-115">In the Solution Explorer, double-click **Transform_1.btm** to open the mapping tool.</span></span> <span data-ttu-id="10e3f-116">链接以下四项：</span><span class="sxs-lookup"><span data-stu-id="10e3f-116">Link the following four items:</span></span>  
  
    -   <span data-ttu-id="10e3f-117">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="10e3f-117">mnCMJobNo</span></span>  
  
    -   <span data-ttu-id="10e3f-118">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="10e3f-118">szCMComputerID</span></span>  
  
    -   <span data-ttu-id="10e3f-119">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="10e3f-119">mnProcessID</span></span>  
  
    -   <span data-ttu-id="10e3f-120">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="10e3f-120">mnTransactionID</span></span>  
  
     ![](../core/media/jde-example-transformmapping.gif "JDE_example_transformmapping")  
  
     <span data-ttu-id="10e3f-121">为方便使用，该示例具有硬编码值。</span><span class="sxs-lookup"><span data-stu-id="10e3f-121">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="10e3f-122">单击目标架构中的项并设置以下值。</span><span class="sxs-lookup"><span data-stu-id="10e3f-122">Click the item in the Destination Schema and set the following Value.</span></span>  
  
     ![](../core/media/jde-hardcoded-mapping-example.gif "JDE_hardcoded_mapping_example")  
  
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
  
4.  <span data-ttu-id="10e3f-123">将构造消息拖至 ReceiveEditLine 后。</span><span class="sxs-lookup"><span data-stu-id="10e3f-123">Drag a Construct Message after ReceiveEditLine.</span></span>  
  
    -   <span data-ttu-id="10e3f-124">**构造的消息：** EndDocMsg</span><span class="sxs-lookup"><span data-stu-id="10e3f-124">**Messages Constructed:** EndDocMsg</span></span>  
  
    -   <span data-ttu-id="10e3f-125">**名称：** ConstructEndDocMessageWithData</span><span class="sxs-lookup"><span data-stu-id="10e3f-125">**Name:** ConstructEndDocMessageWithData</span></span>  
  
     <span data-ttu-id="10e3f-126">右键单击在中间，选择**插入形状**，然后选择**转换**。</span><span class="sxs-lookup"><span data-stu-id="10e3f-126">Right-click in the middle and select **Insert Shape**, and then select **Transform**.</span></span>  
  
5.  <span data-ttu-id="10e3f-127">双击**Transform_2**以打开。</span><span class="sxs-lookup"><span data-stu-id="10e3f-127">Double-click **Transform_2** to open.</span></span>  
  
    1.  <span data-ttu-id="10e3f-128">选择**源**在添加行单击**变量名称**和选择**BeginDocResponseMsg**。</span><span class="sxs-lookup"><span data-stu-id="10e3f-128">Select **Source** and click in the Add row under **Variable Name** and select **BeginDocResponseMsg**.</span></span>  
  
    2.  <span data-ttu-id="10e3f-129">选择**目标**在添加行单击**变量名称**，选择**EndDocMsg**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="10e3f-129">Select **Destination** and click in the Add row under **Variable Name**, select **EndDocMsg**, and click **OK**.</span></span>  
  
6.  <span data-ttu-id="10e3f-130">在解决方案资源管理器中，双击**Transform_2.btm**若要打开的映射工具。</span><span class="sxs-lookup"><span data-stu-id="10e3f-130">In the Solution Explorer, double-click **Transform_2.btm** to open the mapping tool.</span></span> <span data-ttu-id="10e3f-131">链接以下四项：</span><span class="sxs-lookup"><span data-stu-id="10e3f-131">Link the following four items:</span></span>  
  
    -   <span data-ttu-id="10e3f-132">mnCMJobNo</span><span class="sxs-lookup"><span data-stu-id="10e3f-132">mnCMJobNo</span></span>  
  
    -   <span data-ttu-id="10e3f-133">szCMComputerID</span><span class="sxs-lookup"><span data-stu-id="10e3f-133">szCMComputerID</span></span>  
  
    -   <span data-ttu-id="10e3f-134">mnProcessID</span><span class="sxs-lookup"><span data-stu-id="10e3f-134">mnProcessID</span></span>  
  
    -   <span data-ttu-id="10e3f-135">mnTransactionID</span><span class="sxs-lookup"><span data-stu-id="10e3f-135">mnTransactionID</span></span>  
  
     <span data-ttu-id="10e3f-136">为方便使用，该示例具有硬编码值。</span><span class="sxs-lookup"><span data-stu-id="10e3f-136">For ease of use, this example has hardcoded values.</span></span> <span data-ttu-id="10e3f-137">单击目标架构中的项并设置以下值。</span><span class="sxs-lookup"><span data-stu-id="10e3f-137">Click the item in the Destination Schema and set the following Value.</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ns0:F4211FSEndDoc xmlns:ns0="http://schemas.microsoft.com/  
        [JDE://CSALES/B4200310]">  
       <ns0:szCMProgramID>XMLInterop</ns0:szCMProgramID>  
       <ns0:szCMVersion>ZJDE0001</ns0:szCMVersion>  
       <ns0:cCMUseWorkFiles>2</ns0:cCMUseWorkFiles>  
    </ns0:F4211FSEndDoc>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="10e3f-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10e3f-138">See Also</span></span>  
 <span data-ttu-id="10e3f-139">[任务 1： 创建端口](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="10e3f-139">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="10e3f-140">[任务 2： 创建消息](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="10e3f-140">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="10e3f-141">[任务 3： 配置发送和接收形状](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="10e3f-141">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 [<span data-ttu-id="10e3f-142">任务 4： 配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="10e3f-142">Task 4: Configure the Construct Message Shape</span></span>](../core/task-4-configure-the-construct-message-shape2.md)