---
title: "如何使用工具箱 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipeline components, deleting from toolbox
- pipeline components, Pipeline Designer
- pipeline components, adding to toolbox
- Pipeline Designer, toolbox
- pipelines, creating
ms.assetid: 7a60c590-1a38-46fe-addf-0aa2c8b63cf9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3965a063aebcc932f07937fd19c3998412591ea1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-toolbox"></a><span data-ttu-id="c18a3-102">如何使用工具箱</span><span class="sxs-lookup"><span data-stu-id="c18a3-102">How to Use the Toolbox</span></span>
<span data-ttu-id="c18a3-103">您可以通过将组件（形状）从工具箱拖至设计图面来创建管道。</span><span class="sxs-lookup"><span data-stu-id="c18a3-103">You create a pipeline by dragging components (shapes) from the Toolbox to the design surface.</span></span> <span data-ttu-id="c18a3-104">使用管道设计器，可以通过对创建过程进行特定限制来组装有效的管道。</span><span class="sxs-lookup"><span data-stu-id="c18a3-104">Pipeline Designer helps you assemble valid pipelines by placing certain restrictions on the creation process.</span></span> <span data-ttu-id="c18a3-105">您只能选择适用于要创建的管道类型的工具箱组件。</span><span class="sxs-lookup"><span data-stu-id="c18a3-105">You can only select Toolbox components that apply to the pipeline type you are creating.</span></span> <span data-ttu-id="c18a3-106">例如，对于接收管道，解码器、拆装器和验证器将显示为有效的工具箱组件，而编码器和组装器将处于禁用状态（呈灰色）。</span><span class="sxs-lookup"><span data-stu-id="c18a3-106">For example, a receive pipeline will show decoders, disassemblers, and validators as valid Toolbox components, while encoders and assemblers will be disabled (dimmed).</span></span>  
  
 <span data-ttu-id="c18a3-107">此外，阶段只接受有效的组件。</span><span class="sxs-lookup"><span data-stu-id="c18a3-107">In addition, stages can accept only valid components.</span></span> <span data-ttu-id="c18a3-108">例如，不能将编码器组件拖至组装阶段。</span><span class="sxs-lookup"><span data-stu-id="c18a3-108">For example, you cannot drag an encoder component to an Assemble stage.</span></span> <span data-ttu-id="c18a3-109">将组件拖至有效放置位置的附近时，将显示一个箭头，用于指示该组件可插入到的位置。</span><span class="sxs-lookup"><span data-stu-id="c18a3-109">When you drag a component near a valid drop location, an arrow appears, indicating the point where the component can be inserted.</span></span>  
  
 <span data-ttu-id="c18a3-110">如果将有效组件拖至已折叠的阶段，则可在该阶段上将鼠标悬停几秒钟以展开该阶段，然后即可将组件放入该阶段中。</span><span class="sxs-lookup"><span data-stu-id="c18a3-110">If you drag a valid component onto a stage that is collapsed, pause the mouse over the stage for a few seconds to expand it, and then drop the component into the stage.</span></span>  
  
 <span data-ttu-id="c18a3-111">向管道设计器的工具箱中添加自定义组件的过程类似于 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 标准过程。</span><span class="sxs-lookup"><span data-stu-id="c18a3-111">Adding a custom component to the Toolbox in Pipeline Designer is similar to the standard Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] procedure.</span></span>  
  
 <span data-ttu-id="c18a3-112">**开始和结束形状**</span><span class="sxs-lookup"><span data-stu-id="c18a3-112">**Start and End Shapes**</span></span>  
  
 <span data-ttu-id="c18a3-113">**启动**和**结束**形状显示为所有管道中的项目符号。</span><span class="sxs-lookup"><span data-stu-id="c18a3-113">**Start** and **End** shapes appear as bullets on all pipelines.</span></span> <span data-ttu-id="c18a3-114">这些形状显示在设计图面上只是为了直观地进行组织。</span><span class="sxs-lookup"><span data-stu-id="c18a3-114">They are provided on the design surface for visual organization only.</span></span> <span data-ttu-id="c18a3-115">每个形状只有一个，既不能添加，也不能删除。</span><span class="sxs-lookup"><span data-stu-id="c18a3-115">There is only one of each, and they can neither be added nor deleted.</span></span> <span data-ttu-id="c18a3-116">**启动**和**结束**形状不会出现在工具箱中。</span><span class="sxs-lookup"><span data-stu-id="c18a3-116">The **Start** and **End** shapes do not appear in the Toolbox.</span></span>  
  
