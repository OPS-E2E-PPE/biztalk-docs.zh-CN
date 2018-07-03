---
title: 步骤 4： 创建架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, schemas
- creating, schemas
- schemas, creating
ms.assetid: 81b1f538-9743-433a-87f9-a423dcb868c8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 914efbfe8632bb727724a5115f6423b9abb8f54f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000934"
---
# <a name="step-4-create-the-schemas"></a><span data-ttu-id="d8a6d-102">步骤 4： 创建架构</span><span class="sxs-lookup"><span data-stu-id="d8a6d-102">Step 4: Create the Schemas</span></span>
<span data-ttu-id="d8a6d-103">在此步骤中，创建一个新的项目 (**BTAHL7 项目**)，其中包含此项目的项目： 架构、 映射和业务流程。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-103">In this step, you create a new project (**BTAHL7 Project**) that contains the artifacts for this project: the schemas, map, and orchestration.</span></span> <span data-ttu-id="d8a6d-104">然后，创建一个架构 (**Doorbell.xsd**) 传入的 XML 编码的消息，并选择现有的架构 (**ADT_A04_22_GLO_DEF.xsd**) 对于传出 HL7 编码的消息。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-104">You then create a schema (**Doorbell.xsd**) for the incoming XML-encoded message, and select an existing schema (**ADT_A04_22_GLO_DEF.xsd**) for the outgoing HL7-encoded message.</span></span> <span data-ttu-id="d8a6d-105">使用这些架构来定义在业务流程内交换消息的结构。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-105">You use these schemas to define the structure of the messages that you exchange within the orchestration.</span></span>  

### <a name="to-create-the-schemas"></a><span data-ttu-id="d8a6d-106">若要创建架构</span><span class="sxs-lookup"><span data-stu-id="d8a6d-106">To create the schemas</span></span>  

1. <span data-ttu-id="d8a6d-107">在 **“文件”** 菜单上，指向 **“新建”**，再单击 **“项目”**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-107">On the **File** menu, point to **New**, and then click **Project**.</span></span>  

2. <span data-ttu-id="d8a6d-108">在新建项目对话框中，展开**BizTalk 项目**文件夹，，然后单击**BTAHL7Projects**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-108">In the New Project dialog box, expand the **BizTalk Projects** folder, and then click the **BTAHL7Projects** folder.</span></span>  

3. <span data-ttu-id="d8a6d-109">在中**模板**窗格中，单击**BTAHL7 的空项目**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-109">In the **Templates** pane, click **Empty BTAHL7 Project**.</span></span>  

4. <span data-ttu-id="d8a6d-110">在中**名称**字段中，键入**BTAHL7 项目**作为项目名称。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-110">In the **Name** field, type **BTAHL7 Project** as the project name.</span></span>  

5. <span data-ttu-id="d8a6d-111">在中**解决方案**字段中，选择**将添加到解决方案**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-111">In the **Solution** field, select **Add to Solution**.</span></span>  

6. <span data-ttu-id="d8a6d-112">在中**位置**字段中，确认 **\<*驱动器*\>: \Tutorial\BTAHL7V22Common**的路径。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-112">In the **Location** field, verify that **\<*drive*\>:\Tutorial\BTAHL7V22Common** is the path.</span></span>  

7. <span data-ttu-id="d8a6d-113">单击**确定**打开新项目。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-113">Click **OK** to open the new project.</span></span>  

   > [!NOTE]
   >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="d8a6d-114"> 将新项目添加到解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-114"> adds a new project to Solution Explorer.</span></span> <span data-ttu-id="d8a6d-115">它还将添加的项目文件夹，并创建中的文件\<*驱动器*\>: \Tutorial\\**BTAHL7V22Common**项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-115">It also adds the project folder and creates files in the \<*drive*\>:\Tutorial\\**BTAHL7V22Common** Project folder.</span></span>  

