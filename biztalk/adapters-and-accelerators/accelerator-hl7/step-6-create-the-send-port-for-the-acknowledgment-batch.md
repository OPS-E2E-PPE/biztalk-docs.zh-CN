---
title: "步骤 6： 为确认批处理创建发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2a0f1ee-e060-4fb9-923e-ebe8168777d9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 958746634776e9b01c32ff2425122312bc7a841c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="step-6-create-the-send-port-for-the-acknowledgment-batch"></a><span data-ttu-id="6e6d7-102">步骤 6： 为确认批处理创建发送端口</span><span class="sxs-lookup"><span data-stu-id="6e6d7-102">Step 6: Create the Send Port for the Acknowledgment Batch</span></span>
<span data-ttu-id="6e6d7-103">在此步骤中，你可以创建将你创建的确认批处理传送到源方发送端口。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-103">In this step, you create a send port to deliver the acknowledgment batch that you create to the source party.</span></span> <span data-ttu-id="6e6d7-104">这是文件适配器类型的静态单向端口。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-104">This is a static one-way port with a FILE adapter type.</span></span> <span data-ttu-id="6e6d7-105">其中指定的源 (\Tutorial_BatchACKDrop) 的文件文件夹[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将删除确认批处理文件。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-105">You designate a file folder for the source (\Tutorial_BatchACKDrop), where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will drop the acknowledgment batch file.</span></span> <span data-ttu-id="6e6d7-106">你定义筛选器，该值指示端口将发送的确认批处理哪种类型的端口。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-106">You define a filter for the port indicating what type of acknowledgment batches the ports will send.</span></span> <span data-ttu-id="6e6d7-107">筛选器指定 Tutorial_BatchSource 和 OutboundBatch 的消息类型的源。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-107">The filter specifies the source of Tutorial_BatchSource and the message type of OutboundBatch.</span></span>  
  
### <a name="to-create-the-send-port-for-the-acknowledgment-batch"></a><span data-ttu-id="6e6d7-108">若要创建确认批处理发送端口</span><span class="sxs-lookup"><span data-stu-id="6e6d7-108">To create the send port for the acknowledgment batch</span></span>  
  
1.  <span data-ttu-id="6e6d7-109">在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-109">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="6e6d7-110">在“发送端口属性”对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6e6d7-110">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="6e6d7-111">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6e6d7-111">Use this</span></span>|<span data-ttu-id="6e6d7-112">動作</span><span class="sxs-lookup"><span data-stu-id="6e6d7-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6e6d7-113">**名称**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-113">**Name**</span></span>|<span data-ttu-id="6e6d7-114">类型**Tutorial_BatchSource**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-114">Type **Tutorial_BatchSource**.</span></span>|  
    |<span data-ttu-id="6e6d7-115">**类型**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-115">**Type**</span></span>|<span data-ttu-id="6e6d7-116">选择**文件**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-116">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="6e6d7-117">**配置**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-117">**Configure**</span></span>|<span data-ttu-id="6e6d7-118">单击**配置**若要打开的文件传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-118">Click **Configure** to open the FILE Transport Properties dialog box.</span></span>|  
  
3.  <span data-ttu-id="6e6d7-119">在文件传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6e6d7-119">In the FILE Transport Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="6e6d7-120">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6e6d7-120">Use this</span></span>|<span data-ttu-id="6e6d7-121">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6e6d7-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6e6d7-122">**目标文件夹**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-122">**Destination folder**</span></span>|<span data-ttu-id="6e6d7-123">浏览到 **\<*驱动器*:\>files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_BatchACKDrop快捷键**.</span><span class="sxs-lookup"><span data-stu-id="6e6d7-123">Browse to **\<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BatchACKDrop**.</span></span> <span data-ttu-id="6e6d7-124">这是文件系统或到公共共享上的位置的路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将编写包含确认批处理的文件。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-124">This is the path to the location on the file system or public share to which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will write the file containing the acknowledgment batch.</span></span>|  
    |<span data-ttu-id="6e6d7-125">**File name**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-125">**File name**</span></span>|<span data-ttu-id="6e6d7-126">类型**%MessageID%.txt** （替换为.xml 扩展名.txt 扩展名）。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-126">Type **%MessageID%.txt** (replace the .xml extension with the .txt extension).</span></span>|  
    |<span data-ttu-id="6e6d7-127">**副本模式**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-127">**Copy mode**</span></span>|<span data-ttu-id="6e6d7-128">选择**创建新**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-128">Select **Create New**.</span></span>|  
  
4.  <span data-ttu-id="6e6d7-129">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-129">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="6e6d7-130">在发送端口属性对话框中，为**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-130">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
6.  <span data-ttu-id="6e6d7-131">在控制台树中，单击 **筛选器**, ，然后执行以下︰</span><span class="sxs-lookup"><span data-stu-id="6e6d7-131">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="6e6d7-132">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6e6d7-132">Use this</span></span>|<span data-ttu-id="6e6d7-133">動作</span><span class="sxs-lookup"><span data-stu-id="6e6d7-133">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6e6d7-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-134">**Property**</span></span>|<span data-ttu-id="6e6d7-135">单击下的字段**属性**，然后选择**Microsoft.Solutions.BTAHL7.BatchOrchestration.Party**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-135">Click the field under **Property**, and then select **Microsoft.Solutions.BTAHL7.BatchOrchestration.Party** from the drop-down list.</span></span>|  
    |<span data-ttu-id="6e6d7-136">**运算符**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-136">**Operator**</span></span>|<span data-ttu-id="6e6d7-137">保留 **==** 为运算符。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-137">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="6e6d7-138">**Value**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-138">**Value**</span></span>|<span data-ttu-id="6e6d7-139">类型**Tutorial_BatchSource**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-139">Type **Tutorial_BatchSource**.</span></span>|  
    |<span data-ttu-id="6e6d7-140">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-140">**Group By**</span></span>|<span data-ttu-id="6e6d7-141">选择**和**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-141">Select **And** from the drop-down list.</span></span>|  
    |<span data-ttu-id="6e6d7-142">**属性**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-142">**Property**</span></span>|<span data-ttu-id="6e6d7-143">选择**BTAHL7Schemas.BTAHL7MessageType**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-143">Select **BTAHL7Schemas.BTAHL7MessageType**.</span></span>|  
    |<span data-ttu-id="6e6d7-144">**运算符**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-144">**Operator**</span></span>|<span data-ttu-id="6e6d7-145">保留 **==** 为运算符。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-145">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="6e6d7-146">**Value**</span><span class="sxs-lookup"><span data-stu-id="6e6d7-146">**Value**</span></span>|<span data-ttu-id="6e6d7-147">类型**OutboundBatch**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-147">Type **OutboundBatch**.</span></span>|  
  
7.  <span data-ttu-id="6e6d7-148">按 **Enter**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-148">Press **Enter**.</span></span> <span data-ttu-id="6e6d7-149">在对话框中底部窗格中，验证是否正确，输入筛选器表达式，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-149">In the pane at the bottom of the dialog box, verify that you entered the filter expression correctly, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="6e6d7-150">在 BizTalk 管理控制台中，选择**发送端口**，右键单击**Tutorial_BatchSource**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-150">In the BizTalk Administration Console, select **Send Ports**, right-click **Tutorial_BatchSource**, and then click **Start**.</span></span>  
  
### <a name="to-associate-the-send-port-with-the-source-party"></a><span data-ttu-id="6e6d7-151">若要将发送端口与源方相关联</span><span class="sxs-lookup"><span data-stu-id="6e6d7-151">To associate the send port with the source party</span></span>  
  
1.  <span data-ttu-id="6e6d7-152">在 BizTalk 管理控制台中，单击**方**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-152">In the BizTalk Administration Console, click **Parties**.</span></span> <span data-ttu-id="6e6d7-153">右键单击**Tutorial_BatchSource**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-153">Right-click **Tutorial_BatchSource**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6e6d7-154">在参与方属性对话框中，单击**发送端口**在控制台树中。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-154">In the Party Properties dialog box, click **Send Ports** in the console tree.</span></span> <span data-ttu-id="6e6d7-155">有关**发送端口**，选择**Tutorial_BatchSource**从下拉列表，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-155">For **Send Ports**, select **Tutorial_BatchSource** from the drop-down list, and then click **OK**.</span></span>  
  
 <span data-ttu-id="6e6d7-156">继续执行[第 7 步： 启动业务流程和重新启动 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="6e6d7-156">Proceed to [Step 7: Start the Orchestration and Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md).</span></span>