---
title: 步骤 3： 创建和部署触发器事件 （消息） 项目 |Microsoft Docs
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
ms.openlocfilehash: deb9d6160fc0b094f0af6f75ab4ab8e5be22462c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998686"
---
# <a name="step-3-create-and-deploy-a-trigger-event-message-project"></a><span data-ttu-id="5c580-102">步骤 3： 创建和部署触发器事件 （消息） 项目</span><span class="sxs-lookup"><span data-stu-id="5c580-102">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>
<span data-ttu-id="5c580-103">在此步骤中，您的触发器事件消息创建架构。</span><span class="sxs-lookup"><span data-stu-id="5c580-103">In this step, you create the schema for your trigger event message.</span></span> <span data-ttu-id="5c580-104">例如，可能是病人入院出院事项和传输系统 (ADT) 发送消息到医院信息系统 (HIS)。</span><span class="sxs-lookup"><span data-stu-id="5c580-104">For example, you might be the Admissions Discharge and Transfer system (ADT) who sends a message to the Hospital Information System (HIS).</span></span> <span data-ttu-id="5c580-105">需要此架构来定义您的消息的格式。</span><span class="sxs-lookup"><span data-stu-id="5c580-105">You need this schema to define the format of your message.</span></span>  
  
### <a name="to-create-the-project-for-the-trigger-event-message"></a><span data-ttu-id="5c580-106">若要创建触发器事件消息的项目</span><span class="sxs-lookup"><span data-stu-id="5c580-106">To create the project for the trigger event message</span></span>  
  
1. <span data-ttu-id="5c580-107">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，然后在**文件**菜单中，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="5c580-107">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, then click **Project**.</span></span>  
  
2. <span data-ttu-id="5c580-108">在新建项目对话框中，在**项目类型**部分中，展开**BizTalk 项目**，然后单击**BTAHL7Projects**。</span><span class="sxs-lookup"><span data-stu-id="5c580-108">In the New Project dialog box, in the **Project Types** section, expand **BizTalk Projects**, and then click **BTAHL7Projects**.</span></span>  
  
3. <span data-ttu-id="5c580-109">在模板部分中，单击**BTAHL7 的空项目**，在**名称**框中，键入**BTAHL7V231Body 项目**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c580-109">In the Templates section, click **Empty BTAHL7 Project**, in the **Name** box, type **BTAHL7V231Body Project**, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="5c580-110">在解决方案资源管理器，为新项目，在节点下右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="5c580-110">In Solution Explorer, under the node for your new project, right-click **References**, and then click **Add Reference**.</span></span>  
  
5. <span data-ttu-id="5c580-111">在添加引用对话框中，在**项目**选项卡上，选择**BTAHL7V231Common Project1**，单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="5c580-111">In the Add Reference dialog box, on the **Projects** tab, select **BTAHL7V231Common Project1**, click **Add**, and then click **OK**.</span></span>  
  
## <a name="step-3a-add-the-schema"></a><span data-ttu-id="5c580-112">步骤 3A： 将架构添加</span><span class="sxs-lookup"><span data-stu-id="5c580-112">Step 3A: Add the Schema</span></span>  
 <span data-ttu-id="5c580-113">使用以下过程将新的架构添加到项目。</span><span class="sxs-lookup"><span data-stu-id="5c580-113">Use the following procedure to add the new schema to the project.</span></span>  
  
#### <a name="to-add-the-schema-to-the-project"></a><span data-ttu-id="5c580-114">若要将架构添加到项目</span><span class="sxs-lookup"><span data-stu-id="5c580-114">To add the schema to the project</span></span>  
  
1.  <span data-ttu-id="5c580-115">在解决方案资源管理器中右键单击**BTAHL7V231Body 项目**，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="5c580-115">In Solution Explorer, right-click **BTAHL7V231Body Project**, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="5c580-116">在添加新项对话框中，在**类别**部分中，展开**BizTalk 项目项**，然后选择**BTAHL7 架构**。</span><span class="sxs-lookup"><span data-stu-id="5c580-116">In the Add New Item dialog box, in the **Categories** section, expand **BizTalk Project Items**, and then select **BTAHL7 Schemas**.</span></span>  
  
3.  <span data-ttu-id="5c580-117">在模板部分中，双击**BTAHL7 架构**。</span><span class="sxs-lookup"><span data-stu-id="5c580-117">In the Templates section, double-click **BTAHL7 Schemas**.</span></span>  
  