8. <span data-ttu-id="d8a6d-116">在解决方案资源管理器中右键单击**BTAHL7 项目**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-116">In Solution Explorer, right-click the **BTAHL7 Project** project, point to **Add**, and then click **New Item**.</span></span>  

9. <span data-ttu-id="d8a6d-117">在添加新项-BTAHL7 项目对话框中，在**类别**窗格中，单击**架构文件**，然后在**模板**窗格中，单击**架构**.</span><span class="sxs-lookup"><span data-stu-id="d8a6d-117">In the Add New Item - BTAHL7 Project dialog box, in the **Categories** pane, click **Schema Files**, and in the **Templates** pane, click **Schema**.</span></span>  

10. <span data-ttu-id="d8a6d-118">在中**名称**字段中，键入**Doorbell.xsd**命名架构。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-118">In the **Name** field, type **Doorbell.xsd** to name the schema.</span></span>  

11. <span data-ttu-id="d8a6d-119">单击**添加**BizTalk 编辑器中打开空白的架构。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-119">Click **Add** to open the blank schema in BizTalk Editor.</span></span>  

12. <span data-ttu-id="d8a6d-120">在中**\<架构\>** 树中，右键单击**根**节点，并单击**重命名**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-120">In the **\<Schema\>** tree, right-click the **Root** node, and then click **Rename**.</span></span>  

13. <span data-ttu-id="d8a6d-121">类型**DoorbellRoot**作为新名称，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-121">Type **DoorbellRoot** as the new name, and then press **Enter**.</span></span>  

14. <span data-ttu-id="d8a6d-122">右键单击**DoorbellRoot**节点，指向**插入 Schema 节点**，然后单击**子字段元素**添加以下字段 （重复此步骤对于每个字段元素）：</span><span class="sxs-lookup"><span data-stu-id="d8a6d-122">Right-click the **DoorbellRoot** node, point to **Insert Schema Node**, and then click **Child Field Element** to add the following fields (repeat this step for each field element):</span></span>  

    -   <span data-ttu-id="d8a6d-123">**FirstName**</span><span class="sxs-lookup"><span data-stu-id="d8a6d-123">**FirstName**</span></span>  

    -   <span data-ttu-id="d8a6d-124">**MiddleName**</span><span class="sxs-lookup"><span data-stu-id="d8a6d-124">**MiddleName**</span></span>  

    -   <span data-ttu-id="d8a6d-125">**姓氏**</span><span class="sxs-lookup"><span data-stu-id="d8a6d-125">**LastName**</span></span>  

    -   <span data-ttu-id="d8a6d-126">**SSN**</span><span class="sxs-lookup"><span data-stu-id="d8a6d-126">**SSN**</span></span>  

15. <span data-ttu-id="d8a6d-127">在解决方案资源管理器中右键单击**BTAHL7 项目**，依次指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-127">In Solution Explorer, right-click **BTAHL7 Project**, point to **Add**, and then click **New Item**.</span></span>  

16. <span data-ttu-id="d8a6d-128">在添加新项-BTAHL7 项目对话框中，在**类别**窗格中，单击**BTAHL7 架构**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-128">In the Add New Item - BTAHL7 Project dialog box, in the **Categories** pane, click **BTAHL7 Schemas**, and then click **Add**.</span></span>  

