---
title: 步骤 3： 创建和部署的触发器事件 （消息） 项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, trigger events
- trigger events
ms.assetid: 5d21a923-fc2c-4d50-b146-daca0aa26e2a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49fd078f64cbd4163eef648f7a0d58fe6e8db6b2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961275"
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-project"></a><span data-ttu-id="f8551-102">步骤 3： 创建和部署的触发器事件 （消息） 项目</span><span class="sxs-lookup"><span data-stu-id="f8551-102">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>
<span data-ttu-id="f8551-103">在此步骤中，你的触发器事件消息创建架构。</span><span class="sxs-lookup"><span data-stu-id="f8551-103">In this step, you create the schema for your trigger event message.</span></span> <span data-ttu-id="f8551-104">例如，你可能在许可放电并传输系统 (ADT) 发送到医院信息系统 (HIS) 的一条消息。</span><span class="sxs-lookup"><span data-stu-id="f8551-104">For example, you might be the Admissions Discharge and Transfer system (ADT) who sends a message to the Hospital Information System (HIS).</span></span> <span data-ttu-id="f8551-105">你需要此架构来定义你的消息的格式。</span><span class="sxs-lookup"><span data-stu-id="f8551-105">You need this schema to define the format of your message.</span></span>  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a><span data-ttu-id="f8551-106">若要创建触发器事件消息的项目</span><span class="sxs-lookup"><span data-stu-id="f8551-106">To create the project for the trigger event message</span></span>  
  
1.  <span data-ttu-id="f8551-107">在[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]上**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="f8551-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, then click **Project**.</span></span>  
  
2.  <span data-ttu-id="f8551-108">在新建项目对话框中，在**项目类型**部分中，展开**BizTalk 项目**，然后单击**BTAHL7Projects**。</span><span class="sxs-lookup"><span data-stu-id="f8551-108">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3.  <span data-ttu-id="f8551-109">在模板部分中，单击**空 BTAHL7 项目**中**名称**框中，键入**BTAHL7V231Body 项目**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f8551-109">In the Templates section, click **Empty BTAHL7 Project**, in the **Name** box, type **BTAHL7V231Body Project**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="f8551-110">在解决方案资源管理器，新的项目，节点下右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="f8551-110">In Solution Explorer, under the node for your new project, right-click **References**, and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="f8551-111">在添加引用对话框中，在**项目**选项卡上，选择**BTAHL7V231Common Project1**，单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f8551-111">In the Add Reference dialog box, on the **Projects** tab, select **BTAHL7V231Common Project1**, click **Add**, and then click **OK**.</span></span>  
  
## <a name="step-3a-add-the-schema"></a><span data-ttu-id="f8551-112">步骤 3A： 将架构添加</span><span class="sxs-lookup"><span data-stu-id="f8551-112">Step 3A: Add the Schema</span></span>  
 <span data-ttu-id="f8551-113">使用以下过程将新架构添加到项目。</span><span class="sxs-lookup"><span data-stu-id="f8551-113">Use the following procedure to add the new schema to the project.</span></span>  
  
#### <a name="to-add-the-schema-to-the-project"></a><span data-ttu-id="f8551-114">若要将架构添加到项目</span><span class="sxs-lookup"><span data-stu-id="f8551-114">To add the schema to the project</span></span>  
  
1.  <span data-ttu-id="f8551-115">在解决方案资源管理器，右键单击**BTAHL7V231Body 项目**，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="f8551-115">In Solution Explorer, right-click **BTAHL7V231Body Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="f8551-116">在添加新项对话框中，在**类别**部分中，展开**BizTalk 项目项**，然后选择**BTAHL7 架构**。</span><span class="sxs-lookup"><span data-stu-id="f8551-116">In the Add New Item dialog box, in the **Categories** section, expand **BizTalk Project Items**, and then select **BTAHL7 Schemas**.</span></span>  
  
3.  <span data-ttu-id="f8551-117">在模板部分中，双击**BTAHL7 架构**。</span><span class="sxs-lookup"><span data-stu-id="f8551-117">In the Templates section, double-click **BTAHL7 Schemas**.</span></span>  
  
