---
title: 在业务流程设计器中工作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, saving
- deleting, orchestrations
- projects, orchestrations
- orchestrations, properties
- orchestrations, creating
- creating, orchestrations
- naming conventions, orchestrations
- orchestrations, naming conventions
- orchestrations, deleting
ms.assetid: 13e72b41-d9b6-4508-9a44-b3c7c1804f36
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a239c3660fbd5559a6d504dc9f39d94df8a6c6d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240285"
---
# <a name="working-in-orchestration-designer"></a><span data-ttu-id="dab69-102">在业务流程设计器中工作</span><span class="sxs-lookup"><span data-stu-id="dab69-102">Working in Orchestration Designer</span></span>
<span data-ttu-id="dab69-103">启动 BizTalk 项目后，可以创建新的业务流程并向项目添加现有业务流程。</span><span class="sxs-lookup"><span data-stu-id="dab69-103">After you have started a BizTalk project, you can create new orchestrations and add existing orchestrations to the project.</span></span> <span data-ttu-id="dab69-104">请参阅以下过程来创建和保存业务流程，以向项目添加现有的业务流程或删除其中一个从它，若要更改业务流程的名称以及设置业务流程属性。</span><span class="sxs-lookup"><span data-stu-id="dab69-104">See the following procedures to create and save an orchestration, to add an existing orchestration to a project or remove one from it, to change the name of an orchestration, and to set orchestration properties.</span></span>  
  
### <a name="to-create-an-orchestration"></a><span data-ttu-id="dab69-105">若要创建一个业务流程</span><span class="sxs-lookup"><span data-stu-id="dab69-105">To create an orchestration</span></span>  
  
1.  <span data-ttu-id="dab69-106">在解决方案资源管理器，右键单击项目名称，选择**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="dab69-106">In Solution Explorer, right-click the project name, select **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="dab69-107">在中**添加新项**对话框中**类别**窗格中，单击**BizTalk 项目项**，然后在**模板**窗格中，单击**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="dab69-107">In the **Add New Item** dialog box, in the **Categories** pane, click **BizTalk Project Items**, and then in the **Templates** pane, click **BizTalk Orchestration**.</span></span>  
  
3.  <span data-ttu-id="dab69-108">在中**名称**框底部的对话框中，为业务流程中，提供一个名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="dab69-108">In the **Name** box at the bottom of the dialog box, supply a name for the orchestration, and then click **Add**.</span></span>  
  
     <span data-ttu-id="dab69-109">创建新的业务流程并将其显示在业务流程设计器中，并创建相应的.odx 文件并将其显示在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="dab69-109">The new orchestration is created and displayed in Orchestration Designer, and a corresponding .odx file is created and displayed in Solution Explorer.</span></span>  
  
### <a name="to-add-an-existing-orchestration-to-a-project"></a><span data-ttu-id="dab69-110">若要向项目添加现有的业务流程</span><span class="sxs-lookup"><span data-stu-id="dab69-110">To add an existing orchestration to a project</span></span>  
  
1.  <span data-ttu-id="dab69-111">在解决方案资源管理器，右键单击项目名称，单击**外**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="dab69-111">In Solution Explorer, right-click the project name, click **Add**, and then click **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="dab69-112">在中**添加现有项**对话框中，导航到包含该业务流程的目录，选择的业务流程，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="dab69-112">In the **Add Existing Item** dialog box, navigate to the directory containing the orchestration, select the orchestration, and then click **Add**.</span></span>  
  
     <span data-ttu-id="dab69-113">业务流程添加到项目。</span><span class="sxs-lookup"><span data-stu-id="dab69-113">The orchestration is added to the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dab69-114">时添加现有文件，该文件复制到你的项目。</span><span class="sxs-lookup"><span data-stu-id="dab69-114">When you add an existing file, the file is copied to your project.</span></span> <span data-ttu-id="dab69-115">（该文件不会只需添加引用。）如果在项目中更改的文件，原始文件仍保持不变。</span><span class="sxs-lookup"><span data-stu-id="dab69-115">(The file is not simply added by reference.) If you change the file in your project, the original file is left unchanged.</span></span>  
  
### <a name="to-change-the-name-of-an-orchestration"></a><span data-ttu-id="dab69-116">若要更改业务流程的名称</span><span class="sxs-lookup"><span data-stu-id="dab69-116">To change the name of an orchestration</span></span>  
  
