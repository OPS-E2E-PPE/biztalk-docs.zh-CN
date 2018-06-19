---
title: 节点层次结构级别匹配 |Microsoft 文档
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
ms.openlocfilehash: 0b2d0c363abfefb9e3d0eb8abfb332c59539bb67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264757"
---
# <a name="node-hierarchy-level-matching"></a><span data-ttu-id="7901a-102">节点层次结构级别匹配</span><span class="sxs-lookup"><span data-stu-id="7901a-102">Node-Hierarchy Level Matching</span></span>
<span data-ttu-id="7901a-103">BizTalk 映射程序使您能够配置链接属性可控制编译器如何匹配源和目标架构之间的节点层次结构。</span><span class="sxs-lookup"><span data-stu-id="7901a-103">BizTalk Mapper enables you to configure a link property to control how the compiler matches node hierarchies between the source and destination schemas.</span></span> <span data-ttu-id="7901a-104">在从源架构中的字段创建链接到目标架构中的字段上时，BizTalk 映射程序会自动添加编译器链接。</span><span class="sxs-lookup"><span data-stu-id="7901a-104">When you create a link from a field in the source schema to a field in the destination schema, BizTalk Mapper automatically adds compiler links.</span></span> <span data-ttu-id="7901a-105">这些编译器链接取决于你选择的匹配。</span><span class="sxs-lookup"><span data-stu-id="7901a-105">These compiler links depend on the matching you select.</span></span>  
  
 <span data-ttu-id="7901a-106">当显示的网格页中选择一个链接时，其中一个属性显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口是**目标链接**属性。</span><span class="sxs-lookup"><span data-stu-id="7901a-106">When you select a link in the displayed grid page, one of the properties displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window is the **Target Links** property.</span></span> <span data-ttu-id="7901a-107">您可以为映射中的各个链接选择以下可能的值：</span><span class="sxs-lookup"><span data-stu-id="7901a-107">You can choose among the following possible values for each link in your map:</span></span>  
  
-   <span data-ttu-id="7901a-108">**平展链接。**</span><span class="sxs-lookup"><span data-stu-id="7901a-108">**Flatten links.**</span></span> <span data-ttu-id="7901a-109">使用此值可将所有源层次平展至目标架构节点中的父记录。</span><span class="sxs-lookup"><span data-stu-id="7901a-109">Use this value to flatten all source hierarchies to the parent record in the destination schema node.</span></span>  
  
-   <span data-ttu-id="7901a-110">**匹配链接上而下。**</span><span class="sxs-lookup"><span data-stu-id="7901a-110">**Match links top down.**</span></span> <span data-ttu-id="7901a-111">使用此值可从架构顶部到架构底部匹配节点级别。</span><span class="sxs-lookup"><span data-stu-id="7901a-111">Use this value to match node levels from the top of the schemas to the bottom of the schemas.</span></span>  
  
-   <span data-ttu-id="7901a-112">**匹配链接从下往上。**</span><span class="sxs-lookup"><span data-stu-id="7901a-112">**Match links bottom up.**</span></span> <span data-ttu-id="7901a-113">使用此值可从架构底部到架构顶部匹配节点级别。</span><span class="sxs-lookup"><span data-stu-id="7901a-113">Use this value to match node levels from the bottom of the schemas to the top of the schemas.</span></span>  
  
## <a name="flatten-links"></a><span data-ttu-id="7901a-114">平展链接</span><span class="sxs-lookup"><span data-stu-id="7901a-114">Flatten Links</span></span>  
 <span data-ttu-id="7901a-115">在此模式下，所有源层次都将平展至目标节点中的父记录。</span><span class="sxs-lookup"><span data-stu-id="7901a-115">In this mode, all the source hierarchies are flattened to the parent record of the destination node.</span></span> <span data-ttu-id="7901a-116">在第一种情况下，源架构比目标架构更为复杂。</span><span class="sxs-lookup"><span data-stu-id="7901a-116">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="7901a-117">在第二种情况下，目标架构更为复杂。</span><span class="sxs-lookup"><span data-stu-id="7901a-117">In the second case, the destination schema is more complex.</span></span>  
  
 ![](../core/media/bts-tls-flatten.gif "bts_tls_flatten")  
<span data-ttu-id="7901a-118">平展链接</span><span class="sxs-lookup"><span data-stu-id="7901a-118">Flatten Links</span></span>  
  
 ![](../core/media/bts-tls-flatten-2.gif "bts_tls_flatten_2")  
