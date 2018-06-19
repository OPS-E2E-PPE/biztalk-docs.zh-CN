---
title: 创建 FRR 发送端口将发送到 SWIFT |Microsoft 文档
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
ms.openlocfilehash: 75cbda5d505f17f2dd7462cb0b16868a340f625c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210405"
---
# <a name="creating-the-frr-send-port-for-sending-to-swift"></a><span data-ttu-id="cc67d-102">创建用于将发送到 SWIFT FRR 发送端口</span><span class="sxs-lookup"><span data-stu-id="cc67d-102">Creating the FRR Send Port for Sending to SWIFT</span></span>
<span data-ttu-id="cc67d-103">若要执行 FIN 响应对帐，你需要创建发送一条消息从发送端口[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到 SWIFT 网络。</span><span class="sxs-lookup"><span data-stu-id="cc67d-103">To perform FIN Response Reconciliation, you need to create a send port that sends a message from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the SWIFT Network.</span></span>  
  
 <span data-ttu-id="cc67d-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="cc67d-104">**Summary**</span></span>  
  
 <span data-ttu-id="cc67d-105">创建具有以下属性和组件发送端口：</span><span class="sxs-lookup"><span data-stu-id="cc67d-105">Create a send port with the following properties and components:</span></span>  
  
|<span data-ttu-id="cc67d-106">属性 / 组件</span><span class="sxs-lookup"><span data-stu-id="cc67d-106">Property/Component</span></span>|<span data-ttu-id="cc67d-107">设置</span><span class="sxs-lookup"><span data-stu-id="cc67d-107">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="cc67d-108">发送端口</span><span class="sxs-lookup"><span data-stu-id="cc67d-108">Send port</span></span>|<span data-ttu-id="cc67d-109">静态单向端口</span><span class="sxs-lookup"><span data-stu-id="cc67d-109">Static one-way port</span></span>|  
|<span data-ttu-id="cc67d-110">传输类型</span><span class="sxs-lookup"><span data-stu-id="cc67d-110">Transport type</span></span>|<span data-ttu-id="cc67d-111">MQSeries</span><span class="sxs-lookup"><span data-stu-id="cc67d-111">MQSeries</span></span>|  
|<span data-ttu-id="cc67d-112">队列定义 (MQSeries)</span><span class="sxs-lookup"><span data-stu-id="cc67d-112">Queue Definition (MQSeries)</span></span>|<span data-ttu-id="cc67d-113">MQSeries 服务器队列管理器队列</span><span class="sxs-lookup"><span data-stu-id="cc67d-113">MQSeries server Queue manager Queue</span></span>|  
|<span data-ttu-id="cc67d-114">发送管道</span><span class="sxs-lookup"><span data-stu-id="cc67d-114">Send pipeline</span></span>|<span data-ttu-id="cc67d-115">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]为 FRR 创建的发送管道</span><span class="sxs-lookup"><span data-stu-id="cc67d-115">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] send pipeline that you created for FRR</span></span>|  
|<span data-ttu-id="cc67d-116">筛选器</span><span class="sxs-lookup"><span data-stu-id="cc67d-116">Filters</span></span>|<span data-ttu-id="cc67d-117">下表中所示</span><span class="sxs-lookup"><span data-stu-id="cc67d-117">As shown in the table below</span></span>|  
  
### <a name="to-add-a-custom-send-port-for-sending-to-swift"></a><span data-ttu-id="cc67d-118">若要添加自定义发送端口将发送到 SWIFT</span><span class="sxs-lookup"><span data-stu-id="cc67d-118">To add a custom send port for sending to SWIFT</span></span>  
  
1.  <span data-ttu-id="cc67d-119">在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态一个 waySend 端口**。</span><span class="sxs-lookup"><span data-stu-id="cc67d-119">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-waySend Port**.</span></span>  
  
2.  <span data-ttu-id="cc67d-120">在发送端口属性对话框中，在**名称**框中，键入发送端口，如 FRRSWIFTSendPort 的名称。</span><span class="sxs-lookup"><span data-stu-id="cc67d-120">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port, such as FRRSWIFTSendPort.</span></span>  
  
3.  <span data-ttu-id="cc67d-121">有关**类型**，选择**MQSeries**。</span><span class="sxs-lookup"><span data-stu-id="cc67d-121">For **Type**, select **MQSeries**.</span></span>  
  
4.  <span data-ttu-id="cc67d-122">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="cc67d-122">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="cc67d-123">在 MQSeries 传输属性对话框中，单击**队列定义**，然后单击省略号 （） 按钮。</span><span class="sxs-lookup"><span data-stu-id="cc67d-123">In the MQSeries Transport Properties dialog box, click **Queue Definition**, and then click the ellipsis () button.</span></span>  
  
