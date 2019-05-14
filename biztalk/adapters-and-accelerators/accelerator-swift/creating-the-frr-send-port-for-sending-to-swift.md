---
title: 创建用于发送到 SWIFT 的 FRR 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 1ad766db-d1da-437a-a520-a3b04f0695c4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 138fef11bd271979edb564b8639bffb6acc6e7a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378350"
---
# <a name="creating-the-frr-send-port-for-sending-to-swift"></a><span data-ttu-id="298fe-102">创建用于发送到 SWIFT 的 FRR 发送端口</span><span class="sxs-lookup"><span data-stu-id="298fe-102">Creating the FRR Send Port for Sending to SWIFT</span></span>
<span data-ttu-id="298fe-103">若要执行 FIN 响应对帐，需要创建一个发送端口将消息从发送[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到 SWIFT 网络。</span><span class="sxs-lookup"><span data-stu-id="298fe-103">To perform FIN Response Reconciliation, you need to create a send port that sends a message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the SWIFT Network.</span></span>  

 <span data-ttu-id="298fe-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="298fe-104">**Summary**</span></span>  

 <span data-ttu-id="298fe-105">创建具有以下属性和组件的发送端口：</span><span class="sxs-lookup"><span data-stu-id="298fe-105">Create a send port with the following properties and components:</span></span>  


|     <span data-ttu-id="298fe-106">属性 / 组件</span><span class="sxs-lookup"><span data-stu-id="298fe-106">Property/Component</span></span>      |                                                               <span data-ttu-id="298fe-107">设置</span><span class="sxs-lookup"><span data-stu-id="298fe-107">Setting</span></span>                                                                |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
|          <span data-ttu-id="298fe-108">发送端口</span><span class="sxs-lookup"><span data-stu-id="298fe-108">Send port</span></span>          |                                                         <span data-ttu-id="298fe-109">静态单向端口</span><span class="sxs-lookup"><span data-stu-id="298fe-109">Static one-way port</span></span>                                                          |
|       <span data-ttu-id="298fe-110">传输类型</span><span class="sxs-lookup"><span data-stu-id="298fe-110">Transport type</span></span>        |                                                               <span data-ttu-id="298fe-111">MQSeries</span><span class="sxs-lookup"><span data-stu-id="298fe-111">MQSeries</span></span>                                                               |
| <span data-ttu-id="298fe-112">队列定义 (MQSeries)</span><span class="sxs-lookup"><span data-stu-id="298fe-112">Queue Definition (MQSeries)</span></span> |                                                 <span data-ttu-id="298fe-113">MQSeries server 队列管理器队列</span><span class="sxs-lookup"><span data-stu-id="298fe-113">MQSeries server Queue manager Queue</span></span>                                                  |
|        <span data-ttu-id="298fe-114">发送管道</span><span class="sxs-lookup"><span data-stu-id="298fe-114">Send pipeline</span></span>        | <span data-ttu-id="298fe-115">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]您创建了的 FRR 发送管道</span><span class="sxs-lookup"><span data-stu-id="298fe-115">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] send pipeline that you created for FRR</span></span> |
|           <span data-ttu-id="298fe-116">筛选器</span><span class="sxs-lookup"><span data-stu-id="298fe-116">Filters</span></span>           |                                                     <span data-ttu-id="298fe-117">下表中所示</span><span class="sxs-lookup"><span data-stu-id="298fe-117">As shown in the table below</span></span>                                                      |

### <a name="to-add-a-custom-send-port-for-sending-to-swift"></a><span data-ttu-id="298fe-118">若要添加自定义发送端口发送到 SWIFT</span><span class="sxs-lookup"><span data-stu-id="298fe-118">To add a custom send port for sending to SWIFT</span></span>  

1. <span data-ttu-id="298fe-119">在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态一个 waySend 端口**。</span><span class="sxs-lookup"><span data-stu-id="298fe-119">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-waySend Port**.</span></span>  

2. <span data-ttu-id="298fe-120">在发送端口属性对话框中，在**名称**框中，键入发送端口，例如 FRRSWIFTSendPort 的名称。</span><span class="sxs-lookup"><span data-stu-id="298fe-120">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port, such as FRRSWIFTSendPort.</span></span>  

3. <span data-ttu-id="298fe-121">有关**类型**，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="298fe-121">For **Type**, select **MQSeries**.</span></span>  

4. <span data-ttu-id="298fe-122">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="298fe-122">Click **Configure**.</span></span>  