17. <span data-ttu-id="d8a6d-129">HL7 架构选择器对话框中，在中**消息类**框中，选择**V2.X**，然后在**架构的详细信息**窗格中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d8a6d-129">In the HL7 Schema Selector dialog box, in the **Message Class** box, select **V2.X**, and in the **Schema Details** pane, do the following:</span></span>  


    |     <span data-ttu-id="d8a6d-130">使用此选项</span><span class="sxs-lookup"><span data-stu-id="d8a6d-130">Use this</span></span>      |                                     <span data-ttu-id="d8a6d-131">执行的操作</span><span class="sxs-lookup"><span data-stu-id="d8a6d-131">To do this</span></span>                                     |
    |-------------------|------------------------------------------------------------------------------------|
    |    <span data-ttu-id="d8a6d-132">**版本(Version)**</span><span class="sxs-lookup"><span data-stu-id="d8a6d-132">**Version**</span></span>    |    <span data-ttu-id="d8a6d-133">选择 HL7 消息的版本号。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-133">Select the version number of the HL7 message.</span></span> <span data-ttu-id="d8a6d-134">在本教程中，使用**2.2**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-134">In this tutorial, use **2.2**.</span></span>    |
    | <span data-ttu-id="d8a6d-135">**消息类型**</span><span class="sxs-lookup"><span data-stu-id="d8a6d-135">**Message Type**</span></span>  |           <span data-ttu-id="d8a6d-136">选择 HL7 消息的类型。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-136">Select the type of HL7 message.</span></span> <span data-ttu-id="d8a6d-137">在本教程中，使用**ADT**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-137">In this tutorial, use **ADT**.</span></span>           |
    | <span data-ttu-id="d8a6d-138">**触发器事件**</span><span class="sxs-lookup"><span data-stu-id="d8a6d-138">**Trigger Event**</span></span> | <span data-ttu-id="d8a6d-139">选择 HL7 消息的触发器事件值。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-139">Select the Trigger Event value for the HL7 message.</span></span> <span data-ttu-id="d8a6d-140">在本教程中，使用**A04**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-140">In this tutorial, use **A04**.</span></span> |


18. <span data-ttu-id="d8a6d-141">单击**完成**ADT_A04_22_GLO_DEF.xsd （注册患者） 架构添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-141">Click **Finish** to add the ADT_A04_22_GLO_DEF.xsd (Register Patient) schema to your project.</span></span> <span data-ttu-id="d8a6d-142">关闭 HL7 架构选择器对话框。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-142">Close the HL7 Schema Selector dialog box.</span></span>  

19. <span data-ttu-id="d8a6d-143">在解决方案资源管理器下**BTAHL7 项目**，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-143">In Solution Explorer, under **BTAHL7 Project**, right-click **References** and then click **Add Reference**.</span></span>  

20. <span data-ttu-id="d8a6d-144">在添加引用对话框中，在**项目**选项卡上，选择**BTAHL7V22Common**项目，然后单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-144">In the Add Reference dialog box, on the **Projects** tab, select the **BTAHL7V22Common** project, click **Add**, and then click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="d8a6d-145">这会添加对原始项目的引用，以便[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]正确识别 HL7 架构。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-145">This adds a reference to the original project so that [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] recognizes the HL7 schemas correctly.</span></span>  

21. <span data-ttu-id="d8a6d-146">在解决方案资源管理器下**BTAHL7 项目**，右键单击**引用**，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-146">In Solution Explorer, under **BTAHL7 Project**, right-click **References** and then click **Add Reference**.</span></span>  

22. <span data-ttu-id="d8a6d-147">在添加引用对话框中，单击**浏览**选项卡。在中**查找范围**框中，将移动到\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator HL7\SDK\End 端到端教程\Tutorial_BTAHL7Drop\Bin。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-147">In the Add Reference dialog box, click the **Browse** tab. In the **Look In** box, move to \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\End-to-End Tutorial\Tutorial_BTAHL7Drop\Bin.</span></span> <span data-ttu-id="d8a6d-148">单击**Microsoft.Solutions.BTAHL7.HL7Schemas.dll**，单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-148">Click **Microsoft.Solutions.BTAHL7.HL7Schemas.dll**, click **Add**, and then click **OK**.</span></span>  

    <span data-ttu-id="d8a6d-149">请继续执行[步骤 5： 提升架构属性](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d8a6d-149">Proceed to [Step 5: Promote Schema Properties](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="d8a6d-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8a6d-150">See Also</span></span>  
 [<span data-ttu-id="d8a6d-151">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="d8a6d-151">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)