<span data-ttu-id="7901a-119">平展链接，第二种情况</span><span class="sxs-lookup"><span data-stu-id="7901a-119">Flatten Links, Second Case</span></span>  
  
## <a name="match-links-top-down"></a><span data-ttu-id="7901a-120">匹配链接自上而下</span><span class="sxs-lookup"><span data-stu-id="7901a-120">Match Links Top-Down</span></span>  
 <span data-ttu-id="7901a-121">此模式将从上到下对级别进行匹配。</span><span class="sxs-lookup"><span data-stu-id="7901a-121">This mode matches level to level from the top down.</span></span> <span data-ttu-id="7901a-122">在第一种情况下，源架构比目标架构更为复杂。</span><span class="sxs-lookup"><span data-stu-id="7901a-122">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="7901a-123">在第二种情况下，目标架构更为复杂。</span><span class="sxs-lookup"><span data-stu-id="7901a-123">In the second case, the destination schema is more complex.</span></span>  
  
 ![](../core/media/bts-tls-topdown.gif "bts_tls_topdown")  
<span data-ttu-id="7901a-124">自上而下匹配</span><span class="sxs-lookup"><span data-stu-id="7901a-124">Top-Down Matching</span></span>  
  
 ![](../core/media/bts-tls-topdown-2.gif "bts_tls_topdown_2")  
<span data-ttu-id="7901a-125">自上而下匹配，第二个用例</span><span class="sxs-lookup"><span data-stu-id="7901a-125">Top-Down Matching, Second Case</span></span>  
  
## <a name="match-links-bottom-up"></a><span data-ttu-id="7901a-126">匹配链接自下而上</span><span class="sxs-lookup"><span data-stu-id="7901a-126">Match Links Bottom-Up</span></span>  
 <span data-ttu-id="7901a-127">此模式匹配从下至上级别到另一个级别。</span><span class="sxs-lookup"><span data-stu-id="7901a-127">This mode matches level to level from the bottom up.</span></span> <span data-ttu-id="7901a-128">在第一种情况下，源架构比目标架构更为复杂。</span><span class="sxs-lookup"><span data-stu-id="7901a-128">In the first case, the source schema is more complex than the destination schema.</span></span> <span data-ttu-id="7901a-129">在第二种情况下，目标架构更为复杂。</span><span class="sxs-lookup"><span data-stu-id="7901a-129">In the second case, the destination schema is more complex.</span></span>  
  
 ![](../core/media/bts-tls-bottomup.gif "bts_tls_bottomup")  
<span data-ttu-id="7901a-130">自下而上匹配</span><span class="sxs-lookup"><span data-stu-id="7901a-130">Bottom-Up Matching</span></span>  
  
 ![](../core/media/bts-tls-bottomup-2.gif "bts_tls_bottomup_2")  
<span data-ttu-id="7901a-131">自下而上匹配，第二个用例</span><span class="sxs-lookup"><span data-stu-id="7901a-131">Bottom-Up Matching, Second Case</span></span>  
  
## <a name="how-biztalk-mapper-processes-link-types"></a><span data-ttu-id="7901a-132">BizTalk 映射程序如何处理链接类型</span><span class="sxs-lookup"><span data-stu-id="7901a-132">How BizTalk Mapper Processes Link Types</span></span>  
 <span data-ttu-id="7901a-133">因为你可以设置**目标链接**到不同的值不同的链接的属性，BizTalk 映射程序需要一种方式，若要解决的不同设置，在它们可能发生冲突。</span><span class="sxs-lookup"><span data-stu-id="7901a-133">Because you can set the **Target Links** property to different values for different links, BizTalk Mapper needs a way to resolve the different settings when they may conflict.</span></span>  
  
 <span data-ttu-id="7901a-134">例如，如果从链接的使用 flatten 编译器指令、 自上而下的编译器指令和自下而上的编译器指令**字段**节点**字段**中目标架构，并将这些节点节点共享同一个父**记录**节点，BizTalk 映射程序忽略冲突的自顶向下和自下而上的编译器指令，并将所有的链接，就像它们被设置为平展编译器指令。</span><span class="sxs-lookup"><span data-stu-id="7901a-134">For example, if you use a flatten compiler directive, a top-down compiler directive, and a bottom-up compiler directive for links from **Field** nodes to **Field** nodes in the destination schema, and these nodes share the same parent **Record** node, BizTalk Mapper ignores the conflicting top-down and bottom-up compiler directives and treats all the links as if they were set to the flatten compiler directive.</span></span>  
  
 <span data-ttu-id="7901a-135">下表显示如何 BizTalk 映射程序处理指向**字段**中相同的节点**记录**目标架构中的节点上的设置基于**目标链接**在同一个链接的属性**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="7901a-135">The following table shows how BizTalk Mapper treats links to **Field** nodes in the same **Record** node in the destination schema, based on the settings for the **Target Links** property for the links within the same **Record** node.</span></span>  
  
