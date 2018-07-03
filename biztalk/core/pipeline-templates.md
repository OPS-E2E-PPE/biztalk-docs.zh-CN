---
title: 管道模板 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, templates
- Pipeline Designer, templates
- send pipelines, templates
- receive pipelines, templates
ms.assetid: b9779159-e49d-47fb-aa1c-06be5d604c67
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8075611bbf1f64de7b69ee92e1078dc5046c5de4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984982"
---
# <a name="pipeline-templates"></a><span data-ttu-id="ddbbb-102">管道模板</span><span class="sxs-lookup"><span data-stu-id="ddbbb-102">Pipeline Templates</span></span>
<span data-ttu-id="ddbbb-103">除了默认管道，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括两个管道模板： 接收管道模板和发送管道模板。</span><span class="sxs-lookup"><span data-stu-id="ddbbb-103">In addition to the default pipelines, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] includes two pipeline templates: a receive pipeline template and a send pipeline template.</span></span> <span data-ttu-id="ddbbb-104">从 Microsoft 中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，可以向项目添加管道模板，通过使用**添加新项**命令**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="ddbbb-104">From a BizTalk project in Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], you can add a pipeline template to your project by using the **Add New Item** command on the **Project** menu.</span></span> <span data-ttu-id="ddbbb-105">每个模板都有一个关联的策略文件，该文件用于确定管道的阶段并指示管道中允许使用的管道组件。</span><span class="sxs-lookup"><span data-stu-id="ddbbb-105">Each template has an associated policy file, which determines the pipeline's stages and indicates which pipeline components are allowed in the pipeline.</span></span> <span data-ttu-id="ddbbb-106">虽然无法重排策略文件中的阶段，但可以使用管道设计器重排阶段中的组件。</span><span class="sxs-lookup"><span data-stu-id="ddbbb-106">While you cannot reorder the stages in a policy file, you can use Pipeline Designer to reorder the components within a stage.</span></span>  
  
 <span data-ttu-id="ddbbb-107">策略文件指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="ddbbb-107">A policy file specifies:</span></span>  
  
- <span data-ttu-id="ddbbb-108">阶段的顺序。</span><span class="sxs-lookup"><span data-stu-id="ddbbb-108">The sequence of stages.</span></span>  
  
- <span data-ttu-id="ddbbb-109">每个阶段允许使用的组件数。</span><span class="sxs-lookup"><span data-stu-id="ddbbb-109">The number of components allowed per stage.</span></span>  
  
- <span data-ttu-id="ddbbb-110">各个阶段的执行模式。</span><span class="sxs-lookup"><span data-stu-id="ddbbb-110">The execution mode of each stage.</span></span>  
  
  <span data-ttu-id="ddbbb-111">管道模板的策略文件存储在 *\<BizTalk Server 安装目录\>* tools\pipeline Policy Files。</span><span class="sxs-lookup"><span data-stu-id="ddbbb-111">The policy files for the pipeline templates are stored in *\<BizTalk Server installation directory\>* \Developer Tools\Pipeline Policy Files.</span></span> <span data-ttu-id="ddbbb-112">不要修改策略文件。</span><span class="sxs-lookup"><span data-stu-id="ddbbb-112">Do not modify the policy files.</span></span> <span data-ttu-id="ddbbb-113">若要更改管道，请打开管道模板，然后使用管道设计器修改该管道。</span><span class="sxs-lookup"><span data-stu-id="ddbbb-113">To make changes to a pipeline, open the pipeline template and use Pipeline Designer to modify it.</span></span> <span data-ttu-id="ddbbb-114">有关使用管道设计器的详细信息，请参阅[使用管道设计器](../core/using-pipeline-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="ddbbb-114">For more information about using Pipeline Designer, see [Using Pipeline Designer](../core/using-pipeline-designer.md).</span></span>  
  
  <span data-ttu-id="ddbbb-115">空管道模板文件存储在 *\<BizTalk Server 安装目录\>* tools\biztalkprojectitems 中,，名为 BTSReceivePipeline.btp 和 BTSTransmitPipeline.btp.</span><span class="sxs-lookup"><span data-stu-id="ddbbb-115">The empty pipeline template files are stored in *\<BizTalk Server installation directory\>* \Developer Tools\BizTalkProjectItems, and are named BTSReceivePipeline.btp and BTSTransmitPipeline.btp.</span></span> <span data-ttu-id="ddbbb-116">文件扩展名.btp 指示该文件是一个 BizTalk Server 管道，并且可以在管道设计器中编辑。</span><span class="sxs-lookup"><span data-stu-id="ddbbb-116">The file name extension .btp indicates that the file is a BizTalk Server pipeline and can be edited in Pipeline Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddbbb-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddbbb-117">See Also</span></span>  
 <span data-ttu-id="ddbbb-118">[管道类型](../core/types-of-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="ddbbb-118">[Types of Pipelines](../core/types-of-pipelines.md) </span></span>  
 <span data-ttu-id="ddbbb-119">[类型的管道组件](../core/types-of-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="ddbbb-119">[Types of Pipeline Components](../core/types-of-pipeline-components.md) </span></span>  
 <span data-ttu-id="ddbbb-120">[默认管道](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="ddbbb-120">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 <span data-ttu-id="ddbbb-121">[管道组件](../core/pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="ddbbb-121">[Pipeline Components](../core/pipeline-components.md) </span></span>  
 [<span data-ttu-id="ddbbb-122">关于管道、阶段和组件</span><span class="sxs-lookup"><span data-stu-id="ddbbb-122">About Pipelines, Stages, and Components</span></span>](../core/about-pipelines-stages-and-components.md)