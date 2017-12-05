---
title: "步骤 2： 修改或创建发送方和接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d96d02c-b75d-4d18-a127-37002c5ff138
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa94183f0eb83dc51fc0add22ba50484f7282fb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="step-2-modify-or-create-the-send-and-receive-ports"></a><span data-ttu-id="e7c0e-102">步骤 2： 修改或创建发送方和接收端口</span><span class="sxs-lookup"><span data-stu-id="e7c0e-102">Step 2: Modify or Create the Send and Receive Ports</span></span>
<span data-ttu-id="e7c0e-103">你需要文件发送和接收端口批中 / 批处理出教程。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-103">You need FILE send and receive ports for the Batch In/Batch Out tutorial.</span></span> <span data-ttu-id="e7c0e-104">如果你单击**启动教程**末尾的安装 Enterprise Edition 的按钮[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]为你创建这些端口： 名为 Tutorial_BTAHL7Drop，发送端口和一个名为 Tutorial_BTAHL7PickUp 的接收端口。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-104">If you clicked the **Launch Tutorial** button at the end of installing the Enterprise Edition of [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] created these ports for you: a send port named Tutorial_BTAHL7Drop, and a receive port named Tutorial_BTAHL7PickUp.</span></span> <span data-ttu-id="e7c0e-105">如果你有这些端口，你仍需要修改发送端口 Tutorial_BTAHL7Drop。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-105">If you have these ports, you still need to modify the send port Tutorial_BTAHL7Drop.</span></span>  
  
 <span data-ttu-id="e7c0e-106">如果[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装程序不未创建发送和接收端口，请参阅本主题中的"创建 BIBOTutorialPickup 接收端口"过程，然后请参阅"创建 BIBOTutorialDrop 发送端口"还在本主题中的过程。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-106">If [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup did not create the send and receive ports for you, see "To create the BIBOTutorialPickup receive port" procedure in this topic, and then see "To create the BIBOTutorialDrop send port" procedure also in this topic.</span></span>  
  
### <a name="to-modify-the-tutorialbtahl7drop-send-port"></a><span data-ttu-id="e7c0e-107">若要修改 Tutorial_BTAHL7Drop 发送端口</span><span class="sxs-lookup"><span data-stu-id="e7c0e-107">To modify the Tutorial_BTAHL7Drop send port</span></span>  
  
1.  <span data-ttu-id="e7c0e-108">单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-108">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e7c0e-109">在管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-109">In the Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="e7c0e-110">单击**发送端口**，右键单击**Tutorial_BTAHL7Drop**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-110">Click **Send Ports**, right-click **Tutorial_BTAHL7Drop**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="e7c0e-111">在控制台树中，单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-111">In the console tree, click **Filters**.</span></span>  
  
5.  <span data-ttu-id="e7c0e-112">在**筛选器**窗格中，在第二个行中，选择**BTAHL7Schemas.MessageClass**为**属性**，选择 **==** 为**运算符**，和类型**MessageClass2X**为**值**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-112">In the **Filters** pane, in the second row, select **BTAHL7Schemas.MessageClass** for **Properties**, select **==** for **Operator**, and type **MessageClass2X** for **Value**.</span></span> <span data-ttu-id="e7c0e-113">单击 **“输入”**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-113">Click **Enter**.</span></span>  
  
6.  <span data-ttu-id="e7c0e-114">设置**分组依据**上**BTS。ReceivePortName**行**或者**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-114">Set **Group By** on the **BTS.ReceivePortName** line to **Or**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="e7c0e-115">在[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理窗口中，展开**平台设置**，然后展开**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-115">In the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration window, expand **Platform Settings**, and expand **Host Instances**.</span></span> <span data-ttu-id="e7c0e-116">右键单击**BizTalkServerApplication**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-116">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e7c0e-117">仅使用以下过程，如果你安装 Standard Edition 的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]，或如果您没有单击**启动教程**按钮设置完成[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-117">Only use the following procedures if you installed the Standard Edition of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], or if you did not click the **Launch Tutorial** button when you set up [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span>  
  
### <a name="to-create-the-tutorialbtahl7pickup-receive-port-and-location"></a><span data-ttu-id="e7c0e-118">若要创建 Tutorial_BTAHL7Pickup 接收端口和位置</span><span class="sxs-lookup"><span data-stu-id="e7c0e-118">To create the Tutorial_BTAHL7Pickup receive port and location</span></span>  
  
1.  <span data-ttu-id="e7c0e-119">单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-119">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e7c0e-120">在管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-120">In the Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
3.  <span data-ttu-id="e7c0e-121">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  
  
4.  <span data-ttu-id="e7c0e-122">在接收端口属性对话框中，在**名称**框中，键入**Tutorial_BTAHL7PickUp**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-122">In the Receive Port Properties dialog box, in the **Name** box, type **Tutorial_BTAHL7PickUp**.</span></span>  
  
5.  <span data-ttu-id="e7c0e-123">单击**应用**以绑定端口，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-123">Click **Apply** to bind the port, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="e7c0e-124">右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-124">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  
  
7.  <span data-ttu-id="e7c0e-125">在选择接收端口对话框中，单击**Tutorial_BTAHL7PickUp**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-125">In the Select a Receive Port dialog box, click **Tutorial_BTAHL7PickUp**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="e7c0e-126">在接收位置属性对话框中，在**名称**框中，键入**Tutorial_FileReceiveLoc**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-126">In the Receive Location Properties dialog box, in the **Name** box, type **Tutorial_FileReceiveLoc**.</span></span>  
  
9. <span data-ttu-id="e7c0e-127">在**传输**部分中，为**类型**文本框中，单击下拉列表中，，然后选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-127">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  
  
10. <span data-ttu-id="e7c0e-128">单击**配置**类型下拉列表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-128">Click the **Configure** button to the right of the Type drop-down list.</span></span>  
  
11. <span data-ttu-id="e7c0e-129">在文件传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e7c0e-129">In the FILE Transport Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="e7c0e-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e7c0e-130">Use this</span></span>|<span data-ttu-id="e7c0e-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e7c0e-131">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7c0e-132">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-132">**Receive Folder**</span></span>|<span data-ttu-id="e7c0e-133">浏览到 **\<** *驱动器***\>: files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BTAHL7PickUp**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-133">Browse to **\<***drive***\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp**.</span></span> <span data-ttu-id="e7c0e-134">**注意：**这是指向文件系统或公共共享上的位置从何处路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将选取此文件。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-134">**Note:**  This is the path to the location on the file system or public share from where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will pick up the file.</span></span>|  
    |<span data-ttu-id="e7c0e-135">**文件掩码**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-135">**File mask**</span></span>|<span data-ttu-id="e7c0e-136">类型 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-136">Type **\*.txt**.</span></span>|  
  
12. <span data-ttu-id="e7c0e-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-137">Click **OK**.</span></span>  
  
13. <span data-ttu-id="e7c0e-138">在接收位置属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e7c0e-138">In the Receive Location Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="e7c0e-139">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e7c0e-139">Use this</span></span>|<span data-ttu-id="e7c0e-140">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e7c0e-140">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7c0e-141">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-141">**Receive Handler**</span></span>|<span data-ttu-id="e7c0e-142">保留**BizTalkServerApplication**为选中状态。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-142">Keep **BizTalkServerApplication** as selected.</span></span>|  
    |<span data-ttu-id="e7c0e-143">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-143">**Receive Pipeline**</span></span>|<span data-ttu-id="e7c0e-144">选择**BTAHL72XPipelines.BTAHL72XReceivePipeline**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-144">Select **BTAHL72XPipelines.BTAHL72XReceivePipeline**.</span></span>|  
  
14. <span data-ttu-id="e7c0e-145">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-145">Click **OK**.</span></span>  
  
15. <span data-ttu-id="e7c0e-146">在 BizTalk 资源管理器中，右键单击**Tutorial_FileReceiveLoc**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-146">In BizTalk Explorer, right-click **Tutorial_FileReceiveLoc**, and then click **Enable**.</span></span>  
  
### <a name="to-create-the-tutorialbtahl7drop-send-port"></a><span data-ttu-id="e7c0e-147">若要创建 Tutorial_BTAHL7Drop 发送端口</span><span class="sxs-lookup"><span data-stu-id="e7c0e-147">To create the Tutorial_BTAHL7Drop send port</span></span>  
  
1.  <span data-ttu-id="e7c0e-148">在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-148">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="e7c0e-149">在“发送端口属性”对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e7c0e-149">In the Send Port Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="e7c0e-150">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e7c0e-150">Use this</span></span>|<span data-ttu-id="e7c0e-151">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e7c0e-151">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7c0e-152">**名称**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-152">**Name**</span></span>|<span data-ttu-id="e7c0e-153">类型**Tutorial_BTAHL7Drop**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-153">Type **Tutorial_BTAHL7Drop**.</span></span>|  
    |<span data-ttu-id="e7c0e-154">**类型**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-154">**Type**</span></span>|<span data-ttu-id="e7c0e-155">选择**文件**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-155">Select **FILE** from the drop-down list.</span></span>|  
    |<span data-ttu-id="e7c0e-156">**配置**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-156">**Configure**</span></span>|<span data-ttu-id="e7c0e-157">单击**配置**以打开**文件传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-157">Click **Configure** to open the **FILE Transport Properties** dialog box.</span></span>|  
  
3.  <span data-ttu-id="e7c0e-158">在文件传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e7c0e-158">In the FILE Transport Properties dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="e7c0e-159">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e7c0e-159">Use this</span></span>|<span data-ttu-id="e7c0e-160">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e7c0e-160">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7c0e-161">**目标文件夹**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-161">**Destination folder**</span></span>|<span data-ttu-id="e7c0e-162">浏览到 **\<** *驱动器***:\>files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BTAHL7Drop**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-162">Browse to **\<***drive***:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop**.</span></span> <span data-ttu-id="e7c0e-163">**注意：**这是文件系统或到公共共享上的位置的路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将写入文件。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-163">**Note:**  This is the path to the location on the file system or public share to which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will write the file.</span></span>|  
    |<span data-ttu-id="e7c0e-164">**文件名**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-164">**File name**</span></span>|<span data-ttu-id="e7c0e-165">类型**%MessageID%.txt** （请注意，扩展名为 txt、 不是 xml）。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-165">Type **%MessageID%.txt** (note that the extension is txt, not xml).</span></span>|  
  
4.  <span data-ttu-id="e7c0e-166">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-166">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="e7c0e-167">在发送端口属性对话框中，为**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-167">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline** from the drop-down list.</span></span>  
  
6.  <span data-ttu-id="e7c0e-168">在控制台树中，单击**筛选器**，然后执行以下：</span><span class="sxs-lookup"><span data-stu-id="e7c0e-168">In the console tree, click **Filters**, and then do the following:</span></span>  
  
    |<span data-ttu-id="e7c0e-169">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e7c0e-169">Use this</span></span>|<span data-ttu-id="e7c0e-170">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e7c0e-170">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e7c0e-171">**属性**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-171">**Property**</span></span>|<span data-ttu-id="e7c0e-172">选择**BTS。ReceivePortName**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-172">Select **BTS.ReceivePortName** from the drop-down list.</span></span>|  
    |<span data-ttu-id="e7c0e-173">**运算符**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-173">**Operator**</span></span>|<span data-ttu-id="e7c0e-174">保留 **==** 为运算符。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-174">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="e7c0e-175">**值**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-175">**Value**</span></span>|<span data-ttu-id="e7c0e-176">类型**Tutorial_BTAHL7PickUp**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-176">Type **Tutorial_BTAHL7PickUp**.</span></span>|  
    |<span data-ttu-id="e7c0e-177">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-177">**Group By**</span></span>|<span data-ttu-id="e7c0e-178">选择**或**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-178">Select **Or** from the drop-down list.</span></span>|  
    |<span data-ttu-id="e7c0e-179">**属性**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-179">**Property**</span></span>|<span data-ttu-id="e7c0e-180">选择**BTAHL7Schemas.MessageClass**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-180">Select **BTAHL7Schemas.MessageClass**.</span></span>|  
    |<span data-ttu-id="e7c0e-181">**运算符**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-181">**Operator**</span></span>|<span data-ttu-id="e7c0e-182">保留 **==** 为运算符。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-182">Leave **==** as the operator.</span></span>|  
    |<span data-ttu-id="e7c0e-183">**值**</span><span class="sxs-lookup"><span data-stu-id="e7c0e-183">**Value**</span></span>|<span data-ttu-id="e7c0e-184">类型**MessageClass2X**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-184">Type **MessageClass2X**.</span></span>|  
  
7.  <span data-ttu-id="e7c0e-185">单击 **“输入”**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-185">Click **Enter**.</span></span> <span data-ttu-id="e7c0e-186">在对话框中底部窗格中验证筛选器表达式正确。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-186">Verify in the pane at the bottom of the dialog box that the filter expression is correct.</span></span>  
  
8.  <span data-ttu-id="e7c0e-187">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-187">Click **OK**.</span></span>  
  
9. <span data-ttu-id="e7c0e-188">在管理控制台中，单击**发送端口**，右键单击**Tutorial_BTAHL7Drop**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-188">In the Administration Console, click **Send Ports**, right-click **Tutorial_BTAHL7Drop**, and then click **Start**.</span></span>  
  
10. <span data-ttu-id="e7c0e-189">展开**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-189">Expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="e7c0e-190">右键单击**BizTalkServerApplication**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-190">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  
  
 <span data-ttu-id="e7c0e-191">继续执行[步骤 3： 测试中的批处理 / 批处理出方案](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="e7c0e-191">Proceed to [Step 3: Test the Batch In/Batch Out Scenario](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md).</span></span>