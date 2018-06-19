---
title: 如何将组件添加到管道 |Microsoft 文档
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
ms.openlocfilehash: 9a9f11f03e818ae1067bc22027822bfeef202260
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246477"
---
# <a name="how-to-add-a-component-to-a-pipeline"></a><span data-ttu-id="d6e2d-102">如何将组件添加到管道</span><span class="sxs-lookup"><span data-stu-id="d6e2d-102">How to Add a Component to a Pipeline</span></span>
<span data-ttu-id="d6e2d-103">通过将组件从工具箱拖至设计图面可以向管道添加组件。</span><span class="sxs-lookup"><span data-stu-id="d6e2d-103">You add components to pipelines by dragging from the Toolbox to the design surface.</span></span>  
  
### <a name="to-add-a-component-to-a-pipeline"></a><span data-ttu-id="d6e2d-104">若要将组件添加到管道</span><span class="sxs-lookup"><span data-stu-id="d6e2d-104">To add a component to a pipeline</span></span>  
  
-   <span data-ttu-id="d6e2d-105">在工具箱中，将管道组件拖放到**拖至此处 ！**</span><span class="sxs-lookup"><span data-stu-id="d6e2d-105">In the Toolbox, drag the pipeline component onto a **Drop Here!**</span></span> <span data-ttu-id="d6e2d-106">在设计图面上的框。</span><span class="sxs-lookup"><span data-stu-id="d6e2d-106">box on the design surface.</span></span>  
  
 <span data-ttu-id="d6e2d-107">下图显示如何管道设计图面阐释管道。</span><span class="sxs-lookup"><span data-stu-id="d6e2d-107">The following illustration shows how the pipeline design surface illustrates pipelines.</span></span> <span data-ttu-id="d6e2d-108">此管道有两个阶段，即组装阶段和编码阶段。</span><span class="sxs-lookup"><span data-stu-id="d6e2d-108">This pipeline has two stages, the Assemble stage and the Encode stage.</span></span> <span data-ttu-id="d6e2d-109">XML 汇编程序管道组件已添加到组装阶段中，但因为它仍将显示编码阶段是仍为空，**拖至此处 ！**</span><span class="sxs-lookup"><span data-stu-id="d6e2d-109">The XML Assembler pipeline component was added to the Assemble stage, but the Encode stage is still empty, because it still shows **Drop Here!**</span></span> <span data-ttu-id="d6e2d-110">若要指示管道组件，可以添加到的阶段。</span><span class="sxs-lookup"><span data-stu-id="d6e2d-110">to indicate that a pipeline component can be added to the stage.</span></span>  
  
 <span data-ttu-id="d6e2d-111">![阶段和 BizTalk 管道中的组件](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span><span class="sxs-lookup"><span data-stu-id="d6e2d-111">![Stages and components in a BizTalk pipeline](../core/media/ebiz-pipe-stages02.gif "ebiz_pipe_stages02")</span></span>  
<span data-ttu-id="d6e2d-112">BizTalk 管道中的阶段和组件说明图</span><span class="sxs-lookup"><span data-stu-id="d6e2d-112">Illustrates stages and components in a BizTalk pipeline.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6e2d-113">管道组件仅在设计图面上的特定位置中删除。</span><span class="sxs-lookup"><span data-stu-id="d6e2d-113">A pipeline component can only be dropped at specific places on the design surface.</span></span> <span data-ttu-id="d6e2d-114">管道组件只能放在与之有阶段关联的阶段中。</span><span class="sxs-lookup"><span data-stu-id="d6e2d-114">The pipeline component can only be dropped in a stage in which it has stage affinity.</span></span> <span data-ttu-id="d6e2d-115">如果指针旁出现一个带有贯穿线的圆圈，则表示指针处不能放置管道组件。</span><span class="sxs-lookup"><span data-stu-id="d6e2d-115">A circle with a line through it appears next to the pointer where the pipeline component cannot be dropped.</span></span> <span data-ttu-id="d6e2d-116">如果出现一个箭头，并且突出显示了设计图面部分，则表示该处可以放置管道组件。</span><span class="sxs-lookup"><span data-stu-id="d6e2d-116">An arrow appears, and a portion of the design surface is highlighted where a pipeline component can be placed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e2d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6e2d-117">See Also</span></span>  
 <span data-ttu-id="d6e2d-118">[如何创建一条新管道](../core/how-to-create-a-new-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="d6e2d-118">[How to Create a New Pipeline](../core/how-to-create-a-new-pipeline.md) </span></span>  
 <span data-ttu-id="d6e2d-119">[如何打开管道](../core/how-to-open-a-pipeline.md) </span><span class="sxs-lookup"><span data-stu-id="d6e2d-119">[How to Open a Pipeline](../core/how-to-open-a-pipeline.md) </span></span>  
 <span data-ttu-id="d6e2d-120">[如何使用工具箱](../core/how-to-use-the-toolbox.md) </span><span class="sxs-lookup"><span data-stu-id="d6e2d-120">[How to Use the Toolbox](../core/how-to-use-the-toolbox.md) </span></span>  
 <span data-ttu-id="d6e2d-121">[如何使用键盘导航](../core/how-to-navigate-with-the-keyboard.md) </span><span class="sxs-lookup"><span data-stu-id="d6e2d-121">[How to Navigate with the Keyboard](../core/how-to-navigate-with-the-keyboard.md) </span></span>  
 [<span data-ttu-id="d6e2d-122">使用管道设计器中创建管道</span><span class="sxs-lookup"><span data-stu-id="d6e2d-122">Creating Pipelines with Pipeline Designer</span></span>](../core/creating-pipelines-with-pipeline-designer.md)