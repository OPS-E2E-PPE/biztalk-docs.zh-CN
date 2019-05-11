---
title: 如何向管道添加组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, components
ms.assetid: 6b1dbeab-6acc-46d7-8ddd-79b79da3591c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65db8b09dfcb7f1821746ffb5716e5f1e3f3e1dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387396"
---
# <a name="how-to-add-a-component-to-a-pipeline"></a><span data-ttu-id="6d26b-102">如何向管道添加组件</span><span class="sxs-lookup"><span data-stu-id="6d26b-102">How to Add a Component to a Pipeline</span></span>
<span data-ttu-id="6d26b-103">通过从工具箱拖动到设计图面可将组件添加到管道中。</span><span class="sxs-lookup"><span data-stu-id="6d26b-103">You add components to pipelines by dragging from the Toolbox to the design surface.</span></span>  
  
### <a name="to-add-a-component-to-a-pipeline"></a><span data-ttu-id="6d26b-104">若要向管道添加组件</span><span class="sxs-lookup"><span data-stu-id="6d26b-104">To add a component to a pipeline</span></span>  
  
- <span data-ttu-id="6d26b-105">在工具箱中，管道将组件拖放到**放到此处 ！**</span><span class="sxs-lookup"><span data-stu-id="6d26b-105">In the Toolbox, drag the pipeline component onto a **Drop Here!**</span></span> <span data-ttu-id="6d26b-106">在设计图面上的框。</span><span class="sxs-lookup"><span data-stu-id="6d26b-106">box on the design surface.</span></span>  
  
  <span data-ttu-id="6d26b-107">下图显示了如何在管道设计图面了管道。</span><span class="sxs-lookup"><span data-stu-id="6d26b-107">The following illustration shows how the pipeline design surface illustrates pipelines.</span></span> <span data-ttu-id="6d26b-108">此管道包含两个阶段，即组装阶段和编码阶段。</span><span class="sxs-lookup"><span data-stu-id="6d26b-108">This pipeline has two stages, the Assemble stage and the Encode stage.</span></span> <span data-ttu-id="6d26b-109">XML 组装器管道组件已添加到组装阶段中，但编码阶段仍然为空，因为它仍显示**放到此处 ！**</span><span class="sxs-lookup"><span data-stu-id="6d26b-109">The XML Assembler pipeline component was added to the Assemble stage, but the Encode stage is still empty, because it still shows **Drop Here!**</span></span> <span data-ttu-id="6d26b-110">指示可以向阶段添加管道组件。</span><span class="sxs-lookup"><span data-stu-id="6d26b-110">to indicate that a pipeline component can be added to the stage.</span></span>  
  
  <span data-ttu-id="6d26b-111">![阶段和 BizTalk 管道中的组件](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span><span class="sxs-lookup"><span data-stu-id="6d26b-111">![Stages and components in a BizTalk pipeline](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span></span>  
  <span data-ttu-id="6d26b-112">说明了阶段和 BizTalk 管道中的组件。</span><span class="sxs-lookup"><span data-stu-id="6d26b-112">Illustrates stages and components in a BizTalk pipeline.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d26b-113">管道组件只能放在设计图面上的特定位置。</span><span class="sxs-lookup"><span data-stu-id="6d26b-113">A pipeline component can only be dropped at specific places on the design surface.</span></span> <span data-ttu-id="6d26b-114">仅可以在其中之有阶段关联的阶段中删除管道组件。</span><span class="sxs-lookup"><span data-stu-id="6d26b-114">The pipeline component can only be dropped in a stage in which it has stage affinity.</span></span> <span data-ttu-id="6d26b-115">带有贯穿线的圆形旁边会显示指针不能放置管道组件。</span><span class="sxs-lookup"><span data-stu-id="6d26b-115">A circle with a line through it appears next to the pointer where the pipeline component cannot be dropped.</span></span> <span data-ttu-id="6d26b-116">显示一个箭头，并且设计图面上的部分将突出显示可以放置管道组件的位置。</span><span class="sxs-lookup"><span data-stu-id="6d26b-116">An arrow appears, and a portion of the design surface is highlighted where a pipeline component can be placed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d26b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d26b-117">See Also</span></span>  
 <span data-ttu-id="6d26b-118">[如何创建新的管道](../core/how-to-create-a-new-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="6d26b-118">[How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md) </span></span>  
 <span data-ttu-id="6d26b-119">[如何打开管道](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="6d26b-119">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="6d26b-120">[如何使用工具箱](../core/how-to-use-the-toolbox.md) </span><span class="sxs-lookup"><span data-stu-id="6d26b-120">[How to Use the Toolbox](../core/how-to-use-the-toolbox.md) </span></span>  
 <span data-ttu-id="6d26b-121">[如何使用键盘导航](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="6d26b-121">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="6d26b-122">使用管道设计器创建管道</span><span class="sxs-lookup"><span data-stu-id="6d26b-122">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)