---
title: 步骤 6： 创建发送端口，以提供确认 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 739b3e60-db56-46e9-a6b1-0acbe0c08f55
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 978ccb9bf01fe71c3ccce7315e0286ee862bb7ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207997"
---
# <a name="step-6-create-a-send-port-to-deliver-acknowledgments"></a><span data-ttu-id="d5886-102">步骤 6： 创建发送端口，以提供确认</span><span class="sxs-lookup"><span data-stu-id="d5886-102">Step 6: Create a Send Port to Deliver Acknowledgments</span></span>
<span data-ttu-id="d5886-103">在此步骤中，你可以创建要发送确认回批处理的源的端口。</span><span class="sxs-lookup"><span data-stu-id="d5886-103">In this step, you create a port to send acknowledgments back to the source of the batch.</span></span>  
  
 <span data-ttu-id="d5886-104">创建此端口是静态的以便它将仅与关联 MLLP 适配器，并且它才将发送到特定目标 （批处理的源）。</span><span class="sxs-lookup"><span data-stu-id="d5886-104">You create this port to be static, so that it will only be associated with an MLLP adapter, and it will only send to a specific destination (the source of the batch).</span></span> <span data-ttu-id="d5886-105">在本教程中，源是与方 Tutorial_BatchSource 相关联。</span><span class="sxs-lookup"><span data-stu-id="d5886-105">In this tutorial, the source is associated with the party Tutorial_BatchSource.</span></span> <span data-ttu-id="d5886-106">此源方包含在单个消息和 FHS3 MSH3 和 BHS3 原始的批处理。</span><span class="sxs-lookup"><span data-stu-id="d5886-106">This source party is contained in MSH3 of the individual messages and FHS3 and BHS3 of the original batch.</span></span>  
  
 <span data-ttu-id="d5886-107">用于将端口限制到发送确认，不数据消息的筛选器创建该端口。</span><span class="sxs-lookup"><span data-stu-id="d5886-107">You create the port with filters that restrict the port to sending acknowledgments, not data messages.</span></span> <span data-ttu-id="d5886-108">这些筛选器指定一种 ACK_024_GLO_DEF 和 Tutorial_BatchSource 目标之间的消息。</span><span class="sxs-lookup"><span data-stu-id="d5886-108">These filters specify a message type of ACK_024_GLO_DEF and a destination of Tutorial_BatchSource.</span></span>  
  
 <span data-ttu-id="d5886-109">你将配置此发送端口为接收确认从该目标，通过将发送端口与名为接收端口相关联**TwoWayAckReceivePort**。</span><span class="sxs-lookup"><span data-stu-id="d5886-109">You configure this send port to receive acknowledgments from the destination, by associating the send port with a receive port named **TwoWayAckReceivePort**.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="d5886-110">安装程序创建此端口，并随附接收位置的**TwoWayAckReceiveLocation**。</span><span class="sxs-lookup"><span data-stu-id="d5886-110"> setup creates this port, and the accompanying receive location of **TwoWayAckReceiveLocation**.</span></span> <span data-ttu-id="d5886-111">你将设置发送端口为与此端口通过设置**请求作出响应启用**到**否**和设置**提交接收位置 URI**到**127.0.0.1:65535** （接受确认所需的设置）。</span><span class="sxs-lookup"><span data-stu-id="d5886-111">You set the send port up to work with this port by setting **Solicit Response Enable** to **No** and setting the **Submit Receive Location URI** to **127.0.0.1:65535** (the settings required to accept ACKs).</span></span> <span data-ttu-id="d5886-112">有关详细信息，请参阅[设置向上发送端口的接收 Ack](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)。</span><span class="sxs-lookup"><span data-stu-id="d5886-112">For more information, see [Setting Up a Send Port for Receiving ACKs](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md).</span></span>  
  
### <a name="to-create-a-send-port-to-deliver-acknowledgments"></a><span data-ttu-id="d5886-113">若要创建发送端口，以提供确认</span><span class="sxs-lookup"><span data-stu-id="d5886-113">To create a send port to deliver acknowledgments</span></span>  
  
