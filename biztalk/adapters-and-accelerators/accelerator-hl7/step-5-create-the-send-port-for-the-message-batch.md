---
title: "步骤 5： 为消息批创建发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5db815df-5b76-4ba4-99ab-c7766b0c301a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5749166c8a9b34d5e5a04849c4179ac4427201c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="step-5-create-the-send-port-for-the-message-batch"></a><span data-ttu-id="82931-102">步骤 5： 为消息批创建发送端口</span><span class="sxs-lookup"><span data-stu-id="82931-102">Step 5: Create the Send Port for the Message Batch</span></span>
<span data-ttu-id="82931-103">在此步骤中，创建将你创建的消息批处理传送到目标方发送端口。</span><span class="sxs-lookup"><span data-stu-id="82931-103">In this step, you create a send port to deliver the message batch that you create to the destination party.</span></span> <span data-ttu-id="82931-104">这是文件适配器类型的静态单向端口。</span><span class="sxs-lookup"><span data-stu-id="82931-104">This is a static one-way port with a FILE adapter type.</span></span> <span data-ttu-id="82931-105">其中指定用于目标 (\Tutorial_BatchMsgDrop) 的文件文件夹[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将丢弃消息批处理文件。</span><span class="sxs-lookup"><span data-stu-id="82931-105">You designate a file folder for the destination (\Tutorial_BatchMsgDrop) where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will drop the message batch file.</span></span> <span data-ttu-id="82931-106">你定义筛选器，该值指示哪种类型的消息批次将发送端口的端口。</span><span class="sxs-lookup"><span data-stu-id="82931-106">You define a filter for the port indicating what type of message batches the ports will send.</span></span> <span data-ttu-id="82931-107">筛选器指定 Tutorial_BatchDest 和 OutboundBatch 的消息类型的目标。</span><span class="sxs-lookup"><span data-stu-id="82931-107">The filter specifies the destination of Tutorial_BatchDest and the message type of OutboundBatch.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82931-108">当运行本教程的此部分，你可以通过停止使用在本教程的第 2 部分中的发送端口来简化结果： **Tutorial_BTAHL7Drop**发送端口。</span><span class="sxs-lookup"><span data-stu-id="82931-108">When running this part of the tutorial, you can simplify the results by stopping the send port used in Part 2 of the tutorial: the **Tutorial_BTAHL7Drop** send port.</span></span>  
  
### <a name="to-create-the-send-port-for-the-message-batch"></a><span data-ttu-id="82931-109">若要创建消息批发送端口</span><span class="sxs-lookup"><span data-stu-id="82931-109">To create the send port for the message batch</span></span>  
  
1.  <span data-ttu-id="82931-110">在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="82931-110">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="82931-111">在“发送端口属性”对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="82931-111">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="82931-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="82931-112">Use this</span></span>|<span data-ttu-id="82931-113">動作</span><span class="sxs-lookup"><span data-stu-id="82931-113">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="82931-114">**名称**</span><span class="sxs-lookup"><span data-stu-id="82931-114">**Name**</span></span>|<span data-ttu-id="82931-115">类型**Tutorial_BatchDest**。</span><span class="sxs-lookup"><span data-stu-id="82931-115">Type **Tutorial_BatchDest**.</span></span>|  
    |<span data-ttu-id="82931-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="82931-116">**Type**</span></span>|<span data-ttu-id="82931-117">选择**文件**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="82931-117">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="82931-118">**配置**</span><span class="sxs-lookup"><span data-stu-id="82931-118">**Configure**</span></span>|<span data-ttu-id="82931-119">单击**配置**若要打开的文件传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="82931-119">Click **Configure** to open the FILE Transport Properties dialog box.</span></span>|  
  
3.  <span data-ttu-id="82931-120">在**文件传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="82931-120">In the **FILE Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="82931-121">使用此选项</span><span class="sxs-lookup"><span data-stu-id="82931-121">Use this</span></span>|<span data-ttu-id="82931-122">执行的操作</span><span class="sxs-lookup"><span data-stu-id="82931-122">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="82931-123">**目标文件夹**</span><span class="sxs-lookup"><span data-stu-id="82931-123">**Destination folder**</span></span>|<span data-ttu-id="82931-124">浏览到 **\<*驱动器*:\>files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_BatchMsgDrop快捷键**.</span><span class="sxs-lookup"><span data-stu-id="82931-124">Browse to **\<*drive*:\>\Program Files\Microsoft  BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BatchMsgDrop**.</span></span> <span data-ttu-id="82931-125">这是文件系统或到公共共享上的位置的路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将编写包含消息批的文件。</span><span class="sxs-lookup"><span data-stu-id="82931-125">This is the path to the location on the file system or public share to which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will write the file containing the message batch.</span></span>|  
    |<span data-ttu-id="82931-126">**File name**</span><span class="sxs-lookup"><span data-stu-id="82931-126">**File name**</span></span>|<span data-ttu-id="82931-127">类型**%MessageID%.txt** （替换为.xml 扩展名.txt 扩展名）。</span><span class="sxs-lookup"><span data-stu-id="82931-127">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>|  
    |<span data-ttu-id="82931-128">**副本模式**</span><span class="sxs-lookup"><span data-stu-id="82931-128">**Copy mode**</span></span>|<span data-ttu-id="82931-129">选择**创建新**。</span><span class="sxs-lookup"><span data-stu-id="82931-129">Select **Create New**.</span></span>|  
  
4.  <span data-ttu-id="82931-130">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="82931-130">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="82931-131">在发送端口属性对话框中，为**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="82931-131">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
6.  <span data-ttu-id="82931-132">在控制台树中，单击 **筛选器**, ，然后执行以下︰</span><span class="sxs-lookup"><span data-stu-id="82931-132">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="82931-133">使用此选项</span><span class="sxs-lookup"><span data-stu-id="82931-133">Use this</span></span>|<span data-ttu-id="82931-134">動作</span><span class="sxs-lookup"><span data-stu-id="82931-134">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="82931-135">**属性**</span><span class="sxs-lookup"><span data-stu-id="82931-135">**Property**</span></span>|<span data-ttu-id="82931-136">单击下的字段**属性**，然后选择**Microsoft.Solutions.BTAHL7.BatchOrchestration.Party**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="82931-136">Click the field under **Property**, and then select **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party** from the drop-down list.</span></span>|  
    |<span data-ttu-id="82931-137">**运算符**</span><span class="sxs-lookup"><span data-stu-id="82931-137">**Operator**</span></span>|<span data-ttu-id="82931-138">保留 **==** 为运算符。</span><span class="sxs-lookup"><span data-stu-id="82931-138">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="82931-139">**Value**</span><span class="sxs-lookup"><span data-stu-id="82931-139">**Value**</span></span>|<span data-ttu-id="82931-140">类型**Tutorial_BatchDest**。</span><span class="sxs-lookup"><span data-stu-id="82931-140">Type **Tutorial_BatchDest**.</span></span>|  
    |<span data-ttu-id="82931-141">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="82931-141">**Group By**</span></span>|<span data-ttu-id="82931-142">选择**和**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="82931-142">Select **And** from the drop-down list.</span></span>|  
    |<span data-ttu-id="82931-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="82931-143">**Property**</span></span>|<span data-ttu-id="82931-144">选择**BTAHL7Schemas.BTAHL7MessageType**。</span><span class="sxs-lookup"><span data-stu-id="82931-144">Select **BTAHL7Schemas.BTAHL7MessageType**.</span></span>|  
    |<span data-ttu-id="82931-145">**运算符**</span><span class="sxs-lookup"><span data-stu-id="82931-145">**Operator**</span></span>|<span data-ttu-id="82931-146">保留 **==** 为运算符。</span><span class="sxs-lookup"><span data-stu-id="82931-146">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="82931-147">**Value**</span><span class="sxs-lookup"><span data-stu-id="82931-147">**Value**</span></span>|<span data-ttu-id="82931-148">类型**OutboundBatch**。</span><span class="sxs-lookup"><span data-stu-id="82931-148">Type **OutboundBatch**.</span></span>|  
  
7.  <span data-ttu-id="82931-149">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="82931-149">Press **Enter**.</span></span> <span data-ttu-id="82931-150">在对话框中底部窗格中，验证是否正确，输入筛选器表达式，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="82931-150">In the pane at the bottom of the dialog box, verify that you entered the filter expression correctly, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="82931-151">在 BizTalk 管理控制台中，选择**发送端口**，右键单击**Tutorial_BatchDest**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="82931-151">In the BizTalk Administration Console, select **Send Ports**, right-click **Tutorial_BatchDest**, and then click **Start**.</span></span>  
  
### <a name="to-associate-the-send-port-with-the-destination-party"></a><span data-ttu-id="82931-152">若要将发送端口与目标方相关联</span><span class="sxs-lookup"><span data-stu-id="82931-152">To associate the send port with the destination party</span></span>  
  
1.  <span data-ttu-id="82931-153">在 BizTalk Server 管理控制台中，展开**方**，单击**Tutorial_BatchDest**，然后右键单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="82931-153">In the BizTalk Server Administration Console, expand **Parties**, click **Tutorial_BatchDest**, and then right-click **Properties**.</span></span>  
  
2.  <span data-ttu-id="82931-154">在参与方属性对话框中，单击**发送端口**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="82931-154">In the Party Properties dialog box, click  **Send Ports** in the console tree.</span></span>  <span data-ttu-id="82931-155">选择**Tutorial_BatchDest**从下拉列表，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="82931-155">Select **Tutorial_BatchDest** from the drop-down list, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82931-156">如果并发冲突发生时**Tutorial_DestBatch**方已被更新，请单击**确定**并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="82931-156">If a concurrency violation occurs while the **Tutorial_DestBatch** party was being updated, click **OK** and close the dialog box.</span></span> <span data-ttu-id="82931-157">在管理控制台中，右键单击**BizTalk 组**，单击**刷新**，然后重复步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="82931-157">In the Administration Console, right-click **BizTalk Group**, click **Refresh**, and then repeat steps 1 and 2.</span></span>  
  
 <span data-ttu-id="82931-158">继续执行[步骤 6： 确认批处理为创建发送端口](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)。</span><span class="sxs-lookup"><span data-stu-id="82931-158">Proceed to [Step 6: Create the Send Port for the Acknowledgment Batch](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md).</span></span>