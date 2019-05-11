---
title: 如何优化链接的显示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a9e16ff-01d3-4b7d-91c4-59d17266ee6d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da7eec1cb22dfea1522b94d1bbb948a627ed4ffa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335828"
---
# <a name="how-to-optimize-the-display-of-links"></a><span data-ttu-id="34ed2-102">如何优化链接的显示</span><span class="sxs-lookup"><span data-stu-id="34ed2-102">How to Optimize the Display of Links</span></span>
<span data-ttu-id="34ed2-103">如果架构够大，您的映射可能包括大量的源和目标架构之间的链接。</span><span class="sxs-lookup"><span data-stu-id="34ed2-103">When the schemas are big, your maps might include a large number of links between the source and the destination schemas.</span></span> <span data-ttu-id="34ed2-104">由于映射表面的许多链接，您可能会发现难以跟踪的链接或需要处理的对象。</span><span class="sxs-lookup"><span data-stu-id="34ed2-104">With many links across the map surface, you may find it difficult to track a link or an object you need to work on.</span></span> <span data-ttu-id="34ed2-105">而且，它会非常困难，以便跟踪源架构、 链接、 functoid 和目标架构之间的端到端关系。</span><span class="sxs-lookup"><span data-stu-id="34ed2-105">Also, it can be difficult for you to track an end-to-end relationship between a source schema, the links, the functoids, and the destination schema.</span></span> <span data-ttu-id="34ed2-106">在 BizTalk 映射器中，可以更好地管理复杂的大型架构，并使优化显示映射中链接。</span><span class="sxs-lookup"><span data-stu-id="34ed2-106">In the BizTalk Mapper, you can better manage complex and large schemas, and bring out an optimized display of links in the map.</span></span> <span data-ttu-id="34ed2-107">本主题提供有关如何查看链接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="34ed2-107">This topic provides details about how to view links.</span></span>  
  
 <span data-ttu-id="34ed2-108">您可以分类各链接，请按如下所示：</span><span class="sxs-lookup"><span data-stu-id="34ed2-108">You can categorize the links as follows:</span></span>  
  
-   <span data-ttu-id="34ed2-109">部分位于作用域</span><span class="sxs-lookup"><span data-stu-id="34ed2-109">Partially in scope</span></span>  
  
-   <span data-ttu-id="34ed2-110">完全在作用域</span><span class="sxs-lookup"><span data-stu-id="34ed2-110">Completely in scope</span></span>  
  
-   <span data-ttu-id="34ed2-111">完全位于作用域外</span><span class="sxs-lookup"><span data-stu-id="34ed2-111">Completely out of scope</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="34ed2-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="34ed2-112">Prerequisites</span></span>  
 <span data-ttu-id="34ed2-113">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="34ed2-113">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="to-view-the-links-partially-in-scope"></a><span data-ttu-id="34ed2-114">若要查看部分位于作用域的链接</span><span class="sxs-lookup"><span data-stu-id="34ed2-114">To view the links partially in scope</span></span>  
 <span data-ttu-id="34ed2-115">在网格图面上可见的至少一个最终的链接称为"部分位于作用域。</span><span class="sxs-lookup"><span data-stu-id="34ed2-115">Links that have at least one end visible on the grid surface are called “partially in scope.”</span></span>  
  
 <span data-ttu-id="34ed2-116">下图显示了一个链接，"部分在作用域。</span><span class="sxs-lookup"><span data-stu-id="34ed2-116">The figure below shows a link that is “partially in scope.”</span></span> <span data-ttu-id="34ed2-117">下面的链接显示为虚线网格页上。</span><span class="sxs-lookup"><span data-stu-id="34ed2-117">These links are shown as dashed lines on the grid page.</span></span>  
  
 <span data-ttu-id="34ed2-118">单击网格图面上, 部分可见的链接，网格页自动上移/下移以使在当前的视图的关系。</span><span class="sxs-lookup"><span data-stu-id="34ed2-118">Click the link that is partially visible on the grid surface, and the grid page automatically moves up/down to bring the relationship into the current view.</span></span>  
  
 <span data-ttu-id="34ed2-119">![映射器链接部分在作用域](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")</span><span class="sxs-lookup"><span data-stu-id="34ed2-119">![Mapper links partially in scope](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")</span></span>  
  
## <a name="to-view-the-links-completely-in-scope"></a><span data-ttu-id="34ed2-120">若要查看完全位于作用域的链接</span><span class="sxs-lookup"><span data-stu-id="34ed2-120">To view the links completely in scope</span></span>  
 <span data-ttu-id="34ed2-121">两个末端 （节点到节点，节点到 functoid、 functoid 对 functoid 或 functoid 对节点） 显示在网格图面的链接称为"完全位于作用域。</span><span class="sxs-lookup"><span data-stu-id="34ed2-121">A link that has both ends (node to node, node to functoid, functoid-to-functoid, or functoid to node) visible on the grid surface is called “completely in scope.”</span></span>  
  
 <span data-ttu-id="34ed2-122">下图显示 DataCollection1 和 ST01 之间链接的是完全在作用域中。</span><span class="sxs-lookup"><span data-stu-id="34ed2-122">The figure below shows a link between “DataCollection1” and “ST01” that is completely in scope.</span></span>  
  
 <span data-ttu-id="34ed2-123">单击该链接，并选择从源节点到目标节点的关系。</span><span class="sxs-lookup"><span data-stu-id="34ed2-123">Click the link, and the relationship from source node to target node is selected.</span></span>  
  
 <span data-ttu-id="34ed2-124">![映射器链接完全在作用域](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")</span><span class="sxs-lookup"><span data-stu-id="34ed2-124">![Mapper links completely in scope](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")</span></span>  
  
## <a name="to-view-the-links-completely-out-of-scope"></a><span data-ttu-id="34ed2-125">若要查看链接完全超出范围</span><span class="sxs-lookup"><span data-stu-id="34ed2-125">To view the links completely out of scope</span></span>  
 <span data-ttu-id="34ed2-126">既没有当前映射视图中显示其终结点的链接称为"完全超出范围。"</span><span class="sxs-lookup"><span data-stu-id="34ed2-126">A link that has neither of its end points visible in the current map view is called “completely out of scope.”</span></span>  
  
 <span data-ttu-id="34ed2-127">下图显示了完全位于作用域之外的链接。</span><span class="sxs-lookup"><span data-stu-id="34ed2-127">The figure below shows a link that is completely out of scope.</span></span>  
  
 <span data-ttu-id="34ed2-128">如果不想要显示这些链接在地图上图面上，这是 （因为不到任何链接是可见的），您也可通过单击关闭它们![显示所有链接](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks")映射器上实用工具功能区。</span><span class="sxs-lookup"><span data-stu-id="34ed2-128">If you do not want to display these links on the map surface (because none of the links are visible), you may choose to turn them off by clicking ![Show all links](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks") on the Mapper utility ribbon.</span></span> <span data-ttu-id="34ed2-129">这将减少在网格视图可见的链接的数量。</span><span class="sxs-lookup"><span data-stu-id="34ed2-129">This reduces the amount of links that are visible on the grid view.</span></span>  
  
 <span data-ttu-id="34ed2-130">![映射器链接完全超出范围](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")</span><span class="sxs-lookup"><span data-stu-id="34ed2-130">![Mapper links completely out of scope](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34ed2-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="34ed2-131">See Also</span></span>  
 [<span data-ttu-id="34ed2-132">使用 BizTalk 映射器中的增强功能</span><span class="sxs-lookup"><span data-stu-id="34ed2-132">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)