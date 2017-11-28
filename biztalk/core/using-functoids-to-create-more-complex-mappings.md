---
title: "使用 Functoid 创建更复杂的映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d53e3a3-5ccd-4733-8c2f-3101e41fca61
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 736b6fa99844182c59db582182056faea1d3f322
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-functoids-to-create-more-complex-mappings"></a><span data-ttu-id="8bb7a-102">使用 Functoid 创建更复杂的映射</span><span class="sxs-lookup"><span data-stu-id="8bb7a-102">Using Functoids to Create More Complex Mappings</span></span>

## <a name="overview"></a><span data-ttu-id="8bb7a-103">概述</span><span class="sxs-lookup"><span data-stu-id="8bb7a-103">Overview</span></span>
<span data-ttu-id="8bb7a-104">Functoid 在许多映射方案中都起到非常重要的作用。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-104">Functoids play a crucial role in many mapping scenarios.</span></span> <span data-ttu-id="8bb7a-105">如果不使用 functoid，虽然可以复制元素数据和属性数据，但将无法有效地处理这些值本身。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-105">Without functoids, you can copy element and attribute data, but you cannot, to any significant extent, manipulate the values themselves.</span></span> <span data-ttu-id="8bb7a-106">使用 functoid，几乎可以执行任何转换。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-106">Using functoids, almost any transformation is possible.</span></span> <span data-ttu-id="8bb7a-107">例如，使用 functoid，您可以从完全不同的位置获取两个值，将这两个值相加，然后将所得的和置于目标架构中。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-107">For example, with a functoid you can take two values from entirely different locations, add them together, and place the sum in the destination schema.</span></span>  
  
 <span data-ttu-id="8bb7a-108">Functoid 出现在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱中，每个类别，当你编辑 BizTalk 映射时的一个工具箱选项卡。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-108">Functoids appear in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox, one toolbox tab per category, when you are editing a BizTalk map.</span></span> <span data-ttu-id="8bb7a-109">在打开工具箱并通过单击相应的选项卡选择 functoid 类别后，即可将所需的 functoid 拖至网格页上。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-109">After you open the Toolbox and choose a category of functoids by clicking on the corresponding tab, you drag the functoid onto a grid page.</span></span> <span data-ttu-id="8bb7a-110">然后，您可以在 functoid 与 schema 节点或其他 functoid 之间创建输入链接和输出链接。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-110">Then you create input and output links between the functoid and either schema nodes or another functoid.</span></span> <span data-ttu-id="8bb7a-111">输入链接对应于输入参数，从左侧进入 functoid；输出链接对应于输出参数，从 functoid 右侧引出。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-111">Input links correspond to input parameters and lead to a functoid from the left; an output link corresponds to the output parameter and leaves a functoid to the right.</span></span>  
  
 <span data-ttu-id="8bb7a-112">与其他映射元素相似，functoid 也具有属性。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-112">Like other map elements, functoids have properties.</span></span> <span data-ttu-id="8bb7a-113">functoid 的最重要的属性之一是其输入参数集。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-113">One of the most important properties of a functoid is its set of input parameters.</span></span> <span data-ttu-id="8bb7a-114">有关详细信息，请参阅[如何向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-114">For more information, see [How to Add Basic Functoids to a Map](../core/how-to-add-basic-functoids-to-a-map.md).</span></span>  
  
 <span data-ttu-id="8bb7a-115">本部分提供有关在 BizTalk 映射内使用 functoid 的逐步说明。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-115">This section provides step-by-step instructions for working with functoids within BizTalk maps.</span></span> <span data-ttu-id="8bb7a-116">有关 functoid 参考信息，请参阅**Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="8bb7a-116">For reference information about functoids, see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="8bb7a-117">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8bb7a-117">Next steps</span></span> 
  
-   [<span data-ttu-id="8bb7a-118">如何打开 Functoid 工具箱</span><span class="sxs-lookup"><span data-stu-id="8bb7a-118">How to Open the Functoid Toolbox</span></span>](../core/how-to-open-the-functoid-toolbox.md)  
  
-   [<span data-ttu-id="8bb7a-119">如何在向地图添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="8bb7a-119">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="8bb7a-120">向地图添加高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="8bb7a-120">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="8bb7a-121">编辑 Functoid 属性和输入的参数</span><span class="sxs-lookup"><span data-stu-id="8bb7a-121">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)  
  
-   [<span data-ttu-id="8bb7a-122">如何选择多个 Functoid</span><span class="sxs-lookup"><span data-stu-id="8bb7a-122">How to Select Multiple Functoids</span></span>](../core/how-to-select-multiple-functoids.md)  
  
-   [<span data-ttu-id="8bb7a-123">如何删除 Functoid</span><span class="sxs-lookup"><span data-stu-id="8bb7a-123">How to Delete Functoids</span></span>](../core/how-to-delete-functoids.md)  
  
-   [<span data-ttu-id="8bb7a-124">如何复制、 剪切和粘贴 Functoid</span><span class="sxs-lookup"><span data-stu-id="8bb7a-124">How to Copy, Cut, and Paste a Functoid</span></span>](../core/how-to-copy-cut-and-paste-a-functoid.md)