---
title: 步骤 3： 测试批处理中的批处理方案出 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c487d39d-b2be-41d4-963e-d0ee9ba169fb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d84c34eb3019f83ecd28f30425a93708affcecb2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25960795"
---
# <a name="step-3-test-the-batch-inbatch-out-scenario"></a><span data-ttu-id="1925a-102">步骤 3： 测试中的批处理/批处理出方案</span><span class="sxs-lookup"><span data-stu-id="1925a-102">Step 3: Test the Batch In/Batch Out Scenario</span></span>
<span data-ttu-id="1925a-103">在此步骤中，测试批处理中 / 批处理出教程通过删除批处理中的测试实例 / 批处理到文件夹出消息。</span><span class="sxs-lookup"><span data-stu-id="1925a-103">In this step, you test the Batch In/Batch Out tutorial by dropping a test instance of the batch in/batch out message into a folder.</span></span> <span data-ttu-id="1925a-104">你将设置为发送端口将发送消息、 接收端口将接收它，和接收管道将对其进行处理，并将其放到目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="1925a-104">The send port that you set up will send the message, the receive port will receive it, and the receive pipeline will process it and drop it into the destination folder.</span></span>  
  
### <a name="to-test-the-batch-inbatch-out-scenario"></a><span data-ttu-id="1925a-105">若要测试批处理中 / 批处理出方案</span><span class="sxs-lookup"><span data-stu-id="1925a-105">To test the Batch In/Batch Out scenario</span></span>  
  
1.  <span data-ttu-id="1925a-106">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \Batching Tutorial\Instances**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1925a-106">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\Batching Tutorial\Instances** folder.</span></span>  
  
2.  <span data-ttu-id="1925a-107">右键单击**BatchInBatchOut.txt**，然后单击**复制**。</span><span class="sxs-lookup"><span data-stu-id="1925a-107">Right click **BatchInBatchOut.txt**, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="1925a-108">浏览到 **\<*驱动器*\>: files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\End 端到端 Tutorial\Tutorial_BTAHL7PickUp**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1925a-108">Browse to the **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp** folder.</span></span>  
  
4.  <span data-ttu-id="1925a-109">右键单击文件夹，并依次**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="1925a-109">Right-click the folder, and then click **Paste**.</span></span>  
  
### <a name="to-verify-the-results-of-the-batch-inbatch-out-tutorial"></a><span data-ttu-id="1925a-110">若要验证的批处理的结果中 / 批处理出教程</span><span class="sxs-lookup"><span data-stu-id="1925a-110">To verify the results of the Batch In/Batch Out Tutorial</span></span>  
  