1.  <span data-ttu-id="dab69-117">在解决方案资源管理器中右键单击你想要更改，并单击该.odx 文件**重命名**。</span><span class="sxs-lookup"><span data-stu-id="dab69-117">In Solution Explorer, right-click the .odx file you want to change, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="dab69-118">键入新的文件名称，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="dab69-118">Type the new file name you want, and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dab69-119">当您更改.odx 文件的名称时，您可能还需要单击设计图面以显示属性窗口上，更改的值更改业务流程类型的名称**Typename**属性业务流程。</span><span class="sxs-lookup"><span data-stu-id="dab69-119">When you change the name of an .odx file, you might also want to change the name of the orchestration type by clicking on the design surface to bring up the Properties window and changing the value of the **Typename** property of the orchestration.</span></span>  
  
### <a name="to-save-an-orchestration"></a><span data-ttu-id="dab69-120">若要保存业务流程</span><span class="sxs-lookup"><span data-stu-id="dab69-120">To save an orchestration</span></span>  
  
-   <span data-ttu-id="dab69-121">上**文件**菜单上，单击**保存\<业务流程名称\>**。</span><span class="sxs-lookup"><span data-stu-id="dab69-121">On the **File** menu, click **Save \<orchestration name\>**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dab69-122">业务流程文件将保存为 utf-8。</span><span class="sxs-lookup"><span data-stu-id="dab69-122">Orchestration files are saved as UTF-8.</span></span>  <span data-ttu-id="dab69-123">架构、 映射和管道都另存为 utf-16。</span><span class="sxs-lookup"><span data-stu-id="dab69-123">Schemas, maps, and pipelines are saved as UTF-16.</span></span>  
  
### <a name="to-remove-an-orchestration-from-a-project"></a><span data-ttu-id="dab69-124">若要从项目中删除业务流程</span><span class="sxs-lookup"><span data-stu-id="dab69-124">To remove an orchestration from a project</span></span>  
  
-   <span data-ttu-id="dab69-125">在解决方案资源管理器中右键单击你想要删除，然后单击的文件**从项目中排除**。</span><span class="sxs-lookup"><span data-stu-id="dab69-125">In Solution Explorer, right-click the file you want to remove, and then click **Exclude From Project**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dab69-126">若要从项目中删除该业务流程并永久删除该文件，请单击**删除**相反。</span><span class="sxs-lookup"><span data-stu-id="dab69-126">To remove the orchestration from a project and permanently delete the file, click **Delete** instead.</span></span>  
  
### <a name="to-include-an-excluded-orchestration-in-a-project"></a><span data-ttu-id="dab69-127">若要包括在项目中排除的业务流程</span><span class="sxs-lookup"><span data-stu-id="dab69-127">To include an excluded orchestration in a project</span></span>  
  
-   <span data-ttu-id="dab69-128">在解决方案资源管理器，单击**全部显示**工具栏按钮，右键单击所需的.odx 文件并选择**包括在项目**。</span><span class="sxs-lookup"><span data-stu-id="dab69-128">In Solution Explorer, click the **Show All** toolbar button, right-click the .odx file you want, and select **Include in Project**.</span></span>  
  
### <a name="to-set-orchestration-properties"></a><span data-ttu-id="dab69-129">若要设置业务流程属性</span><span class="sxs-lookup"><span data-stu-id="dab69-129">To set orchestration properties</span></span>  
  
1.  <span data-ttu-id="dab69-130">打开该业务流程的.odx 文件在项目中，双击或通过选择包含在流程区域中的业务流程选项卡。</span><span class="sxs-lookup"><span data-stu-id="dab69-130">Open the orchestration by double-clicking on the .odx file in the project, or by selecting the tab containing the orchestration in the Process Area.</span></span>  
  
2.  <span data-ttu-id="dab69-131">在业务流程视图窗口中，选择**业务流程属性**。</span><span class="sxs-lookup"><span data-stu-id="dab69-131">In the Orchestration View window, select **Orchestration Properties**.</span></span>  
  
     <span data-ttu-id="dab69-132">-或-</span><span class="sxs-lookup"><span data-stu-id="dab69-132">—Or—</span></span>  
  
     <span data-ttu-id="dab69-133">单击**流程区域**业务流程设计图面背景。</span><span class="sxs-lookup"><span data-stu-id="dab69-133">Click the **Process Area** background of the Orchestration Design Surface.</span></span>  
  
