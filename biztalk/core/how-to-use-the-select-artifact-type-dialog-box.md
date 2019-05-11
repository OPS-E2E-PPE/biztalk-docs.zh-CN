---
title: 如何使用选择项目类型对话框 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Select Artifact Type dialog box
- artifacts, Select Artifact Type dialog box
- Orchestration Designer, items
ms.assetid: f0f767f1-4130-4ff0-a898-a089343ee71f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 362f1ffe21023aaddb5b492548914d35348fa5e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333218"
---
# <a name="how-to-use-the-select-artifact-type-dialog-box"></a><span data-ttu-id="ff9be-102">如何使用选择项目类型对话框</span><span class="sxs-lookup"><span data-stu-id="ff9be-102">How to Use the Select Artifact Type Dialog Box</span></span>
<span data-ttu-id="ff9be-103">*项*用于在业务流程设计器中配置业务流程的元素。</span><span class="sxs-lookup"><span data-stu-id="ff9be-103">An *item* is used to configure elements of an orchestration in Orchestration Designer.</span></span> <span data-ttu-id="ff9be-104">项的例子包括架构、 映射、 管道、 端口类型和多部分消息类型。</span><span class="sxs-lookup"><span data-stu-id="ff9be-104">Examples of items are schemas, maps, pipelines, port types, and multi-part message types.</span></span> <span data-ttu-id="ff9be-105">当开发业务流程，并如端口形状、 转换形状和消息及其组成部分时，可能需要到不位于当前业务流程，但位于当前项目或已编译到的另一个项目中的项，请参阅BizTalk 服务器程序集。</span><span class="sxs-lookup"><span data-stu-id="ff9be-105">When you develop an orchestration and its constituent parts such as port shapes, transform shapes, and messages, you may need to refer to items that do not reside in the current orchestration, but are in the current project or another project that has been compiled into a BizTalk Server assembly.</span></span> <span data-ttu-id="ff9be-106">您使用**选择项目类型**对话框找到并配置业务流程中的某个元素时，然后指定项。</span><span class="sxs-lookup"><span data-stu-id="ff9be-106">You use the **Select Artifact Type** dialog box to locate and then specify items when configuring an element within an orchestration.</span></span>  
  
 <span data-ttu-id="ff9be-107">**选择项目类型**从业务流程设计器中的许多位置对话框才可用。</span><span class="sxs-lookup"><span data-stu-id="ff9be-107">The **Select Artifact Type** dialog box is available from many locations in Orchestration Designer.</span></span> <span data-ttu-id="ff9be-108">可以选择\<从引用的程序集中\>下拉列表中显示配置选项; 单击此文本会打开**选择项目类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="ff9be-108">You can select \<Select from referenced assembly\> in a drop-down list that displays configuration options; clicking this text opens the **Select Artifact Type** dialog box.</span></span>  
  
 <span data-ttu-id="ff9be-109">可以选择一项之前，必须首先选择你想要配置的元素。</span><span class="sxs-lookup"><span data-stu-id="ff9be-109">Before you can select an item, you must first select the element you want to configure.</span></span>  
  
 <span data-ttu-id="ff9be-110">可以使用**选择项目类型**以下特定目的的对话框：</span><span class="sxs-lookup"><span data-stu-id="ff9be-110">You can use the **Select Artifact Type** dialog box for the following specific purposes:</span></span>  
  
