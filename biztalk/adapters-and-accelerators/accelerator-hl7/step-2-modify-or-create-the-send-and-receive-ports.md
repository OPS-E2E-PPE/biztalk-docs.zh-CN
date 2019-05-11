---
title: 第 2 步：修改或创建发送和接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d96d02c-b75d-4d18-a127-37002c5ff138
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8538bd8f67a78c77c0dca0a875c26ed169672e80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288612"
---
# <a name="step-2-modify-or-create-the-send-and-receive-ports"></a><span data-ttu-id="54577-102">第 2 步：修改或创建发送和接收端口</span><span class="sxs-lookup"><span data-stu-id="54577-102">Step 2: Modify or Create the Send and Receive Ports</span></span>
<span data-ttu-id="54577-103">所需文件发送和接收端口的批处理中 / 出站教程批处理。</span><span class="sxs-lookup"><span data-stu-id="54577-103">You need FILE send and receive ports for the Batch In/Batch Out tutorial.</span></span> <span data-ttu-id="54577-104">如果单击了**启动教程**安装的 Enterprise Edition 的末尾按钮[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]为你创建这些端口： 名为 Tutorial_BTAHL7Drop，一个发送端口和一个名为 Tutorial_BTAHL7PickUp 的接收端口。</span><span class="sxs-lookup"><span data-stu-id="54577-104">If you clicked the **Launch Tutorial** button at the end of installing the Enterprise Edition of [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] created these ports for you: a send port named Tutorial_BTAHL7Drop, and a receive port named Tutorial_BTAHL7PickUp.</span></span> <span data-ttu-id="54577-105">如果您有这些端口，仍需要修改发送端口 Tutorial_BTAHL7Drop。</span><span class="sxs-lookup"><span data-stu-id="54577-105">If you have these ports, you still need to modify the send port Tutorial_BTAHL7Drop.</span></span>  

 <span data-ttu-id="54577-106">如果[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装程序不未创建发送和接收端口，请参阅本主题中的"创建 BIBOTutorialPickup 接收端口"过程，然后请参阅"创建 BIBOTutorialDrop 发送端口"还在本主题中的过程。</span><span class="sxs-lookup"><span data-stu-id="54577-106">If [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] setup did not create the send and receive ports for you, see "To create the BIBOTutorialPickup receive port" procedure in this topic, and then see "To create the BIBOTutorialDrop send port" procedure also in this topic.</span></span>  

### <a name="to-modify-the-tutorialbtahl7drop-send-port"></a><span data-ttu-id="54577-107">若要修改 Tutorial_BTAHL7Drop 发送端口</span><span class="sxs-lookup"><span data-stu-id="54577-107">To modify the Tutorial_BTAHL7Drop send port</span></span>  

1. <span data-ttu-id="54577-108">单击**启动**，依次指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="54577-108">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="54577-109">在管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="54577-109">In the Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  

3. <span data-ttu-id="54577-110">单击**发送端口**，右键单击**Tutorial_BTAHL7Drop**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="54577-110">Click **Send Ports**, right-click **Tutorial_BTAHL7Drop**, and then click **Properties**.</span></span>  

4. <span data-ttu-id="54577-111">在控制台树中，单击**筛选器**。</span><span class="sxs-lookup"><span data-stu-id="54577-111">In the console tree, click **Filters**.</span></span>  

5. <span data-ttu-id="54577-112">在中**筛选器**窗格中的，在第二个行中，选择**BTAHL7Schemas.MessageClass**有关**属性**，选择**==** 为**运算符**，然后键入**MessageClass2X**有关**值**。</span><span class="sxs-lookup"><span data-stu-id="54577-112">In the **Filters** pane, in the second row, select **BTAHL7Schemas.MessageClass** for **Properties**, select **==** for **Operator**, and type **MessageClass2X** for **Value**.</span></span> <span data-ttu-id="54577-113">单击 **“输入”**。</span><span class="sxs-lookup"><span data-stu-id="54577-113">Click **Enter**.</span></span>  

6. <span data-ttu-id="54577-114">设置**分组依据**上**BTS。ReceivePortName**到行**或者**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="54577-114">Set **Group By** on the **BTS.ReceivePortName** line to **Or**, and then click **OK**.</span></span>  

7. <span data-ttu-id="54577-115">在 microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理窗口中，展开**平台设置**，然后展开**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="54577-115">In the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration window, expand **Platform Settings**, and expand **Host Instances**.</span></span> <span data-ttu-id="54577-116">右键单击**BizTalkServerApplication**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="54577-116">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="54577-117">仅使用以下过程，如果安装 Standard Edition [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]，或如果未单击**启动教程**按钮设置时[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="54577-117">Only use the following procedures if you installed the Standard Edition of [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)], or if you did not click the **Launch Tutorial** button when you set up [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span>  

### <a name="to-create-the-tutorialbtahl7pickup-receive-port-and-location"></a><span data-ttu-id="54577-118">若要创建 Tutorial_BTAHL7Pickup 接收端口和位置</span><span class="sxs-lookup"><span data-stu-id="54577-118">To create the Tutorial_BTAHL7Pickup receive port and location</span></span>  

1. <span data-ttu-id="54577-119">单击**启动**，依次指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="54577-119">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="54577-120">在管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="54577-120">In the Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  

3. <span data-ttu-id="54577-121">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="54577-121">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port**.</span></span>  

4. <span data-ttu-id="54577-122">在接收端口属性对话框中，在**名称**框中，键入**Tutorial_BTAHL7PickUp**。</span><span class="sxs-lookup"><span data-stu-id="54577-122">In the Receive Port Properties dialog box, in the **Name** box, type **Tutorial_BTAHL7PickUp**.</span></span>  

5. <span data-ttu-id="54577-123">单击**Apply**以绑定端口，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="54577-123">Click **Apply** to bind the port, and then click **OK**.</span></span>  

6. <span data-ttu-id="54577-124">右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。</span><span class="sxs-lookup"><span data-stu-id="54577-124">Right-click **Receive Locations**, point to **New**, and then click **One-way Receive Location**.</span></span>  

7. <span data-ttu-id="54577-125">在选择接收端口对话框中，单击**Tutorial_BTAHL7PickUp**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="54577-125">In the Select a Receive Port dialog box, click **Tutorial_BTAHL7PickUp**, and then click **OK**.</span></span>  

8. <span data-ttu-id="54577-126">在接收位置属性对话框中，在**名称**框中，键入**Tutorial_FileReceiveLoc**。</span><span class="sxs-lookup"><span data-stu-id="54577-126">In the Receive Location Properties dialog box, in the **Name** box, type **Tutorial_FileReceiveLoc**.</span></span>  

9. <span data-ttu-id="54577-127">在中**传输**部分中，对于**类型**文本框中，单击下拉列表，然后选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="54577-127">In the **Transport** section, for the **Type** text box, click the drop-down list, and then select **FILE**.</span></span>  

10. <span data-ttu-id="54577-128">单击**配置**类型下拉列表右侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="54577-128">Click the **Configure** button to the right of the Type drop-down list.</span></span>  

11. <span data-ttu-id="54577-129">在 FILE 传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54577-129">In the FILE Transport Properties dialog box, do the following:</span></span>  


    |      <span data-ttu-id="54577-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="54577-130">Use this</span></span>      |                                                                                                                                                                         <span data-ttu-id="54577-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="54577-131">To do this</span></span>                                                                                                                                                                          |
    |--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="54577-132">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="54577-132">**Receive Folder**</span></span> | <span data-ttu-id="54577-133">浏览到**\<**<em>驱动器</em>**\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BTAHL7PickUp**。</span><span class="sxs-lookup"><span data-stu-id="54577-133">Browse to **\<**<em>drive</em>**\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7PickUp**.</span></span> <span data-ttu-id="54577-134">**注意：** 这是到公共共享的文件系统上的位置中的位置的路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]会选取该文件。</span><span class="sxs-lookup"><span data-stu-id="54577-134">**Note:**  This is the path to the location on the file system or public share from where [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will pick up the file.</span></span> |
    |   <span data-ttu-id="54577-135">**文件掩码**</span><span class="sxs-lookup"><span data-stu-id="54577-135">**File mask**</span></span>    |                                                                                                                                                                      <span data-ttu-id="54577-136">类型 **\*.txt**。</span><span class="sxs-lookup"><span data-stu-id="54577-136">Type **\*.txt**.</span></span>                                                                                                                                                                       |


12. <span data-ttu-id="54577-137">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="54577-137">Click **OK**.</span></span>  

13. <span data-ttu-id="54577-138">在接收位置属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54577-138">In the Receive Location Properties dialog box, do the following:</span></span>  


    |       <span data-ttu-id="54577-139">使用此选项</span><span class="sxs-lookup"><span data-stu-id="54577-139">Use this</span></span>       |                      <span data-ttu-id="54577-140">执行的操作</span><span class="sxs-lookup"><span data-stu-id="54577-140">To do this</span></span>                       |
    |----------------------|-------------------------------------------------------|
    | <span data-ttu-id="54577-141">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="54577-141">**Receive Handler**</span></span>  |    <span data-ttu-id="54577-142">保持**BizTalkServerApplication**为选中状态。</span><span class="sxs-lookup"><span data-stu-id="54577-142">Keep **BizTalkServerApplication** as selected.</span></span>     |
    | <span data-ttu-id="54577-143">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="54577-143">**Receive Pipeline**</span></span> | <span data-ttu-id="54577-144">选择**BTAHL72XPipelines.BTAHL72XReceivePipeline**。</span><span class="sxs-lookup"><span data-stu-id="54577-144">Select **BTAHL72XPipelines.BTAHL72XReceivePipeline**.</span></span> |


14. <span data-ttu-id="54577-145">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="54577-145">Click **OK**.</span></span>  

15. <span data-ttu-id="54577-146">在 BizTalk 浏览器中右键单击**Tutorial_FileReceiveLoc**，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="54577-146">In BizTalk Explorer, right-click **Tutorial_FileReceiveLoc**, and then click **Enable**.</span></span>  

### <a name="to-create-the-tutorialbtahl7drop-send-port"></a><span data-ttu-id="54577-147">若要创建 Tutorial_BTAHL7Drop 发送端口</span><span class="sxs-lookup"><span data-stu-id="54577-147">To create the Tutorial_BTAHL7Drop send port</span></span>  

1. <span data-ttu-id="54577-148">在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="54577-148">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="54577-149">在发送端口属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54577-149">In the Send Port Properties dialog box, do the following:</span></span>  


   |   <span data-ttu-id="54577-150">使用此选项</span><span class="sxs-lookup"><span data-stu-id="54577-150">Use this</span></span>    |                                <span data-ttu-id="54577-151">执行的操作</span><span class="sxs-lookup"><span data-stu-id="54577-151">To do this</span></span>                                 |
   |---------------|---------------------------------------------------------------------------|
   |   <span data-ttu-id="54577-152">**名称**</span><span class="sxs-lookup"><span data-stu-id="54577-152">**Name**</span></span>    |                       <span data-ttu-id="54577-153">类型**Tutorial_BTAHL7Drop**。</span><span class="sxs-lookup"><span data-stu-id="54577-153">Type **Tutorial_BTAHL7Drop**.</span></span>                       |
   |   <span data-ttu-id="54577-154">**类型**</span><span class="sxs-lookup"><span data-stu-id="54577-154">**Type**</span></span>    |                 <span data-ttu-id="54577-155">选择**文件**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="54577-155">Select **FILE** from the drop-down list.</span></span>                  |
   | <span data-ttu-id="54577-156">**配置**</span><span class="sxs-lookup"><span data-stu-id="54577-156">**Configure**</span></span> | <span data-ttu-id="54577-157">单击**配置**以打开**FILE 传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="54577-157">Click **Configure** to open the **FILE Transport Properties** dialog box.</span></span> |


3. <span data-ttu-id="54577-158">在 FILE 传输属性对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54577-158">In the FILE Transport Properties dialog box, do the following:</span></span>  


   |        <span data-ttu-id="54577-159">使用此选项</span><span class="sxs-lookup"><span data-stu-id="54577-159">Use this</span></span>        |                                                                                                                                                                      <span data-ttu-id="54577-160">执行的操作</span><span class="sxs-lookup"><span data-stu-id="54577-160">To do this</span></span>                                                                                                                                                                       |
   |------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="54577-161">**目标文件夹**</span><span class="sxs-lookup"><span data-stu-id="54577-161">**Destination folder**</span></span> | <span data-ttu-id="54577-162">浏览到**\<**<em>驱动器</em>**:\>\Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BTAHL7Drop**。</span><span class="sxs-lookup"><span data-stu-id="54577-162">Browse to **\<**<em>drive</em>**:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop**.</span></span> <span data-ttu-id="54577-163">**注意：** 这是到公共共享的文件系统上的位置的路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将写入文件。</span><span class="sxs-lookup"><span data-stu-id="54577-163">**Note:**  This is the path to the location on the file system or public share to which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] will write the file.</span></span> |
   |     <span data-ttu-id="54577-164">**文件名**</span><span class="sxs-lookup"><span data-stu-id="54577-164">**File name**</span></span>      |                                                                                                                                          <span data-ttu-id="54577-165">类型 **%MessageID%.txt** （请注意该扩展名是 txt、 非 xml）。</span><span class="sxs-lookup"><span data-stu-id="54577-165">Type **%MessageID%.txt** (note that the extension is txt, not xml).</span></span>                                                                                                                                          |


4. <span data-ttu-id="54577-166">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="54577-166">Click **OK**.</span></span>  

5. <span data-ttu-id="54577-167">在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="54577-167">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline** from the drop-down list.</span></span>  

6. <span data-ttu-id="54577-168">在控制台树中，单击**筛选器**，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54577-168">In the console tree, click **Filters**, and then do the following:</span></span>  


   |   <span data-ttu-id="54577-169">使用此选项</span><span class="sxs-lookup"><span data-stu-id="54577-169">Use this</span></span>   |                       <span data-ttu-id="54577-170">执行的操作</span><span class="sxs-lookup"><span data-stu-id="54577-170">To do this</span></span>                        |
   |--------------|---------------------------------------------------------|
   | <span data-ttu-id="54577-171">**属性**</span><span class="sxs-lookup"><span data-stu-id="54577-171">**Property**</span></span> | <span data-ttu-id="54577-172">选择**BTS。ReceivePortName**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="54577-172">Select **BTS.ReceivePortName** from the drop-down list.</span></span> |
   | <span data-ttu-id="54577-173">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="54577-173">**Operator**</span></span> |              <span data-ttu-id="54577-174">将保留**==** 与运算符。</span><span class="sxs-lookup"><span data-stu-id="54577-174">Leave **==** as the operator.</span></span>              |
   |  <span data-ttu-id="54577-175">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="54577-175">**Value**</span></span>   |             <span data-ttu-id="54577-176">类型**Tutorial_BTAHL7PickUp**。</span><span class="sxs-lookup"><span data-stu-id="54577-176">Type **Tutorial_BTAHL7PickUp**.</span></span>             |
   | <span data-ttu-id="54577-177">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="54577-177">**Group By**</span></span> |         <span data-ttu-id="54577-178">选择**或**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="54577-178">Select **Or** from the drop-down list.</span></span>          |
   | <span data-ttu-id="54577-179">**属性**</span><span class="sxs-lookup"><span data-stu-id="54577-179">**Property**</span></span> |         <span data-ttu-id="54577-180">选择**BTAHL7Schemas.MessageClass**。</span><span class="sxs-lookup"><span data-stu-id="54577-180">Select **BTAHL7Schemas.MessageClass**.</span></span>          |
   | <span data-ttu-id="54577-181">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="54577-181">**Operator**</span></span> |              <span data-ttu-id="54577-182">将保留**==** 与运算符。</span><span class="sxs-lookup"><span data-stu-id="54577-182">Leave **==** as the operator.</span></span>              |
   |  <span data-ttu-id="54577-183">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="54577-183">**Value**</span></span>   |                <span data-ttu-id="54577-184">类型**MessageClass2X**。</span><span class="sxs-lookup"><span data-stu-id="54577-184">Type **MessageClass2X**.</span></span>                 |


7. <span data-ttu-id="54577-185">单击 **“输入”**。</span><span class="sxs-lookup"><span data-stu-id="54577-185">Click **Enter**.</span></span> <span data-ttu-id="54577-186">在对话框中底部窗格中验证筛选器表达式正确。</span><span class="sxs-lookup"><span data-stu-id="54577-186">Verify in the pane at the bottom of the dialog box that the filter expression is correct.</span></span>  

8. <span data-ttu-id="54577-187">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="54577-187">Click **OK**.</span></span>  

9. <span data-ttu-id="54577-188">在管理控制台中，单击**发送端口**，右键单击**Tutorial_BTAHL7Drop**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="54577-188">In the Administration Console, click **Send Ports**, right-click **Tutorial_BTAHL7Drop**, and then click **Start**.</span></span>  

10. <span data-ttu-id="54577-189">展开**平台设置**，然后单击**主机实例**。</span><span class="sxs-lookup"><span data-stu-id="54577-189">Expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="54577-190">右键单击**BizTalkServerApplication**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="54577-190">Right-click **BizTalkServerApplication**, and then click **Restart**.</span></span>  

    <span data-ttu-id="54577-191">请继续执行[步骤 3:测试在入站批处理 / 出站批处理方案](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="54577-191">Proceed to [Step 3: Test the Batch In/Batch Out Scenario](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md).</span></span>