---
title: 步骤 5： 创建发送端口将消息传递 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f56ad7a7-5c77-4191-a001-691e5e0652a1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e85033256f7a49ed506fea00a7b48db67b0da1b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207597"
---
# <a name="step-5-create-a-send-port-to-deliver-messages"></a><span data-ttu-id="a1c43-102">步骤 5： 创建发送端口将消息传递</span><span class="sxs-lookup"><span data-stu-id="a1c43-102">Step 5: Create a Send Port to Deliver Messages</span></span>
<span data-ttu-id="a1c43-103">在此步骤中，你可以创建和配置用于发送单个消息中收到批处理包含端口。</span><span class="sxs-lookup"><span data-stu-id="a1c43-103">In this step, you create and configure a port for sending the individual messages contained in the received batch.</span></span> <span data-ttu-id="a1c43-104">更高版本在教程中，将在启用发起方 (Tutorial_BatchSource) 的碎片[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="a1c43-104">Later in the tutorial, you will enable fragmentation for the originating party (Tutorial_BatchSource) in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span> <span data-ttu-id="a1c43-105">因此，BizTalk 集成引擎将转换为单个消息，片段批处理和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将通过在此步骤中创建的发送端口发送这些消息。</span><span class="sxs-lookup"><span data-stu-id="a1c43-105">As a result, the BizTalk integration engine will fragment the batch into individual messages, and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will send those messages over the send port that you create in this step.</span></span>  
  
 <span data-ttu-id="a1c43-106">创建此端口是静态的以便它将仅与关联 MLLP 适配器，并且它才将发送到特定目标 （目标业务线应用程序）。</span><span class="sxs-lookup"><span data-stu-id="a1c43-106">You create this port to be static, so that it will only be associated with an MLLP adapter, and it will only send to a specific destination (the destination line-of-business application).</span></span> <span data-ttu-id="a1c43-107">在本教程中，该目标是 MESA_IS，MSH5 各条消息中。</span><span class="sxs-lookup"><span data-stu-id="a1c43-107">In this tutorial, that destination is MESA_IS, as contained in MSH5 of the individual messages.</span></span> <span data-ttu-id="a1c43-108">用于限制通过过滤掉符合 ACK_024_GLO_DEF 架构或任何静态确认 (ACK) 的消息中发送消息，不确认，对端口的筛选器创建该端口。</span><span class="sxs-lookup"><span data-stu-id="a1c43-108">You create the port with filters that restrict the port to sending messages, not acknowledgments, by filtering out messages conforming to the ACK_024_GLO_DEF schema or any static acknowledgment (ACK).</span></span>  
  
 <span data-ttu-id="a1c43-109">你将配置此发送端口为接收确认从该目标，通过将发送端口与名为接收端口相关联**TwoWayAckReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-109">You configure this send port to receive ACKs from the destination, by associating the send port with a receive port named **TwoWayAckReceivePort**.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="a1c43-110">安装程序创建此端口，并随附接收位置的**TwoWayAckReceiveLocation**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-110"> setup creates this port, and the accompanying receive location of **TwoWayAckReceiveLocation**.</span></span> <span data-ttu-id="a1c43-111">你将设置发送端口为与此端口通过设置**请求作出响应启用**到**是**和设置**提交接收位置 URI**到**127.0.0.1:65535** （接受确认所需的设置）。</span><span class="sxs-lookup"><span data-stu-id="a1c43-111">You set the send port up to work with this port by setting **Solicit Response Enable** to **Yes** and setting the **Submit Receive Location URI** to **127.0.0.1:65535** (the settings required to accept ACKs).</span></span> <span data-ttu-id="a1c43-112">有关详细信息，请参阅[设置向上发送端口的接收 Ack](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)。</span><span class="sxs-lookup"><span data-stu-id="a1c43-112">For more information, see [Setting Up a Send Port for Receiving ACKs](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md).</span></span>  
  
### <a name="to-create-a-send-port-to-deliver-messages"></a><span data-ttu-id="a1c43-113">若要创建发送端口将消息传递</span><span class="sxs-lookup"><span data-stu-id="a1c43-113">To create a send port to deliver messages</span></span>  
  
1.  <span data-ttu-id="a1c43-114">在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-114">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="a1c43-115">在“发送端口属性”对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a1c43-115">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a1c43-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a1c43-116">Use this</span></span>|<span data-ttu-id="a1c43-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a1c43-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a1c43-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="a1c43-118">**Name**</span></span>|<span data-ttu-id="a1c43-119">类型**Tutorial_2wayMsg**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-119">Type **Tutorial_2wayMsg**.</span></span>|  
    |<span data-ttu-id="a1c43-120">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="a1c43-120">**Transport type**</span></span>|<span data-ttu-id="a1c43-121">选择**MLLP**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a1c43-121">Select **MLLP** from the drop-down list.</span></span>|  
    |<span data-ttu-id="a1c43-122">**配置**</span><span class="sxs-lookup"><span data-stu-id="a1c43-122">**Configure**</span></span>|<span data-ttu-id="a1c43-123">单击**配置**以打开 MLLP 传输属性对话框。</span><span class="sxs-lookup"><span data-stu-id="a1c43-123">Click **Configure** to open the MLLP Transport Properties dialog box.</span></span>|  
  
3.  <span data-ttu-id="a1c43-124">在 MLLP 传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a1c43-124">In the MLLP Transport Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a1c43-125">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a1c43-125">Use this</span></span>|<span data-ttu-id="a1c43-126">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a1c43-126">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a1c43-127">**连接名称**</span><span class="sxs-lookup"><span data-stu-id="a1c43-127">**Connection Name**</span></span>|<span data-ttu-id="a1c43-128">类型**2wayMsg**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-128">Type **2wayMsg**.</span></span>|  
    |<span data-ttu-id="a1c43-129">**主机**</span><span class="sxs-lookup"><span data-stu-id="a1c43-129">**Host**</span></span>|<span data-ttu-id="a1c43-130">类型**localhost**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-130">Type **localhost**.</span></span>|  
    |<span data-ttu-id="a1c43-131">**端口**</span><span class="sxs-lookup"><span data-stu-id="a1c43-131">**Port**</span></span>|<span data-ttu-id="a1c43-132">类型**41000**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-132">Type **41000**.</span></span>|  
    |<span data-ttu-id="a1c43-133">**要求启用的响应**</span><span class="sxs-lookup"><span data-stu-id="a1c43-133">**Solicit Response Enabled**</span></span>|<span data-ttu-id="a1c43-134">单击右侧的字段**请求作出响应启用**，然后选择**是**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a1c43-134">Click the field to the right of **Solicit Response Enabled**, and then select **Yes** from the drop-down list.</span></span>|  
    |<span data-ttu-id="a1c43-135">**提交收到 ACK 位置 (URI)**</span><span class="sxs-lookup"><span data-stu-id="a1c43-135">**Submit Receive Location (URI) for ACK**</span></span>|<span data-ttu-id="a1c43-136">类型**127.0.0.1:65535**</span><span class="sxs-lookup"><span data-stu-id="a1c43-136">Type**127.0.0.1:65535**</span></span>|  
  
4.  <span data-ttu-id="a1c43-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-137">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="a1c43-138">在发送端口属性对话框中，为**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-138">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
6.  <span data-ttu-id="a1c43-139">在控制台树中，单击**筛选器**，然后执行以下：</span><span class="sxs-lookup"><span data-stu-id="a1c43-139">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="a1c43-140">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a1c43-140">Use this</span></span>|<span data-ttu-id="a1c43-141">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a1c43-141">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a1c43-142">**属性**（首行）</span><span class="sxs-lookup"><span data-stu-id="a1c43-142">**Property** (first line)</span></span>|<span data-ttu-id="a1c43-143">单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a1c43-143">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="a1c43-144">**运算符**</span><span class="sxs-lookup"><span data-stu-id="a1c43-144">**Operator**</span></span>|<span data-ttu-id="a1c43-145">选择 **！ =** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a1c43-145">Select **!=** from the drop-down list.</span></span>|  
    |<span data-ttu-id="a1c43-146">**值**</span><span class="sxs-lookup"><span data-stu-id="a1c43-146">**Value**</span></span>|<span data-ttu-id="a1c43-147">类型**http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-147">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="a1c43-148">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="a1c43-148">**Group By**</span></span>|<span data-ttu-id="a1c43-149">选择**AND**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a1c43-149">Select **AND** from the drop-down list.</span></span>|  
    |<span data-ttu-id="a1c43-150">**属性**（第二个行）</span><span class="sxs-lookup"><span data-stu-id="a1c43-150">**Property** (second line)</span></span>|<span data-ttu-id="a1c43-151">单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a1c43-151">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="a1c43-152">**运算符**</span><span class="sxs-lookup"><span data-stu-id="a1c43-152">**Operator**</span></span>|<span data-ttu-id="a1c43-153">选择 **！ =** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a1c43-153">Select **!=** from the drop-down list.</span></span>|  
    |<span data-ttu-id="a1c43-154">**值**</span><span class="sxs-lookup"><span data-stu-id="a1c43-154">**Value**</span></span>|<span data-ttu-id="a1c43-155">类型**http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF。**</span><span class="sxs-lookup"><span data-stu-id="a1c43-155">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.**</span></span>|  
    |<span data-ttu-id="a1c43-156">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="a1c43-156">**Group By**</span></span>|<span data-ttu-id="a1c43-157">选择**和**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a1c43-157">Select **And** from the drop-down list.</span></span>|  
    |<span data-ttu-id="a1c43-158">**属性**（第三个行）</span><span class="sxs-lookup"><span data-stu-id="a1c43-158">**Property** (third line)</span></span>|<span data-ttu-id="a1c43-159">单击下的第二个行上的字段**属性**，然后选择**BTS。MessageType**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a1c43-159">Click the field on the second line under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="a1c43-160">**运算符**</span><span class="sxs-lookup"><span data-stu-id="a1c43-160">**Operator**</span></span>|<span data-ttu-id="a1c43-161">选择 **！ =** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a1c43-161">Select **!=** from the drop-down list.</span></span>|  
    |<span data-ttu-id="a1c43-162">**值**</span><span class="sxs-lookup"><span data-stu-id="a1c43-162">**Value**</span></span>|<span data-ttu-id="a1c43-163">类型**StaticAck**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-163">Type **StaticAck**.</span></span>|  
  
7.  <span data-ttu-id="a1c43-164">单击 **“输入”**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-164">Click **Enter**.</span></span> <span data-ttu-id="a1c43-165">在对话框中底部窗格中，验证是否正确，输入筛选器表达式，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-165">In the pane at the bottom of the dialog box, verify that you entered the filter expression correctly, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="a1c43-166">在管理控制台中，单击**发送端口**，右键单击**Tutorial_2wayMsg**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="a1c43-166">In the Administration Console, click **Send Ports**, right-click **Tutorial_2wayMsg**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="a1c43-167">继续执行[步骤 6： 创建发送端口，以提供确认](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)。</span><span class="sxs-lookup"><span data-stu-id="a1c43-167">Proceed to [Step 6: Create a Send Port to Deliver Acknowledgments](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md).</span></span>