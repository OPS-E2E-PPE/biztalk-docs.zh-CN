---
title: "创建 A4SWIFT 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
ms.assetid: d1ee18f8-a6aa-4cd5-9e65-fb2e0fa2d0c2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cf24cb99643acc869123450ce14fd5050ee7408
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-an-a4swift-send-port"></a><span data-ttu-id="8c445-102">创建 A4SWIFT 发送端口</span><span class="sxs-lookup"><span data-stu-id="8c445-102">Creating an A4SWIFT Send Port</span></span>
<span data-ttu-id="8c445-103">你必须创建发送端口以启用[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]若要将消息发送到 SWIFT 网络，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="8c445-103">You must create a send port to enable [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to send a message to the SWIFT network, as shown in the following figure.</span></span> <span data-ttu-id="8c445-104">此发送端口将将平面文件消息发送到的出站文件文件夹。</span><span class="sxs-lookup"><span data-stu-id="8c445-104">This send port will send flat file messages to an outbound file folder.</span></span> <span data-ttu-id="8c445-105">此发送端口用于处理消息修复和新提交功能。</span><span class="sxs-lookup"><span data-stu-id="8c445-105">This send port is designed to work with the Message Repair and New Submission feature.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-send-port-configuration.gif "A4SWIFT_Send_Port_Configuration")  
  
 <span data-ttu-id="8c445-106">**摘要**</span><span class="sxs-lookup"><span data-stu-id="8c445-106">**Summary**</span></span>  
  
 <span data-ttu-id="8c445-107">创建并启动与以下属性和组件的静态单向发送端口：</span><span class="sxs-lookup"><span data-stu-id="8c445-107">Create and start a static one-way send port with the following properties and components:</span></span>  
  
|<span data-ttu-id="8c445-108">属性 / 组件</span><span class="sxs-lookup"><span data-stu-id="8c445-108">Property/Component</span></span>|<span data-ttu-id="8c445-109">设置</span><span class="sxs-lookup"><span data-stu-id="8c445-109">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="8c445-110">发送端口</span><span class="sxs-lookup"><span data-stu-id="8c445-110">Send port</span></span>|<span data-ttu-id="8c445-111">静态单向端口</span><span class="sxs-lookup"><span data-stu-id="8c445-111">Static one-way port</span></span>|  
|<span data-ttu-id="8c445-112">传输类型</span><span class="sxs-lookup"><span data-stu-id="8c445-112">Transport type</span></span>|<span data-ttu-id="8c445-113">FILE</span><span class="sxs-lookup"><span data-stu-id="8c445-113">FILE</span></span>|  
|<span data-ttu-id="8c445-114">目标文件夹 (地址 URI)</span><span class="sxs-lookup"><span data-stu-id="8c445-114">Destination folder (Address URI)</span></span>|<span data-ttu-id="8c445-115">你想要从发送消息的文件夹名称</span><span class="sxs-lookup"><span data-stu-id="8c445-115">Name of the folder that you want to send messages from</span></span>|  
|<span data-ttu-id="8c445-116">文件名称 （地址 URI）</span><span class="sxs-lookup"><span data-stu-id="8c445-116">File Name (Address URI)</span></span>|<span data-ttu-id="8c445-117">%MessageID%.txt</span><span class="sxs-lookup"><span data-stu-id="8c445-117">%MessageID%.txt</span></span>|  
|<span data-ttu-id="8c445-118">筛选器</span><span class="sxs-lookup"><span data-stu-id="8c445-118">Filters</span></span>|<span data-ttu-id="8c445-119">下表中所述</span><span class="sxs-lookup"><span data-stu-id="8c445-119">As described in the table below</span></span>|  
  
### <a name="to-add-the-sent-port"></a><span data-ttu-id="8c445-120">若要添加的发送的端口</span><span class="sxs-lookup"><span data-stu-id="8c445-120">To add the sent port</span></span>  
  
1.  <span data-ttu-id="8c445-121">在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="8c445-121">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="8c445-122">在发送端口属性对话框中，在**名称**框中，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="8c445-122">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port.</span></span>  
  
3.  <span data-ttu-id="8c445-123">在**传输**部分中，为**类型**框中，单击下拉列表中，，然后选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="8c445-123">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="8c445-124">单击**配置**类型下拉列表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="8c445-124">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="8c445-125">在文件传输属性对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="8c445-125">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="8c445-126">在浏览文件夹对话框中，移动到你想要从发送消息的文件夹。</span><span class="sxs-lookup"><span data-stu-id="8c445-126">In the Browse For Folder dialog box, move to the folder that you want to send messages from.</span></span> <span data-ttu-id="8c445-127">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8c445-127">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8c445-128">如果此文件夹不存在，则可以创建使用**新建文件夹**命令。</span><span class="sxs-lookup"><span data-stu-id="8c445-128">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  
  
