---
title: 步骤 6： 创建用于传递查询消息的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: a3cfa2aa-888d-4a82-9eb3-2e9cc29ee582
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24e65ec7bc4e04850907609fc6d1d63e6f166593
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004046"
---
# <a name="step-6-create-a-send-port-to-deliver-query-messages"></a><span data-ttu-id="4f65e-102">步骤 6： 创建用于传递查询消息的发送端口</span><span class="sxs-lookup"><span data-stu-id="4f65e-102">Step 6: Create a Send Port to Deliver Query Messages</span></span>
<span data-ttu-id="4f65e-103">在此步骤中，创建发送端口以将传入的查询 (QRY ^ Q01 消息) 到医院信息系统 (HIS)。</span><span class="sxs-lookup"><span data-stu-id="4f65e-103">In this step, you create the send port to deliver the incoming queries (QRY^Q01 messages) to the Hospital Information System (HIS).</span></span>  

### <a name="to-create-the-hissend-send-port"></a><span data-ttu-id="4f65e-104">若要创建 HIS_Send 发送端口</span><span class="sxs-lookup"><span data-stu-id="4f65e-104">To create the HIS_Send send port</span></span>  

1. <span data-ttu-id="4f65e-105">在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后选择**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then select **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="4f65e-106">在“发送端口属性”对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4f65e-106">In the Send Port Properties dialog box, do the following:</span></span>  


   |      <span data-ttu-id="4f65e-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4f65e-107">Use this</span></span>      |                        <span data-ttu-id="4f65e-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4f65e-108">To do this</span></span>                        |
   |--------------------|----------------------------------------------------------|
   |      <span data-ttu-id="4f65e-109">**名称**</span><span class="sxs-lookup"><span data-stu-id="4f65e-109">**Name**</span></span>      |                    <span data-ttu-id="4f65e-110">类型**HIS_Send**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-110">Type **HIS_Send**.</span></span>                    |
   | <span data-ttu-id="4f65e-111">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="4f65e-111">**Transport type**</span></span> |                     <span data-ttu-id="4f65e-112">选择**MLLP**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-112">Select **MLLP**.</span></span>                     |
   |   <span data-ttu-id="4f65e-113">**配置**</span><span class="sxs-lookup"><span data-stu-id="4f65e-113">**Configure**</span></span>    | <span data-ttu-id="4f65e-114">单击**配置**右侧的按钮**类型**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-114">Click the **Configure** button to the right of **Type**.</span></span> |


3. <span data-ttu-id="4f65e-115">在处的 MLLP 传输属性对话框中，输入以下信息，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-115">In the MLLP Transport Properties dialog box, enter the following information and then click **OK**.</span></span>  


   |      <span data-ttu-id="4f65e-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4f65e-116">Use this</span></span>       |       <span data-ttu-id="4f65e-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4f65e-117">To do this</span></span>       |
   |---------------------|------------------------|
   | <span data-ttu-id="4f65e-118">**连接名称**</span><span class="sxs-lookup"><span data-stu-id="4f65e-118">**Connection Name**</span></span> | <span data-ttu-id="4f65e-119">类型**HIS_SendMLLP**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-119">Type **HIS_SendMLLP**.</span></span> |
   |      <span data-ttu-id="4f65e-120">**主机**</span><span class="sxs-lookup"><span data-stu-id="4f65e-120">**Host**</span></span>       |  <span data-ttu-id="4f65e-121">类型**localhost**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-121">Type **localhost**.</span></span>   |
   |      <span data-ttu-id="4f65e-122">**端口**</span><span class="sxs-lookup"><span data-stu-id="4f65e-122">**Port**</span></span>       |    <span data-ttu-id="4f65e-123">类型**24000**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-123">Type **24000**.</span></span>     |


4. <span data-ttu-id="4f65e-124">在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

5. <span data-ttu-id="4f65e-125">在控制台树中，单击**筛选器**，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4f65e-125">In the Console Tree, click **Filters**, and then do the following:</span></span>  


   |   <span data-ttu-id="4f65e-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4f65e-126">Use this</span></span>   |                              <span data-ttu-id="4f65e-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4f65e-127">To do this</span></span>                               |
   |--------------|-----------------------------------------------------------------------|
   | <span data-ttu-id="4f65e-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="4f65e-128">**Property**</span></span> |             <span data-ttu-id="4f65e-129">有关**属性**，选择**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-129">For **Property**, select **BTS.MessageType**.</span></span>             |
   | <span data-ttu-id="4f65e-130">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="4f65e-130">**Operator**</span></span> |                <span data-ttu-id="4f65e-131">选择**==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4f65e-131">Select **==** from the drop-down list.</span></span>                 |
   |  <span data-ttu-id="4f65e-132">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="4f65e-132">**Value**</span></span>   | <span data-ttu-id="4f65e-133">类型**<http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF>**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-133">Type **<http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF>**.</span></span> |
   | <span data-ttu-id="4f65e-134">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="4f65e-134">**Group By**</span></span> |                <span data-ttu-id="4f65e-135">选择**AND**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4f65e-135">Select **AND** from the drop-down list.</span></span>                |
   | <span data-ttu-id="4f65e-136">**属性**</span><span class="sxs-lookup"><span data-stu-id="4f65e-136">**Property**</span></span> | <span data-ttu-id="4f65e-137">有关**属性**在第二行中，选择**BTAHL7Schemas.MSH5_1**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-137">For **Property** on the second line, select **BTAHL7Schemas.MSH5_1**.</span></span> |
   | <span data-ttu-id="4f65e-138">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="4f65e-138">**Operator**</span></span> |                <span data-ttu-id="4f65e-139">选择**==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4f65e-139">Select **==** from the drop-down list.</span></span>                 |
   |  <span data-ttu-id="4f65e-140">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="4f65e-140">**Value**</span></span>   |                             <span data-ttu-id="4f65e-141">类型**HIS**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-141">Type **HIS**.</span></span>                             |

   > [!NOTE]
   >  <span data-ttu-id="4f65e-142">第一个筛选器指定发送端口只选择消息符合 QRY ^ Q01 架构在步骤 3A 中创建。</span><span class="sxs-lookup"><span data-stu-id="4f65e-142">The first filter specifies that the send port only selects messages conforming to the QRY^Q01 schema you created in step 3A.</span></span> <span data-ttu-id="4f65e-143">第二个筛选器指定到的目标[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎将发送这些消息。</span><span class="sxs-lookup"><span data-stu-id="4f65e-143">The second filter specifies the destination to which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine sends these messages.</span></span>  

6. <span data-ttu-id="4f65e-144">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="4f65e-144">Click **OK**.</span></span>  

7. <span data-ttu-id="4f65e-145">在管理控制台中，选择**发送端口**，右键单击**HIS_Send**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="4f65e-145">In the Administration console, select **Send Ports**, right-click **HIS_Send**, and then click **Start**.</span></span>  

   <span data-ttu-id="4f65e-146">请继续执行[步骤 7： 创建用于传递响应消息的发送端口](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="4f65e-146">Proceed to [Step 7: Create a Send Port to Deliver Response Messages](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md).</span></span>