---
title: "步骤 3： 添加触发器事件 （消息） 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc4a67d9-9582-4f2b-9bc9-18fbff823d29
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 439caac8f1da151a9f203a1372039aaeedbfe83c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-add-a-trigger-event-message-schema"></a><span data-ttu-id="4fcfe-102">步骤 3： 添加触发器事件 （消息） 架构</span><span class="sxs-lookup"><span data-stu-id="4fcfe-102">Step 3: Add a Trigger Event (Message) Schema</span></span>
<span data-ttu-id="4fcfe-103">在此步骤中，你创建新的项目基于空[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]项目模板。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-103">In this step, you create a new project based on the Empty [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Project template.</span></span> <span data-ttu-id="4fcfe-104">将架构添加到此项目，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将用于验证传入的批处理中消息 (ADT ^ A03)。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-104">To this project, you add the schema that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will use to validate the messages in the incoming batch (ADT^A03).</span></span> <span data-ttu-id="4fcfe-105">添加对包含 v2.3.1 通用架构的项目的引用、 为该项目中，指定强名称，然后部署该项目。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-105">You add a reference to the project containing the v2.3.1 common schemas, assign the strong name to the project, and then deploy the project.</span></span>  
  
### <a name="to-add-the-project-containing-the-message-schema"></a><span data-ttu-id="4fcfe-106">若要添加包含的消息架构的项目</span><span class="sxs-lookup"><span data-stu-id="4fcfe-106">To add the project containing the message schema</span></span>  
  
1.  <span data-ttu-id="4fcfe-107">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="4fcfe-108">在新建项目对话框中，在**项目类型**部分中，展开**BizTalk 项目**，然后选择**BTAHL7Projects**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-108">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then select **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="4fcfe-109">在**模板**部分中，选择**空 BTAHL7 项目**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-109">In the **Templates** section, select **Empty BTAHL7 Project**.</span></span>  
  
4.  <span data-ttu-id="4fcfe-110">在**名称**框中，输入**BTAHL7V231Body**作为项目名称。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-110">In the **Name** box, enter **BTAHL7V231Body** as the project name.</span></span>  
  
5.  <span data-ttu-id="4fcfe-111">在**解决方案**框中，选择**将添加到解决方案**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-111">In the **Solution** box, select **Add to Solution**.</span></span>  
  
6.  <span data-ttu-id="4fcfe-112">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-112">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="4fcfe-113">在解决方案资源管理器，新的项目，节点下右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-113">In Solution Explorer, under the node for your new project, right-click **References**, and then click **Add Reference**.</span></span>  
  
8.  <span data-ttu-id="4fcfe-114">在添加引用对话框中，在**项目**选项卡上，单击**BTAHL7V231Common 项目**中**项目名称**列中，单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-114">In the Add Reference dialog box, on the **Projects** tab, click **BTAHL7V231Common Project** in the **Project Name** column, click **Add**, and then click **OK**.</span></span>  
  
### <a name="to-add-the-schema-to-the-project"></a><span data-ttu-id="4fcfe-115">若要将架构添加到项目</span><span class="sxs-lookup"><span data-stu-id="4fcfe-115">To add the schema to the project</span></span>  
  