5. <span data-ttu-id="298fe-123">在 MQSeries 传输属性对话框中，单击**队列定义**，然后单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="298fe-123">In the MQSeries Transport Properties dialog box, click **Queue Definition**, and then click the ellipsis () button.</span></span>  

6. <span data-ttu-id="298fe-124">在队列定义对话框中，输入 MQSeries 服务器、 队列管理器和队列。</span><span class="sxs-lookup"><span data-stu-id="298fe-124">In the Queue Definition dialog box, enter the MQSeries server, queue manager, and queue.</span></span> <span data-ttu-id="298fe-125">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="298fe-125">Click **OK**.</span></span>  

7. <span data-ttu-id="298fe-126">在 MQSeries 传输属性对话框中，验证对属性进行了所需。</span><span class="sxs-lookup"><span data-stu-id="298fe-126">In the MQSeries Transport Properties dialog box, verify that the properties are as needed.</span></span> <span data-ttu-id="298fe-127">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="298fe-127">Click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="298fe-128">MQSeries 传输属性的详细信息，请参阅 MQSeries 文档。</span><span class="sxs-lookup"><span data-stu-id="298fe-128">For more information about MQSeries transport properties, see the MQSeries documentation.</span></span>  

8. <span data-ttu-id="298fe-129">在发送端口属性对话框中，对于**发送处理程序**，验证是否选择 BizTalkServerApplication。</span><span class="sxs-lookup"><span data-stu-id="298fe-129">In the Send Port Properties dialog box, for **Send handler**, verify that BizTalkServerApplication is selected.</span></span>  

9. <span data-ttu-id="298fe-130">有关**发送管道**，选择[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]您创建了的 FRR 发送管道。</span><span class="sxs-lookup"><span data-stu-id="298fe-130">For **Send Pipeline**, select the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] send pipeline that you created for FRR.</span></span>  

10. <span data-ttu-id="298fe-131">单击**筛选器**中左窗格中，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="298fe-131">Click **Filters** in the left pane, and then do the following:</span></span>  


    |   <span data-ttu-id="298fe-132">使用此选项</span><span class="sxs-lookup"><span data-stu-id="298fe-132">Use this</span></span>   |                            <span data-ttu-id="298fe-133">执行的操作</span><span class="sxs-lookup"><span data-stu-id="298fe-133">To do this</span></span>                             |
    |--------------|-------------------------------------------------------------------|
    | <span data-ttu-id="298fe-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="298fe-134">**Property**</span></span> |  <span data-ttu-id="298fe-135">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**。</span><span class="sxs-lookup"><span data-stu-id="298fe-135">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span></span>  |
    | <span data-ttu-id="298fe-136">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="298fe-136">**Operator**</span></span> |                          <span data-ttu-id="298fe-137">选择 ==。</span><span class="sxs-lookup"><span data-stu-id="298fe-137">Select **==**.</span></span>                           |
    |  <span data-ttu-id="298fe-138">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="298fe-138">**Value**</span></span>   |                          <span data-ttu-id="298fe-139">类型**False**。</span><span class="sxs-lookup"><span data-stu-id="298fe-139">Type **False**.</span></span>                          |
    |  <span data-ttu-id="298fe-140">**分组**</span><span class="sxs-lookup"><span data-stu-id="298fe-140">**Group**</span></span>   |                          <span data-ttu-id="298fe-141">选择**和**。</span><span class="sxs-lookup"><span data-stu-id="298fe-141">Select **And**.</span></span>                          |
    | <span data-ttu-id="298fe-142">**属性**</span><span class="sxs-lookup"><span data-stu-id="298fe-142">**Property**</span></span> | <span data-ttu-id="298fe-143">类型**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**。</span><span class="sxs-lookup"><span data-stu-id="298fe-143">Type **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**.</span></span> |
    | <span data-ttu-id="298fe-144">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="298fe-144">**Operator**</span></span> |                          <span data-ttu-id="298fe-145">选择 ==。</span><span class="sxs-lookup"><span data-stu-id="298fe-145">Select **==**.</span></span>                           |
    |  <span data-ttu-id="298fe-146">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="298fe-146">**Value**</span></span>   |                          <span data-ttu-id="298fe-147">类型 **，则返回 True**。</span><span class="sxs-lookup"><span data-stu-id="298fe-147">Type **True**.</span></span>                           |


11. <span data-ttu-id="298fe-148">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="298fe-148">Click **Apply**, and then click **OK**.</span></span>  

12. <span data-ttu-id="298fe-149">右键单击该发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="298fe-149">Right-click the send port, and then click **Start**.</span></span>
