---
title: 步骤 3： 创建和部署触发器事件 （消息） Project_hl7_main |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, trigger events
ms.assetid: 90b65ad1-7953-4009-a1eb-1c2a85c7980a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ba388eef1f5dbfb885e33c6263c4e0f8ef4be29
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961459"
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-projecthl7main"></a><span data-ttu-id="f8382-102">步骤 3： 创建和部署触发器事件 （消息） Project_hl7_main</span><span class="sxs-lookup"><span data-stu-id="f8382-102">Step 3: Create and Deploy a Trigger Event (Message) Project_hl7_main</span></span>
<span data-ttu-id="f8382-103">在此步骤中，你创建的触发器事件消息所使用的架构。</span><span class="sxs-lookup"><span data-stu-id="f8382-103">In this step, you create the schema used by a trigger event message.</span></span> <span data-ttu-id="f8382-104">例如，许可放电并传输系统 (ADT)，将发送一条消息到医院信息系统 (HIS)。</span><span class="sxs-lookup"><span data-stu-id="f8382-104">For example, the Admissions Discharge and Transfer system (ADT) that sends a message to the Hospital Information System (HIS).</span></span> <span data-ttu-id="f8382-105">此架构用于定义你的消息的格式。</span><span class="sxs-lookup"><span data-stu-id="f8382-105">You use this schema to define the format of your message.</span></span>  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a><span data-ttu-id="f8382-106">若要创建触发器事件消息的项目</span><span class="sxs-lookup"><span data-stu-id="f8382-106">To create the project for the trigger event message</span></span>  
  
1.  <span data-ttu-id="f8382-107">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="f8382-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="f8382-108">在新建项目对话框中，在**项目类型**列表中，展开**BizTalk 项目**，然后单击**BTAHL7Projects**。</span><span class="sxs-lookup"><span data-stu-id="f8382-108">In the New Project dialog box, in the **Project Types** list, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="f8382-109">在**模板**列表中，单击**空 BTAHL7 项目**。</span><span class="sxs-lookup"><span data-stu-id="f8382-109">In the **Templates** list, click **Empty BTAHL7 Project**.</span></span>  
  
4.  <span data-ttu-id="f8382-110">在**名称**字段中，键入**BTAHL7V24Body 项目**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f8382-110">In the **Name** field, type **BTAHL7V24Body Project**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="f8382-111">在解决方案资源管理器中的新节点下**BTAHL7V24Body**项目，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="f8382-111">In Solution Explorer, under the node for your new **BTAHL7V24Body** project, right-click **References**, and then click **Add Reference**.</span></span>  
  
6.  <span data-ttu-id="f8382-112">在添加引用对话框中，单击**项目**选项卡上，选择**Interrogative_24Schemas**，单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f8382-112">In the Add Reference dialog box, click the **Projects** tab, select **Interrogative_24Schemas**, click **Add**, and then click **OK**.</span></span>  
  
## <a name="step-3a-add-the-schemas"></a><span data-ttu-id="f8382-113">步骤 3A： 将架构添加</span><span class="sxs-lookup"><span data-stu-id="f8382-113">Step 3A: Add the Schemas</span></span>  
 <span data-ttu-id="f8382-114">使用以下过程将新架构添加到项目。</span><span class="sxs-lookup"><span data-stu-id="f8382-114">Use the following procedure to add the new schemas to the project.</span></span>  
  
#### <a name="to-add-the-schemas-to-the-project"></a><span data-ttu-id="f8382-115">若要将架构添加到项目</span><span class="sxs-lookup"><span data-stu-id="f8382-115">To add the schemas to the project</span></span>  
  
1.  <span data-ttu-id="f8382-116">在解决方案资源管理器，右键单击**BTAHL7V24Body 项目**，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="f8382-116">In Solution Explorer, right-click **BTAHL7V24Body Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="f8382-117">在添加新项对话框中，展开**BizTalk 项目项**，然后双击**BTAHL7 架构**右窗格中。</span><span class="sxs-lookup"><span data-stu-id="f8382-117">In the Add New Item dialog box, expand **BizTalk Project Items**, and then double-click **BTAHL7 Schemas** in the right pane.</span></span>  
  
3.  <span data-ttu-id="f8382-118">在 HL7 架构选择器对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f8382-118">In the HL7 Schema Selector dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="f8382-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f8382-119">Use this</span></span>|<span data-ttu-id="f8382-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f8382-120">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f8382-121">**Message 类**</span><span class="sxs-lookup"><span data-stu-id="f8382-121">**Message Class**</span></span>|<span data-ttu-id="f8382-122">保留**V2.X**选。</span><span class="sxs-lookup"><span data-stu-id="f8382-122">Keep **V2.X** selected.</span></span>|  
    |<span data-ttu-id="f8382-123">**版本**</span><span class="sxs-lookup"><span data-stu-id="f8382-123">**Version**</span></span>|<span data-ttu-id="f8382-124">选择**2.4**。</span><span class="sxs-lookup"><span data-stu-id="f8382-124">Select **2.4**.</span></span>|  
    |<span data-ttu-id="f8382-125">**消息类型**</span><span class="sxs-lookup"><span data-stu-id="f8382-125">**Message Type**</span></span>|<span data-ttu-id="f8382-126">选择**QRY**。</span><span class="sxs-lookup"><span data-stu-id="f8382-126">Select **QRY**.</span></span>|  
    |<span data-ttu-id="f8382-127">**触发器事件**</span><span class="sxs-lookup"><span data-stu-id="f8382-127">**Trigger Event**</span></span>|<span data-ttu-id="f8382-128">选择**Q01**。</span><span class="sxs-lookup"><span data-stu-id="f8382-128">Select **Q01**.</span></span>|  
  
