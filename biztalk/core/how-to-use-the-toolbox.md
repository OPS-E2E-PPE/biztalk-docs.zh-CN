---
title: 如何使用工具箱 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, pipelines
- pipeline components, deleting from toolbox
- pipeline components, Pipeline Designer
- pipeline components, adding to toolbox
- Pipeline Designer, toolbox
- pipelines, creating
ms.assetid: 7a60c590-1a38-46fe-addf-0aa2c8b63cf9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2990cdf576f1678078da564932542081512d09dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383181"
---
# <a name="how-to-use-the-toolbox"></a><span data-ttu-id="3c97c-102">如何使用工具箱</span><span class="sxs-lookup"><span data-stu-id="3c97c-102">How to Use the Toolbox</span></span>
<span data-ttu-id="3c97c-103">通过将组件 （形状） 从工具箱拖动到设计图面创建的管道。</span><span class="sxs-lookup"><span data-stu-id="3c97c-103">You create a pipeline by dragging components (shapes) from the Toolbox to the design surface.</span></span> <span data-ttu-id="3c97c-104">管道设计器可帮助你通过在创建过程上放置某些限制组装有效的管道。</span><span class="sxs-lookup"><span data-stu-id="3c97c-104">Pipeline Designer helps you assemble valid pipelines by placing certain restrictions on the creation process.</span></span> <span data-ttu-id="3c97c-105">您只能选择适用于要创建的管道类型的工具箱组件。</span><span class="sxs-lookup"><span data-stu-id="3c97c-105">You can only select Toolbox components that apply to the pipeline type you are creating.</span></span> <span data-ttu-id="3c97c-106">例如，接收管道将显示解码器、 拆装器和验证为有效的工具箱组件，而编码器和组装器将被禁用 （灰显）。</span><span class="sxs-lookup"><span data-stu-id="3c97c-106">For example, a receive pipeline will show decoders, disassemblers, and validators as valid Toolbox components, while encoders and assemblers will be disabled (dimmed).</span></span>  
  
 <span data-ttu-id="3c97c-107">此外，阶段可以接受有效的组件。</span><span class="sxs-lookup"><span data-stu-id="3c97c-107">In addition, stages can accept only valid components.</span></span> <span data-ttu-id="3c97c-108">例如，不能将编码器组件拖至组装阶段。</span><span class="sxs-lookup"><span data-stu-id="3c97c-108">For example, you cannot drag an encoder component to an Assemble stage.</span></span> <span data-ttu-id="3c97c-109">将组件拖放有效放置位置附近，会出现一个箭头，指示该组件可的插入的位置。</span><span class="sxs-lookup"><span data-stu-id="3c97c-109">When you drag a component near a valid drop location, an arrow appears, indicating the point where the component can be inserted.</span></span>  
  
 <span data-ttu-id="3c97c-110">如果是有效的组件拖到某一阶段的处于折叠状态，将鼠标悬停几秒钟以展开它，然后将组件放入阶段的阶段。</span><span class="sxs-lookup"><span data-stu-id="3c97c-110">If you drag a valid component onto a stage that is collapsed, pause the mouse over the stage for a few seconds to expand it, and then drop the component into the stage.</span></span>  
  
 <span data-ttu-id="3c97c-111">将自定义组件添加到管道设计器中的工具箱是类似于标准 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]过程。</span><span class="sxs-lookup"><span data-stu-id="3c97c-111">Adding a custom component to the Toolbox in Pipeline Designer is similar to the standard Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] procedure.</span></span>  
  
 <span data-ttu-id="3c97c-112">**开始和结束形状**</span><span class="sxs-lookup"><span data-stu-id="3c97c-112">**Start and End Shapes**</span></span>  
  
 <span data-ttu-id="3c97c-113">**启动**并**最终**形状显示为在所有管道上的项目符号。</span><span class="sxs-lookup"><span data-stu-id="3c97c-113">**Start** and **End** shapes appear as bullets on all pipelines.</span></span> <span data-ttu-id="3c97c-114">它们提供设计图面上，为 visual 的组织。</span><span class="sxs-lookup"><span data-stu-id="3c97c-114">They are provided on the design surface for visual organization only.</span></span> <span data-ttu-id="3c97c-115">没有仅各项之一，并且它们都不能添加也不能删除。</span><span class="sxs-lookup"><span data-stu-id="3c97c-115">There is only one of each, and they can neither be added nor deleted.</span></span> <span data-ttu-id="3c97c-116">**启动**并**最终**形状并显示在工具箱中。</span><span class="sxs-lookup"><span data-stu-id="3c97c-116">The **Start** and **End** shapes do not appear in the Toolbox.</span></span>  
  
