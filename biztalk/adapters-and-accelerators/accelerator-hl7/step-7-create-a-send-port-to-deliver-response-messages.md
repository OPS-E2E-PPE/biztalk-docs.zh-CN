---
title: 步骤 7： 创建用于传递响应消息的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: 5edaefb6-72f2-4317-9477-f3a0d0027e0c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4139e07c5ca503a8cb58b1aa88fe8e602a92ee07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987822"
---
# <a name="step-7-create-a-send-port-to-deliver-response-messages"></a><span data-ttu-id="3dc6a-102">步骤 7： 创建用于传递响应消息的发送端口</span><span class="sxs-lookup"><span data-stu-id="3dc6a-102">Step 7: Create a Send Port to Deliver Response Messages</span></span>
<span data-ttu-id="3dc6a-103">在此步骤中，创建发送端口以将查询响应返回到病人入院、 放电装置和传输 (ADT) 系统。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-103">In this step, you create the send port to deliver the query responses back to the Admissions, Discharge, and Transfer (ADT) system.</span></span>  

### <a name="to-create-the-adtsend-send-port"></a><span data-ttu-id="3dc6a-104">若要创建 ADT_Send 发送端口</span><span class="sxs-lookup"><span data-stu-id="3dc6a-104">To create the ADT_Send send port</span></span>  

1. <span data-ttu-id="3dc6a-105">在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后选择**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-105">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then select **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="3dc6a-106">在“发送端口属性”对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3dc6a-106">In the Send Port Properties dialog box, do the following:</span></span>  


   |      <span data-ttu-id="3dc6a-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="3dc6a-107">Use this</span></span>      |                        <span data-ttu-id="3dc6a-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="3dc6a-108">To do this</span></span>                        |
   |--------------------|----------------------------------------------------------|
   |      <span data-ttu-id="3dc6a-109">**名称**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-109">**Name**</span></span>      |                    <span data-ttu-id="3dc6a-110">类型**ADT_Send**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-110">Type **ADT_Send**.</span></span>                    |
   | <span data-ttu-id="3dc6a-111">**传输类型**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-111">**Transport type**</span></span> |                     <span data-ttu-id="3dc6a-112">选择**MLLP**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-112">Select **MLLP**.</span></span>                     |
   |   <span data-ttu-id="3dc6a-113">**配置**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-113">**Configure**</span></span>    | <span data-ttu-id="3dc6a-114">单击**配置**右侧的按钮**类型**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-114">Click the **Configure** button to the right of **Type**.</span></span> |


3. <span data-ttu-id="3dc6a-115">在处的 MLLP 传输属性对话框中，输入以下信息，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-115">In the MLLP Transport Properties dialog box, enter the following information, and then click **OK**.</span></span>  


   |      <span data-ttu-id="3dc6a-116">使用此选项</span><span class="sxs-lookup"><span data-stu-id="3dc6a-116">Use this</span></span>       |       <span data-ttu-id="3dc6a-117">执行的操作</span><span class="sxs-lookup"><span data-stu-id="3dc6a-117">To do this</span></span>       |
   |---------------------|------------------------|
   | <span data-ttu-id="3dc6a-118">**连接名称**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-118">**Connection Name**</span></span> | <span data-ttu-id="3dc6a-119">类型**ADT_SendMLLP**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-119">Type **ADT_SendMLLP**.</span></span> |
   |      <span data-ttu-id="3dc6a-120">**主机**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-120">**Host**</span></span>       |  <span data-ttu-id="3dc6a-121">类型**localhost**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-121">Type **localhost**.</span></span>   |
   |      <span data-ttu-id="3dc6a-122">**端口**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-122">**Port**</span></span>       |    <span data-ttu-id="3dc6a-123">类型**25000**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-123">Type **25000**.</span></span>     |


4. <span data-ttu-id="3dc6a-124">在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-124">In the Send Port Properties dialog box, for **Send Pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**.</span></span>  

5. <span data-ttu-id="3dc6a-125">在控制台树中，单击**筛选器**，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3dc6a-125">In the Console Tree, click **Filters**, and then do the following:</span></span>  


   |   <span data-ttu-id="3dc6a-126">使用此选项</span><span class="sxs-lookup"><span data-stu-id="3dc6a-126">Use this</span></span>   |                                        <span data-ttu-id="3dc6a-127">执行的操作</span><span class="sxs-lookup"><span data-stu-id="3dc6a-127">To do this</span></span>                                        |
   |--------------|------------------------------------------------------------------------------------------|
   | <span data-ttu-id="3dc6a-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-128">**Property**</span></span> |                               <span data-ttu-id="3dc6a-129">选择**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-129">Select **BTS.MessageType**.</span></span>                                |
   | <span data-ttu-id="3dc6a-130">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-130">**Operator**</span></span> |                          <span data-ttu-id="3dc6a-131">选择**==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-131">Select **==** from the drop-down list.</span></span>                          |
   |  <span data-ttu-id="3dc6a-132">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-132">**Value**</span></span>   |          <span data-ttu-id="3dc6a-133">类型**<http://microsoft.com/HealthCare/HL7/2X#DSR_Q01_24_GLO_DEF>**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-133">Type **<http://microsoft.com/HealthCare/HL7/2X#DSR_Q01_24_GLO_DEF>**.</span></span>           |
   | <span data-ttu-id="3dc6a-134">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-134">**Group By**</span></span> |                         <span data-ttu-id="3dc6a-135">选择**AND**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-135">Select **AND** from the drop-down list.</span></span>                          |
   | <span data-ttu-id="3dc6a-136">**属性**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-136">**Property**</span></span> | <span data-ttu-id="3dc6a-137">在第一个属性，单击空白框中，然后选择**BTAHL7Schemas.MSH5_1**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-137">Under the first property, click the blank box, and then select **BTAHL7Schemas.MSH5_1**.</span></span> |
   | <span data-ttu-id="3dc6a-138">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-138">**Operator**</span></span> |                          <span data-ttu-id="3dc6a-139">选择**==** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-139">Select **==** from the drop-down list.</span></span>                          |
   |  <span data-ttu-id="3dc6a-140">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="3dc6a-140">**Value**</span></span>   |                                      <span data-ttu-id="3dc6a-141">类型**ADT**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-141">Type **ADT**.</span></span>                                       |

   > [!NOTE]
   >  <span data-ttu-id="3dc6a-142">第一个筛选器指定发送端口只选择消息符合 DSR ^ Q01 架构在步骤 3A 中创建。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-142">The first filter specifies that the send port only selects messages conforming to the DSR^Q01 schema you created in step 3A.</span></span> <span data-ttu-id="3dc6a-143">第二个筛选器指定到的目标[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎将发送这些消息。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-143">The second filter specifies the destination to which the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Interface Engine sends these messages.</span></span>  

6. <span data-ttu-id="3dc6a-144">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-144">Click **OK**.</span></span>  

7. <span data-ttu-id="3dc6a-145">在管理控制台中，单击**发送端口**，右键单击**ADT_Send**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-145">In the Administration Console, click **Send Ports**, right-click **ADT_Send**, and then click **Start**.</span></span>  

   <span data-ttu-id="3dc6a-146">请继续执行[步骤 8： 配置参与方信息](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)。</span><span class="sxs-lookup"><span data-stu-id="3dc6a-146">Proceed to [Step 8: Configure Party Information](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md).</span></span>