1.  <span data-ttu-id="d5886-114">在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d5886-114">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="d5886-115">在“发送端口属性”对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d5886-115">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="d5886-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d5886-116">Use this</span></span>|<span data-ttu-id="d5886-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d5886-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d5886-118">**名称**</span><span class="sxs-lookup"><span data-stu-id="d5886-118">**Name**</span></span>|<span data-ttu-id="d5886-119">类型**Tutorial_2wayAck**。</span><span class="sxs-lookup"><span data-stu-id="d5886-119">Type **Tutorial_2wayAck**.</span></span>|  
    |<span data-ttu-id="d5886-120">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="d5886-120">**Transport type**</span></span>|<span data-ttu-id="d5886-121">选择**MLLP**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d5886-121">Select **MLLP** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d5886-122">**配置**</span><span class="sxs-lookup"><span data-stu-id="d5886-122">**Configure**</span></span>|<span data-ttu-id="d5886-123">单击**配置**以打开**MLLP 传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="d5886-123">Click **Configure** to open the **MLLP Transport Properties** dialog box.</span></span>|  
  
3.  <span data-ttu-id="d5886-124">在 MLLP 传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d5886-124">In the MLLP Transport Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="d5886-125">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d5886-125">Use this</span></span>|<span data-ttu-id="d5886-126">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d5886-126">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d5886-127">**连接名称**</span><span class="sxs-lookup"><span data-stu-id="d5886-127">**Connection Name**</span></span>|<span data-ttu-id="d5886-128">类型**2wayAck**。</span><span class="sxs-lookup"><span data-stu-id="d5886-128">Type **2wayAck**.</span></span>|  
    |<span data-ttu-id="d5886-129">**主机**</span><span class="sxs-lookup"><span data-stu-id="d5886-129">**Host**</span></span>|<span data-ttu-id="d5886-130">类型**localhost**。</span><span class="sxs-lookup"><span data-stu-id="d5886-130">Type **localhost**.</span></span>|  
    |<span data-ttu-id="d5886-131">**端口**</span><span class="sxs-lookup"><span data-stu-id="d5886-131">**Port**</span></span>|<span data-ttu-id="d5886-132">类型**41002**。</span><span class="sxs-lookup"><span data-stu-id="d5886-132">Type **41002**.</span></span>|  
    |<span data-ttu-id="d5886-133">**要求启用的响应**</span><span class="sxs-lookup"><span data-stu-id="d5886-133">**Solicit Response Enabled**</span></span>|<span data-ttu-id="d5886-134">保留该字段作为**否**。</span><span class="sxs-lookup"><span data-stu-id="d5886-134">Keep the field as **No**.</span></span>|  
    |<span data-ttu-id="d5886-135">**提交收到 ACK 位置 (URI)**</span><span class="sxs-lookup"><span data-stu-id="d5886-135">**Submit Receive Location (URI) for ACK**</span></span>|<span data-ttu-id="d5886-136">类型**127.0.0.1:65535**</span><span class="sxs-lookup"><span data-stu-id="d5886-136">Type **127.0.0.1:65535**</span></span>|  
  