-   <span data-ttu-id="1925a-111">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BTAHL7Drop**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1925a-111">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop** folder.</span></span> <span data-ttu-id="1925a-112">一段时间后你应看到的批处理消息，并确认已处理的实例，请在文件夹中显示。</span><span class="sxs-lookup"><span data-stu-id="1925a-112">After a short period, you should see the processed instance of the batch message, and an acknowledgment, appear in the folder.</span></span> <span data-ttu-id="1925a-113">如果它们不会出现，请检查[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]一条错误消息的事件查看器。</span><span class="sxs-lookup"><span data-stu-id="1925a-113">If they do not appear, check the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer for an error message.</span></span> <span data-ttu-id="1925a-114">每个文件应具有不同名称的形式\< *Guid*\>.txt。</span><span class="sxs-lookup"><span data-stu-id="1925a-114">Each file should have a different name in the form \<*Guid*\>.txt.</span></span>  
  
     <span data-ttu-id="1925a-115">第一条消息应包含两条消息批处理。</span><span class="sxs-lookup"><span data-stu-id="1925a-115">The first message should be the batch consisting of two messages.</span></span> <span data-ttu-id="1925a-116">BizTalk Accelerator for HL7 (BTAHL7) 已包含这两条消息按顺序在.txt 文件。</span><span class="sxs-lookup"><span data-stu-id="1925a-116">BizTalk Accelerator for HL7 (BTAHL7) has included these two messages sequentially in the .txt file.</span></span> <span data-ttu-id="1925a-117">此批处理不包含 FHS/FT 和 BHS/BTS 标记。</span><span class="sxs-lookup"><span data-stu-id="1925a-117">This batch does not contain FHS/FTS and BHS/BTS tags.</span></span> <span data-ttu-id="1925a-118">批处理必须包含任一所有 FHS/FT 和 BHS/BTS 标记，或如此批处理消息、 没有 FHS/FT 和无 BHS/BTS 标记。</span><span class="sxs-lookup"><span data-stu-id="1925a-118">A batch must contain either all FHS/FTS and BHS/BTS tags, or like this batch message, no FHS/FTS and no BHS/BTS tags.</span></span>  
  
    |<span data-ttu-id="1925a-119">MSH.9</span><span class="sxs-lookup"><span data-stu-id="1925a-119">MSH.9</span></span>|<span data-ttu-id="1925a-120">MSH.10</span><span class="sxs-lookup"><span data-stu-id="1925a-120">MSH.10</span></span>|<span data-ttu-id="1925a-121">MSH.3</span><span class="sxs-lookup"><span data-stu-id="1925a-121">MSH.3</span></span>|<span data-ttu-id="1925a-122">MSH.5</span><span class="sxs-lookup"><span data-stu-id="1925a-122">MSH.5</span></span>|  
    |-----------|------------|-----------|-----------|  
    |<span data-ttu-id="1925a-123">ADT^A03</span><span class="sxs-lookup"><span data-stu-id="1925a-123">ADT^A03</span></span>|<span data-ttu-id="1925a-124">000001</span><span class="sxs-lookup"><span data-stu-id="1925a-124">000001</span></span>|<span data-ttu-id="1925a-125">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="1925a-125">Tutorial_BatchSource</span></span>|<span data-ttu-id="1925a-126">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="1925a-126">MESA_IS</span></span>|  
    |<span data-ttu-id="1925a-127">ADT^A03</span><span class="sxs-lookup"><span data-stu-id="1925a-127">ADT^A03</span></span>|<span data-ttu-id="1925a-128">000002</span><span class="sxs-lookup"><span data-stu-id="1925a-128">000002</span></span>|<span data-ttu-id="1925a-129">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="1925a-129">Tutorial_BatchSource</span></span>|<span data-ttu-id="1925a-130">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="1925a-130">MESA_IS</span></span>|  
  
     <span data-ttu-id="1925a-131">第二个消息都应在批处理消息，使用以下字段的响应中发送的单个应用程序确认：</span><span class="sxs-lookup"><span data-stu-id="1925a-131">The second message should be a single application acknowledgment sent in response to the batch message, with the following fields:</span></span>  
  
    |<span data-ttu-id="1925a-132">MSH.9</span><span class="sxs-lookup"><span data-stu-id="1925a-132">MSH.9</span></span>|<span data-ttu-id="1925a-133">MSH.3</span><span class="sxs-lookup"><span data-stu-id="1925a-133">MSH.3</span></span>|<span data-ttu-id="1925a-134">MSH.5</span><span class="sxs-lookup"><span data-stu-id="1925a-134">MSH.5</span></span>|<span data-ttu-id="1925a-135">MSA.1</span><span class="sxs-lookup"><span data-stu-id="1925a-135">MSA.1</span></span>|<span data-ttu-id="1925a-136">MSA.2</span><span class="sxs-lookup"><span data-stu-id="1925a-136">MSA.2</span></span>|  
    |-----------|-----------|-----------|-----------|-----------|  
    |<span data-ttu-id="1925a-137">ACK^A03^ACK</span><span class="sxs-lookup"><span data-stu-id="1925a-137">ACK^A03^ACK</span></span>|<span data-ttu-id="1925a-138">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="1925a-138">MESA_IS</span></span>|<span data-ttu-id="1925a-139">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="1925a-139">Tutorial_BatchSource</span></span>|<span data-ttu-id="1925a-140">AA</span><span class="sxs-lookup"><span data-stu-id="1925a-140">AA</span></span>|<span data-ttu-id="1925a-141">000001</span><span class="sxs-lookup"><span data-stu-id="1925a-141">000001</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1925a-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1925a-142">See Also</span></span>  
 <span data-ttu-id="1925a-143">[第 1 部分： 零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="1925a-143">[Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span></span>  
 [<span data-ttu-id="1925a-144">第 3 部分：Create-Batch 方案</span><span class="sxs-lookup"><span data-stu-id="1925a-144">Part 3: Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)