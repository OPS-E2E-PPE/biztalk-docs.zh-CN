---
title: 如何优化的链接显示 |Microsoft 文档
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
ms.openlocfilehash: 689ab4c67bfe8cabc8109c373e899d391fdd56a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254381"
---
# <a name="how-to-optimize-the-display-of-links"></a><span data-ttu-id="1d51f-102">如何优化链接的显示</span><span class="sxs-lookup"><span data-stu-id="1d51f-102">How to Optimize the Display of Links</span></span>
<span data-ttu-id="1d51f-103">如果架构够大，您的映射可能包括源和目标架构之间的大量链接。</span><span class="sxs-lookup"><span data-stu-id="1d51f-103">When the schemas are big, your maps might include a large number of links between the source and the destination schemas.</span></span> <span data-ttu-id="1d51f-104">由于映射表面有许多链接，可能很难跟踪您要处理的项目或连接。</span><span class="sxs-lookup"><span data-stu-id="1d51f-104">With many links across the map surface, you may find it difficult to track a link or an object you need to work on.</span></span> <span data-ttu-id="1d51f-105">此外，跟踪源架构、链接、functoid 和目标架构之间的端对端关系可能也很困难。</span><span class="sxs-lookup"><span data-stu-id="1d51f-105">Also, it can be difficult for you to track an end-to-end relationship between a source schema, the links, the functoids, and the destination schema.</span></span> <span data-ttu-id="1d51f-106">在 BizTalk 映射器中，您可以更好地管理复杂的大型架构，并可以优化显示映射中的链接。</span><span class="sxs-lookup"><span data-stu-id="1d51f-106">In the BizTalk Mapper, you can better manage complex and large schemas, and bring out an optimized display of links in the map.</span></span> <span data-ttu-id="1d51f-107">本主题提供关于如何查看链接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1d51f-107">This topic provides details about how to view links.</span></span>  
  
 <span data-ttu-id="1d51f-108">您可以分类各链接，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1d51f-108">You can categorize the links as follows:</span></span>  
  
-   <span data-ttu-id="1d51f-109">部分位于作用域</span><span class="sxs-lookup"><span data-stu-id="1d51f-109">Partially in scope</span></span>  
  
-   <span data-ttu-id="1d51f-110">完全在作用域内</span><span class="sxs-lookup"><span data-stu-id="1d51f-110">Completely in scope</span></span>  
  
