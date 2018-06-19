---
title: 步骤 6： 创建发送端口将查询消息传递 |Microsoft 文档
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
ms.openlocfilehash: 43c373940d8ab1e847b66527d83ef24e952d84d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206797"
---
# <a name="step-6-create-a-send-port-to-deliver-query-messages"></a><span data-ttu-id="352a4-102">步骤 6： 创建发送端口将查询消息传递</span><span class="sxs-lookup"><span data-stu-id="352a4-102">Step 6: Create a Send Port to Deliver Query Messages</span></span>
<span data-ttu-id="352a4-103">在此步骤中，创建要发送传入的查询的发送端口 (QRY ^ Q01 消息) 到医院信息系统 (HIS)。</span><span class="sxs-lookup"><span data-stu-id="352a4-103">In this step, you create the send port to deliver the incoming queries (QRY^Q01 messages) to the Hospital Information System (HIS).</span></span>  
  
### <a name="to-create-the-hissend-send-port"></a><span data-ttu-id="352a4-104">若要创建 HIS_Send 发送端口</span><span class="sxs-lookup"><span data-stu-id="352a4-104">To create the HIS_Send send port</span></span>  
  
1.  <span data-ttu-id="352a4-105">在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后选择**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="352a4-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then select **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="352a4-106">在“发送端口属性”对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="352a4-106">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="352a4-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="352a4-107">Use this</span></span>|<span data-ttu-id="352a4-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="352a4-108">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="352a4-109">**名称**</span><span class="sxs-lookup"><span data-stu-id="352a4-109">**Name**</span></span>|<span data-ttu-id="352a4-110">类型**HIS_Send**。</span><span class="sxs-lookup"><span data-stu-id="352a4-110">Type **HIS_Send**.</span></span>|  
    |<span data-ttu-id="352a4-111">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="352a4-111">**Transport type**</span></span>|<span data-ttu-id="352a4-112">选择**MLLP**。</span><span class="sxs-lookup"><span data-stu-id="352a4-112">Select **MLLP**.</span></span>|  
    |<span data-ttu-id="352a4-113">**配置**</span><span class="sxs-lookup"><span data-stu-id="352a4-113">**Configure**</span></span>|<span data-ttu-id="352a4-114">单击**配置**右侧的按钮**类型**。</span><span class="sxs-lookup"><span data-stu-id="352a4-114">Click the **Configure** button to the right of **Type**.</span></span>|  
  
3.  <span data-ttu-id="352a4-115">在 MLLP 传输属性对话框中，输入以下信息，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="352a4-115">In the MLLP Transport Properties dialog box, enter the following information and then click **OK**.</span></span>  
  
    |<span data-ttu-id="352a4-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="352a4-116">Use this</span></span>|<span data-ttu-id="352a4-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="352a4-117">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="352a4-118">**连接名称**</span><span class="sxs-lookup"><span data-stu-id="352a4-118">**Connection Name**</span></span>|<span data-ttu-id="352a4-119">类型**HIS_SendMLLP**。</span><span class="sxs-lookup"><span data-stu-id="352a4-119">Type **HIS_SendMLLP**.</span></span>|  
    |<span data-ttu-id="352a4-120">**主机**</span><span class="sxs-lookup"><span data-stu-id="352a4-120">**Host**</span></span>|<span data-ttu-id="352a4-121">类型**localhost**。</span><span class="sxs-lookup"><span data-stu-id="352a4-121">Type **localhost**.</span></span>|  
    |<span data-ttu-id="352a4-122">**端口**</span><span class="sxs-lookup"><span data-stu-id="352a4-122">**Port**</span></span>|<span data-ttu-id="352a4-123">类型**24000**。</span><span class="sxs-lookup"><span data-stu-id="352a4-123">Type **24000**.</span></span>|  
  
4.  <span data-ttu-id="352a4-124">在发送端口属性对话框中，为**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="352a4-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  
  
5.  <span data-ttu-id="352a4-125">在控制台树中，单击**筛选器**，然后执行以下：</span><span class="sxs-lookup"><span data-stu-id="352a4-125">In the Console Tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="352a4-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="352a4-126">Use this</span></span>|<span data-ttu-id="352a4-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="352a4-127">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="352a4-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="352a4-128">**Property**</span></span>|<span data-ttu-id="352a4-129">有关**属性**，选择**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="352a4-129">For **Property**, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="352a4-130">**运算符**</span><span class="sxs-lookup"><span data-stu-id="352a4-130">**Operator**</span></span>|<span data-ttu-id="352a4-131">选择 **==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="352a4-131">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="352a4-132">**值**</span><span class="sxs-lookup"><span data-stu-id="352a4-132">**Value**</span></span>|<span data-ttu-id="352a4-133">类型**http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF**。</span><span class="sxs-lookup"><span data-stu-id="352a4-133">Type **http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF**.</span></span>|  
    |<span data-ttu-id="352a4-134">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="352a4-134">**Group By**</span></span>|<span data-ttu-id="352a4-135">选择**AND**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="352a4-135">Select **AND** from the drop-down list.</span></span>|  
    |<span data-ttu-id="352a4-136">**属性**</span><span class="sxs-lookup"><span data-stu-id="352a4-136">**Property**</span></span>|<span data-ttu-id="352a4-137">有关**属性**在第二行中，选择**BTAHL7Schemas.MSH5_1**。</span><span class="sxs-lookup"><span data-stu-id="352a4-137">For **Property** on the second line, select **BTAHL7Schemas.MSH5_1**.</span></span>|  
    |<span data-ttu-id="352a4-138">**运算符**</span><span class="sxs-lookup"><span data-stu-id="352a4-138">**Operator**</span></span>|<span data-ttu-id="352a4-139">选择 **==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="352a4-139">Select **==** from the drop-down list.</span></span>|  
    |<span data-ttu-id="352a4-140">**值**</span><span class="sxs-lookup"><span data-stu-id="352a4-140">**Value**</span></span>|<span data-ttu-id="352a4-141">类型**HIS**。</span><span class="sxs-lookup"><span data-stu-id="352a4-141">Type **HIS**.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="352a4-142">第一个筛选器指定发送端口仅选择消息符合 QRY ^ 步骤 3A 中创建的 Q01 架构。</span><span class="sxs-lookup"><span data-stu-id="352a4-142">The first filter specifies that the send port only selects messages conforming to the QRY^Q01 schema you created in step 3A.</span></span> <span data-ttu-id="352a4-143">第二个筛选器指定到的目标[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎将发送这些消息。</span><span class="sxs-lookup"><span data-stu-id="352a4-143">The second filter specifies the destination to which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine sends these messages.</span></span>  
  
6.  <span data-ttu-id="352a4-144">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="352a4-144">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="352a4-145">在管理控制台中，选择**发送端口**，右键单击**HIS_Send**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="352a4-145">In the Administration console, select **Send Ports**, right-click **HIS_Send**, and then click **Start**.</span></span>  
  
 <span data-ttu-id="352a4-146">继续执行[步骤 7： 创建发送端口将响应消息传递](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="352a4-146">Proceed to [Step 7: Create a Send Port to Deliver Response Messages](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md).</span></span>