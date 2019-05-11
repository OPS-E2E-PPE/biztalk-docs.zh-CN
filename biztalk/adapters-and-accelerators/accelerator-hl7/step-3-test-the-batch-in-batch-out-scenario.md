---
title: 步骤 3：测试批处理中的批处理方案 |Microsoft Docs
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
ms.openlocfilehash: 2c619c6f6ba1ee874c6b6eb54b9e499957d1dcee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288189"
---
# <a name="step-3-test-the-batch-inbatch-out-scenario"></a><span data-ttu-id="1e24c-102">步骤 3：测试在入站批处理/出站批处理方案</span><span class="sxs-lookup"><span data-stu-id="1e24c-102">Step 3: Test the Batch In/Batch Out Scenario</span></span>
<span data-ttu-id="1e24c-103">在此步骤中，您将测试批处理中 / 批处理出教程通过删除测试实例中的批处理 / 出消息批处理到的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e24c-103">In this step, you test the Batch In/Batch Out tutorial by dropping a test instance of the batch in/batch out message into a folder.</span></span> <span data-ttu-id="1e24c-104">设置发送端口将消息发送、 接收端口将接收它，并接收管道将对其进行处理并将其放到目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e24c-104">The send port that you set up will send the message, the receive port will receive it, and the receive pipeline will process it and drop it into the destination folder.</span></span>  
  
### <a name="to-test-the-batch-inbatch-out-scenario"></a><span data-ttu-id="1e24c-105">若要测试批处理中 / 出站批处理方案</span><span class="sxs-lookup"><span data-stu-id="1e24c-105">To test the Batch In/Batch Out scenario</span></span>  
  
1. <span data-ttu-id="1e24c-106">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \Batching Tutorial\Instances**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e24c-106">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\Batching Tutorial\Instances** folder.</span></span>  
  
2. <span data-ttu-id="1e24c-107">右键单击**BatchInBatchOut.txt**，然后单击**副本**。</span><span class="sxs-lookup"><span data-stu-id="1e24c-107">Right click **BatchInBatchOut.txt**, and then click **Copy**.</span></span>  
  
3. <span data-ttu-id="1e24c-108">浏览到 **\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for HL7\SDK\End 端到端 Tutorial\Tutorial_BTAHL7PickUp**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e24c-108">Browse to the **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp** folder.</span></span>  
  
4. <span data-ttu-id="1e24c-109">右键单击文件夹，然后依次**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="1e24c-109">Right-click the folder, and then click **Paste**.</span></span>  
  
### <a name="to-verify-the-results-of-the-batch-inbatch-out-tutorial"></a><span data-ttu-id="1e24c-110">若要验证的批处理结果中 / 出站教程批处理</span><span class="sxs-lookup"><span data-stu-id="1e24c-110">To verify the results of the Batch In/Batch Out Tutorial</span></span>  
  