-   <span data-ttu-id="1d51f-111">完全位于作用域外</span><span class="sxs-lookup"><span data-stu-id="1d51f-111">Completely out of scope</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1d51f-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="1d51f-112">Prerequisites</span></span>  
 <span data-ttu-id="1d51f-113">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="1d51f-113">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="to-view-the-links-partially-in-scope"></a><span data-ttu-id="1d51f-114">查看部分位于作用域的链接</span><span class="sxs-lookup"><span data-stu-id="1d51f-114">To view the links partially in scope</span></span>  
 <span data-ttu-id="1d51f-115">在网格图面上至少可以看见一个末端的链接称为“部分位于作用域”。</span><span class="sxs-lookup"><span data-stu-id="1d51f-115">Links that have at least one end visible on the grid surface are called “partially in scope.”</span></span>  
  
 <span data-ttu-id="1d51f-116">下图显示了一个“部分位作用域”的链接。</span><span class="sxs-lookup"><span data-stu-id="1d51f-116">The figure below shows a link that is “partially in scope.”</span></span> <span data-ttu-id="1d51f-117">这些链接在网格图面上显示为虚线。</span><span class="sxs-lookup"><span data-stu-id="1d51f-117">These links are shown as dashed lines on the grid page.</span></span>  
  
 <span data-ttu-id="1d51f-118">单击在网格图面上部分可见的链接，网格页会自动上移/下移以在当前视图中显示端对端关系。</span><span class="sxs-lookup"><span data-stu-id="1d51f-118">Click the link that is partially visible on the grid surface, and the grid page automatically moves up/down to bring the relationship into the current view.</span></span>  
  
 <span data-ttu-id="1d51f-119">![作用域中的部分的映射器链接](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")</span><span class="sxs-lookup"><span data-stu-id="1d51f-119">![Mapper links partially in scope](../core/media/mapper-partiallyinscope.gif "Mapper_PartiallyInScope")</span></span>  
  
## <a name="to-view-the-links-completely-in-scope"></a><span data-ttu-id="1d51f-120">查看完全位于作用域的链接</span><span class="sxs-lookup"><span data-stu-id="1d51f-120">To view the links completely in scope</span></span>  
 <span data-ttu-id="1d51f-121">可以在网格图面上看到两个末端（节点对节点、节点对 functoid、functoid 对 functoid 或 functoid 对节点）的链接称为“完全位于作用域”。</span><span class="sxs-lookup"><span data-stu-id="1d51f-121">A link that has both ends (node to node, node to functoid, functoid-to-functoid, or functoid to node) visible on the grid surface is called “completely in scope.”</span></span>  
  
 <span data-ttu-id="1d51f-122">下图显示 DataCollection1 和 ST01 之间完全位于作用域的链接。</span><span class="sxs-lookup"><span data-stu-id="1d51f-122">The figure below shows a link between “DataCollection1” and “ST01” that is completely in scope.</span></span>  
  
 <span data-ttu-id="1d51f-123">单击该链接，会选中从源节点到目标节点的关系。</span><span class="sxs-lookup"><span data-stu-id="1d51f-123">Click the link, and the relationship from source node to target node is selected.</span></span>  
  
 <span data-ttu-id="1d51f-124">![完全作用域中的映射器链接](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")</span><span class="sxs-lookup"><span data-stu-id="1d51f-124">![Mapper links completely in scope](../core/media/mapper-completelyinscope.gif "Mapper_CompletelyInScope")</span></span>  
  
## <a name="to-view-the-links-completely-out-of-scope"></a><span data-ttu-id="1d51f-125">查看完全位于作用域外的链接</span><span class="sxs-lookup"><span data-stu-id="1d51f-125">To view the links completely out of scope</span></span>  
 <span data-ttu-id="1d51f-126">在当前映射视图中看不到任何终结点的链接称为“完全位于作用域外”。</span><span class="sxs-lookup"><span data-stu-id="1d51f-126">A link that has neither of its end points visible in the current map view is called “completely out of scope.”</span></span>  
  
 <span data-ttu-id="1d51f-127">下图显示了完全位于作用域外的链接。</span><span class="sxs-lookup"><span data-stu-id="1d51f-127">The figure below shows a link that is completely out of scope.</span></span>  
  
 <span data-ttu-id="1d51f-128">如果你不想要显示这些链接在地图上的图面 （因为所有链接都可见），你可以选择通过单击关闭它们![显示所有链接](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks")上映射器实用程序功能区。</span><span class="sxs-lookup"><span data-stu-id="1d51f-128">If you do not want to display these links on the map surface (because none of the links are visible), you may choose to turn them off by clicking ![Show all links](../core/media/mapper-showhideoutscopelinks.gif "Mapper_ShowHideOutScopeLinks") on the Mapper utility ribbon.</span></span> <span data-ttu-id="1d51f-129">这样，就减少了网格视图上可见链接的数量。</span><span class="sxs-lookup"><span data-stu-id="1d51f-129">This reduces the amount of links that are visible on the grid view.</span></span>  
  
 <span data-ttu-id="1d51f-130">![完全超出范围的映射器链接](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")</span><span class="sxs-lookup"><span data-stu-id="1d51f-130">![Mapper links completely out of scope](../core/media/mapper-completelyoutscope.gif "Mapper_CompletelyOutScope")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d51f-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d51f-131">See Also</span></span>  
 [<span data-ttu-id="1d51f-132">在 BizTalk 映射程序中使用增强的功能</span><span class="sxs-lookup"><span data-stu-id="1d51f-132">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)