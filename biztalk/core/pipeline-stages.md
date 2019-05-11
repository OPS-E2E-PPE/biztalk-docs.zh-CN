---
title: 管道阶段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- CATID_AssemblingSerializer component category
- CATID_Encoder component category
- pipelines, stages
- CATID_DisassemblingParser component category
- CATID_Validate component category
- ComponentCategory class attribute
- CATID_Decoder component category
- CATID_Any component category
- CATID_PartyResolver component category
- Execution Mode property
ms.assetid: ac50c48c-6ed5-4322-95cc-af55df6bcd1c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3e24d6660e56bfbd44391b092152735f67fbb23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395779"
---
# <a name="pipeline-stages"></a><span data-ttu-id="21041-102">管道阶段</span><span class="sxs-lookup"><span data-stu-id="21041-102">Pipeline Stages</span></span>
<span data-ttu-id="21041-103">本主题讨论**执行模式**属性和阶段关联。</span><span class="sxs-lookup"><span data-stu-id="21041-103">This topic discusses the **Execution Mode** property and stage affinity.</span></span>  
  
## <a name="execution-mode-property"></a><span data-ttu-id="21041-104">执行模式属性</span><span class="sxs-lookup"><span data-stu-id="21041-104">Execution Mode property</span></span>  
 <span data-ttu-id="21041-105">执行过程中的管道，管道阶段可以运行仅识别消息格式的第一个组件或所有组件。</span><span class="sxs-lookup"><span data-stu-id="21041-105">During the execution of a pipeline, the pipeline stages can run only the first component that recognizes the message format, or all components.</span></span> <span data-ttu-id="21041-106">属性，用于确定执行模式是**执行模式**。</span><span class="sxs-lookup"><span data-stu-id="21041-106">The property that determines the execution pattern is **Execution Mode**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21041-107">此属性在管道模板中包括的阶段上是只读的但了解其工作原理是一个重要概念。</span><span class="sxs-lookup"><span data-stu-id="21041-107">This property is read-only on the stages included in the pipeline templates, but understanding how it works is an important concept.</span></span>  
  
 <span data-ttu-id="21041-108">当**执行模式**属性设置为**所有**，阶段中的所有组件中配置的顺序都运行。</span><span class="sxs-lookup"><span data-stu-id="21041-108">When the **Execution Mode** property is set to **All**, all the components within the stage are run in the configured sequence.</span></span> <span data-ttu-id="21041-109">此模式下运行多个组件完成一项逻辑任务。</span><span class="sxs-lookup"><span data-stu-id="21041-109">This mode runs several components to complete a logical task.</span></span> <span data-ttu-id="21041-110">在这种情况下，如果任何组件在此管道阶段处理消息时遇到错误会导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="21041-110">In this case, a run-time error results if any component encounters an error while processing a message during this pipeline stage.</span></span>  
  
 <span data-ttu-id="21041-111">当管道用于接收多种格式的消息，然后**执行模式**属性设置为**FirstMatch**。</span><span class="sxs-lookup"><span data-stu-id="21041-111">When a pipeline is used to receive messages in several formats, then the **Execution Mode** property is set to **FirstMatch**.</span></span> <span data-ttu-id="21041-112">在此模式下，运行仅识别该消息的第一个组件。</span><span class="sxs-lookup"><span data-stu-id="21041-112">In this mode, only the first component that recognizes the message is run.</span></span> <span data-ttu-id="21041-113">如果阶段中的没有组件可识别消息，会运行时错误。</span><span class="sxs-lookup"><span data-stu-id="21041-113">If no components in the stage recognize the message, a run-time error results.</span></span>  
  
 <span data-ttu-id="21041-114">请注意，每个阶段可以具有其自己**执行模式**在管道中的设置，因此不同阶段可以具有不同的执行模式。</span><span class="sxs-lookup"><span data-stu-id="21041-114">Note that each stage can have its own **Execution Mode** setting, so different stages within a pipeline can have different execution modes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21041-115">在此版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，在发送中的所有阶段的都管道，并且除拆装的接收都管道中的所有阶段都具有的值**执行模式**属性设置为**所有**。</span><span class="sxs-lookup"><span data-stu-id="21041-115">In this release of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], all the stages in a send pipeline and all stages except Disassemble in a receive pipeline have the value of the **Execution Mode** property set to **All**.</span></span> <span data-ttu-id="21041-116">值**执行模式**拆装阶段中的属性设置为**FirstMatch**。</span><span class="sxs-lookup"><span data-stu-id="21041-116">The value of the **Execution Mode** property in the Disassemble stage is set to **FirstMatch**.</span></span> <span data-ttu-id="21041-117">不能更改**执行模式**阶段的属性。</span><span class="sxs-lookup"><span data-stu-id="21041-117">You cannot change the **Execution Mode** property of a stage.</span></span>  
  