1.  <span data-ttu-id="4fcfe-116">在解决方案资源管理器，右键单击**BTAHL7V231Body**，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-116">In Solution Explorer, right-click **BTAHL7V231Body**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="4fcfe-117">在添加新项对话框中，展开**BizTalk 项目项**，然后单击**BTAHL7 架构**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-117">In the Add New Item dialog box, expand **BizTalk Project Items**, and then click **BTAHL7 Schemas**.</span></span> <span data-ttu-id="4fcfe-118">在**模板**窗格中，单击**BTAHL7 架构**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-118">In the **Templates** pane, click **BTAHL7 Schemas**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="4fcfe-119">在**HL7 架构选择器**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4fcfe-119">In the **HL7 Schema Selector** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="4fcfe-120">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4fcfe-120">Use this</span></span>|<span data-ttu-id="4fcfe-121">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4fcfe-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4fcfe-122">**Message 类**</span><span class="sxs-lookup"><span data-stu-id="4fcfe-122">**Message Class**</span></span>|<span data-ttu-id="4fcfe-123">保留**V2.X**为选中状态。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-123">Keep **V2.X** as selected.</span></span>|  
    |<span data-ttu-id="4fcfe-124">**版本**</span><span class="sxs-lookup"><span data-stu-id="4fcfe-124">**Version**</span></span>|<span data-ttu-id="4fcfe-125">选择**2.3.1**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-125">Select **2.3.1**.</span></span>|  
    |<span data-ttu-id="4fcfe-126">**消息类型**</span><span class="sxs-lookup"><span data-stu-id="4fcfe-126">**Message Type**</span></span>|<span data-ttu-id="4fcfe-127">选择**ADT**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-127">Select **ADT**.</span></span>|  
    |<span data-ttu-id="4fcfe-128">**触发器事件**</span><span class="sxs-lookup"><span data-stu-id="4fcfe-128">**Trigger Event**</span></span>|<span data-ttu-id="4fcfe-129">选择**A03**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-129">Select **A03**.</span></span>|  
  
4.  <span data-ttu-id="4fcfe-130">单击**创建**若要将架构添加到项目，然后单击**取消**以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-130">Click **Create** to add the schema to the project, then click **Cancel** to close the dialog box.</span></span> <span data-ttu-id="4fcfe-131">请注意该 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 已添加到 BTAHL7V231Body 项目 ADT_A03_231_GLO_DEF.xsd 架构。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-131">Note that BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) has added the ADT_A03_231_GLO_DEF.xsd schema to the BTAHL7V231Body project.</span></span>  
  
### <a name="to-assign-a-strong-key-and-deploy"></a><span data-ttu-id="4fcfe-132">分配一个强密钥和部署</span><span class="sxs-lookup"><span data-stu-id="4fcfe-132">To assign a strong key and deploy</span></span>  
  
1.  <span data-ttu-id="4fcfe-133">在解决方案资源管理器，右键单击**BTAHL7V231Body**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-133">In Solution Explorer, right-click **BTAHL7V231Body**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="4fcfe-134">在 BTAHL7V231Body 属性页对话框中，单击**签名**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-134">In the BTAHL7V231Body Property Page dialog box, click **Signing**.</span></span>  
  
3.  <span data-ttu-id="4fcfe-135">检查**对程序集签名**复选框。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-135">Check **Sign the assembly** check box.</span></span>  
  
4.  <span data-ttu-id="4fcfe-136">在**选择强名称密钥文件**下拉列表中，选择**\<浏览...\>.**</span><span class="sxs-lookup"><span data-stu-id="4fcfe-136">In **Choose a strong name key file** drop down list select **\<Browse…\>.**</span></span>  
  
5.  <span data-ttu-id="4fcfe-137">浏览到  **\<*驱动器*\>: \Batching 教程 * *，选择**key.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-137">Browse to **\<*drive*\>:\Batching Tutorial**, select **key.snk**, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="4fcfe-138">在解决方案资源管理器，右键单击**BTAHL7V231Body**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-138">In Solution Explorer, right-click **BTAHL7V231Body**, and then click **Deploy**.</span></span> <span data-ttu-id="4fcfe-139">确保在输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-139">Ensure that a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4fcfe-140">如果未显示 successful-deploy 消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决你的架构。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-140">If a successful-deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="4fcfe-141">继续执行[步骤 4： 创建用于接受批处理消息接收端口](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)。</span><span class="sxs-lookup"><span data-stu-id="4fcfe-141">Proceed to [Step 4: Create a Receive Port for Accepting the Batch Message](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md).</span></span>