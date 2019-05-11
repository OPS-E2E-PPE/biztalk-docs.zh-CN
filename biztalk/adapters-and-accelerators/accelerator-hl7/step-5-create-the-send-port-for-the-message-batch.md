---
title: 步骤 5：为消息批处理创建发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5db815df-5b76-4ba4-99ab-c7766b0c301a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4d69f21413e084ae81eda69827c079b39379bca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287968"
---
# <a name="step-5-create-the-send-port-for-the-message-batch"></a><span data-ttu-id="9dd9e-102">步骤 5：为消息批处理创建发送端口</span><span class="sxs-lookup"><span data-stu-id="9dd9e-102">Step 5: Create the Send Port for the Message Batch</span></span>
<span data-ttu-id="9dd9e-103">在此步骤中，您创建用于将您创建的消息批传送到目标参与方的发送端口。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-103">In this step, you create a send port to deliver the message batch that you create to the destination party.</span></span> <span data-ttu-id="9dd9e-104">这是一个静态单向端口与文件适配器类型。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-104">This is a static one-way port with a FILE adapter type.</span></span> <span data-ttu-id="9dd9e-105">指定用于目标 (\Tutorial_BatchMsgDrop) 的文件文件夹位置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]会丢弃消息批处理文件。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-105">You designate a file folder for the destination (\Tutorial_BatchMsgDrop) where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will drop the message batch file.</span></span> <span data-ttu-id="9dd9e-106">定义用于指示哪种类型的消息批将发送端口的端口的筛选器。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-106">You define a filter for the port indicating what type of message batches the ports will send.</span></span> <span data-ttu-id="9dd9e-107">筛选器指定的 Tutorial_BatchDest 和 OutboundBatch 的消息类型的目标。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-107">The filter specifies the destination of Tutorial_BatchDest and the message type of OutboundBatch.</span></span>  

> [!NOTE]
>  <span data-ttu-id="9dd9e-108">当运行本教程的此部分，可以通过停止使用本教程的第 2 部分中的发送端口来简化结果： **Tutorial_BTAHL7Drop**发送端口。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-108">When running this part of the tutorial, you can simplify the results by stopping the send port used in Part 2 of the tutorial: the **Tutorial_BTAHL7Drop** send port.</span></span>  

### <a name="to-create-the-send-port-for-the-message-batch"></a><span data-ttu-id="9dd9e-109">若要创建消息批的发送端口</span><span class="sxs-lookup"><span data-stu-id="9dd9e-109">To create the send port for the message batch</span></span>  

1. <span data-ttu-id="9dd9e-110">在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-110">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="9dd9e-111">在发送端口属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9dd9e-111">In the Send Port Properties dialog box, do the following:</span></span>  


   |   <span data-ttu-id="9dd9e-112">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9dd9e-112">Use this</span></span>    |                              <span data-ttu-id="9dd9e-113">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9dd9e-113">To do this</span></span>                               |
   |---------------|-----------------------------------------------------------------------|
   |   <span data-ttu-id="9dd9e-114">**名称**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-114">**Name**</span></span>    |                     <span data-ttu-id="9dd9e-115">类型**Tutorial_BatchDest**。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-115">Type **Tutorial_BatchDest**.</span></span>                      |
   |   <span data-ttu-id="9dd9e-116">**类型**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-116">**Type**</span></span>    |               <span data-ttu-id="9dd9e-117">选择**文件**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-117">Select **FILE** from the drop-down list.</span></span>                |
   | <span data-ttu-id="9dd9e-118">**配置**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-118">**Configure**</span></span> | <span data-ttu-id="9dd9e-119">单击**配置**打开 FILE 传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-119">Click **Configure** to open the FILE Transport Properties dialog box.</span></span> |


3. <span data-ttu-id="9dd9e-120">在中**FILE 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9dd9e-120">In the **FILE Transport Properties** dialog box, do the following:</span></span>  


   |        <span data-ttu-id="9dd9e-121">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9dd9e-121">Use this</span></span>        |                                                                                                                                                                           <span data-ttu-id="9dd9e-122">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9dd9e-122">To do this</span></span>                                                                                                                                                                            |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="9dd9e-123">**目标文件夹**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-123">**Destination folder**</span></span> | <span data-ttu-id="9dd9e-124">浏览到 **\<*驱动器*:\>\Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_BatchMsgDrop的快捷键**.</span><span class="sxs-lookup"><span data-stu-id="9dd9e-124">Browse to **\<*drive*:\>\Program Files\Microsoft  BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BatchMsgDrop**.</span></span> <span data-ttu-id="9dd9e-125">这是到公共共享的文件系统上的位置的路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将编写包含消息批的文件。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-125">This is the path to the location on the file system or public share to which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will write the file containing the message batch.</span></span> |
   |     <span data-ttu-id="9dd9e-126">**文件名**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-126">**File name**</span></span>      |                                                                                                                                         <span data-ttu-id="9dd9e-127">类型 **%MessageID%.txt** （替换带.txt 扩展名的.xml 扩展名）。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-127">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>                                                                                                                                          |
   |     <span data-ttu-id="9dd9e-128">**副本模式**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-128">**Copy mode**</span></span>      |                                                                                                                                                                     <span data-ttu-id="9dd9e-129">选择**创建新的**。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-129">Select **Create New**.</span></span>                                                                                                                                                                      |


