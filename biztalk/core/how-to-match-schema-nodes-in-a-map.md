---
title: "如何匹配映射中的架构节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 584f85d2-6198-4ef3-90d9-a322f1457d9a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1e2ce880489ca49b0b55d2e6f45b9e887d719a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-match-schema-nodes-in-a-map"></a><span data-ttu-id="a04d4-102">如何在映射中匹配架构节点</span><span class="sxs-lookup"><span data-stu-id="a04d4-102">How to Match Schema Nodes in a Map</span></span>
<span data-ttu-id="a04d4-103">如果源或目标架构很复杂，映射元素将非常困难。</span><span class="sxs-lookup"><span data-stu-id="a04d4-103">When the source or destination schemas are complex, it can be difficult to map the elements.</span></span> <span data-ttu-id="a04d4-104">BizTalk 映射程序引入了**指示匹配**功能，使得您可以将复杂架构元素映射的建议最可能的匹配。</span><span class="sxs-lookup"><span data-stu-id="a04d4-104">The BizTalk Mapper introduces the **Indicative Match** feature, which enables you to map complex schema elements by suggesting the best possible matches.</span></span> <span data-ttu-id="a04d4-105">本主题提供有关如何执行此操作的信息。</span><span class="sxs-lookup"><span data-stu-id="a04d4-105">This topic provides information about how to perform this operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a04d4-106">BizTalk 映射器为架构节点建议可能的匹配。</span><span class="sxs-lookup"><span data-stu-id="a04d4-106">The BizTalk Mapper suggests possible matches for a schema node.</span></span> <span data-ttu-id="a04d4-107">当前仅为英语名称支持此功能。</span><span class="sxs-lookup"><span data-stu-id="a04d4-107">This feature is currently supported only for English names.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a04d4-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="a04d4-108">Prerequisites</span></span>  
 <span data-ttu-id="a04d4-109">这些操作需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="a04d4-109">These instructions require that the BizTalk Mapper is running.</span></span>  
  
### <a name="to-match-relevant-schema-nodes"></a><span data-ttu-id="a04d4-110">匹配相关架构节点</span><span class="sxs-lookup"><span data-stu-id="a04d4-110">To match relevant schema nodes</span></span>  
  
1.  <span data-ttu-id="a04d4-111">选择并右键单击你需要知道最佳匹配项，并依次的架构元素**指示匹配**。</span><span class="sxs-lookup"><span data-stu-id="a04d4-111">Select and right-click the schema element for which you need to know the best matches, and then click **Indicate Matches**.</span></span> <span data-ttu-id="a04d4-112">BizTalk 映射器突出显示最佳匹配（仅限于 7 个），且最优化匹配处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="a04d4-112">The BizTalk Mapper highlights the best matches (restricted to seven), with the most optimum match selected.</span></span>  
  
     <span data-ttu-id="a04d4-113">或者，你可以选择**指示匹配**BizTalk 菜单上，或者按 SHIFT + 空间键。</span><span class="sxs-lookup"><span data-stu-id="a04d4-113">Alternatively, you can select **Indicate Matches** from the BizTalk menu, or press SHIFT + SPACE keys.</span></span>  
  
     <span data-ttu-id="a04d4-114">下图显示了目标架构中所选节点的建议匹配。</span><span class="sxs-lookup"><span data-stu-id="a04d4-114">The following figure shows suggestive matches for the selected node in destination schema.</span></span>  
  
     <span data-ttu-id="a04d4-115">![暗示映射](../core/media/suggestive-mapping.gif "Suggestive_Mapping")</span><span class="sxs-lookup"><span data-stu-id="a04d4-115">![Suggestive mapping](../core/media/suggestive-mapping.gif "Suggestive_Mapping")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a04d4-116">按住 SHIFT 键以遍历建议匹配。</span><span class="sxs-lookup"><span data-stu-id="a04d4-116">Hold down the SHIFT key to traverse among the suggestive matches.</span></span>  
  
2.  <span data-ttu-id="a04d4-117">现在您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a04d4-117">You can now do the following:</span></span>  
  
    -   <span data-ttu-id="a04d4-118">按 Enter 确认突出显示（最佳）的匹配。</span><span class="sxs-lookup"><span data-stu-id="a04d4-118">Press ENTER to confirm the highlighted (best possible) match.</span></span>  
  
    -   <span data-ttu-id="a04d4-119">使用向上/向下键按优先顺序在突出显示的匹配中循环选择。</span><span class="sxs-lookup"><span data-stu-id="a04d4-119">Use the UP/DOWN ARROW keys to cycle through the highlighted matches in the order of preference.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a04d4-120">按向下键可遍历到下一个最佳匹配，按向上键可突出显示上一个最佳匹配。</span><span class="sxs-lookup"><span data-stu-id="a04d4-120">Press the DOWN ARROW key to traverse to the next best match, and the UP ARROW key highlights the previous best match.</span></span>  
  
    -   <span data-ttu-id="a04d4-121">按主页键返回到顶部的匹配项。</span><span class="sxs-lookup"><span data-stu-id="a04d4-121">Press the HOME key to return to the top match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a04d4-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a04d4-122">See Also</span></span>  
 [<span data-ttu-id="a04d4-123">在 BizTalk 映射程序中使用增强的功能</span><span class="sxs-lookup"><span data-stu-id="a04d4-123">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)