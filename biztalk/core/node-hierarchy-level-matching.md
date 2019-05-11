---
title: 节点层次级别匹配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Field nodes
- BizTalk Mapper, processing
- Record node
- BizTalk Mapper, compiler directives
- destination schemas, matching nodes
- source schemas, matching nodes
- maps, links
- Target Links property
- BizTalk Mapper, links
- compiler directives, matching schema nodes
- compiler directives, flattening source hierarchies
- maps, processing
ms.assetid: 5ba1ac77-0e70-4c58-9b8c-1b379dbbb3bd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 016a02be9634c86c03ac0a5532caf49a59a26c7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323562"
---
# <a name="node-hierarchy-level-matching"></a><span data-ttu-id="d1827-102">节点层次级别匹配</span><span class="sxs-lookup"><span data-stu-id="d1827-102">Node-Hierarchy Level Matching</span></span>
<span data-ttu-id="d1827-103">BizTalk 映射器，您可以配置要控制编译器如何匹配节点层次结构的源和目标架构之间的链接属性。</span><span class="sxs-lookup"><span data-stu-id="d1827-103">BizTalk Mapper enables you to configure a link property to control how the compiler matches node hierarchies between the source and destination schemas.</span></span> <span data-ttu-id="d1827-104">从源架构中的字段创建链接到目标架构中的字段上时，BizTalk 映射器会自动添加编译器链接。</span><span class="sxs-lookup"><span data-stu-id="d1827-104">When you create a link from a field in the source schema to a field in the destination schema, BizTalk Mapper automatically adds compiler links.</span></span> <span data-ttu-id="d1827-105">这些编译器链接取决于您选择的匹配。</span><span class="sxs-lookup"><span data-stu-id="d1827-105">These compiler links depend on the matching you select.</span></span>  
  
 <span data-ttu-id="d1827-106">当在显示的网格页中选择一个链接时，其中一个属性显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口是**目标链接**属性。</span><span class="sxs-lookup"><span data-stu-id="d1827-106">When you select a link in the displayed grid page, one of the properties displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window is the **Target Links** property.</span></span> <span data-ttu-id="d1827-107">您可以在地图中选择以下可能值为每个链接：</span><span class="sxs-lookup"><span data-stu-id="d1827-107">You can choose among the following possible values for each link in your map:</span></span>  
  
-   <span data-ttu-id="d1827-108">**平展链接。**</span><span class="sxs-lookup"><span data-stu-id="d1827-108">**Flatten links.**</span></span> <span data-ttu-id="d1827-109">此值用于平展至目标架构节点中的父记录的所有源层次结构。</span><span class="sxs-lookup"><span data-stu-id="d1827-109">Use this value to flatten all source hierarchies to the parent record in the destination schema node.</span></span>  
  
-   <span data-ttu-id="d1827-110">**匹配项的链接上而下。**</span><span class="sxs-lookup"><span data-stu-id="d1827-110">**Match links top down.**</span></span> <span data-ttu-id="d1827-111">使用此值可匹配节点级别从架构顶部到架构底部。</span><span class="sxs-lookup"><span data-stu-id="d1827-111">Use this value to match node levels from the top of the schemas to the bottom of the schemas.</span></span>  
  
-   <span data-ttu-id="d1827-112">**下到上匹配链接。**</span><span class="sxs-lookup"><span data-stu-id="d1827-112">**Match links bottom up.**</span></span> <span data-ttu-id="d1827-113">使用此值可匹配节点级别从架构底部到架构顶部。</span><span class="sxs-lookup"><span data-stu-id="d1827-113">Use this value to match node levels from the bottom of the schemas to the top of the schemas.</span></span>  
  
## <a name="flatten-links"></a><span data-ttu-id="d1827-114">平展链接</span><span class="sxs-lookup"><span data-stu-id="d1827-114">Flatten Links</span></span>  
 <span data-ttu-id="d1827-115">在此模式下，所有源层次都将都平展至目标节点的父记录。</span><span class="sxs-lookup"><span data-stu-id="d1827-115">In this mode, all the source hierarchies are flattened to the parent record of the destination node.</span></span> <span data-ttu-id="d1827-116">在第一种情况下，源架构是比目标架构更为复杂。</span><span class="sxs-lookup"><span data-stu-id="d1827-116">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="d1827-117">在第二种情况下，目标架构是更复杂。</span><span class="sxs-lookup"><span data-stu-id="d1827-117">In the second case, the destination schema is more complex.</span></span>  
  
 <span data-ttu-id="d1827-118">![](../core/media/bts-tls-flatten.gif "bts_tls_flatten")</span><span class="sxs-lookup"><span data-stu-id="d1827-118">![](../core/media/bts-tls-flatten.gif "bts_tls_flatten")</span></span>  
