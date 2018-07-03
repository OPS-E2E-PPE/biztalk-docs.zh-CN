---
title: 创建和部署 A4SWIFT 管道 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- deploying, pipelines
- pipelines, deploying
- pipelines, creating
ms.assetid: 2a614510-7e15-4e88-9012-fc019d3aefee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d337b97dfb1973ef10c113ae0a206a51dcd63b1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002446"
---
# <a name="creating-and-deploying-a4swift-pipelines"></a><span data-ttu-id="a7198-102">创建和部署 A4SWIFT 管道</span><span class="sxs-lookup"><span data-stu-id="a7198-102">Creating and Deploying A4SWIFT Pipelines</span></span>
<span data-ttu-id="a7198-103">下图中所示，请执行以下步骤来创建和部署消息修复和新提交的 SWIFT 管道。</span><span class="sxs-lookup"><span data-stu-id="a7198-103">Perform the following steps to create and deploy SWIFT pipelines for message repair and new submission, as shown in the following figure.</span></span>  

 <span data-ttu-id="a7198-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-pipeline-configuration.gif "A4SWIFT_Pipeline_Configuration")</span><span class="sxs-lookup"><span data-stu-id="a7198-104">![](../../adapters-and-accelerators/accelerator-swift/media/a4swift-pipeline-configuration.gif "A4SWIFT_Pipeline_Configuration")</span></span>  

 <span data-ttu-id="a7198-105">**摘要**</span><span class="sxs-lookup"><span data-stu-id="a7198-105">**Summary**</span></span>  

 <span data-ttu-id="a7198-106">部署了以下架构：</span><span class="sxs-lookup"><span data-stu-id="a7198-106">Deploy the following schemas:</span></span>  

-   <span data-ttu-id="a7198-107">自定义接收管道，其中包含 SWIFT 反汇编程序。</span><span class="sxs-lookup"><span data-stu-id="a7198-107">Custom receive pipeline with the SWIFT Disassembler.</span></span> <span data-ttu-id="a7198-108">BRE 验证和 XML 验证属性设置为 True，并将 SWIFT 标头架构属性为 （无）。</span><span class="sxs-lookup"><span data-stu-id="a7198-108">Set BRE Validation and XML Validation properties to True, and the SWIFT Header Schema property to (None).</span></span>  

-   <span data-ttu-id="a7198-109">自定义发送管道，其中包含 SWIFT 汇编程序</span><span class="sxs-lookup"><span data-stu-id="a7198-109">Custom send pipeline with the SWIFT Assembler</span></span>  

### <a name="to-create-a-pipeline-project"></a><span data-ttu-id="a7198-110">若要创建管道项目</span><span class="sxs-lookup"><span data-stu-id="a7198-110">To create a pipeline project</span></span>  

1. <span data-ttu-id="a7198-111">在 Visual Studio 中，单击**文件**，依次指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="a7198-111">In Visual Studio, click **File**, point to **New**, and then click **Project**.</span></span>  

2. <span data-ttu-id="a7198-112">在新建项目对话框中，在**项目类型**窗格中，选择**BizTalk 项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="a7198-112">In the New Project dialog box, in the **Project types** pane, select the **BizTalk Projects** folder.</span></span>  

3. <span data-ttu-id="a7198-113">在中**模板**窗格中，选择**空的 BizTalk Server 项目**。</span><span class="sxs-lookup"><span data-stu-id="a7198-113">In the **Templates** pane, select **Empty BizTalk Server Project**.</span></span>  

4. <span data-ttu-id="a7198-114">在中**名称**框中，键入所需的项目名称的名称。</span><span class="sxs-lookup"><span data-stu-id="a7198-114">In the **Name** box, type the name you want for the project name.</span></span>  