|<span data-ttu-id="7901a-136">平展</span><span class="sxs-lookup"><span data-stu-id="7901a-136">Flatten</span></span>|<span data-ttu-id="7901a-137">自上而下</span><span class="sxs-lookup"><span data-stu-id="7901a-137">Top-down</span></span>|<span data-ttu-id="7901a-138">自下而上</span><span class="sxs-lookup"><span data-stu-id="7901a-138">Bottom-up</span></span>|<span data-ttu-id="7901a-139">结果</span><span class="sxs-lookup"><span data-stu-id="7901a-139">Result</span></span>|  
|-------------|---------------|----------------|------------|  
|<span data-ttu-id="7901a-140">0 或更多</span><span class="sxs-lookup"><span data-stu-id="7901a-140">0 or more</span></span>|<span data-ttu-id="7901a-141">1 或更多</span><span class="sxs-lookup"><span data-stu-id="7901a-141">1 or more</span></span>|<span data-ttu-id="7901a-142">1 或更多</span><span class="sxs-lookup"><span data-stu-id="7901a-142">1 or more</span></span>|<span data-ttu-id="7901a-143">BizTalk 映射程序将所有的链接，就像它们被设置为平展编译器指令。</span><span class="sxs-lookup"><span data-stu-id="7901a-143">BizTalk Mapper treats all the links as if they were set to the flatten compiler directive.</span></span>|  
|<span data-ttu-id="7901a-144">1 或更多</span><span class="sxs-lookup"><span data-stu-id="7901a-144">1 or more</span></span>|<span data-ttu-id="7901a-145">1 或更多</span><span class="sxs-lookup"><span data-stu-id="7901a-145">1 or more</span></span>|<span data-ttu-id="7901a-146">0</span><span class="sxs-lookup"><span data-stu-id="7901a-146">0</span></span>|<span data-ttu-id="7901a-147">BizTalk 映射程序将所有的链接，就像它们被设置为自上而下的编译器指令。</span><span class="sxs-lookup"><span data-stu-id="7901a-147">BizTalk Mapper treats all the links as if they were set to the top-down compiler directive.</span></span>|  
|<span data-ttu-id="7901a-148">1 或更多</span><span class="sxs-lookup"><span data-stu-id="7901a-148">1 or more</span></span>|<span data-ttu-id="7901a-149">0</span><span class="sxs-lookup"><span data-stu-id="7901a-149">0</span></span>|<span data-ttu-id="7901a-150">1 或更多</span><span class="sxs-lookup"><span data-stu-id="7901a-150">1 or more</span></span>|<span data-ttu-id="7901a-151">BizTalk 映射程序将所有的链接，就像它们被设置为自下而上的编译器指令。</span><span class="sxs-lookup"><span data-stu-id="7901a-151">BizTalk Mapper treats all the links as if they were set to the bottom-up compiler directive.</span></span>|  
  
 <span data-ttu-id="7901a-152">自顶向下和自下而上的编译器指令将优先于 flatten 编译器指令，但相互抵消两者都存在。</span><span class="sxs-lookup"><span data-stu-id="7901a-152">The top-down and bottom-up compiler directives take precedence over the flatten compiler directive, but cancel each other out when both are present.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7901a-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7901a-153">See Also</span></span>  
 <span data-ttu-id="7901a-154">[大容量复制 Functoid](../core/mass-copy-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="7901a-154">[Mass Copy Functoid](../core/mass-copy-functoid.md) </span></span>  
 <span data-ttu-id="7901a-155">[如何将源链接编译器值设置](../core/how-to-set-the-source-links-compiler-value.md) </span><span class="sxs-lookup"><span data-stu-id="7901a-155">[How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md) </span></span>  
 [<span data-ttu-id="7901a-156">编译地图</span><span class="sxs-lookup"><span data-stu-id="7901a-156">Compiling Maps</span></span>](../core/compiling-maps.md)