7.  <span data-ttu-id="8c445-129">在**文件名**框中，键入**%MessageID%.txt**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8c445-129">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="8c445-130">在**发送端口属性**对话框框中，单击下拉列表**发送管道**框中，，然后选择你自定义发送管道。</span><span class="sxs-lookup"><span data-stu-id="8c445-130">In the **Send Port Properties** dialog box, click the drop-down list for the **Send pipeline** box, and then select your custom send pipeline.</span></span>  
  
9. <span data-ttu-id="8c445-131">在左窗格中，单击**筛选器**，然后执行以下：</span><span class="sxs-lookup"><span data-stu-id="8c445-131">In the left pane, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="8c445-132">使用此选项</span><span class="sxs-lookup"><span data-stu-id="8c445-132">Use this</span></span>|<span data-ttu-id="8c445-133">执行的操作</span><span class="sxs-lookup"><span data-stu-id="8c445-133">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="8c445-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="8c445-134">**Property**</span></span>|<span data-ttu-id="8c445-135">选择**BTS。操作**。</span><span class="sxs-lookup"><span data-stu-id="8c445-135">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="8c445-136">**运算符**</span><span class="sxs-lookup"><span data-stu-id="8c445-136">**Operator**</span></span>|<span data-ttu-id="8c445-137">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="8c445-137">Select **==**.</span></span>|  
    |<span data-ttu-id="8c445-138">**值**</span><span class="sxs-lookup"><span data-stu-id="8c445-138">**Value**</span></span>|<span data-ttu-id="8c445-139">类型**A4SWIFT_MRSRCompleted**。</span><span class="sxs-lookup"><span data-stu-id="8c445-139">Type **A4SWIFT_MRSRCompleted**.</span></span>|  
    |<span data-ttu-id="8c445-140">**分组**</span><span class="sxs-lookup"><span data-stu-id="8c445-140">**Group**</span></span>|<span data-ttu-id="8c445-141">选择**或者。**</span><span class="sxs-lookup"><span data-stu-id="8c445-141">Select **Or.**</span></span>|  
    |<span data-ttu-id="8c445-142">**属性**</span><span class="sxs-lookup"><span data-stu-id="8c445-142">**Property**</span></span>|<span data-ttu-id="8c445-143">选择**BTS。操作**。</span><span class="sxs-lookup"><span data-stu-id="8c445-143">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="8c445-144">**运算符**</span><span class="sxs-lookup"><span data-stu-id="8c445-144">**Operator**</span></span>|<span data-ttu-id="8c445-145">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="8c445-145">Select **==**.</span></span>|  
    |<span data-ttu-id="8c445-146">**值**</span><span class="sxs-lookup"><span data-stu-id="8c445-146">**Value**</span></span>|<span data-ttu-id="8c445-147">类型**A4SWIFT_MRSRFailed**。</span><span class="sxs-lookup"><span data-stu-id="8c445-147">Type **A4SWIFT_MRSRFailed**.</span></span>|  
    |<span data-ttu-id="8c445-148">**分组**</span><span class="sxs-lookup"><span data-stu-id="8c445-148">**Group**</span></span>|<span data-ttu-id="8c445-149">选择**或**。</span><span class="sxs-lookup"><span data-stu-id="8c445-149">Select **Or**.</span></span>|  
    |<span data-ttu-id="8c445-150">**属性**</span><span class="sxs-lookup"><span data-stu-id="8c445-150">**Property**</span></span>|<span data-ttu-id="8c445-151">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**。</span><span class="sxs-lookup"><span data-stu-id="8c445-151">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span></span>|  
    |<span data-ttu-id="8c445-152">**运算符**</span><span class="sxs-lookup"><span data-stu-id="8c445-152">**Operator**</span></span>|<span data-ttu-id="8c445-153">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="8c445-153">Select **==**.</span></span>|  
    |<span data-ttu-id="8c445-154">**值**</span><span class="sxs-lookup"><span data-stu-id="8c445-154">**Value**</span></span>|<span data-ttu-id="8c445-155">类型**True**。</span><span class="sxs-lookup"><span data-stu-id="8c445-155">Type **True**.</span></span>|  
  
10. <span data-ttu-id="8c445-156">单击**应用**，然后单击**确定。**</span><span class="sxs-lookup"><span data-stu-id="8c445-156">Click **Apply**, and then click **OK.**</span></span>  
  
11. <span data-ttu-id="8c445-157">在**发送端口**窗格中，右击发送端口，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="8c445-157">In the **Send Ports** pane, right-click the send port, and then click **Start**.</span></span>