5. <span data-ttu-id="a7198-115">在中**解决方案**框中，选择**将添加到解决方案**。</span><span class="sxs-lookup"><span data-stu-id="a7198-115">In the **Solution** box, select **Add to Solution**.</span></span> <span data-ttu-id="a7198-116">在中**位置**框中，输入你在中创建架构项目的位置[部署 A4SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="a7198-116">In the **Location** box, enter the location of the schema project that you created in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span></span>  

6. <span data-ttu-id="a7198-117">单击**确定**打开新项目。</span><span class="sxs-lookup"><span data-stu-id="a7198-117">Click **OK** to open the new project.</span></span>  
   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="a7198-118">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] 将新项目添加到解决方案资源管理器，并指定的文件夹中创建的项目文件夹和文件。</span><span class="sxs-lookup"><span data-stu-id="a7198-118">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] adds a new project to Solution Explorer, and creates the project folder and files in the folder specified.</span></span>  

7. <span data-ttu-id="a7198-119">创建并分配到项目的强密钥文件。</span><span class="sxs-lookup"><span data-stu-id="a7198-119">Create and assign a strong key file to the project.</span></span> <span data-ttu-id="a7198-120">有关详细信息，请参阅"创建强名称的 SWIFT 项目"中[部署 A4SWIFT 架构](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="a7198-120">For more information, see "To create a strong-named SWIFT project" in [Deploying A4SWIFT Schemas](../../adapters-and-accelerators/accelerator-swift/deploying-a4swift-schemas.md).</span></span>  

### <a name="to-add-a-custom-receive-pipeline"></a><span data-ttu-id="a7198-121">若要添加自定义接收管道</span><span class="sxs-lookup"><span data-stu-id="a7198-121">To add a custom receive pipeline</span></span>  

1. <span data-ttu-id="a7198-122">在解决方案资源管理器中右键单击管道项目，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="a7198-122">In Solution Explorer, right-click your pipeline project, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="a7198-123">在添加新项对话框中，单击**管道文件**在类别窗格中，然后选择**接收管道**从模板窗格。</span><span class="sxs-lookup"><span data-stu-id="a7198-123">In the Add New Item dialog box, click **Pipeline Files** in the Categories pane, and then select **Receive Pipeline** from the Templates pane.</span></span>  

3. <span data-ttu-id="a7198-124">在中**名称**框中，键入管道的名称。</span><span class="sxs-lookup"><span data-stu-id="a7198-124">In the **Name** box, type a name for the pipeline.</span></span>  

4. <span data-ttu-id="a7198-125">单击**添加**若要在 BizTalk 管道设计器中打开空白的管道。</span><span class="sxs-lookup"><span data-stu-id="a7198-125">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  

5. <span data-ttu-id="a7198-126">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**视图**，然后**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="a7198-126">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  

6. <span data-ttu-id="a7198-127">从**BizTalk 管道组件工具箱**，拖动**SWIFT 反汇编程序**到**拖至此处**下面的框**拆装**阶段在形状**BizTalk 管道设计器**。</span><span class="sxs-lookup"><span data-stu-id="a7198-127">From the **BizTalk Pipeline Components Toolbox**, drag the **SWIFT Disassembler** to the **Drop Here** box below the **Disassemble** stage shape in **BizTalk Pipeline Designer**.</span></span> <span data-ttu-id="a7198-128">将保留**SWIFT 反汇编程序**中为选中状态**BizTalk 管道设计器**。</span><span class="sxs-lookup"><span data-stu-id="a7198-128">Leave the **SWIFT Disassembler** as selected in the **BizTalk Pipeline Designer**.</span></span>  

7. <span data-ttu-id="a7198-129">在中**属性**，确认**BRE 验证**并**XML 验证**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="a7198-129">In **Properties**, verify that the **BRE Validation** and **XML Validation** properties are set to **True**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a7198-130">SWIFT 标头架构属性应设置为 **（无）**。</span><span class="sxs-lookup"><span data-stu-id="a7198-130">The SWIFT Header Schema property should be set to **(None)**.</span></span>  

8. <span data-ttu-id="a7198-131">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**文件**，然后**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="a7198-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then **Save All**.</span></span>  

### <a name="to-add-a-custom-send-pipeline"></a><span data-ttu-id="a7198-132">若要添加自定义发送管道</span><span class="sxs-lookup"><span data-stu-id="a7198-132">To add a custom send pipeline</span></span>  

1. <span data-ttu-id="a7198-133">在解决方案资源管理器中右键单击**SWIFTPipelines**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="a7198-133">In Solution Explorer, right-click the **SWIFTPipelines** project, point to **Add**, and then click **New Item**.</span></span>  

2. <span data-ttu-id="a7198-134">在添加新项对话框中，验证是否**管道文件**所选的类别窗格中，并选择**发送管道**从模板窗格。</span><span class="sxs-lookup"><span data-stu-id="a7198-134">In the Add New Item dialog box, verify that **Pipeline Files** is selected in the Categories pane, and then select **Send Pipeline** from the Templates pane.</span></span>  

3. <span data-ttu-id="a7198-135">在中**名称**框中，键入管道的名称。</span><span class="sxs-lookup"><span data-stu-id="a7198-135">In the **Name** box, type a name for the pipeline.</span></span>  

4. <span data-ttu-id="a7198-136">单击**添加**若要在 BizTalk 管道设计器中打开空白的管道。</span><span class="sxs-lookup"><span data-stu-id="a7198-136">Click **Add** to open the blank pipeline in BizTalk Pipeline Designer.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a7198-137">BizTalk 管道设计器中显示空管道。</span><span class="sxs-lookup"><span data-stu-id="a7198-137">An empty pipeline appears in the BizTalk Pipeline Designer.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="a7198-138"> 将新的管道添加到解决方案资源管理器中，SWIFTPipelines 项目下。</span><span class="sxs-lookup"><span data-stu-id="a7198-138"> adds the new pipeline to Solution Explorer under the SWIFTPipelines project.</span></span>  

5. <span data-ttu-id="a7198-139">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**视图**，然后**工具箱**。</span><span class="sxs-lookup"><span data-stu-id="a7198-139">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **View** and then **Toolbox**.</span></span>  

6. <span data-ttu-id="a7198-140">在中**BizTalk 管道组件工具箱**，拖动**SWIFT 汇编程序**到**拖至此处**下面的框**组装**阶段中的形状**BizTalk 管道设计器**。</span><span class="sxs-lookup"><span data-stu-id="a7198-140">In the **BizTalk Pipeline Components Toolbox**, drag **SWIFT Assembler** to the **Drop Here** box below the **Assemble** stage shape in **BizTalk Pipeline Designer**.</span></span>  

7. <span data-ttu-id="a7198-141">在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，单击**文件**，然后**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="a7198-141">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], click **File**, and then **Save All**.</span></span>  

