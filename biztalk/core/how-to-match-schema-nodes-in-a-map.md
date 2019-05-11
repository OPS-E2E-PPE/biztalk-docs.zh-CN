---
title: 如何匹配在映射中的架构节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 584f85d2-6198-4ef3-90d9-a322f1457d9a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a25bf295a767f34b692d54fc922fb8fe489ecc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336154"
---
# <a name="how-to-match-schema-nodes-in-a-map"></a><span data-ttu-id="199a9-102">如何匹配在映射中的架构节点</span><span class="sxs-lookup"><span data-stu-id="199a9-102">How to Match Schema Nodes in a Map</span></span>
<span data-ttu-id="199a9-103">当源或目标架构很复杂时，它可能很难将元素映射。</span><span class="sxs-lookup"><span data-stu-id="199a9-103">When the source or destination schemas are complex, it can be difficult to map the elements.</span></span> <span data-ttu-id="199a9-104">BizTalk 映射器引入**指示匹配**功能，它使您能够通过建议最佳匹配映射复杂架构元素。</span><span class="sxs-lookup"><span data-stu-id="199a9-104">The BizTalk Mapper introduces the **Indicative Match** feature, which enables you to map complex schema elements by suggesting the best possible matches.</span></span> <span data-ttu-id="199a9-105">本主题提供有关如何执行此操作的信息。</span><span class="sxs-lookup"><span data-stu-id="199a9-105">This topic provides information about how to perform this operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="199a9-106">BizTalk 映射器建议可能的匹配架构节点。</span><span class="sxs-lookup"><span data-stu-id="199a9-106">The BizTalk Mapper suggests possible matches for a schema node.</span></span> <span data-ttu-id="199a9-107">当前仅为英语名称支持此功能。</span><span class="sxs-lookup"><span data-stu-id="199a9-107">This feature is currently supported only for English names.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="199a9-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="199a9-108">Prerequisites</span></span>  
 <span data-ttu-id="199a9-109">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="199a9-109">These instructions require that the BizTalk Mapper is running.</span></span>  
  
### <a name="to-match-relevant-schema-nodes"></a><span data-ttu-id="199a9-110">若要匹配相关架构节点</span><span class="sxs-lookup"><span data-stu-id="199a9-110">To match relevant schema nodes</span></span>  
  
1.  <span data-ttu-id="199a9-111">选择并右键单击的架构元素，需要知道最佳匹配项，然后依次**指示匹配**。</span><span class="sxs-lookup"><span data-stu-id="199a9-111">Select and right-click the schema element for which you need to know the best matches, and then click **Indicate Matches**.</span></span> <span data-ttu-id="199a9-112">BizTalk 映射器突出显示最佳匹配 （仅限于 7 个），并选中最佳匹配。</span><span class="sxs-lookup"><span data-stu-id="199a9-112">The BizTalk Mapper highlights the best matches (restricted to seven), with the most optimum match selected.</span></span>  
  
     <span data-ttu-id="199a9-113">或者，可以选择**指示匹配**从 BizTalk 菜单中或按 SHIFT + 空格键。</span><span class="sxs-lookup"><span data-stu-id="199a9-113">Alternatively, you can select **Indicate Matches** from the BizTalk menu, or press SHIFT + SPACE keys.</span></span>  
  
     <span data-ttu-id="199a9-114">下图显示目标架构中所选节点的建议匹配。</span><span class="sxs-lookup"><span data-stu-id="199a9-114">The following figure shows suggestive matches for the selected node in destination schema.</span></span>  
  
     <span data-ttu-id="199a9-115">![暗示性映射](../core/media/suggestive-mapping.gif "Suggestive_Mapping")</span><span class="sxs-lookup"><span data-stu-id="199a9-115">![Suggestive mapping](../core/media/suggestive-mapping.gif "Suggestive_Mapping")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="199a9-116">按住 SHIFT 键以遍历建议匹配。</span><span class="sxs-lookup"><span data-stu-id="199a9-116">Hold down the SHIFT key to traverse among the suggestive matches.</span></span>  
  
2.  <span data-ttu-id="199a9-117">您现在可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="199a9-117">You can now do the following:</span></span>  
  
    -   <span data-ttu-id="199a9-118">按 ENTER 确认突出显示最佳 （如有可能） 的匹配。</span><span class="sxs-lookup"><span data-stu-id="199a9-118">Press ENTER to confirm the highlighted (best possible) match.</span></span>  
  
    -   <span data-ttu-id="199a9-119">使用向上箭头键循环按首选项顺序在突出显示匹配。</span><span class="sxs-lookup"><span data-stu-id="199a9-119">Use the UP/DOWN ARROW keys to cycle through the highlighted matches in the order of preference.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="199a9-120">按向下箭头键可遍历到下一个最佳匹配项，并向上箭头键突出显示上一个最佳匹配项。</span><span class="sxs-lookup"><span data-stu-id="199a9-120">Press the DOWN ARROW key to traverse to the next best match, and the UP ARROW key highlights the previous best match.</span></span>  
  
    -   <span data-ttu-id="199a9-121">按 HOME 键返回到上匹配。</span><span class="sxs-lookup"><span data-stu-id="199a9-121">Press the HOME key to return to the top match.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="199a9-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="199a9-122">See Also</span></span>  
 [<span data-ttu-id="199a9-123">使用 BizTalk 映射器中的增强功能</span><span class="sxs-lookup"><span data-stu-id="199a9-123">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)