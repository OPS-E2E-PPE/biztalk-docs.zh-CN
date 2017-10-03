---
title: "如何使用选择项目类型对话框中 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Select Artifact Type dialog box
- artifacts, Select Artifact Type dialog box
- Orchestration Designer, items
ms.assetid: f0f767f1-4130-4ff0-a898-a089343ee71f
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3027971059d99a921bd743ff28aca1617c5d628d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-select-artifact-type-dialog-box"></a><span data-ttu-id="09627-102">如何使用选择项目类型对话框</span><span class="sxs-lookup"><span data-stu-id="09627-102">How to Use the Select Artifact Type Dialog Box</span></span>
<span data-ttu-id="09627-103">*项*用于在业务流程设计器中配置的业务流程的元素。</span><span class="sxs-lookup"><span data-stu-id="09627-103">An *item* is used to configure elements of an orchestration in Orchestration Designer.</span></span> <span data-ttu-id="09627-104">项的例子包括架构、映射、管道、端口类型和多部分消息类型。</span><span class="sxs-lookup"><span data-stu-id="09627-104">Examples of items are schemas, maps, pipelines, port types, and multi-part message types.</span></span> <span data-ttu-id="09627-105">开发业务流程及其构成部分（例如，端口形状、转换形状和消息）时，您可能需要引用某些项，这些项不位于当前业务流程，而是位于当前项目或者已编译到 BizTalk Server 程序集的其他项目中。</span><span class="sxs-lookup"><span data-stu-id="09627-105">When you develop an orchestration and its constituent parts such as port shapes, transform shapes, and messages, you may need to refer to items that do not reside in the current orchestration, but are in the current project or another project that has been compiled into a BizTalk Server assembly.</span></span> <span data-ttu-id="09627-106">你使用**选择项目类型**对话框中，以查找并配置业务流程中的某个元素时，然后指定项。</span><span class="sxs-lookup"><span data-stu-id="09627-106">You use the **Select Artifact Type** dialog box to locate and then specify items when configuring an element within an orchestration.</span></span>  
  
 <span data-ttu-id="09627-107">**选择项目类型**从 Orchestration 设计器中的多个位置对话框才可用。</span><span class="sxs-lookup"><span data-stu-id="09627-107">The **Select Artifact Type** dialog box is available from many locations in Orchestration Designer.</span></span> <span data-ttu-id="09627-108">你可以选择\<选择从引用的程序集 > 下拉列表中显示配置选项; 单击此文本将打开**选择项目类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="09627-108">You can select \<Select from referenced assembly> in a drop-down list that displays configuration options; clicking this text opens the **Select Artifact Type** dialog box.</span></span>  
  
 <span data-ttu-id="09627-109">必须先选择要配置的元素，然后才可以选择项。</span><span class="sxs-lookup"><span data-stu-id="09627-109">Before you can select an item, you must first select the element you want to configure.</span></span>  
  
 <span data-ttu-id="09627-110">你可以使用**选择项目类型**以下特定用途的对话框中：</span><span class="sxs-lookup"><span data-stu-id="09627-110">You can use the **Select Artifact Type** dialog box for the following specific purposes:</span></span>  
  
|<span data-ttu-id="09627-111">操作</span><span class="sxs-lookup"><span data-stu-id="09627-111">Action</span></span>|<span data-ttu-id="09627-112">用途</span><span class="sxs-lookup"><span data-stu-id="09627-112">Purpose</span></span>|  
|------------|-------------|  
|<span data-ttu-id="09627-113">选择管道</span><span class="sxs-lookup"><span data-stu-id="09627-113">Select a pipeline</span></span>|<span data-ttu-id="09627-114">为直接（早期）绑定配置端口时，针对管道属性选择管道。</span><span class="sxs-lookup"><span data-stu-id="09627-114">Select a pipeline for the pipeline property when configuring a port for direct (early) binding.</span></span>|  
|<span data-ttu-id="09627-115">选择映射</span><span class="sxs-lookup"><span data-stu-id="09627-115">Select a map</span></span>|<span data-ttu-id="09627-116">选择一个映射，以便与使用**转换**形状。</span><span class="sxs-lookup"><span data-stu-id="09627-116">Select a map to use with a **Transform** shape.</span></span>|  
|<span data-ttu-id="09627-117">选择一个架构</span><span class="sxs-lookup"><span data-stu-id="09627-117">Select a schema</span></span>|<span data-ttu-id="09627-118">创建多部分消息类型时，在项目中选择架构。</span><span class="sxs-lookup"><span data-stu-id="09627-118">Select schemas in the project when creating multi-part message types.</span></span>|  
|<span data-ttu-id="09627-119">选择端口类型</span><span class="sxs-lookup"><span data-stu-id="09627-119">Select a port type</span></span>|<span data-ttu-id="09627-120">创建端口时引用现有端口类型。</span><span class="sxs-lookup"><span data-stu-id="09627-120">Refer to existing port types when creating a port.</span></span>|  
|<span data-ttu-id="09627-121">选择多部分消息类型</span><span class="sxs-lookup"><span data-stu-id="09627-121">Select a multi-part message type</span></span>|<span data-ttu-id="09627-122">创建消息时引用现有的多部分类型。</span><span class="sxs-lookup"><span data-stu-id="09627-122">Refer to existing multipart types when creating messages.</span></span>|  
|<span data-ttu-id="09627-123">选择 .NET 类型</span><span class="sxs-lookup"><span data-stu-id="09627-123">Select a .NET type</span></span>|<span data-ttu-id="09627-124">创建变量或消息时引用现有的 .NET 类型。</span><span class="sxs-lookup"><span data-stu-id="09627-124">Refer to existing .NET types when creating variables or messages.</span></span>|  
  
 <span data-ttu-id="09627-125">**引用窗格**</span><span class="sxs-lookup"><span data-stu-id="09627-125">**Reference pane**</span></span>  
  
 <span data-ttu-id="09627-126">引用窗格中的**选择项目类型**对话框中将显示在当前项目和其他可用的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="09627-126">The reference pane of the **Select Artifact Type** dialog box displays references in the current project and in other available assemblies.</span></span> <span data-ttu-id="09627-127">若要在此窗格中选择某个引用，请单击该引用。</span><span class="sxs-lookup"><span data-stu-id="09627-127">To select a reference in this pane, click it.</span></span> <span data-ttu-id="09627-128">若要展开此窗格中的容器 (如**程序集**容器)，单击它旁边的加号 （+）。</span><span class="sxs-lookup"><span data-stu-id="09627-128">To expand a container in this pane (such as the **Assemblies** container), click the plus sign (+) beside it.</span></span>  
  
 <span data-ttu-id="09627-129">**项窗格**</span><span class="sxs-lookup"><span data-stu-id="09627-129">**Item pane**</span></span>  
  
 <span data-ttu-id="09627-130">项窗格中的**选择项目类型**对话框中显示引用窗格中当前选定的引用中包含的项。</span><span class="sxs-lookup"><span data-stu-id="09627-130">The item pane of the **Select Artifact Type** dialog box displays the items contained in the reference currently selected in the reference pane.</span></span> <span data-ttu-id="09627-131">项窗格中有两个列，**项**和**限定名称**，其中显示当前引用中的项目的信息。</span><span class="sxs-lookup"><span data-stu-id="09627-131">The item pane has two columns, **Item** and **Qualified Name**, which display information about the items in the current reference.</span></span>  
  