|<span data-ttu-id="ff9be-111">操作</span><span class="sxs-lookup"><span data-stu-id="ff9be-111">Action</span></span>|<span data-ttu-id="ff9be-112">用途</span><span class="sxs-lookup"><span data-stu-id="ff9be-112">Purpose</span></span>|  
|------------|-------------|  
|<span data-ttu-id="ff9be-113">选择管道</span><span class="sxs-lookup"><span data-stu-id="ff9be-113">Select a pipeline</span></span>|<span data-ttu-id="ff9be-114">配置为直接 （早期） 绑定的端口时，请选择用于将管道属性的管道。</span><span class="sxs-lookup"><span data-stu-id="ff9be-114">Select a pipeline for the pipeline property when configuring a port for direct (early) binding.</span></span>|  
|<span data-ttu-id="ff9be-115">选择映射</span><span class="sxs-lookup"><span data-stu-id="ff9be-115">Select a map</span></span>|<span data-ttu-id="ff9be-116">选择要用于映射**转换**形状。</span><span class="sxs-lookup"><span data-stu-id="ff9be-116">Select a map to use with a **Transform** shape.</span></span>|  
|<span data-ttu-id="ff9be-117">选择架构</span><span class="sxs-lookup"><span data-stu-id="ff9be-117">Select a schema</span></span>|<span data-ttu-id="ff9be-118">创建多部分消息类型时，请在项目中选择架构。</span><span class="sxs-lookup"><span data-stu-id="ff9be-118">Select schemas in the project when creating multi-part message types.</span></span>|  
|<span data-ttu-id="ff9be-119">选择端口类型</span><span class="sxs-lookup"><span data-stu-id="ff9be-119">Select a port type</span></span>|<span data-ttu-id="ff9be-120">创建端口时引用现有端口类型。</span><span class="sxs-lookup"><span data-stu-id="ff9be-120">Refer to existing port types when creating a port.</span></span>|  
|<span data-ttu-id="ff9be-121">选择多部分消息类型</span><span class="sxs-lookup"><span data-stu-id="ff9be-121">Select a multi-part message type</span></span>|<span data-ttu-id="ff9be-122">创建消息时引用现有的多部分类型。</span><span class="sxs-lookup"><span data-stu-id="ff9be-122">Refer to existing multipart types when creating messages.</span></span>|  
|<span data-ttu-id="ff9be-123">选择.NET 类型</span><span class="sxs-lookup"><span data-stu-id="ff9be-123">Select a .NET type</span></span>|<span data-ttu-id="ff9be-124">创建变量或消息时引用现有的.NET 类型。</span><span class="sxs-lookup"><span data-stu-id="ff9be-124">Refer to existing .NET types when creating variables or messages.</span></span>|  
  
 <span data-ttu-id="ff9be-125">**引用窗格**</span><span class="sxs-lookup"><span data-stu-id="ff9be-125">**Reference pane**</span></span>  
  
 <span data-ttu-id="ff9be-126">引用窗格**选择项目类型**对话框中显示的引用在当前项目和其他可用程序集中。</span><span class="sxs-lookup"><span data-stu-id="ff9be-126">The reference pane of the **Select Artifact Type** dialog box displays references in the current project and in other available assemblies.</span></span> <span data-ttu-id="ff9be-127">若要在此窗格中选择一个引用，请单击它。</span><span class="sxs-lookup"><span data-stu-id="ff9be-127">To select a reference in this pane, click it.</span></span> <span data-ttu-id="ff9be-128">若要展开此窗格中的容器 (如**程序集**容器)，单击其旁边的加号 （+）。</span><span class="sxs-lookup"><span data-stu-id="ff9be-128">To expand a container in this pane (such as the **Assemblies** container), click the plus sign (+) beside it.</span></span>  
  
 <span data-ttu-id="ff9be-129">**项窗格**</span><span class="sxs-lookup"><span data-stu-id="ff9be-129">**Item pane**</span></span>  
  
 <span data-ttu-id="ff9be-130">项窗格**选择项目类型**对话框显示当前在引用窗格中选定的引用中包含的项。</span><span class="sxs-lookup"><span data-stu-id="ff9be-130">The item pane of the **Select Artifact Type** dialog box displays the items contained in the reference currently selected in the reference pane.</span></span> <span data-ttu-id="ff9be-131">项窗格会显示两个列，**项**并**限定名**，随后显示当前引用中的项信息。</span><span class="sxs-lookup"><span data-stu-id="ff9be-131">The item pane has two columns, **Item** and **Qualified Name**, which display information about the items in the current reference.</span></span>  
  
