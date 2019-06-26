---
title: 步骤 7：创建发送端口以将 ^ A03 消息到他使用 MLLP 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: d9e7f281-3d25-4675-a13e-0e2057f5e69a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49d75da284ecbf0852d62e614cae2a787bc6dc52
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287916"
---
# <a name="step-7-create-a-send-port-to-deliver-the-adta03-message-to-his-using-the-mllp-adapter"></a><span data-ttu-id="e5af3-102">步骤 7：创建发送端口以将 ^ A03 消息到他使用 MLLP 适配器</span><span class="sxs-lookup"><span data-stu-id="e5af3-102">Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter</span></span>
<span data-ttu-id="e5af3-103">在此步骤中，你创建发送端口将消息发送到医院信息系统 (HIS) 使用 MLLP 适配器。</span><span class="sxs-lookup"><span data-stu-id="e5af3-103">In this step, you create the send port to send the message to the Hospital Information System (HIS) using the MLLP adapter.</span></span>  

### <a name="to-create-the-tutorialmllpsend-send-port"></a><span data-ttu-id="e5af3-104">若要创建 Tutorial_MllpSend 发送端口</span><span class="sxs-lookup"><span data-stu-id="e5af3-104">To create the Tutorial_MllpSend send port</span></span>  

1. <span data-ttu-id="e5af3-105">在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="e5af3-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="e5af3-106">在发送端口属性对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e5af3-106">In the Send Port Properties dialog box, do the following actions:</span></span>  


   |      <span data-ttu-id="e5af3-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e5af3-107">Use this</span></span>      |                                <span data-ttu-id="e5af3-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e5af3-108">To do this</span></span>                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      <span data-ttu-id="e5af3-109">**名称**</span><span class="sxs-lookup"><span data-stu-id="e5af3-109">**Name**</span></span>      |                        <span data-ttu-id="e5af3-110">类型**Tutorial_MllpSend**。</span><span class="sxs-lookup"><span data-stu-id="e5af3-110">Type **Tutorial_MllpSend**.</span></span>                        |
   | <span data-ttu-id="e5af3-111">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="e5af3-111">**Transport type**</span></span> |                 <span data-ttu-id="e5af3-112">选择**MLLP**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e5af3-112">Select **MLLP** from the drop-down list.</span></span>                  |
   |   <span data-ttu-id="e5af3-113">**配置**</span><span class="sxs-lookup"><span data-stu-id="e5af3-113">**Configure**</span></span>    | <span data-ttu-id="e5af3-114">单击**配置**以打开**MLLP 传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e5af3-114">Click **Configure** to open the **MLLP Transport Properties** dialog box.</span></span> |


3. <span data-ttu-id="e5af3-115">在处的 MLLP 传输属性对话框中，执行以下操作，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e5af3-115">In the MLLP Transport Properties dialog box, do the following actions and then click **OK**.</span></span>  


   |      <span data-ttu-id="e5af3-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e5af3-116">Use this</span></span>       |     <span data-ttu-id="e5af3-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e5af3-117">To do this</span></span>      |
   |---------------------|---------------------|
   | <span data-ttu-id="e5af3-118">**连接名称**</span><span class="sxs-lookup"><span data-stu-id="e5af3-118">**Connection Name**</span></span> | <span data-ttu-id="e5af3-119">类型**1WaySend**。</span><span class="sxs-lookup"><span data-stu-id="e5af3-119">Type **1WaySend**.</span></span>  |
   |      <span data-ttu-id="e5af3-120">**主机**</span><span class="sxs-lookup"><span data-stu-id="e5af3-120">**Host**</span></span>       | <span data-ttu-id="e5af3-121">类型**localhost**。</span><span class="sxs-lookup"><span data-stu-id="e5af3-121">Type **localhost**.</span></span> |
   |      <span data-ttu-id="e5af3-122">**端口**</span><span class="sxs-lookup"><span data-stu-id="e5af3-122">**Port**</span></span>       |   <span data-ttu-id="e5af3-123">类型**14000**。</span><span class="sxs-lookup"><span data-stu-id="e5af3-123">Type **14000**.</span></span>   |


4. <span data-ttu-id="e5af3-124">在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="e5af3-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

5. <span data-ttu-id="e5af3-125">在左窗格中，选择**筛选器**，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e5af3-125">In the left pane, select **Filters**, and then do the following:</span></span>  

   |<span data-ttu-id="e5af3-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e5af3-126">Use this</span></span>|<span data-ttu-id="e5af3-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e5af3-127">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="e5af3-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="e5af3-128">**Property**</span></span>|<span data-ttu-id="e5af3-129">选择**BTS。ReceivePortName**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e5af3-129">Select **BTS.ReceivePortName** from the drop-down list.</span></span>|  
   |<span data-ttu-id="e5af3-130">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="e5af3-130">**Operator**</span></span>|<span data-ttu-id="e5af3-131">选择 **==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e5af3-131">Select **==** from the drop-down list.</span></span>|  
   |<span data-ttu-id="e5af3-132">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="e5af3-132">**Value**</span></span>|<span data-ttu-id="e5af3-133">类型**Tutorial_1WayReceive**。</span><span class="sxs-lookup"><span data-stu-id="e5af3-133">Type **Tutorial_1WayReceive**.</span></span>|  

   > [!NOTE]
   >  <span data-ttu-id="e5af3-134">该端口将侦听 1WayReceive 的任何消息中指定的端口。</span><span class="sxs-lookup"><span data-stu-id="e5af3-134">The port will listen to the port specified in 1WayReceive for any messages.</span></span>  

6. <span data-ttu-id="e5af3-135">单击**Apply**，然后单击**确定。**</span><span class="sxs-lookup"><span data-stu-id="e5af3-135">Click **Apply**, and then click **OK.**</span></span>  

7. <span data-ttu-id="e5af3-136">在管理控制台中，单击**发送端口**，右键单击**Tutorial_MllpSend**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="e5af3-136">In the Administration Console, click **Send Ports**, right-click **Tutorial_MllpSend**, and then click **Start**.</span></span>  

   <span data-ttu-id="e5af3-137">请继续执行[步骤 8:配置参与方信息](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)。</span><span class="sxs-lookup"><span data-stu-id="e5af3-137">Proceed to [Step 8: Configure Party Information](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md).</span></span>