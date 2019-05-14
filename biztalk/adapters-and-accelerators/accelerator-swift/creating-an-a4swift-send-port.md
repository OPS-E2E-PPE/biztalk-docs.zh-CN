---
title: 创建 A4SWIFT 发送端口 |Microsoft Docs
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
ms.assetid: d1ee18f8-a6aa-4cd5-9e65-fb2e0fa2d0c2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73a6b90f5b0fb6dcd3075c6ea1b0dc22e05934de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378506"
---
# <a name="creating-an-a4swift-send-port"></a><span data-ttu-id="d0787-102">创建 A4SWIFT 发送端口</span><span class="sxs-lookup"><span data-stu-id="d0787-102">Creating an A4SWIFT Send Port</span></span>
<span data-ttu-id="d0787-103">必须创建一个发送端口以启用[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]若要将消息发送到 SWIFT 网络，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="d0787-103">You must create a send port to enable [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to send a message to the SWIFT network, as shown in the following figure.</span></span> <span data-ttu-id="d0787-104">此发送端口将发送到出站文件文件夹的平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="d0787-104">This send port will send flat file messages to an outbound file folder.</span></span> <span data-ttu-id="d0787-105">此发送端口用于消息修复和新提交功能处理。</span><span class="sxs-lookup"><span data-stu-id="d0787-105">This send port is designed to work with the Message Repair and New Submission feature.</span></span>  
  
 <span data-ttu-id="d0787-106">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-send-port-configuration.gif "A4SWIFT_Send_Port_Configuration")</span><span class="sxs-lookup"><span data-stu-id="d0787-106">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-send-port-configuration.gif "A4SWIFT_Send_Port_Configuration")</span></span>  
  
 <span data-ttu-id="d0787-107">**摘要**</span><span class="sxs-lookup"><span data-stu-id="d0787-107">**Summary**</span></span>  
  
 <span data-ttu-id="d0787-108">创建并使用以下属性和组件启动静态单向发送端口：</span><span class="sxs-lookup"><span data-stu-id="d0787-108">Create and start a static one-way send port with the following properties and components:</span></span>  
  
|<span data-ttu-id="d0787-109">属性 / 组件</span><span class="sxs-lookup"><span data-stu-id="d0787-109">Property/Component</span></span>|<span data-ttu-id="d0787-110">设置</span><span class="sxs-lookup"><span data-stu-id="d0787-110">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="d0787-111">发送端口</span><span class="sxs-lookup"><span data-stu-id="d0787-111">Send port</span></span>|<span data-ttu-id="d0787-112">静态单向端口</span><span class="sxs-lookup"><span data-stu-id="d0787-112">Static one-way port</span></span>|  
|<span data-ttu-id="d0787-113">传输类型</span><span class="sxs-lookup"><span data-stu-id="d0787-113">Transport type</span></span>|<span data-ttu-id="d0787-114">FILE</span><span class="sxs-lookup"><span data-stu-id="d0787-114">FILE</span></span>|  
|<span data-ttu-id="d0787-115">目标文件夹 (地址 URI)</span><span class="sxs-lookup"><span data-stu-id="d0787-115">Destination folder (Address URI)</span></span>|<span data-ttu-id="d0787-116">你想要从发送消息的文件夹的名称</span><span class="sxs-lookup"><span data-stu-id="d0787-116">Name of the folder that you want to send messages from</span></span>|  
|<span data-ttu-id="d0787-117">文件名 （地址 URI）</span><span class="sxs-lookup"><span data-stu-id="d0787-117">File Name (Address URI)</span></span>|<span data-ttu-id="d0787-118">%MessageID%.txt</span><span class="sxs-lookup"><span data-stu-id="d0787-118">%MessageID%.txt</span></span>|  
|<span data-ttu-id="d0787-119">筛选器</span><span class="sxs-lookup"><span data-stu-id="d0787-119">Filters</span></span>|<span data-ttu-id="d0787-120">下表中所述</span><span class="sxs-lookup"><span data-stu-id="d0787-120">As described in the table below</span></span>|  
  
### <a name="to-add-the-sent-port"></a><span data-ttu-id="d0787-121">若要添加发送的端口</span><span class="sxs-lookup"><span data-stu-id="d0787-121">To add the sent port</span></span>  
  
1.  <span data-ttu-id="d0787-122">在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="d0787-122">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="d0787-123">在发送端口属性对话框中，在**名称**框中，键入发送端口的名称。</span><span class="sxs-lookup"><span data-stu-id="d0787-123">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port.</span></span>  
  
3.  <span data-ttu-id="d0787-124">在中**传输**部分中，对于**类型**框中，单击下拉列表中，并选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="d0787-124">In the **Transport** section, for the **Type** box, click the drop-down list, and then select **FILE**.</span></span>  
  