- <span data-ttu-id="1e24c-111">使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BTAHL7Drop**文件夹。</span><span class="sxs-lookup"><span data-stu-id="1e24c-111">Using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, browse to the **\<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop** folder.</span></span> <span data-ttu-id="1e24c-112">一段时间后应会看到已处理的批处理消息，并确认实例，出现在文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1e24c-112">After a short period, you should see the processed instance of the batch message, and an acknowledgment, appear in the folder.</span></span> <span data-ttu-id="1e24c-113">如果未显示，检查[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]一条错误消息的事件查看器。</span><span class="sxs-lookup"><span data-stu-id="1e24c-113">If they do not appear, check the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer for an error message.</span></span> <span data-ttu-id="1e24c-114">每个文件应包含不同的名称，形式\< *Guid*\>.txt。</span><span class="sxs-lookup"><span data-stu-id="1e24c-114">Each file should have a different name in the form \<*Guid*\>.txt.</span></span>  
  
   <span data-ttu-id="1e24c-115">第一条消息应为包含两条消息的批处理。</span><span class="sxs-lookup"><span data-stu-id="1e24c-115">The first message should be the batch consisting of two messages.</span></span> <span data-ttu-id="1e24c-116">BizTalk Accelerator for HL7 (BTAHL7) 具有包含这两条消息按顺序在.txt 文件中。</span><span class="sxs-lookup"><span data-stu-id="1e24c-116">BizTalk Accelerator for HL7 (BTAHL7) has included these two messages sequentially in the .txt file.</span></span> <span data-ttu-id="1e24c-117">此批处理不包含 FHS/FTS 和 BHS/BTS 标记。</span><span class="sxs-lookup"><span data-stu-id="1e24c-117">This batch does not contain FHS/FTS and BHS/BTS tags.</span></span> <span data-ttu-id="1e24c-118">批处理必须包含任一所有 FHS/FTS 和 BHS/BTS 标记，或此批处理消息、 没有 FHS/FTS 和没有 BHS/BTS 标记等。</span><span class="sxs-lookup"><span data-stu-id="1e24c-118">A batch must contain either all FHS/FTS and BHS/BTS tags, or like this batch message, no FHS/FTS and no BHS/BTS tags.</span></span>  
  
  |<span data-ttu-id="1e24c-119">MSH.9</span><span class="sxs-lookup"><span data-stu-id="1e24c-119">MSH.9</span></span>|<span data-ttu-id="1e24c-120">MSH.10</span><span class="sxs-lookup"><span data-stu-id="1e24c-120">MSH.10</span></span>|<span data-ttu-id="1e24c-121">MSH.3</span><span class="sxs-lookup"><span data-stu-id="1e24c-121">MSH.3</span></span>|<span data-ttu-id="1e24c-122">MSH.5</span><span class="sxs-lookup"><span data-stu-id="1e24c-122">MSH.5</span></span>|  
  |-----------|------------|-----------|-----------|  
  |<span data-ttu-id="1e24c-123">ADT^A03</span><span class="sxs-lookup"><span data-stu-id="1e24c-123">ADT^A03</span></span>|<span data-ttu-id="1e24c-124">000001</span><span class="sxs-lookup"><span data-stu-id="1e24c-124">000001</span></span>|<span data-ttu-id="1e24c-125">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="1e24c-125">Tutorial_BatchSource</span></span>|<span data-ttu-id="1e24c-126">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="1e24c-126">MESA_IS</span></span>|  
  |<span data-ttu-id="1e24c-127">ADT^A03</span><span class="sxs-lookup"><span data-stu-id="1e24c-127">ADT^A03</span></span>|<span data-ttu-id="1e24c-128">000002</span><span class="sxs-lookup"><span data-stu-id="1e24c-128">000002</span></span>|<span data-ttu-id="1e24c-129">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="1e24c-129">Tutorial_BatchSource</span></span>|<span data-ttu-id="1e24c-130">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="1e24c-130">MESA_IS</span></span>|  
  
   <span data-ttu-id="1e24c-131">第二条消息应发送到批消息，包含以下字段的响应中的单个应用程序确认：</span><span class="sxs-lookup"><span data-stu-id="1e24c-131">The second message should be a single application acknowledgment sent in response to the batch message, with the following fields:</span></span>  
  
  |<span data-ttu-id="1e24c-132">MSH.9</span><span class="sxs-lookup"><span data-stu-id="1e24c-132">MSH.9</span></span>|<span data-ttu-id="1e24c-133">MSH.3</span><span class="sxs-lookup"><span data-stu-id="1e24c-133">MSH.3</span></span>|<span data-ttu-id="1e24c-134">MSH.5</span><span class="sxs-lookup"><span data-stu-id="1e24c-134">MSH.5</span></span>|<span data-ttu-id="1e24c-135">MSA.1</span><span class="sxs-lookup"><span data-stu-id="1e24c-135">MSA.1</span></span>|<span data-ttu-id="1e24c-136">MSA.2</span><span class="sxs-lookup"><span data-stu-id="1e24c-136">MSA.2</span></span>|  
  |-----------|-----------|-----------|-----------|-----------|  
  |<span data-ttu-id="1e24c-137">ACK^A03^ACK</span><span class="sxs-lookup"><span data-stu-id="1e24c-137">ACK^A03^ACK</span></span>|<span data-ttu-id="1e24c-138">MESA_IS</span><span class="sxs-lookup"><span data-stu-id="1e24c-138">MESA_IS</span></span>|<span data-ttu-id="1e24c-139">Tutorial_BatchSource</span><span class="sxs-lookup"><span data-stu-id="1e24c-139">Tutorial_BatchSource</span></span>|<span data-ttu-id="1e24c-140">AA</span><span class="sxs-lookup"><span data-stu-id="1e24c-140">AA</span></span>|<span data-ttu-id="1e24c-141">000001</span><span class="sxs-lookup"><span data-stu-id="1e24c-141">000001</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e24c-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e24c-142">See Also</span></span>  
 <span data-ttu-id="1e24c-143">[第 1 部分：零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="1e24c-143">[Part 1: Fragmented Inbound Batch Scenario](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md) </span></span>  
 [<span data-ttu-id="1e24c-144">第 3 部分：Create-Batch 方案</span><span class="sxs-lookup"><span data-stu-id="1e24c-144">Part 3: Create-Batch Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)