<span data-ttu-id="d1827-119">平展链接</span><span class="sxs-lookup"><span data-stu-id="d1827-119">Flatten Links</span></span>  
  
 <span data-ttu-id="d1827-120">![](../core/media/bts-tls-flatten-2.gif "bts_tls_flatten_2")</span><span class="sxs-lookup"><span data-stu-id="d1827-120">![](../core/media/bts-tls-flatten-2.gif "bts_tls_flatten_2")</span></span>  
<span data-ttu-id="d1827-121">平展链接，第二种情况</span><span class="sxs-lookup"><span data-stu-id="d1827-121">Flatten Links, Second Case</span></span>  
  
## <a name="match-links-top-down"></a><span data-ttu-id="d1827-122">匹配项的链接上而下</span><span class="sxs-lookup"><span data-stu-id="d1827-122">Match Links Top-Down</span></span>  
 <span data-ttu-id="d1827-123">此模式下从上到下匹配级别的。</span><span class="sxs-lookup"><span data-stu-id="d1827-123">This mode matches level to level from the top down.</span></span> <span data-ttu-id="d1827-124">在第一种情况下，源架构是比目标架构更为复杂。</span><span class="sxs-lookup"><span data-stu-id="d1827-124">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="d1827-125">在第二种情况下，目标架构是更复杂。</span><span class="sxs-lookup"><span data-stu-id="d1827-125">In the second case, the destination schema is more complex.</span></span>  
  
 <span data-ttu-id="d1827-126">![](../core/media/bts-tls-topdown.gif "bts_tls_topdown")</span><span class="sxs-lookup"><span data-stu-id="d1827-126">![](../core/media/bts-tls-topdown.gif "bts_tls_topdown")</span></span>  
<span data-ttu-id="d1827-127">自上而下的匹配</span><span class="sxs-lookup"><span data-stu-id="d1827-127">Top-Down Matching</span></span>  
  
 <span data-ttu-id="d1827-128">![](../core/media/bts-tls-topdown-2.gif "bts_tls_topdown_2")</span><span class="sxs-lookup"><span data-stu-id="d1827-128">![](../core/media/bts-tls-topdown-2.gif "bts_tls_topdown_2")</span></span>  
<span data-ttu-id="d1827-129">自上而下的匹配，第二个用例</span><span class="sxs-lookup"><span data-stu-id="d1827-129">Top-Down Matching, Second Case</span></span>  
  
## <a name="match-links-bottom-up"></a><span data-ttu-id="d1827-130">匹配项的链接下到上</span><span class="sxs-lookup"><span data-stu-id="d1827-130">Match Links Bottom-Up</span></span>  
 <span data-ttu-id="d1827-131">此模式下从下到上匹配级别的。</span><span class="sxs-lookup"><span data-stu-id="d1827-131">This mode matches level to level from the bottom up.</span></span> <span data-ttu-id="d1827-132">在第一种情况下，源架构是比目标架构更为复杂。</span><span class="sxs-lookup"><span data-stu-id="d1827-132">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="d1827-133">在第二种情况下，目标架构是更复杂。</span><span class="sxs-lookup"><span data-stu-id="d1827-133">In the second case, the destination schema is more complex.</span></span>  
  
 <span data-ttu-id="d1827-134">![](../core/media/bts-tls-bottomup.gif "bts_tls_bottomup")</span><span class="sxs-lookup"><span data-stu-id="d1827-134">![](../core/media/bts-tls-bottomup.gif "bts_tls_bottomup")</span></span>  
<span data-ttu-id="d1827-135">自下而上的匹配</span><span class="sxs-lookup"><span data-stu-id="d1827-135">Bottom-Up Matching</span></span>  
  
 <span data-ttu-id="d1827-136">![](../core/media/bts-tls-bottomup-2.gif "bts_tls_bottomup_2")</span><span class="sxs-lookup"><span data-stu-id="d1827-136">![](../core/media/bts-tls-bottomup-2.gif "bts_tls_bottomup_2")</span></span>  
<span data-ttu-id="d1827-137">自下而上的匹配，第二个用例</span><span class="sxs-lookup"><span data-stu-id="d1827-137">Bottom-Up Matching, Second Case</span></span>  
  