### <a name="to-use-the-select-artifact-type-dialog-box"></a><span data-ttu-id="09627-132">使用“选择项目类型”对话框</span><span class="sxs-lookup"><span data-stu-id="09627-132">To use the Select Artifact Type dialog box</span></span>  
  
1.  <span data-ttu-id="09627-133">展开**引用**的左窗格中的节点。</span><span class="sxs-lookup"><span data-stu-id="09627-133">Expand the **References** node in the left pane.</span></span> <span data-ttu-id="09627-134">该窗格显示了可用的项目和程序集。</span><span class="sxs-lookup"><span data-stu-id="09627-134">The pane displays available projects and assemblies.</span></span>  
  
2.  <span data-ttu-id="09627-135">展开**程序集**节点。</span><span class="sxs-lookup"><span data-stu-id="09627-135">Expand the **Assemblies** node.</span></span> <span data-ttu-id="09627-136">将列出一个或多个程序集，例如 SYSTEM.DLL 和 MICROSOFT.BIZTALK.PIPELINES.DLL。</span><span class="sxs-lookup"><span data-stu-id="09627-136">One or more assemblies are listed, such as SYSTEM.DLL and MICROSOFT.BIZTALK.PIPELINES.DLL.</span></span>  
  
3.  <span data-ttu-id="09627-137">单击程序集。</span><span class="sxs-lookup"><span data-stu-id="09627-137">Click an assembly.</span></span> <span data-ttu-id="09627-138">如果程序集包含项，则这些项将显示在右侧窗格中。</span><span class="sxs-lookup"><span data-stu-id="09627-138">If the assembly contains items, they are displayed in the right pane.</span></span> <span data-ttu-id="09627-139">项的限定名将显示在右侧窗格的右侧列中。</span><span class="sxs-lookup"><span data-stu-id="09627-139">The qualified name of an item is displayed in the right column of the right pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="09627-140">如果当前项目包含项，则可以单击该项目来查看其项并选择其中一项。</span><span class="sxs-lookup"><span data-stu-id="09627-140">If the current project contains items, you can click it to view its items and select one.</span></span>  
  
4.  <span data-ttu-id="09627-141">若要在右窗格中选择一个项，单击它，然后单击**确定**退出**选择项目类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="09627-141">To select an item in the right pane, click it and then click **OK** to exit the **Select Artifact Type** dialog box.</span></span> <span data-ttu-id="09627-142">这将会指定该项作为所选元素的类型。</span><span class="sxs-lookup"><span data-stu-id="09627-142">This assigns that item as the type for the selected element.</span></span> <span data-ttu-id="09627-143">若要关闭**选择项目类型**对话框中没有选择和分配某一项，请单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="09627-143">To close the **Select Artifact Type** dialog box without selecting and assigning an item, click **Cancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09627-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09627-144">See Also</span></span>  
 <span data-ttu-id="09627-145">[业务流程形状](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="09627-145">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="09627-146">[如何将形状添加到业务流程](../core/how-to-add-shapes-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="09627-146">[How to Add Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md) </span></span>  
 [<span data-ttu-id="09627-147">如何将参数添加到业务流程</span><span class="sxs-lookup"><span data-stu-id="09627-147">How to Add Parameters to Orchestrations</span></span>](../core/how-to-add-parameters-to-orchestrations.md)