6.  <span data-ttu-id="cc67d-124">在队列定义对话框中，输入 MQSeries 服务器、 队列管理器和队列。</span><span class="sxs-lookup"><span data-stu-id="cc67d-124">In the Queue Definition dialog box, enter the MQSeries server, queue manager, and queue.</span></span> <span data-ttu-id="cc67d-125">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="cc67d-125">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="cc67d-126">在 MQSeries 传输属性对话框中，验证的属性是根据需要。</span><span class="sxs-lookup"><span data-stu-id="cc67d-126">In the MQSeries Transport Properties dialog box, verify that the properties are as needed.</span></span> <span data-ttu-id="cc67d-127">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="cc67d-127">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc67d-128">有关 MQSeries 传输属性的详细信息，请参阅 MQSeries 文档。</span><span class="sxs-lookup"><span data-stu-id="cc67d-128">For more information about MQSeries transport properties, see the MQSeries documentation.</span></span>  
  
8.  <span data-ttu-id="cc67d-129">在发送端口属性对话框中，为**发送处理程序**，验证是否已选中 BizTalkServerApplication。</span><span class="sxs-lookup"><span data-stu-id="cc67d-129">In the Send Port Properties dialog box, for **Send handler**, verify that BizTalkServerApplication is selected.</span></span>  
  
9. <span data-ttu-id="cc67d-130">有关**发送管道**，选择[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]为 FRR 创建的发送管道。</span><span class="sxs-lookup"><span data-stu-id="cc67d-130">For **Send Pipeline**, select the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] send pipeline that you created for FRR.</span></span>  
  
10. <span data-ttu-id="cc67d-131">单击**筛选器**在左窗格中，然后再执行以下：</span><span class="sxs-lookup"><span data-stu-id="cc67d-131">Click **Filters** in the left pane, and then do the following:</span></span>  
  
    |<span data-ttu-id="cc67d-132">使用此选项</span><span class="sxs-lookup"><span data-stu-id="cc67d-132">Use this</span></span>|<span data-ttu-id="cc67d-133">执行的操作</span><span class="sxs-lookup"><span data-stu-id="cc67d-133">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="cc67d-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="cc67d-134">**Property**</span></span>|<span data-ttu-id="cc67d-135">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**。</span><span class="sxs-lookup"><span data-stu-id="cc67d-135">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span></span>|  
    |<span data-ttu-id="cc67d-136">**运算符**</span><span class="sxs-lookup"><span data-stu-id="cc67d-136">**Operator**</span></span>|<span data-ttu-id="cc67d-137">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="cc67d-137">Select **==**.</span></span>|  
    |<span data-ttu-id="cc67d-138">**值**</span><span class="sxs-lookup"><span data-stu-id="cc67d-138">**Value**</span></span>|<span data-ttu-id="cc67d-139">类型**False**。</span><span class="sxs-lookup"><span data-stu-id="cc67d-139">Type **False**.</span></span>|  
    |<span data-ttu-id="cc67d-140">**分组**</span><span class="sxs-lookup"><span data-stu-id="cc67d-140">**Group**</span></span>|<span data-ttu-id="cc67d-141">选择**和**。</span><span class="sxs-lookup"><span data-stu-id="cc67d-141">Select **And**.</span></span>|  
    |<span data-ttu-id="cc67d-142">**属性**</span><span class="sxs-lookup"><span data-stu-id="cc67d-142">**Property**</span></span>|<span data-ttu-id="cc67d-143">类型**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**。</span><span class="sxs-lookup"><span data-stu-id="cc67d-143">Type **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**.</span></span>|  
    |<span data-ttu-id="cc67d-144">**运算符**</span><span class="sxs-lookup"><span data-stu-id="cc67d-144">**Operator**</span></span>|<span data-ttu-id="cc67d-145">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="cc67d-145">Select **==**.</span></span>|  
    |<span data-ttu-id="cc67d-146">**值**</span><span class="sxs-lookup"><span data-stu-id="cc67d-146">**Value**</span></span>|<span data-ttu-id="cc67d-147">类型**True**。</span><span class="sxs-lookup"><span data-stu-id="cc67d-147">Type **True**.</span></span>|  
  
11. <span data-ttu-id="cc67d-148">单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cc67d-148">Click **Apply**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="cc67d-149">发送端口中，右键单击，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="cc67d-149">Right-click the send port, and then click **Start**.</span></span>