3.  <span data-ttu-id="dab69-134">在属性窗口中，指定以下属性。</span><span class="sxs-lookup"><span data-stu-id="dab69-134">In the Properties window, specify the following properties.</span></span> <span data-ttu-id="dab69-135">请注意，某些属性仅在某些情况下将显示。</span><span class="sxs-lookup"><span data-stu-id="dab69-135">Note that some properties appear only under certain circumstances.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dab69-136">业务流程、 端口类型和多部分消息类型的名称必须是模块的作用域内唯一。</span><span class="sxs-lookup"><span data-stu-id="dab69-136">The names of orchestrations, port types and multi-part message types must be unique within the scope of a module.</span></span>  
  
    |<span data-ttu-id="dab69-137">属性</span><span class="sxs-lookup"><span data-stu-id="dab69-137">Property</span></span>|<span data-ttu-id="dab69-138">Description</span><span class="sxs-lookup"><span data-stu-id="dab69-138">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="dab69-139">批处理</span><span class="sxs-lookup"><span data-stu-id="dab69-139">Batch</span></span>|<span data-ttu-id="dab69-140">确定是否可以与其他实例批处理是原子事务的业务流程。</span><span class="sxs-lookup"><span data-stu-id="dab69-140">Determines whether an orchestration that is an atomic transaction can be batched with other instances.</span></span>|  
    |<span data-ttu-id="dab69-141">补偿</span><span class="sxs-lookup"><span data-stu-id="dab69-141">Compensation</span></span>|<span data-ttu-id="dab69-142">指定哪种类型的补偿业务流程上执行。</span><span class="sxs-lookup"><span data-stu-id="dab69-142">Specifies what type of compensation to perform on the orchestration.</span></span>|  
    |<span data-ttu-id="dab69-143">隔离级别</span><span class="sxs-lookup"><span data-stu-id="dab69-143">Isolation Level</span></span>|<span data-ttu-id="dab69-144">对于事务性业务流程，确定并发事务中可访问数据的程度。</span><span class="sxs-lookup"><span data-stu-id="dab69-144">For transactional orchestrations, determines the degree to which data is accessible among concurrent transactions.</span></span>|  
    |<span data-ttu-id="dab69-145">可导出模块</span><span class="sxs-lookup"><span data-stu-id="dab69-145">Module Exportable</span></span>|<span data-ttu-id="dab69-146">确定该模块可导出到 BPEL4WS。</span><span class="sxs-lookup"><span data-stu-id="dab69-146">Determines whether or not the module can be exported to BPEL4WS.</span></span>|  
    |<span data-ttu-id="dab69-147">模块 XML 目标 Namespace</span><span class="sxs-lookup"><span data-stu-id="dab69-147">Module XML Target Namespace</span></span>|<span data-ttu-id="dab69-148">将类型导出到 BPEL4WS 时使用的 XML 目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="dab69-148">The XML target namespace used when exporting types to BPEL4WS.</span></span>|  
    |<span data-ttu-id="dab69-149">命名空间</span><span class="sxs-lookup"><span data-stu-id="dab69-149">Namespace</span></span>|<span data-ttu-id="dab69-150">确定包括业务流程和业务流程类型的包含模块的名称。</span><span class="sxs-lookup"><span data-stu-id="dab69-150">Determines the name of the containing module that includes the orchestration and the orchestration types.</span></span>|  
    |<span data-ttu-id="dab69-151">可导出的业务流程</span><span class="sxs-lookup"><span data-stu-id="dab69-151">Orchestration Exportable</span></span>|<span data-ttu-id="dab69-152">指示是否适用此业务流程可导出到 BPEL4WS。</span><span class="sxs-lookup"><span data-stu-id="dab69-152">Indicates whether this orchestration is intended to be exportable to BPEL4WS.</span></span>|  
    |<span data-ttu-id="dab69-153">业务流程 XML 目标 Namespace</span><span class="sxs-lookup"><span data-stu-id="dab69-153">Orchestration XML Target Namespace</span></span>|<span data-ttu-id="dab69-154">将此业务流程导出到 BPEL4WS 时使用的 XML 目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="dab69-154">The XML target namespace used when exporting this orchestration to BPEL4WS.</span></span>|  
    |<span data-ttu-id="dab69-155">重试</span><span class="sxs-lookup"><span data-stu-id="dab69-155">Retry</span></span>|<span data-ttu-id="dab69-156">指定是否失败后重试事务性业务流程。</span><span class="sxs-lookup"><span data-stu-id="dab69-156">Specify whether to retry a transactional orchestration if it fails.</span></span>|  
    |<span data-ttu-id="dab69-157">超时</span><span class="sxs-lookup"><span data-stu-id="dab69-157">Timeout</span></span>|<span data-ttu-id="dab69-158">时间 （秒） 直到事务性业务流程因处于非活动状态。</span><span class="sxs-lookup"><span data-stu-id="dab69-158">The time in seconds until a transactional orchestration fails due to inactivity.</span></span>|  
    |<span data-ttu-id="dab69-159">事务标识符</span><span class="sxs-lookup"><span data-stu-id="dab69-159">Transaction Identifier</span></span>|<span data-ttu-id="dab69-160">事务性业务流程的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="dab69-160">Unique identifier for a transactional orchestration.</span></span>|  
    |<span data-ttu-id="dab69-161">事务类型</span><span class="sxs-lookup"><span data-stu-id="dab69-161">Transaction Type</span></span>|<span data-ttu-id="dab69-162">确定是否在业务流程是原子事务、 长时间运行的事务，或者未进行事务处理。</span><span class="sxs-lookup"><span data-stu-id="dab69-162">Determines whether the orchestration is an atomic transaction, a long-running transaction, or is not transacted.</span></span>|  
    |<span data-ttu-id="dab69-163">类型修饰符</span><span class="sxs-lookup"><span data-stu-id="dab69-163">Type Modifier</span></span>|<span data-ttu-id="dab69-164">确定业务流程级别变量的作用域：</span><span class="sxs-lookup"><span data-stu-id="dab69-164">Determines the scope of orchestration-level variables:</span></span><br /><br /> <span data-ttu-id="dab69-165">私有 — 对此业务流程的访问仅限于包含模块。</span><span class="sxs-lookup"><span data-stu-id="dab69-165">Private—Access to this orchestration is limited to the containing module.</span></span><br /><br /> <span data-ttu-id="dab69-166">公共 — 对此业务流程的访问没有限制。</span><span class="sxs-lookup"><span data-stu-id="dab69-166">Public—Access to this orchestration is not limited.</span></span><br /><br /> <span data-ttu-id="dab69-167">内部 — 对此业务流程的访问仅限于同一项目中的模块。</span><span class="sxs-lookup"><span data-stu-id="dab69-167">Internal—Access to this orchestration is limited to modules within the same project.</span></span>|  
    |<span data-ttu-id="dab69-168">类型名称</span><span class="sxs-lookup"><span data-stu-id="dab69-168">Typename</span></span>|<span data-ttu-id="dab69-169">确定此业务流程中包含的模块的名称。</span><span class="sxs-lookup"><span data-stu-id="dab69-169">Determines the name of this orchestration within the containing module.</span></span> <span data-ttu-id="dab69-170">**注意：** 如果你使用与根级别命名空间中，相同的类型名称定义消息和变量的类型名称和尝试执行分配操作在其上的时，可能会从业务流程设计器收到错误。</span><span class="sxs-lookup"><span data-stu-id="dab69-170">**Note:**  If you to use a Typename that is the same as a root-level namespace, you may receive an error from Orchestration Designer when you define messages and variables based on the Typename and attempt to perform assign operations on them.</span></span> <span data-ttu-id="dab69-171">例如，如果指定一个系统类型名称，然后定义 System.String 之类的变量和消息，你可能会收到错误。</span><span class="sxs-lookup"><span data-stu-id="dab69-171">For example, if you specify a Typename of System, and then define messages and variables like System.String, you may receive an error.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dab69-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="dab69-172">See Also</span></span>  
 <span data-ttu-id="dab69-173">[业务流程形状](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="dab69-173">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="dab69-174">[如何向业务流程添加形状](../core/how-to-add-shapes-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="dab69-174">[How to Add Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md) </span></span>  
 <span data-ttu-id="dab69-175">[如何将参数添加到业务流程](../core/how-to-add-parameters-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="dab69-175">[How to Add Parameters to Orchestrations](../core/how-to-add-parameters-to-orchestrations.md) </span></span>  
 [<span data-ttu-id="dab69-176">如何使用选择项目类型对话框</span><span class="sxs-lookup"><span data-stu-id="dab69-176">How to Use the Select Artifact Type Dialog Box</span></span>](../core/how-to-use-the-select-artifact-type-dialog-box.md)