4.  <span data-ttu-id="f8551-118">在 HL7 架构选择器对话框中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f8551-118">In the HL7 Schema Selector dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="f8551-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f8551-119">Use this</span></span>|<span data-ttu-id="f8551-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f8551-120">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f8551-121">**Message 类**</span><span class="sxs-lookup"><span data-stu-id="f8551-121">**Message Class**</span></span>|<span data-ttu-id="f8551-122">保留默认的**V2.X**选。</span><span class="sxs-lookup"><span data-stu-id="f8551-122">Leave the default of **V2.X** selected.</span></span>|  
    |<span data-ttu-id="f8551-123">**版本**</span><span class="sxs-lookup"><span data-stu-id="f8551-123">**Version**</span></span>|<span data-ttu-id="f8551-124">选择**2.3.1**。</span><span class="sxs-lookup"><span data-stu-id="f8551-124">Select **2.3.1**.</span></span>|  
    |<span data-ttu-id="f8551-125">**消息类型**</span><span class="sxs-lookup"><span data-stu-id="f8551-125">**Message Type**</span></span>|<span data-ttu-id="f8551-126">选择**ADT**。</span><span class="sxs-lookup"><span data-stu-id="f8551-126">Select **ADT**.</span></span>|  
    |<span data-ttu-id="f8551-127">**触发器事件**</span><span class="sxs-lookup"><span data-stu-id="f8551-127">**Trigger Event**</span></span>|<span data-ttu-id="f8551-128">选择**A03**。</span><span class="sxs-lookup"><span data-stu-id="f8551-128">Select **A03**.</span></span>|  
  
5.  <span data-ttu-id="f8551-129">单击**完成**将该架构添加到项目。</span><span class="sxs-lookup"><span data-stu-id="f8551-129">Click **Finish** to add the schema to the project.</span></span>  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="f8551-130">步骤 3B： 向程序集分配强密钥和部署</span><span class="sxs-lookup"><span data-stu-id="f8551-130">Step 3B: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="f8551-131">使用以下过程向程序集分配强密钥，然后将部署程序集。</span><span class="sxs-lookup"><span data-stu-id="f8551-131">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="f8551-132">分配一个强密钥和部署程序集</span><span class="sxs-lookup"><span data-stu-id="f8551-132">To assign a strong key and deploy the assembly</span></span>  
  
1.  <span data-ttu-id="f8551-133">在解决方案资源管理器，右键单击**BTAHL7V231Body 项目**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f8551-133">In Solution Explorer, right-click **BTAHL7V231Body Project**, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f8551-134">在项目属性页页中，单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="f8551-134">In the Project Property Pages page, click **Assembly**.</span></span>  
  
3.  <span data-ttu-id="f8551-135">在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="f8551-135">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (**…**) button.</span></span>  
  
4.  <span data-ttu-id="f8551-136">在程序集密钥文件对话框中，浏览到\<*驱动器*\>: files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\End 端到端教程中，单击**key.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="f8551-136">In the Assembly Key File dialog box, browse to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="f8551-137">在项目属性页对话框中，单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f8551-137">In the Project Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
6.  <span data-ttu-id="f8551-138">在解决方案资源管理器中右键单击**BTAHL7V231Body 项目**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="f8551-138">In Solution Explorer right-click **BTAHL7V231Body Project**, and then click **Deploy**.</span></span> <span data-ttu-id="f8551-139">确保输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="f8551-139">Ensure a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8551-140">如果未显示成功部署消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决你的架构。</span><span class="sxs-lookup"><span data-stu-id="f8551-140">If a successful deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
 <span data-ttu-id="f8551-141">继续执行[步骤 4： 创建用于接受 ADT 接收端口 ^ A03 消息从 ADT 系统使用 MLLP 适配器](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)。</span><span class="sxs-lookup"><span data-stu-id="f8551-141">Proceed to [Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md).</span></span>