#### <a name="to-read-pipeline-stage-properties"></a><span data-ttu-id="21041-118">若要查看管道阶段属性</span><span class="sxs-lookup"><span data-stu-id="21041-118">To read pipeline stage properties</span></span>  
  
1.  <span data-ttu-id="21041-119">在管道设计器中，单击的阶段形状。</span><span class="sxs-lookup"><span data-stu-id="21041-119">In Pipeline Designer, click a stage shape.</span></span>  
  
2.  <span data-ttu-id="21041-120">在属性窗口中**常规**部分中，读取以下属性：</span><span class="sxs-lookup"><span data-stu-id="21041-120">In the Properties window, in the **General** section, read the following properties:</span></span>  
  
    |<span data-ttu-id="21041-121">使用此选项</span><span class="sxs-lookup"><span data-stu-id="21041-121">Use this</span></span>|<span data-ttu-id="21041-122">执行的操作</span><span class="sxs-lookup"><span data-stu-id="21041-122">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="21041-123">**名称**</span><span class="sxs-lookup"><span data-stu-id="21041-123">**Name**</span></span>|<span data-ttu-id="21041-124">指示阶段的名称。</span><span class="sxs-lookup"><span data-stu-id="21041-124">Indicates the name of the stage.</span></span>|  
    |<span data-ttu-id="21041-125">**执行模式**</span><span class="sxs-lookup"><span data-stu-id="21041-125">**Execution Mode**</span></span>|<span data-ttu-id="21041-126">指示阶段的执行模式。</span><span class="sxs-lookup"><span data-stu-id="21041-126">Indicates the execution pattern of the stage.</span></span><br /><br /> <span data-ttu-id="21041-127">有效的值：**所有**或**第一个匹配**</span><span class="sxs-lookup"><span data-stu-id="21041-127">Valid values: **All** or **FirstMatch**</span></span>|  
    |<span data-ttu-id="21041-128">**最小组件数**</span><span class="sxs-lookup"><span data-stu-id="21041-128">**Minimum Number of Components**</span></span>|<span data-ttu-id="21041-129">指示可向阶段添加管道组件的最小数目。</span><span class="sxs-lookup"><span data-stu-id="21041-129">Indicates the minimum number of pipeline components that can be added to the stage.</span></span>|  
    |<span data-ttu-id="21041-130">**最大组件数**</span><span class="sxs-lookup"><span data-stu-id="21041-130">**Maximum Number of Components**</span></span>|<span data-ttu-id="21041-131">指示可向阶段添加管道组件的最大数目。</span><span class="sxs-lookup"><span data-stu-id="21041-131">Indicates the maximum number of pipeline components that can be added to the stage.</span></span>|  
    |<span data-ttu-id="21041-132">**StageID**</span><span class="sxs-lookup"><span data-stu-id="21041-132">**StageID**</span></span>|<span data-ttu-id="21041-133">指示阶段的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="21041-133">Indicates the unique identifier for the stage.</span></span>|  
  
## <a name="stage-affinity"></a><span data-ttu-id="21041-134">阶段关联</span><span class="sxs-lookup"><span data-stu-id="21041-134">Stage affinity</span></span>  
 <span data-ttu-id="21041-135">管道组件有阶段关联，这意味着在创建某个特定阶段或管道中的阶段中使用。</span><span class="sxs-lookup"><span data-stu-id="21041-135">Pipeline components have stage affinity, meaning that they are created for use within a particular stage or stages in a pipeline.</span></span>  
  
 <span data-ttu-id="21041-136">基于 COM 的管道组件通过使用阶段 ID 作为实现类别中，将自己注册来表示它们的阶段关联时。基于 NET 的管道组件通过使用指定它们的阶段关联**ComponentCategory**类属性。</span><span class="sxs-lookup"><span data-stu-id="21041-136">COM-based pipeline components express their stage affinity by registering themselves using the stage ID as the implementation category, while .NET-based pipeline components specify their stage affinity by using the **ComponentCategory** class attribute.</span></span> <span data-ttu-id="21041-137">请注意，很可能要将自身与多个阶段相关联的组件，组件可以有多个实现类别或**ComponentCategory**属性。</span><span class="sxs-lookup"><span data-stu-id="21041-137">Note that it is possible for a component to associate itself with more than one stage—components can have more than one implementation category or **ComponentCategory** attribute.</span></span>  
  
 <span data-ttu-id="21041-138">下表显示了可用的组件类别和及其关联的阶段。</span><span class="sxs-lookup"><span data-stu-id="21041-138">The following table shows the available component categories and their associated stages.</span></span>  
  
