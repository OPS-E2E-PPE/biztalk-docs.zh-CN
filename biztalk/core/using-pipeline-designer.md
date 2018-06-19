---
title: 使用管道设计器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, how to
- pipelines, Pipeline Designer
ms.assetid: bdb2f5c7-f8a2-4bd6-a8d8-8b7a64f97bd0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce7a8bc7c7943ff96f0d70a802a2756f8d8c4783
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287829"
---
# <a name="using-pipeline-designer"></a><span data-ttu-id="cd27c-102">使用管道设计器</span><span class="sxs-lookup"><span data-stu-id="cd27c-102">Using Pipeline Designer</span></span>
<span data-ttu-id="cd27c-103">管道设计器是一个以 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 为宿主的图形编辑器，使用该设计器，可以创建新的管道；查看 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 附带的管道模板；在管道中移动管道组件以及配置管道、阶段和管道组件。</span><span class="sxs-lookup"><span data-stu-id="cd27c-103">Pipeline Designer is a graphical editor, hosted in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], which enables you to create new pipelines; view the pipeline templates included with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]; move pipeline components within a pipeline; and configure pipelines, stages, and pipeline components.</span></span>  
  
 <span data-ttu-id="cd27c-104">管道设计器采用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 外壳程序的三个主要工具来丰富您的设计体验：</span><span class="sxs-lookup"><span data-stu-id="cd27c-104">Pipeline Designer uses three key tools of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell as part of the design experience:</span></span>  
  
-   <span data-ttu-id="cd27c-105">“属性”窗口，用于查看和修改管道对象的大多数特性。</span><span class="sxs-lookup"><span data-stu-id="cd27c-105">The Properties window, where most of the characteristics of pipeline objects are viewed and modified.</span></span>  
  
-   <span data-ttu-id="cd27c-106">工具箱，用作设计图面的来源。</span><span class="sxs-lookup"><span data-stu-id="cd27c-106">The Toolbox, which is used as a source for the design surface.</span></span>  
  
-   <span data-ttu-id="cd27c-107">设计图面，用于从工具箱拖放组件。</span><span class="sxs-lookup"><span data-stu-id="cd27c-107">The design surface, where components from the Toolbox are dragged and dropped.</span></span>  
  
 <span data-ttu-id="cd27c-108">下图显示了管道设计器环境。</span><span class="sxs-lookup"><span data-stu-id="cd27c-108">The following figure shows the Pipeline Designer environment.</span></span>  
  
 <span data-ttu-id="cd27c-109">![管道设计器编辑环境](../core/media/ebiz-prog-usepipe.gif "ebiz_prog_usepipe")</span><span class="sxs-lookup"><span data-stu-id="cd27c-109">![The Pipeline Designer editing environment](../core/media/ebiz-prog-usepipe.gif "ebiz_prog_usepipe")</span></span>  
<span data-ttu-id="cd27c-110">管道设计器环境示意图</span><span class="sxs-lookup"><span data-stu-id="cd27c-110">Depicts the Pipeline Designer environment.</span></span>  
  
 <span data-ttu-id="cd27c-111">管道设计器与 BizTalk 项目模板进行了集成，以增强您的开发体验。</span><span class="sxs-lookup"><span data-stu-id="cd27c-111">Pipeline Designer is integrated with the BizTalk project template to enhance your development experience.</span></span> <span data-ttu-id="cd27c-112">使用项目系统创建新的 BizTalk 项目之后, 你可以使用**添加新项**命令**文件**菜单添加到你的解决方案的管道。</span><span class="sxs-lookup"><span data-stu-id="cd27c-112">After using the project system to create a new BizTalk project, you can use the **Add New Item** command on the **File** menu to add a pipeline to your solution.</span></span> <span data-ttu-id="cd27c-113">有关 BizTalk 项目模板的详细信息，请参阅[使用 BizTalk 项目系统](../core/using-the-biztalk-project-system.md)。</span><span class="sxs-lookup"><span data-stu-id="cd27c-113">For more information about the BizTalk project template, see [Using the BizTalk Project System](../core/using-the-biztalk-project-system.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cd27c-114">在早期版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，管道的概念包含在消息通道和端口中，它定义了一组按固定顺序应用于文档的特定组件。</span><span class="sxs-lookup"><span data-stu-id="cd27c-114">In previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the concept of a pipeline was encapsulated in message channels and ports, which defined a set order of specific components that were applied to a document.</span></span> <span data-ttu-id="cd27c-115">在此版本中，管道非常灵活，不仅可以随意重排管道的各个阶段的组件，还可以在管道内轻松插入多个自定义组件。</span><span class="sxs-lookup"><span data-stu-id="cd27c-115">In this version, the pipeline is flexible because you are free to reorder the components in each stage of the pipeline and can easily insert multiple custom components throughout the pipeline.</span></span>  
  
 <span data-ttu-id="cd27c-116">通过管道设计器设计图面，您可以绘制管道的图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="cd27c-116">The Pipeline Designer design surface enables you to draw a graphical representation of a pipeline.</span></span> <span data-ttu-id="cd27c-117">设计图面所占据的主要部分[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]窗口并使你能够编辑 BizTalk 项目所属于的管道。</span><span class="sxs-lookup"><span data-stu-id="cd27c-117">The design surface occupies the main section of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window and enables you to edit the pipelines belonging to a BizTalk project.</span></span> <span data-ttu-id="cd27c-118">通过单击设计图面上方的选项卡，可以在管道之间进行导航。</span><span class="sxs-lookup"><span data-stu-id="cd27c-118">You can navigate between pipelines by clicking the tabs above the design surface.</span></span>  
  
 <span data-ttu-id="cd27c-119">每个管道都由多个阶段构成，每个阶段包含一个或多个组件。</span><span class="sxs-lookup"><span data-stu-id="cd27c-119">Each pipeline is composed of stages, with each stage containing one or more components.</span></span> <span data-ttu-id="cd27c-120">如果阶段中没有组件，则将显示带文本的水印，指示可以从工具箱插入形状。</span><span class="sxs-lookup"><span data-stu-id="cd27c-120">If there are no components in a stage, a watermark with text indicates that shapes can be inserted from the Toolbox.</span></span> <span data-ttu-id="cd27c-121">向阶段中插入第一个形状之后，原来的文本将消失。</span><span class="sxs-lookup"><span data-stu-id="cd27c-121">When the first shape is inserted into a stage, the initial text disappears.</span></span> <span data-ttu-id="cd27c-122">设计图面沿垂直方向显示管道，运行顺序为从上（开始）到下（结束）。</span><span class="sxs-lookup"><span data-stu-id="cd27c-122">The design surface shows the pipeline vertically, running from top (start) to bottom (end).</span></span>  
  
 <span data-ttu-id="cd27c-123">如其他常见的 Microsoft Windows 程序，你可以执行多个任务，如**打开**和**保存**从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="cd27c-123">As with other common Microsoft Windows programs, you can perform several tasks, such as **Open** and **Save** from the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd27c-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd27c-124">See Also</span></span>  
 <span data-ttu-id="cd27c-125">[使用管道设计器中创建管道](../core/creating-pipelines-with-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="cd27c-125">[Creating Pipelines with Pipeline Designer](../core/creating-pipelines-with-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="cd27c-126">创建管道使用管道设计器</span><span class="sxs-lookup"><span data-stu-id="cd27c-126">Creating Pipelines Using Pipeline Designer</span></span>](../core/creating-pipelines-using-pipeline-designer.md)