### <a name="to-add-a-pipeline-component-to-the-toolbox"></a><span data-ttu-id="c18a3-117">向工具箱添加管道组件</span><span class="sxs-lookup"><span data-stu-id="c18a3-117">To add a pipeline component to the Toolbox</span></span>  
  
1.  <span data-ttu-id="c18a3-118">在 **“工具”** 菜单上，单击 **“选择工具箱项”**。</span><span class="sxs-lookup"><span data-stu-id="c18a3-118">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
     <span data-ttu-id="c18a3-119">-或者-</span><span class="sxs-lookup"><span data-stu-id="c18a3-119">—Or—</span></span>  
  
     <span data-ttu-id="c18a3-120">右键单击工具箱，然后单击**选择项**。</span><span class="sxs-lookup"><span data-stu-id="c18a3-120">Right-click the Toolbox and then click **Choose Items**.</span></span>  
  
2.  <span data-ttu-id="c18a3-121">在**自定义工具箱**对话框中，单击**BizTalk 管道组件**选项卡。</span><span class="sxs-lookup"><span data-stu-id="c18a3-121">In the **Customize Toolbox** dialog box, click the **BizTalk Pipeline Components** tab.</span></span>  
  
     <span data-ttu-id="c18a3-122">此时，将出现一个显示兼容管道组件的对话框。</span><span class="sxs-lookup"><span data-stu-id="c18a3-122">A dialog box displays the compatible pipeline components.</span></span> <span data-ttu-id="c18a3-123">您可以通过单击该对话框顶部的各个选项卡来浏览不同的类别。</span><span class="sxs-lookup"><span data-stu-id="c18a3-123">You can navigate through the categories by clicking the tabs at the top of the dialog box.</span></span>  
  
3.  <span data-ttu-id="c18a3-124">选择要添加到工具箱的组件。</span><span class="sxs-lookup"><span data-stu-id="c18a3-124">Select the component you want to add to the Toolbox.</span></span>  
  
4.  <span data-ttu-id="c18a3-125">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="c18a3-125">Click **OK**.</span></span> <span data-ttu-id="c18a3-126">该组件将出现在**BizTalk 管道组件**工具箱选项卡中的。</span><span class="sxs-lookup"><span data-stu-id="c18a3-126">The component will appear on the **BizTalk Pipeline Components** tab of the Toolbox.</span></span>  
  
### <a name="to-remove-a-pipeline-component-from-the-toolbox"></a><span data-ttu-id="c18a3-127">从工具箱中删除管道组件</span><span class="sxs-lookup"><span data-stu-id="c18a3-127">To remove a pipeline component from the Toolbox</span></span>  
  
-   <span data-ttu-id="c18a3-128">打开**自定义工具箱**（如前面的过程中） 的对话框中，然后清除要删除的组件。</span><span class="sxs-lookup"><span data-stu-id="c18a3-128">Open the **Customize Toolbox** dialog box (as in the preceding procedure) and clear the component to be removed.</span></span>  
  
     <span data-ttu-id="c18a3-129">从工具箱中删除后，组件仍会保持为已注册状态。</span><span class="sxs-lookup"><span data-stu-id="c18a3-129">A component remains registered even after it has been removed from the Toolbox.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c18a3-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c18a3-130">See Also</span></span>  
 <span data-ttu-id="c18a3-131">[如何创建一条新管道](../core/how-to-create-a-new-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="c18a3-131">[How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md) </span></span>  
 <span data-ttu-id="c18a3-132">[如何打开管道](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="c18a3-132">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="c18a3-133">[如何使用键盘导航](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="c18a3-133">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="c18a3-134">使用管道设计器中创建管道</span><span class="sxs-lookup"><span data-stu-id="c18a3-134">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)