4.  <span data-ttu-id="f8382-129">单击**完成**将该架构添加到项目。</span><span class="sxs-lookup"><span data-stu-id="f8382-129">Click **Finish** to add the schema to the project.</span></span>  
  
     <span data-ttu-id="f8382-130">这将创建查询架构文件 QRY_Q01_24_GLO_DEF.xsd。</span><span class="sxs-lookup"><span data-stu-id="f8382-130">This creates the query schema file QRY_Q01_24_GLO_DEF.xsd.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8382-131">不要关闭 HL7 架构选择器对话框。</span><span class="sxs-lookup"><span data-stu-id="f8382-131">Do not close the HL7 Schema Selector dialog box.</span></span>  
  
5.  <span data-ttu-id="f8382-132">在 HL7 架构选择器对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f8382-132">In the HL7 Schema Selector dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="f8382-133">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f8382-133">Use this</span></span>|<span data-ttu-id="f8382-134">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f8382-134">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f8382-135">**Message 类**</span><span class="sxs-lookup"><span data-stu-id="f8382-135">**Message Class**</span></span>|<span data-ttu-id="f8382-136">保留**V2.X**选。</span><span class="sxs-lookup"><span data-stu-id="f8382-136">Keep **V2.X** selected.</span></span>|  
    |<span data-ttu-id="f8382-137">**版本**</span><span class="sxs-lookup"><span data-stu-id="f8382-137">**Version**</span></span>|<span data-ttu-id="f8382-138">选择**2.4**。</span><span class="sxs-lookup"><span data-stu-id="f8382-138">Select **2.4**.</span></span>|  
    |<span data-ttu-id="f8382-139">**消息类型**</span><span class="sxs-lookup"><span data-stu-id="f8382-139">**Message Type**</span></span>|<span data-ttu-id="f8382-140">选择**DSR**。</span><span class="sxs-lookup"><span data-stu-id="f8382-140">Select **DSR**.</span></span>|  
    |<span data-ttu-id="f8382-141">**触发器事件**</span><span class="sxs-lookup"><span data-stu-id="f8382-141">**Trigger Event**</span></span>|<span data-ttu-id="f8382-142">选择**Q01**。</span><span class="sxs-lookup"><span data-stu-id="f8382-142">Select **Q01**.</span></span>|  
  
6.  <span data-ttu-id="f8382-143">单击**完成**将该架构添加到项目。</span><span class="sxs-lookup"><span data-stu-id="f8382-143">Click **Finish** to add the schema to the project.</span></span>  
  
     <span data-ttu-id="f8382-144">这将创建响应架构文件 DSR_Q01_24_GLO_DEF.xsd。</span><span class="sxs-lookup"><span data-stu-id="f8382-144">This creates the response schema file DSR_Q01_24_GLO_DEF.xsd.</span></span>  
  
7.  <span data-ttu-id="f8382-145">单击**取消**关闭**HL7 架构选择器**对话框。</span><span class="sxs-lookup"><span data-stu-id="f8382-145">Click **Cancel** to close the **HL7 Schema Selector** dialog box.</span></span>  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="f8382-146">步骤 3B： 向程序集分配强密钥和部署</span><span class="sxs-lookup"><span data-stu-id="f8382-146">Step 3B: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="f8382-147">使用以下过程向程序集分配强密钥，然后将部署程序集。</span><span class="sxs-lookup"><span data-stu-id="f8382-147">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="f8382-148">分配一个强密钥和部署程序集</span><span class="sxs-lookup"><span data-stu-id="f8382-148">To assign a strong key and deploy the assembly</span></span>  
  
1.  <span data-ttu-id="f8382-149">在解决方案资源管理器，右键单击**BTAHL7V24Body**项目，，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f8382-149">In Solution Explorer, right-click **BTAHL7V24Body** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f8382-150">在**BTAHL7V24Body 属性页**对话框中，单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="f8382-150">In the **BTAHL7V24Body Property Pages** dialog box, click **Assembly**.</span></span>  
  
3.  <span data-ttu-id="f8382-151">在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 （...） 按钮。</span><span class="sxs-lookup"><span data-stu-id="f8382-151">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
4.  <span data-ttu-id="f8382-152">在**程序集密钥文件**对话框中，浏览到\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>Accelerator for HL7\SDK\Interrogative 教程中，单击**key.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="f8382-152">In the **Assembly Key File** dialog box, browse to \<*drive*\>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for HL7\SDK\Interrogative Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="f8382-153">在**BTAHL7V24Body 属性页**对话框中，单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f8382-153">In the **BTAHL7V24Body Property Pages** dialog box, click **OK** to save your changes.</span></span>  
  
6.  <span data-ttu-id="f8382-154">在解决方案资源管理器中右键单击**BTAHL7V24Body 项目**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="f8382-154">In Solution Explorer right-click **BTAHL7V24Body Project**, and then click **Deploy**.</span></span> <span data-ttu-id="f8382-155">确保输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="f8382-155">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8382-156">如果未显示成功部署消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决你的架构。</span><span class="sxs-lookup"><span data-stu-id="f8382-156">If a successful deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="f8382-157">继续执行[步骤 4： 创建用于接受 ADT 查询消息接收端口](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="f8382-157">Proceed to [Step 4: Create the Receive Port for Accepting ADT Query Messages](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md).</span></span>