4. <span data-ttu-id="9dd9e-130">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-130">Click **OK**.</span></span>  

5. <span data-ttu-id="9dd9e-131">在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-131">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

6. <span data-ttu-id="9dd9e-132">在控制台树中，单击**筛选器**，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9dd9e-132">In the console tree, click **Filters**, and then do the following:</span></span>  


   |   <span data-ttu-id="9dd9e-133">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9dd9e-133">Use this</span></span>   |                                                              <span data-ttu-id="9dd9e-134">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9dd9e-134">To do this</span></span>                                                              |
   |--------------|--------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="9dd9e-135">**属性**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-135">**Property**</span></span> | <span data-ttu-id="9dd9e-136">单击下的字段**属性**，然后选择**Microsoft.Solutions.BTAHL7.BatchOrchestration.Party**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-136">Click the field under **Property**, and then select **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party** from the drop-down list.</span></span> |
   | <span data-ttu-id="9dd9e-137">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-137">**Operator**</span></span> |                                                    <span data-ttu-id="9dd9e-138">将保留**==** 与运算符。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-138">Leave **==** as the operator.</span></span>                                                     |
   |  <span data-ttu-id="9dd9e-139">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-139">**Value**</span></span>   |                                                     <span data-ttu-id="9dd9e-140">类型**Tutorial_BatchDest**。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-140">Type **Tutorial_BatchDest**.</span></span>                                                     |
   | <span data-ttu-id="9dd9e-141">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-141">**Group By**</span></span> |                                               <span data-ttu-id="9dd9e-142">选择**和**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-142">Select **And** from the drop-down list.</span></span>                                                |
   | <span data-ttu-id="9dd9e-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-143">**Property**</span></span> |                                             <span data-ttu-id="9dd9e-144">选择**BTAHL7Schemas.BTAHL7MessageType**。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-144">Select **BTAHL7Schemas.BTAHL7MessageType**.</span></span>                                              |
   | <span data-ttu-id="9dd9e-145">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-145">**Operator**</span></span> |                                                    <span data-ttu-id="9dd9e-146">将保留**==** 与运算符。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-146">Leave **==** as the operator.</span></span>                                                     |
   |  <span data-ttu-id="9dd9e-147">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="9dd9e-147">**Value**</span></span>   |                                                       <span data-ttu-id="9dd9e-148">类型**OutboundBatch**。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-148">Type **OutboundBatch**.</span></span>                                                        |


7. <span data-ttu-id="9dd9e-149">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-149">Press **Enter**.</span></span> <span data-ttu-id="9dd9e-150">在对话框中底部窗格中，验证是否正确，输入筛选器表达式，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-150">In the pane at the bottom of the dialog box, verify that you entered the filter expression correctly, and then click **OK**.</span></span>  

8. <span data-ttu-id="9dd9e-151">在 BizTalk 管理控制台中，选择**发送端口**，右键单击**Tutorial_BatchDest**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-151">In the BizTalk Administration Console, select **Send Ports**, right-click **Tutorial_BatchDest**, and then click **Start**.</span></span>  

### <a name="to-associate-the-send-port-with-the-destination-party"></a><span data-ttu-id="9dd9e-152">若要使用的目标参与方关联的发送端口</span><span class="sxs-lookup"><span data-stu-id="9dd9e-152">To associate the send port with the destination party</span></span>  

1. <span data-ttu-id="9dd9e-153">在 BizTalk Server 管理控制台中，展开**参与方**，单击**Tutorial_BatchDest**，然后右键单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-153">In the BizTalk Server Administration Console, expand **Parties**, click **Tutorial_BatchDest**, and then right-click **Properties**.</span></span>  

2. <span data-ttu-id="9dd9e-154">在参与方属性对话框中，单击**发送端口**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-154">In the Party Properties dialog box, click  **Send Ports** in the console tree.</span></span>  <span data-ttu-id="9dd9e-155">选择**Tutorial_BatchDest**从下拉列表中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-155">Select **Tutorial_BatchDest** from the drop-down list, and then click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="9dd9e-156">如果并发冲突发生时**Tutorial_DestBatch**更新参与方，单击**确定**并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-156">If a concurrency violation occurs while the **Tutorial_DestBatch** party was being updated, click **OK** and close the dialog box.</span></span> <span data-ttu-id="9dd9e-157">在管理控制台中，右键单击**BizTalk 组**，单击**刷新**，然后重复步骤 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-157">In the Administration Console, right-click **BizTalk Group**, click **Refresh**, and then repeat steps 1 and 2.</span></span>  

   <span data-ttu-id="9dd9e-158">请继续执行[步骤 6:为确认批处理创建发送端口](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)。</span><span class="sxs-lookup"><span data-stu-id="9dd9e-158">Proceed to [Step 6: Create the Send Port for the Acknowledgment Batch](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md).</span></span>