## <a name="how-biztalk-mapper-processes-link-types"></a><span data-ttu-id="d1827-138">BizTalk 映射器如何处理链接类型</span><span class="sxs-lookup"><span data-stu-id="d1827-138">How BizTalk Mapper Processes Link Types</span></span>  
 <span data-ttu-id="d1827-139">因为可以设置**目标链接**属性设置为不同的值不同的链接，BizTalk 映射器需要一种方法时可能发生的冲突解决不同的设置。</span><span class="sxs-lookup"><span data-stu-id="d1827-139">Because you can set the **Target Links** property to different values for different links, BizTalk Mapper needs a way to resolve the different settings when they may conflict.</span></span>  
  
 <span data-ttu-id="d1827-140">例如，如果从链接使用平展编译器指令、 自上而下的编译器指令和下到上编译器指令**字段**到节点**字段**中目标架构中，并将这些节点节点共享同一个父**记录**节点，BizTalk 映射器将忽略自上而下和自下而上的编译器指令冲突并将所有链接视为它们设置为平展编译器指令。</span><span class="sxs-lookup"><span data-stu-id="d1827-140">For example, if you use a flatten compiler directive, a top-down compiler directive, and a bottom-up compiler directive for links from **Field** nodes to **Field** nodes in the destination schema, and these nodes share the same parent **Record** node, BizTalk Mapper ignores the conflicting top-down and bottom-up compiler directives and treats all the links as if they were set to the flatten compiler directive.</span></span>  
  
 <span data-ttu-id="d1827-141">下表显示了 BizTalk 映射器如何处理指向**字段**中相同的节点**记录**上的设置基于目标架构中的节点**目标链接**在同一链接的属性**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="d1827-141">The following table shows how BizTalk Mapper treats links to **Field** nodes in the same **Record** node in the destination schema, based on the settings for the **Target Links** property for the links within the same **Record** node.</span></span>  
  
|<span data-ttu-id="d1827-142">平展</span><span class="sxs-lookup"><span data-stu-id="d1827-142">Flatten</span></span>|<span data-ttu-id="d1827-143">自上而下的</span><span class="sxs-lookup"><span data-stu-id="d1827-143">Top-down</span></span>|<span data-ttu-id="d1827-144">自下而上的</span><span class="sxs-lookup"><span data-stu-id="d1827-144">Bottom-up</span></span>|<span data-ttu-id="d1827-145">结果</span><span class="sxs-lookup"><span data-stu-id="d1827-145">Result</span></span>|  
|-------------|---------------|----------------|------------|  
|<span data-ttu-id="d1827-146">0 或更多</span><span class="sxs-lookup"><span data-stu-id="d1827-146">0 or more</span></span>|<span data-ttu-id="d1827-147">一个或多个</span><span class="sxs-lookup"><span data-stu-id="d1827-147">1 or more</span></span>|<span data-ttu-id="d1827-148">一个或多个</span><span class="sxs-lookup"><span data-stu-id="d1827-148">1 or more</span></span>|<span data-ttu-id="d1827-149">BizTalk 映射器将所有链接视为它们设置为平展编译器指令。</span><span class="sxs-lookup"><span data-stu-id="d1827-149">BizTalk Mapper treats all the links as if they were set to the flatten compiler directive.</span></span>|  
|<span data-ttu-id="d1827-150">一个或多个</span><span class="sxs-lookup"><span data-stu-id="d1827-150">1 or more</span></span>|<span data-ttu-id="d1827-151">一个或多个</span><span class="sxs-lookup"><span data-stu-id="d1827-151">1 or more</span></span>|<span data-ttu-id="d1827-152">0</span><span class="sxs-lookup"><span data-stu-id="d1827-152">0</span></span>|<span data-ttu-id="d1827-153">BizTalk 映射器将所有链接视为它们设置为上到下编译器指令。</span><span class="sxs-lookup"><span data-stu-id="d1827-153">BizTalk Mapper treats all the links as if they were set to the top-down compiler directive.</span></span>|  
|<span data-ttu-id="d1827-154">一个或多个</span><span class="sxs-lookup"><span data-stu-id="d1827-154">1 or more</span></span>|<span data-ttu-id="d1827-155">0</span><span class="sxs-lookup"><span data-stu-id="d1827-155">0</span></span>|<span data-ttu-id="d1827-156">一个或多个</span><span class="sxs-lookup"><span data-stu-id="d1827-156">1 or more</span></span>|<span data-ttu-id="d1827-157">BizTalk 映射器将所有链接视为它们设置为下到上编译器指令。</span><span class="sxs-lookup"><span data-stu-id="d1827-157">BizTalk Mapper treats all the links as if they were set to the bottom-up compiler directive.</span></span>|  
  
 <span data-ttu-id="d1827-158">自上而下和自下而上的编译器指令优先于平展编译器指令，但相互抵消两者都存在。</span><span class="sxs-lookup"><span data-stu-id="d1827-158">The top-down and bottom-up compiler directives take precedence over the flatten compiler directive, but cancel each other out when both are present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1827-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1827-159">See Also</span></span>  
 <span data-ttu-id="d1827-160">[批量复制 Functoid](../core/mass-copy-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="d1827-160">[Mass Copy Functoid](../core/mass-copy-functoid.md) </span></span>  
 <span data-ttu-id="d1827-161">[如何设置源链接编译器值](../core/how-to-set-the-source-links-compiler-value.md) </span><span class="sxs-lookup"><span data-stu-id="d1827-161">[How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md) </span></span>  
 [<span data-ttu-id="d1827-162">编译映射</span><span class="sxs-lookup"><span data-stu-id="d1827-162">Compiling Maps</span></span>](../core/compiling-maps.md)