8. <span data-ttu-id="a7198-142">右键单击管道项目，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="a7198-142">Right click the pipelines project, and then click **Build**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a7198-143">在编译过程中，不应看到任何失败。</span><span class="sxs-lookup"><span data-stu-id="a7198-143">During the compilation process, you should not see any failures.</span></span> <span data-ttu-id="a7198-144">如果这样做，请检查错误的源、 更正，然后重新生成该项目。</span><span class="sxs-lookup"><span data-stu-id="a7198-144">If you do, check the source of the error, correct it and then re-build the project.</span></span> <span data-ttu-id="a7198-145">但是，您可以看到警告。</span><span class="sxs-lookup"><span data-stu-id="a7198-145">You may, however, see warnings.</span></span> <span data-ttu-id="a7198-146">您可以更正导致警告的条件。</span><span class="sxs-lookup"><span data-stu-id="a7198-146">You can correct the condition leading to the warnings.</span></span> <span data-ttu-id="a7198-147">详细信息，请参阅"生成管道项目可能会导致警告"中[其他已知问题](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6)。</span><span class="sxs-lookup"><span data-stu-id="a7198-147">For more information, see "Building a pipeline project may result in warnings" in [Miscellaneous Known Issues](http://msdn.microsoft.com/library/bc94c781-2a56-4f80-8ecb-e654de2f6ed6).</span></span>  

9. <span data-ttu-id="a7198-148">右键单击管道项目，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="a7198-148">Right click the pipelines project, and then click **Deploy**.</span></span>