|<span data-ttu-id="21041-139">组件类别</span><span class="sxs-lookup"><span data-stu-id="21041-139">Component category</span></span>|<span data-ttu-id="21041-140">何处可放置组件的阶段</span><span class="sxs-lookup"><span data-stu-id="21041-140">Stage where component can be placed</span></span>|<span data-ttu-id="21041-141">Description</span><span class="sxs-lookup"><span data-stu-id="21041-141">Description</span></span>|  
|------------------------|-----------------------------------------|-----------------|  
|<span data-ttu-id="21041-142">CATID_Decoder {9d0e4103-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="21041-142">CATID_Decoder {9d0e4103-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="21041-143">解码</span><span class="sxs-lookup"><span data-stu-id="21041-143">Decode</span></span>|<span data-ttu-id="21041-144">所有解码组件都应都实现此类别。</span><span class="sxs-lookup"><span data-stu-id="21041-144">All decoding components should implement this category.</span></span>|  
|<span data-ttu-id="21041-145">CATID_DisassemblingParser {9d0e4105-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="21041-145">CATID_DisassemblingParser {9d0e4105-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="21041-146">反汇编</span><span class="sxs-lookup"><span data-stu-id="21041-146">Disassemble</span></span>|<span data-ttu-id="21041-147">所有拆装组件和解析组件应实现此类别。</span><span class="sxs-lookup"><span data-stu-id="21041-147">All disassembling and parsing components should implement this category.</span></span>|  
|<span data-ttu-id="21041-148">CATID_Validate {9d0e410d-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="21041-148">CATID_Validate {9d0e410d-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="21041-149">验证</span><span class="sxs-lookup"><span data-stu-id="21041-149">Validate</span></span>|<span data-ttu-id="21041-150">验证组件应实现此类别。</span><span class="sxs-lookup"><span data-stu-id="21041-150">Validation components should implement this category.</span></span>|  
|<span data-ttu-id="21041-151">CATID_PartyResolver {9d0e410e-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="21041-151">CATID_PartyResolver {9d0e410e-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="21041-152">ResolveParty</span><span class="sxs-lookup"><span data-stu-id="21041-152">ResolveParty</span></span>|<span data-ttu-id="21041-153">用于参与方解析组件的阶段。</span><span class="sxs-lookup"><span data-stu-id="21041-153">Stage used for Party Resolution component.</span></span>|  
|<span data-ttu-id="21041-154">CATID_Encoder {9d0e4108-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="21041-154">CATID_Encoder {9d0e4108-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="21041-155">编码</span><span class="sxs-lookup"><span data-stu-id="21041-155">Encode</span></span>|<span data-ttu-id="21041-156">所有编码组件应实现此类别。</span><span class="sxs-lookup"><span data-stu-id="21041-156">All encoding components should implement this category.</span></span>|  
|<span data-ttu-id="21041-157">CATID_AssemblingSerializer {9d0e4107-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="21041-157">CATID_AssemblingSerializer {9d0e4107-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="21041-158">序列化</span><span class="sxs-lookup"><span data-stu-id="21041-158">Serialize</span></span>|<span data-ttu-id="21041-159">所有序列化和组装组件应实现此类别。</span><span class="sxs-lookup"><span data-stu-id="21041-159">All serializing and assembling components should implement this category.</span></span>|  
|<span data-ttu-id="21041-160">CATID_Any {9d0e4101-4cce-4536-83fa-4a5040674ad6}</span><span class="sxs-lookup"><span data-stu-id="21041-160">CATID_Any {9d0e4101-4cce-4536-83fa-4a5040674ad6}</span></span>|<span data-ttu-id="21041-161">这些阶段的任何</span><span class="sxs-lookup"><span data-stu-id="21041-161">Any of these stages</span></span>|<span data-ttu-id="21041-162">如果某管道组件实现此类别，则意味着该组件可置于任何阶段的管道。</span><span class="sxs-lookup"><span data-stu-id="21041-162">If a pipeline component implements this category, it means that the component can be placed into any stage of a pipeline.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21041-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="21041-163">See Also</span></span>  
 <span data-ttu-id="21041-164">[使用管道设计器创建管道](../core/creating-pipelines-using-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="21041-164">[Creating Pipelines Using Pipeline Designer](../core/creating-pipelines-using-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="21041-165">关于管道、阶段和组件</span><span class="sxs-lookup"><span data-stu-id="21041-165">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)