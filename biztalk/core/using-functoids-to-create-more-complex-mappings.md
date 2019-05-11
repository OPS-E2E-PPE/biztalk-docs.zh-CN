---
title: 使用 Functoid 创建更复杂的映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d53e3a3-5ccd-4733-8c2f-3101e41fca61
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e16b692f3f91aff47e978080be124220db68a89
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247227"
---
# <a name="using-functoids-to-create-more-complex-mappings"></a><span data-ttu-id="a3c3b-102">使用 Functoid 创建更复杂的映射</span><span class="sxs-lookup"><span data-stu-id="a3c3b-102">Using Functoids to Create More Complex Mappings</span></span>

## <a name="overview"></a><span data-ttu-id="a3c3b-103">概述</span><span class="sxs-lookup"><span data-stu-id="a3c3b-103">Overview</span></span>
<span data-ttu-id="a3c3b-104">Functoid 在许多映射方案中扮演着重要角色。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-104">Functoids play a crucial role in many mapping scenarios.</span></span> <span data-ttu-id="a3c3b-105">如果不使用 functoid，您可以复制元素和属性数据，但您不能有效地，处理这些值本身。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-105">Without functoids, you can copy element and attribute data, but you cannot, to any significant extent, manipulate the values themselves.</span></span> <span data-ttu-id="a3c3b-106">使用 functoid，则有可能的几乎任何转换。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-106">Using functoids, almost any transformation is possible.</span></span> <span data-ttu-id="a3c3b-107">例如，functoid 您利用两个值从完全不同的位置，将它们相加，以及将其放在目标架构中。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-107">For example, with a functoid you can take two values from entirely different locations, add them together, and place the sum in the destination schema.</span></span>  
  
 <span data-ttu-id="a3c3b-108">Functoid 显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱中，每个类别，编辑 BizTalk 映射时的对应一个工具箱选项卡。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-108">Functoids appear in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox, one toolbox tab per category, when you are editing a BizTalk map.</span></span> <span data-ttu-id="a3c3b-109">在打开工具箱并通过单击相应的选项卡选择 functoid 类别后，您的 functoid 拖到网格页上。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-109">After you open the Toolbox and choose a category of functoids by clicking on the corresponding tab, you drag the functoid onto a grid page.</span></span> <span data-ttu-id="a3c3b-110">然后，您将创建输入和输出之间 functoid 与 schema 节点或另一个 functoid 的链接。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-110">Then you create input and output links between the functoid and either schema nodes or another functoid.</span></span> <span data-ttu-id="a3c3b-111">输入的链接对应于输入参数，并且会导致 functoid 从左;输出链接对应于输出参数，并使 functoid 右侧。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-111">Input links correspond to input parameters and lead to a functoid from the left; an output link corresponds to the output parameter and leaves a functoid to the right.</span></span>  
  
 <span data-ttu-id="a3c3b-112">像其他地图元素，functoid 也具有属性。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-112">Like other map elements, functoids have properties.</span></span> <span data-ttu-id="a3c3b-113">Functoid 的最重要属性之一是其组的输入参数。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-113">One of the most important properties of a functoid is its set of input parameters.</span></span> <span data-ttu-id="a3c3b-114">有关详细信息，请参阅[如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-114">For more information, see [How to Add Basic Functoids to a Map](../core/how-to-add-basic-functoids-to-a-map.md).</span></span>  
  
 <span data-ttu-id="a3c3b-115">本部分提供使用 BizTalk 映射内 functoid 的分步说明。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-115">This section provides step-by-step instructions for working with functoids within BizTalk maps.</span></span> <span data-ttu-id="a3c3b-116">有关 functoid 的参考信息，请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="a3c3b-116">For reference information about functoids, see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="a3c3b-117">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a3c3b-117">Next steps</span></span> 
  
-   [<span data-ttu-id="a3c3b-118">如何打开 Functoid 工具箱</span><span class="sxs-lookup"><span data-stu-id="a3c3b-118">How to Open the Functoid Toolbox</span></span>](../core/how-to-open-the-functoid-toolbox.md)  
  
-   [<span data-ttu-id="a3c3b-119">如何向映射添加基本 Functoid</span><span class="sxs-lookup"><span data-stu-id="a3c3b-119">How to Add Basic Functoids to a Map</span></span>](../core/how-to-add-basic-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="a3c3b-120">向映射添加高级 Functoid</span><span class="sxs-lookup"><span data-stu-id="a3c3b-120">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)  
  
-   [<span data-ttu-id="a3c3b-121">编辑 Functoid 属性和输入参数</span><span class="sxs-lookup"><span data-stu-id="a3c3b-121">Editing Functoid Properties and Input Parameters</span></span>](../core/editing-functoid-properties-and-input-parameters.md)  
  
-   [<span data-ttu-id="a3c3b-122">如何选择多个 Functoid</span><span class="sxs-lookup"><span data-stu-id="a3c3b-122">How to Select Multiple Functoids</span></span>](../core/how-to-select-multiple-functoids.md)  
  
-   [<span data-ttu-id="a3c3b-123">如何删除 Functoid</span><span class="sxs-lookup"><span data-stu-id="a3c3b-123">How to Delete Functoids</span></span>](../core/how-to-delete-functoids.md)  
  
-   [<span data-ttu-id="a3c3b-124">如何复制、 剪切和粘贴 Functoid</span><span class="sxs-lookup"><span data-stu-id="a3c3b-124">How to Copy, Cut, and Paste a Functoid</span></span>](../core/how-to-copy-cut-and-paste-a-functoid.md)