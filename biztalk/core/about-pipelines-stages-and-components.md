---
title: 关于管道、 阶段和组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Microsoft.BizTalk.Component.Interop namespace
- pipelines, about pipelines
ms.assetid: a98e1c93-f264-4577-bd12-4430a5859e3c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04bef6e1c443ca2723029014f5a4d3b703b4d7a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362348"
---
# <a name="about-pipelines-stages-and-components"></a><span data-ttu-id="79689-102">关于管道、 阶段和组件</span><span class="sxs-lookup"><span data-stu-id="79689-102">About Pipelines, Stages, and Components</span></span>
<span data-ttu-id="79689-103">管道是一种软件基础结构，其中包含一组按预定义的顺序处理消息的.NET 或 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="79689-103">A pipeline is a piece of software infrastructure that contains a set of .NET or COM components that process messages in a predefined sequence.</span></span> <span data-ttu-id="79689-104">管道将处理到类别的工作为称作阶段，并确定的执行阶段的。</span><span class="sxs-lookup"><span data-stu-id="79689-104">A pipeline divides processing into categories of work called stages, and determines the sequence in which the stages are performed.</span></span> <span data-ttu-id="79689-105">每个阶段定义逻辑工作组，确定哪些组件可以在该阶段中，转并指定如何运行阶段中的管道组件。</span><span class="sxs-lookup"><span data-stu-id="79689-105">Each stage defines logical work groups, determines which components can go in that stage, and specifies how the pipeline components in the stage are run.</span></span>  
  
 <span data-ttu-id="79689-106">在每个阶段，管道组件执行特定任务。</span><span class="sxs-lookup"><span data-stu-id="79689-106">Within each stage, pipeline components perform specific tasks.</span></span> <span data-ttu-id="79689-107">例如，接收管道的阶段中的组件可能解码、 反汇编程序，且然后将文档从其他格式转换为 XML。</span><span class="sxs-lookup"><span data-stu-id="79689-107">For example, components within stages of a receive pipeline may decode, disassemble, and then convert documents from other formats to XML.</span></span> <span data-ttu-id="79689-108">发送管道的操作与此正好相反： 将文档从 XML 转换为其他格式、 组装和加密，其中每个管道组件执行整个过程的一部分。</span><span class="sxs-lookup"><span data-stu-id="79689-108">Send pipelines do essentially the opposite: convert documents from XML to other formats, assemble, and encrypt, with each pipeline component performing a portion of the entire process.</span></span> <span data-ttu-id="79689-109">尽管阶段是组件的容器，每个阶段本身就是具有元数据的组件。</span><span class="sxs-lookup"><span data-stu-id="79689-109">Although a stage is a container of components, each stage is itself a component with metadata.</span></span> <span data-ttu-id="79689-110">阶段有执行代码，而不是管道组件，它们具有执行代码。</span><span class="sxs-lookup"><span data-stu-id="79689-110">Stages have no execution code, as opposed to pipeline components, which do have execution code.</span></span>  
  
 <span data-ttu-id="79689-111">下图显示了如何在管道设计图面了管道。</span><span class="sxs-lookup"><span data-stu-id="79689-111">The following figure shows how the pipeline design surface illustrates pipelines.</span></span> <span data-ttu-id="79689-112">此管道包含两个阶段，即组装阶段和编码阶段。</span><span class="sxs-lookup"><span data-stu-id="79689-112">This pipeline has two stages, the Assemble stage and the Encode stage.</span></span> <span data-ttu-id="79689-113">XML 组装器管道组件已添加到组装阶段中，但编码阶段仍然为空，因为它仍显示**放到此处 ！**</span><span class="sxs-lookup"><span data-stu-id="79689-113">The XML Assembler pipeline component was added to the Assemble stage, but the Encode stage is still empty, because it still shows **Drop Here!**</span></span> <span data-ttu-id="79689-114">指示可以向阶段添加管道组件。</span><span class="sxs-lookup"><span data-stu-id="79689-114">to indicate that a pipeline component can be added to the stage.</span></span>  
  
 <span data-ttu-id="79689-115">![阶段和 BizTalk 管道中的组件](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span><span class="sxs-lookup"><span data-stu-id="79689-115">![Stages and components in a BizTalk pipeline](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span></span>  
<span data-ttu-id="79689-116">说明了阶段和 BizTalk 管道中的组件。</span><span class="sxs-lookup"><span data-stu-id="79689-116">Illustrates stages and components in a BizTalk pipeline.</span></span>  
  
 <span data-ttu-id="79689-117">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含一组管道模板、 管道组件和默认管道。</span><span class="sxs-lookup"><span data-stu-id="79689-117">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] contains a set of pipeline templates, pipeline components, and default pipelines.</span></span> <span data-ttu-id="79689-118">您可以创建和配置管道通过使用管道设计器用户界面;使用中的 API 实现管道**Microsoft.BizTalk.Component.Interop**命名空间。</span><span class="sxs-lookup"><span data-stu-id="79689-118">You can create and configure pipelines by using the Pipeline Designer user interface; you implement pipelines by using the API in the **Microsoft.BizTalk.Component.Interop** namespace.</span></span> <span data-ttu-id="79689-119">无法修改管道模板。</span><span class="sxs-lookup"><span data-stu-id="79689-119">You cannot modify the pipeline templates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79689-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="79689-120">In This Section</span></span>  
  
-   [<span data-ttu-id="79689-121">类型的管道</span><span class="sxs-lookup"><span data-stu-id="79689-121">Types of Pipelines</span></span>](../core/types-of-pipelines.md)  
  
-   [<span data-ttu-id="79689-122">类型的管道组件</span><span class="sxs-lookup"><span data-stu-id="79689-122">Types of Pipeline Components</span></span>](../core/types-of-pipeline-components.md)  
  
-   [<span data-ttu-id="79689-123">管道阶段</span><span class="sxs-lookup"><span data-stu-id="79689-123">Pipeline Stages</span></span>](../core/pipeline-stages.md)  
  
-   [<span data-ttu-id="79689-124">默认管道</span><span class="sxs-lookup"><span data-stu-id="79689-124">Default Pipelines</span></span>](../core/default-pipelines.md)  
  
-   [<span data-ttu-id="79689-125">管道模板</span><span class="sxs-lookup"><span data-stu-id="79689-125">Pipeline Templates</span></span>](../core/pipeline-templates.md)  
  
-   [<span data-ttu-id="79689-126">管道组件</span><span class="sxs-lookup"><span data-stu-id="79689-126">Pipeline Components</span></span>](../core/pipeline-components.md)  
  
-   [<span data-ttu-id="79689-127">管道组件中的架构解析</span><span class="sxs-lookup"><span data-stu-id="79689-127">Schema Resolution in Pipeline Components</span></span>](../core/schema-resolution-in-pipeline-components.md)  
  
-   [<span data-ttu-id="79689-128">在 XML 汇编程序和反汇编程序管道组件中使用信封</span><span class="sxs-lookup"><span data-stu-id="79689-128">Envelope Use in the XML Assembler and Disassembler Pipeline Components</span></span>](../core/envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components.md)  
  
-   [<span data-ttu-id="79689-129">汇编程序管道组件中的属性降级</span><span class="sxs-lookup"><span data-stu-id="79689-129">Property Demotion in Assembler Pipeline Components</span></span>](../core/property-demotion-in-assembler-pipeline-components.md)  
  
-   [<span data-ttu-id="79689-130">管道组件中的属性升级</span><span class="sxs-lookup"><span data-stu-id="79689-130">Property Promotion in Disassembler Pipeline Components</span></span>](../core/property-promotion-in-disassembler-pipeline-components.md)  
  
-   [<span data-ttu-id="79689-131">反汇编程序管道组件中的可分辨字段</span><span class="sxs-lookup"><span data-stu-id="79689-131">Distinguished Fields in Disassembler Pipeline Components</span></span>](../core/distinguished-fields-in-disassembler-pipeline-components.md)