### <a name="to-use-the-select-artifact-type-dialog-box"></a><span data-ttu-id="ff9be-132">若要使用选择项目类型对话框</span><span class="sxs-lookup"><span data-stu-id="ff9be-132">To use the Select Artifact Type dialog box</span></span>  
  
1.  <span data-ttu-id="ff9be-133">展开**引用**的左窗格中的节点。</span><span class="sxs-lookup"><span data-stu-id="ff9be-133">Expand the **References** node in the left pane.</span></span> <span data-ttu-id="ff9be-134">该窗格显示可用的项目和程序集。</span><span class="sxs-lookup"><span data-stu-id="ff9be-134">The pane displays available projects and assemblies.</span></span>  
  
2.  <span data-ttu-id="ff9be-135">展开**程序集**节点。</span><span class="sxs-lookup"><span data-stu-id="ff9be-135">Expand the **Assemblies** node.</span></span> <span data-ttu-id="ff9be-136">列出一个或多个程序集，如系统。DLL 和 MICROSOFT.BIZTALK.PIPELINES.DLL。</span><span class="sxs-lookup"><span data-stu-id="ff9be-136">One or more assemblies are listed, such as SYSTEM.DLL and MICROSOFT.BIZTALK.PIPELINES.DLL.</span></span>  
  
3.  <span data-ttu-id="ff9be-137">单击程序集。</span><span class="sxs-lookup"><span data-stu-id="ff9be-137">Click an assembly.</span></span> <span data-ttu-id="ff9be-138">如果该程序集包含项，它们显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="ff9be-138">If the assembly contains items, they are displayed in the right pane.</span></span> <span data-ttu-id="ff9be-139">在右窗格的右侧列中显示项的限定的名称。</span><span class="sxs-lookup"><span data-stu-id="ff9be-139">The qualified name of an item is displayed in the right column of the right pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ff9be-140">如果当前项目包含项，可以单击它以查看其项并进行选择。</span><span class="sxs-lookup"><span data-stu-id="ff9be-140">If the current project contains items, you can click it to view its items and select one.</span></span>  
  
4.  <span data-ttu-id="ff9be-141">若要在右窗格中选择某个项目，单击它，然后单击**确定**退出**选择项目类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="ff9be-141">To select an item in the right pane, click it and then click **OK** to exit the **Select Artifact Type** dialog box.</span></span> <span data-ttu-id="ff9be-142">这将会指定该项作为所选元素的类型。</span><span class="sxs-lookup"><span data-stu-id="ff9be-142">This assigns that item as the type for the selected element.</span></span> <span data-ttu-id="ff9be-143">若要关闭**选择项目类型**没有选择并分配一个项，请单击对话框**取消**。</span><span class="sxs-lookup"><span data-stu-id="ff9be-143">To close the **Select Artifact Type** dialog box without selecting and assigning an item, click **Cancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff9be-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff9be-144">See Also</span></span>  
 <span data-ttu-id="ff9be-145">[业务流程形状](../core/orchestration-shapes.md) </span><span class="sxs-lookup"><span data-stu-id="ff9be-145">[Orchestration Shapes](../core/orchestration-shapes.md) </span></span>  
 <span data-ttu-id="ff9be-146">[如何向业务流程添加形状](../core/how-to-add-shapes-to-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="ff9be-146">[How to Add Shapes to Orchestrations](../core/how-to-add-shapes-to-orchestrations.md) </span></span>  
 [<span data-ttu-id="ff9be-147">如何将参数添加到业务流程</span><span class="sxs-lookup"><span data-stu-id="ff9be-147">How to Add Parameters to Orchestrations</span></span>](../core/how-to-add-parameters-to-orchestrations.md)