### <a name="to-add-a-pipeline-component-to-the-toolbox"></a><span data-ttu-id="3c97c-117">若要向工具箱添加管道组件</span><span class="sxs-lookup"><span data-stu-id="3c97c-117">To add a pipeline component to the Toolbox</span></span>  
  
1.  <span data-ttu-id="3c97c-118">在 **“工具”** 菜单上，单击 **“选择工具箱项”**。</span><span class="sxs-lookup"><span data-stu-id="3c97c-118">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
     <span data-ttu-id="3c97c-119">-或-</span><span class="sxs-lookup"><span data-stu-id="3c97c-119">—Or—</span></span>  
  
     <span data-ttu-id="3c97c-120">右键单击工具箱，然后单击**选择项**。</span><span class="sxs-lookup"><span data-stu-id="3c97c-120">Right-click the Toolbox and then click **Choose Items**.</span></span>  
  
2.  <span data-ttu-id="3c97c-121">在中**自定义工具箱**对话框中，单击**BizTalk 管道组件**选项卡。</span><span class="sxs-lookup"><span data-stu-id="3c97c-121">In the **Customize Toolbox** dialog box, click the **BizTalk Pipeline Components** tab.</span></span>  
  
     <span data-ttu-id="3c97c-122">对话框中显示兼容管道组件。</span><span class="sxs-lookup"><span data-stu-id="3c97c-122">A dialog box displays the compatible pipeline components.</span></span> <span data-ttu-id="3c97c-123">可以通过单击顶部的对话框的选项卡在类别间进行导航。</span><span class="sxs-lookup"><span data-stu-id="3c97c-123">You can navigate through the categories by clicking the tabs at the top of the dialog box.</span></span>  
  
3.  <span data-ttu-id="3c97c-124">选择你想要添加到工具箱的组件。</span><span class="sxs-lookup"><span data-stu-id="3c97c-124">Select the component you want to add to the Toolbox.</span></span>  
  
4.  <span data-ttu-id="3c97c-125">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="3c97c-125">Click **OK**.</span></span> <span data-ttu-id="3c97c-126">该组件将出现在**BizTalk 管道组件**工具箱选项卡中的。</span><span class="sxs-lookup"><span data-stu-id="3c97c-126">The component will appear on the **BizTalk Pipeline Components** tab of the Toolbox.</span></span>  
  
### <a name="to-remove-a-pipeline-component-from-the-toolbox"></a><span data-ttu-id="3c97c-127">若要从工具箱中删除的管道组件</span><span class="sxs-lookup"><span data-stu-id="3c97c-127">To remove a pipeline component from the Toolbox</span></span>  
  
-   <span data-ttu-id="3c97c-128">打开**自定义工具箱**对话框 （如在前面的过程中），然后清除要删除的组件。</span><span class="sxs-lookup"><span data-stu-id="3c97c-128">Open the **Customize Toolbox** dialog box (as in the preceding procedure) and clear the component to be removed.</span></span>  
  
     <span data-ttu-id="3c97c-129">即使已从工具箱将保持已注册组件。</span><span class="sxs-lookup"><span data-stu-id="3c97c-129">A component remains registered even after it has been removed from the Toolbox.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c97c-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c97c-130">See Also</span></span>  
 <span data-ttu-id="3c97c-131">[如何创建新的管道](../core/how-to-create-a-new-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="3c97c-131">[How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md) </span></span>  
 <span data-ttu-id="3c97c-132">[如何打开管道](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="3c97c-132">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="3c97c-133">[如何使用键盘导航](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="3c97c-133">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="3c97c-134">使用管道设计器创建管道</span><span class="sxs-lookup"><span data-stu-id="3c97c-134">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)