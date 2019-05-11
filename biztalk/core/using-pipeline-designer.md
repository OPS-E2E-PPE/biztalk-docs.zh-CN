---
title: 使用管道设计器 |Microsoft Docs
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
ms.openlocfilehash: 9d69860203103990c642f5da13cdc916e1185581
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396596"
---
# <a name="using-pipeline-designer"></a><span data-ttu-id="f2dae-102">使用管道设计器</span><span class="sxs-lookup"><span data-stu-id="f2dae-102">Using Pipeline Designer</span></span>
<span data-ttu-id="f2dae-103">管道设计器是图形编辑器，在 Microsoft 中托管[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，其中，您可以创建新的管道; 查看 Microsoft 中附带的管道模板[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]; 管道; 中移动管道组件和配置管道、阶段和管道组件。</span><span class="sxs-lookup"><span data-stu-id="f2dae-103">Pipeline Designer is a graphical editor, hosted in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], which enables you to create new pipelines; view the pipeline templates included with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]; move pipeline components within a pipeline; and configure pipelines, stages, and pipeline components.</span></span>  
  
 <span data-ttu-id="f2dae-104">管道设计器使用的三个主要工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]作为设计体验的一部分的 shell:</span><span class="sxs-lookup"><span data-stu-id="f2dae-104">Pipeline Designer uses three key tools of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell as part of the design experience:</span></span>  
  
- <span data-ttu-id="f2dae-105">属性窗口中，在其中查看和修改的大多数管道对象的特性。</span><span class="sxs-lookup"><span data-stu-id="f2dae-105">The Properties window, where most of the characteristics of pipeline objects are viewed and modified.</span></span>  
  
- <span data-ttu-id="f2dae-106">工具箱作为源用于在设计图面。</span><span class="sxs-lookup"><span data-stu-id="f2dae-106">The Toolbox, which is used as a source for the design surface.</span></span>  
  
- <span data-ttu-id="f2dae-107">设计图面上，其中组件从工具箱拖放。</span><span class="sxs-lookup"><span data-stu-id="f2dae-107">The design surface, where components from the Toolbox are dragged and dropped.</span></span>  
  
  <span data-ttu-id="f2dae-108">下图显示了管道设计器环境。</span><span class="sxs-lookup"><span data-stu-id="f2dae-108">The following figure shows the Pipeline Designer environment.</span></span>  
  
  <span data-ttu-id="f2dae-109">![管道设计器编辑环境](../core/media/ebiz-prog-usepipe.gif "ebiz_prog_usepipe")</span><span class="sxs-lookup"><span data-stu-id="f2dae-109">![The Pipeline Designer editing environment](../core/media/ebiz-prog-usepipe.gif "ebiz_prog_usepipe")</span></span>  
  <span data-ttu-id="f2dae-110">描绘了管道设计器环境。</span><span class="sxs-lookup"><span data-stu-id="f2dae-110">Depicts the Pipeline Designer environment.</span></span>  
  
  <span data-ttu-id="f2dae-111">管道设计器与 BizTalk 项目模板，以增强您的开发体验集成。</span><span class="sxs-lookup"><span data-stu-id="f2dae-111">Pipeline Designer is integrated with the BizTalk project template to enhance your development experience.</span></span> <span data-ttu-id="f2dae-112">在使用项目系统创建一个新的 BizTalk 项目之后, 可以使用**添加新项**命令**文件**菜单添加到你的解决方案的管道。</span><span class="sxs-lookup"><span data-stu-id="f2dae-112">After using the project system to create a new BizTalk project, you can use the **Add New Item** command on the **File** menu to add a pipeline to your solution.</span></span> <span data-ttu-id="f2dae-113">有关 BizTalk 项目模板的详细信息，请参阅[使用 BizTalk 项目系统](../core/using-the-biztalk-project-system.md)。</span><span class="sxs-lookup"><span data-stu-id="f2dae-113">For more information about the BizTalk project template, see [Using the BizTalk Project System](../core/using-the-biztalk-project-system.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2dae-114">在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，管道的概念已封装在消息通道和端口，它定义了应用于文档的特定组件设置顺序。</span><span class="sxs-lookup"><span data-stu-id="f2dae-114">In previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the concept of a pipeline was encapsulated in message channels and ports, which defined a set order of specific components that were applied to a document.</span></span> <span data-ttu-id="f2dae-115">在此版本中，管道非常灵活，因为您可以随意重排管道的每个阶段中的组件，可以轻松地将整个管道的多个自定义组件。</span><span class="sxs-lookup"><span data-stu-id="f2dae-115">In this version, the pipeline is flexible because you are free to reorder the components in each stage of the pipeline and can easily insert multiple custom components throughout the pipeline.</span></span>  
  
 <span data-ttu-id="f2dae-116">管道设计器设计图面可以绘制管道的图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="f2dae-116">The Pipeline Designer design surface enables you to draw a graphical representation of a pipeline.</span></span> <span data-ttu-id="f2dae-117">在设计图面占据的主要部分[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]窗口并使您能够编辑属于 BizTalk 项目的管道。</span><span class="sxs-lookup"><span data-stu-id="f2dae-117">The design surface occupies the main section of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] window and enables you to edit the pipelines belonging to a BizTalk project.</span></span> <span data-ttu-id="f2dae-118">您可以通过单击设计图面上的选项卡的管道之间进行导航。</span><span class="sxs-lookup"><span data-stu-id="f2dae-118">You can navigate between pipelines by clicking the tabs above the design surface.</span></span>  
  
 <span data-ttu-id="f2dae-119">每个管道由几个阶段，每个阶段包含一个或多个组件组成。</span><span class="sxs-lookup"><span data-stu-id="f2dae-119">Each pipeline is composed of stages, with each stage containing one or more components.</span></span> <span data-ttu-id="f2dae-120">如果阶段中没有任何组件，用文本水印指示，可以从工具箱插入形状。</span><span class="sxs-lookup"><span data-stu-id="f2dae-120">If there are no components in a stage, a watermark with text indicates that shapes can be inserted from the Toolbox.</span></span> <span data-ttu-id="f2dae-121">第一个形状插入到一个阶段，初始文本将消失。</span><span class="sxs-lookup"><span data-stu-id="f2dae-121">When the first shape is inserted into a stage, the initial text disappears.</span></span> <span data-ttu-id="f2dae-122">在设计图面显示管道竖向，从顶部 （启动） 运行到下 （结束）。</span><span class="sxs-lookup"><span data-stu-id="f2dae-122">The design surface shows the pipeline vertically, running from top (start) to bottom (end).</span></span>  
  
 <span data-ttu-id="f2dae-123">一样与其他常用的 Microsoft Windows 程序，您可以执行多项任务，如**开放**并**保存**从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="f2dae-123">As with other common Microsoft Windows programs, you can perform several tasks, such as **Open** and **Save** from the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2dae-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2dae-124">See Also</span></span>  
 <span data-ttu-id="f2dae-125">[使用管道设计器创建管道](../core/creating-pipelines-with-pipeline-designer.md) </span><span class="sxs-lookup"><span data-stu-id="f2dae-125">[Creating Pipelines with Pipeline Designer](../core/creating-pipelines-with-pipeline-designer.md) </span></span>  
 [<span data-ttu-id="f2dae-126">使用管道设计器创建管道</span><span class="sxs-lookup"><span data-stu-id="f2dae-126">Creating Pipelines Using Pipeline Designer</span></span>](../core/creating-pipelines-using-pipeline-designer.md)