4.  <span data-ttu-id="d0787-125">单击**配置**类型下拉列表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="d0787-125">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
5.  <span data-ttu-id="d0787-126">在 FILE 传输属性对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="d0787-126">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="d0787-127">在浏览文件夹对话框中，转至你想要从发送消息的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d0787-127">In the Browse For Folder dialog box, move to the folder that you want to send messages from.</span></span> <span data-ttu-id="d0787-128">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="d0787-128">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d0787-129">如果此文件夹不存在，则可以创建使用其**建立新文件夹**命令。</span><span class="sxs-lookup"><span data-stu-id="d0787-129">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  
  
7.  <span data-ttu-id="d0787-130">在中**文件名**框中，键入 **%MessageID%.txt**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d0787-130">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="d0787-131">在中**发送端口属性**对话框框中，单击下拉列表**发送管道**框，并选择自定义发送管道。</span><span class="sxs-lookup"><span data-stu-id="d0787-131">In the **Send Port Properties** dialog box, click the drop-down list for the **Send pipeline** box, and then select your custom send pipeline.</span></span>  
  
9. <span data-ttu-id="d0787-132">在左窗格中，单击**筛选器**，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0787-132">In the left pane, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="d0787-133">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d0787-133">Use this</span></span>|<span data-ttu-id="d0787-134">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d0787-134">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d0787-135">**属性**</span><span class="sxs-lookup"><span data-stu-id="d0787-135">**Property**</span></span>|<span data-ttu-id="d0787-136">选择**BTS。操作**。</span><span class="sxs-lookup"><span data-stu-id="d0787-136">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="d0787-137">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="d0787-137">**Operator**</span></span>|<span data-ttu-id="d0787-138">选择 ==。</span><span class="sxs-lookup"><span data-stu-id="d0787-138">Select **==**.</span></span>|  
    |<span data-ttu-id="d0787-139">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="d0787-139">**Value**</span></span>|<span data-ttu-id="d0787-140">类型**A4SWIFT_MRSRCompleted**。</span><span class="sxs-lookup"><span data-stu-id="d0787-140">Type **A4SWIFT_MRSRCompleted**.</span></span>|  
    |<span data-ttu-id="d0787-141">**分组**</span><span class="sxs-lookup"><span data-stu-id="d0787-141">**Group**</span></span>|<span data-ttu-id="d0787-142">选择**或者。**</span><span class="sxs-lookup"><span data-stu-id="d0787-142">Select **Or.**</span></span>|  
    |<span data-ttu-id="d0787-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="d0787-143">**Property**</span></span>|<span data-ttu-id="d0787-144">选择**BTS。操作**。</span><span class="sxs-lookup"><span data-stu-id="d0787-144">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="d0787-145">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="d0787-145">**Operator**</span></span>|<span data-ttu-id="d0787-146">选择 ==。</span><span class="sxs-lookup"><span data-stu-id="d0787-146">Select **==**.</span></span>|  
    |<span data-ttu-id="d0787-147">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="d0787-147">**Value**</span></span>|<span data-ttu-id="d0787-148">类型**A4SWIFT_MRSRFailed**。</span><span class="sxs-lookup"><span data-stu-id="d0787-148">Type **A4SWIFT_MRSRFailed**.</span></span>|  
    |<span data-ttu-id="d0787-149">**分组**</span><span class="sxs-lookup"><span data-stu-id="d0787-149">**Group**</span></span>|<span data-ttu-id="d0787-150">选择**或**。</span><span class="sxs-lookup"><span data-stu-id="d0787-150">Select **Or**.</span></span>|  
    |<span data-ttu-id="d0787-151">**属性**</span><span class="sxs-lookup"><span data-stu-id="d0787-151">**Property**</span></span>|<span data-ttu-id="d0787-152">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**。</span><span class="sxs-lookup"><span data-stu-id="d0787-152">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**.</span></span>|  
    |<span data-ttu-id="d0787-153">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="d0787-153">**Operator**</span></span>|<span data-ttu-id="d0787-154">选择 ==。</span><span class="sxs-lookup"><span data-stu-id="d0787-154">Select **==**.</span></span>|  
    |<span data-ttu-id="d0787-155">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="d0787-155">**Value**</span></span>|<span data-ttu-id="d0787-156">类型 **，则返回 True**。</span><span class="sxs-lookup"><span data-stu-id="d0787-156">Type **True**.</span></span>|  
  
10. <span data-ttu-id="d0787-157">单击**Apply**，然后单击**确定。**</span><span class="sxs-lookup"><span data-stu-id="d0787-157">Click **Apply**, and then click **OK.**</span></span>  
  
11. <span data-ttu-id="d0787-158">在中**发送端口**窗格中，右键单击该发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="d0787-158">In the **Send Ports** pane, right-click the send port, and then click **Start**.</span></span>