4.  <span data-ttu-id="5c580-118">在 HL7 架构选择器对话框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5c580-118">In the HL7 Schema Selector dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="5c580-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="5c580-119">Use this</span></span>|<span data-ttu-id="5c580-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="5c580-120">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="5c580-121">**Message 类**</span><span class="sxs-lookup"><span data-stu-id="5c580-121">**Message Class**</span></span>|<span data-ttu-id="5c580-122">保留默认值为**V2.X**选定。</span><span class="sxs-lookup"><span data-stu-id="5c580-122">Leave the default of **V2.X** selected.</span></span>|  
    |<span data-ttu-id="5c580-123">**版本(Version)**</span><span class="sxs-lookup"><span data-stu-id="5c580-123">**Version**</span></span>|<span data-ttu-id="5c580-124">选择**2.3.1**。</span><span class="sxs-lookup"><span data-stu-id="5c580-124">Select **2.3.1**.</span></span>|  
    |<span data-ttu-id="5c580-125">**消息类型**</span><span class="sxs-lookup"><span data-stu-id="5c580-125">**Message Type**</span></span>|<span data-ttu-id="5c580-126">选择**ADT**。</span><span class="sxs-lookup"><span data-stu-id="5c580-126">Select **ADT**.</span></span>|  
    |<span data-ttu-id="5c580-127">**触发器事件**</span><span class="sxs-lookup"><span data-stu-id="5c580-127">**Trigger Event**</span></span>|<span data-ttu-id="5c580-128">选择**A03**。</span><span class="sxs-lookup"><span data-stu-id="5c580-128">Select **A03**.</span></span>|  
  
5.  <span data-ttu-id="5c580-129">单击**完成**将该架构添加到项目。</span><span class="sxs-lookup"><span data-stu-id="5c580-129">Click **Finish** to add the schema to the project.</span></span>  
  
## <a name="step-3b-assign-a-strong-key-to-the-assembly-and-deploy"></a><span data-ttu-id="5c580-130">步骤 3B： 对程序集分配强密钥并将其部署</span><span class="sxs-lookup"><span data-stu-id="5c580-130">Step 3B: Assign a Strong Key to the Assembly and Deploy</span></span>  
 <span data-ttu-id="5c580-131">使用以下过程来对程序集分配强密钥并随后部署该程序集。</span><span class="sxs-lookup"><span data-stu-id="5c580-131">Use the following procedure to assign a strong key to the assembly and then deploy the assembly.</span></span>  
  
#### <a name="to-assign-a-strong-key-and-deploy-the-assembly"></a><span data-ttu-id="5c580-132">若要分配一个强密钥并将其部署该程序集</span><span class="sxs-lookup"><span data-stu-id="5c580-132">To assign a strong key and deploy the assembly</span></span>  
  
1. <span data-ttu-id="5c580-133">在解决方案资源管理器中右键单击**BTAHL7V231Body 项目**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="5c580-133">In Solution Explorer, right-click **BTAHL7V231Body Project**, and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="5c580-134">在项目属性页页中，单击**程序集**。</span><span class="sxs-lookup"><span data-stu-id="5c580-134">In the Project Property Pages page, click **Assembly**.</span></span>  
  
3. <span data-ttu-id="5c580-135">在右窗格中，向下滚动到**强名称**部分中，单击右侧的字段**程序集密钥文件**，然后单击省略号 (**...**) 按钮。</span><span class="sxs-lookup"><span data-stu-id="5c580-135">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (**…**) button.</span></span>  
  
4. <span data-ttu-id="5c580-136">在程序集密钥文件对话框中，浏览到\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator HL7\SDK\End 端到端教程中，单击**key.snk**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="5c580-136">In the Assembly Key File dialog box, browse to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial, click **key.snk**, and then click **Open**.</span></span>  
  
5. <span data-ttu-id="5c580-137">在项目属性页对话框中，单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5c580-137">In the Project Property Pages dialog box, click **OK** to save your changes.</span></span>  
  
6. <span data-ttu-id="5c580-138">在解决方案资源管理器中右键单击**BTAHL7V231Body 项目**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="5c580-138">In Solution Explorer right-click **BTAHL7V231Body Project**, and then click **Deploy**.</span></span> <span data-ttu-id="5c580-139">请确保在输出窗口中将显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="5c580-139">Ensure a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5c580-140">如果未显示成功部署消息，使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来解决您的架构。</span><span class="sxs-lookup"><span data-stu-id="5c580-140">If a successful deploy message does not appear, use [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to troubleshoot your schemas.</span></span>  
  
   <span data-ttu-id="5c580-141">请继续执行[步骤 4： 创建接收端口用于接收 ADT ^ A03 消息从 ADT 系统使用 MLLP 适配器](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)。</span><span class="sxs-lookup"><span data-stu-id="5c580-141">Proceed to [Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md).</span></span>