4.  <span data-ttu-id="d5886-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d5886-137">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="d5886-138">在发送端口属性对话框中，为**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="d5886-138">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
6.  <span data-ttu-id="d5886-139">在控制台树中，单击**筛选器**，然后执行以下：</span><span class="sxs-lookup"><span data-stu-id="d5886-139">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5886-140">确保将以下数据输入严格按照所示。</span><span class="sxs-lookup"><span data-stu-id="d5886-140">Ensure that you enter the following data exactly as shown.</span></span> <span data-ttu-id="d5886-141">此数据是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d5886-141">This data is case-sensitive.</span></span>  
  
    |<span data-ttu-id="d5886-142">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d5886-142">Use this</span></span>|<span data-ttu-id="d5886-143">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d5886-143">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d5886-144">**属性**（首行）</span><span class="sxs-lookup"><span data-stu-id="d5886-144">**Property** (first line)</span></span>|<span data-ttu-id="d5886-145">单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d5886-145">Click the field under **Property**, then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d5886-146">**运算符**</span><span class="sxs-lookup"><span data-stu-id="d5886-146">**Operator**</span></span>|<span data-ttu-id="d5886-147">选择 **==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d5886-147">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d5886-148">**值**</span><span class="sxs-lookup"><span data-stu-id="d5886-148">**Value**</span></span>|<span data-ttu-id="d5886-149">类型**http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**。</span><span class="sxs-lookup"><span data-stu-id="d5886-149">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="d5886-150">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="d5886-150">**Group By**</span></span>|<span data-ttu-id="d5886-151">选择**或**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d5886-151">Select **OR** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d5886-152">**属性**（第二个行）</span><span class="sxs-lookup"><span data-stu-id="d5886-152">**Property** (second line)</span></span>|<span data-ttu-id="d5886-153">单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d5886-153">Click the field under **Property**, and then select **BTS.MessageType** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d5886-154">**运算符**</span><span class="sxs-lookup"><span data-stu-id="d5886-154">**Operator**</span></span>|<span data-ttu-id="d5886-155">选择 **==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d5886-155">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d5886-156">**值**</span><span class="sxs-lookup"><span data-stu-id="d5886-156">**Value**</span></span>|<span data-ttu-id="d5886-157">类型**http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF。**</span><span class="sxs-lookup"><span data-stu-id="d5886-157">Type **http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF.**</span></span>|  
    |<span data-ttu-id="d5886-158">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="d5886-158">**Group By**</span></span>|<span data-ttu-id="d5886-159">选择**和**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d5886-159">Select **And** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d5886-160">**属性**（第三个行）</span><span class="sxs-lookup"><span data-stu-id="d5886-160">**Property** (third line)</span></span>|<span data-ttu-id="d5886-161">单击下的第二个行上的字段**属性**，然后选择**BTAHL7Schemas.MSH5_1**。</span><span class="sxs-lookup"><span data-stu-id="d5886-161">Click the field on the second line under **Property**, then select **BTAHL7Schemas.MSH5_1**.</span></span>|  
    |<span data-ttu-id="d5886-162">**运算符**</span><span class="sxs-lookup"><span data-stu-id="d5886-162">**Operator**</span></span>|<span data-ttu-id="d5886-163">选择 **==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="d5886-163">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="d5886-164">**值**</span><span class="sxs-lookup"><span data-stu-id="d5886-164">**Value**</span></span>|<span data-ttu-id="d5886-165">类型**Tutorial_BatchSource**。</span><span class="sxs-lookup"><span data-stu-id="d5886-165">Type **Tutorial_BatchSource**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="d5886-166">第一个筛选器意味着您的订阅的确认消息。</span><span class="sxs-lookup"><span data-stu-id="d5886-166">The first filter means that you are subscribing to the acknowledgment message.</span></span> <span data-ttu-id="d5886-167">第二个筛选器表示你希望具有目标为发布服务器上，确认**Tutorial_BatchSource**。</span><span class="sxs-lookup"><span data-stu-id="d5886-167">The second filter means that you want the acknowledgment that has the destination of the publisher, **Tutorial_BatchSource**.</span></span>  
  
7.  <span data-ttu-id="d5886-168">单击 **“输入”**。</span><span class="sxs-lookup"><span data-stu-id="d5886-168">Click **Enter**.</span></span> <span data-ttu-id="d5886-169">在对话框中底部窗格中，验证是否正确，输入筛选器表达式，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d5886-169">In the pane at the bottom of the dialog box, verify that you entered the filter expression correctly, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="d5886-170">在管理控制台中，单击**发送端口**，右键单击**Tutorial_2wayAck**，然后选择**启动**。</span><span class="sxs-lookup"><span data-stu-id="d5886-170">In the Administration Console, click **Send Ports**, right-click **Tutorial_2wayAck**, and then select **Start**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d5886-171">为 Tutorial_2wayAck 发送端口才能正常工作，必须启用 TwoWayAckReceivePort 接收位置。</span><span class="sxs-lookup"><span data-stu-id="d5886-171">For the Tutorial_2wayAck send port to function properly, you must enable the TwoWayAckReceivePort receive location.</span></span>  
  
9. <span data-ttu-id="d5886-172">单击**接收位置**。</span><span class="sxs-lookup"><span data-stu-id="d5886-172">Click **Receive Locations**.</span></span> <span data-ttu-id="d5886-173">验证已启用 TwoWayAckReceiveLocation 的状态。</span><span class="sxs-lookup"><span data-stu-id="d5886-173">Verify that the status for the TwoWayAckReceiveLocation is enabled.</span></span> <span data-ttu-id="d5886-174">如果没有，请右键单击**TwoWayAckReceiveLocation**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="d5886-174">If not, right-click **TwoWayAckReceiveLocation**, and then click **Enable**.</span></span>  
  
 <span data-ttu-id="d5886-175">继续执行[步骤 7： 创建和配置源方](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)。</span><span class="sxs-lookup"><span data-stu-id="d5886-175">Proceed to [Step 7: Create and Configure a Source Party](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md).</span></span>