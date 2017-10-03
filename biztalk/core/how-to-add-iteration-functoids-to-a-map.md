---
title: "如何在向地图添加迭代 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1eaea929-e352-447d-b119-bd69b6b24e6c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2df7cda082a9a85e54e1dce427d73ea15d8f920
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-iteration-functoids-to-a-map"></a><span data-ttu-id="3b45b-102">如何向映射添加“迭代”Functoid</span><span class="sxs-lookup"><span data-stu-id="3b45b-102">How to Add Iteration Functoids to a Map</span></span>
<span data-ttu-id="3b45b-103">**迭代**functoid 输出中循环的当前记录的索引结构，对于第一个记录，对于第二个记录，2 1 开始，依次类推。</span><span class="sxs-lookup"><span data-stu-id="3b45b-103">The **Iteration** functoid outputs the index of the current record in a looping structure, beginning at 1 for the first record, 2 for the second record, and so on.</span></span>  
  
 <span data-ttu-id="3b45b-104">有关概念性信息**迭代**functoid，请参阅[迭代 Functoid](../core/iteration-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="3b45b-104">For conceptual information about the **Iteration** functoid, see [Iteration Functoid](../core/iteration-functoid.md).</span></span>  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="3b45b-105">向映射添加“索引”functoid 并对其进行配置</span><span class="sxs-lookup"><span data-stu-id="3b45b-105">To add the Index functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="3b45b-106">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。</span><span class="sxs-lookup"><span data-stu-id="3b45b-106">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="3b45b-107">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="3b45b-107">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="3b45b-108">拖动**索引**functoid (![](../core/media/bts-tls-iteration.gif "bts_tls_iteration")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="3b45b-108">Drag the **Index** functoid (![](../core/media/bts-tls-iteration.gif "bts_tls_iteration")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3b45b-109">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="3b45b-109">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="3b45b-110">如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。</span><span class="sxs-lookup"><span data-stu-id="3b45b-110">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3b45b-111">如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。</span><span class="sxs-lookup"><span data-stu-id="3b45b-111">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="3b45b-112">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="3b45b-112">Functoids are executed from left to right.</span></span> <span data-ttu-id="3b45b-113">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="3b45b-113">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="3b45b-114">若要建立的循环记录输入的参数**迭代**functoid，通过将循环记录拖到源架构中创建的输入的链接**迭代**functoid，或通过拖动**迭代**functoid 到源架构中的循环记录。</span><span class="sxs-lookup"><span data-stu-id="3b45b-114">To establish the looping record input parameter for the **Iteration** functoid, create an input link by dragging a looping record from the source schema to the **Iteration** functoid, or by dragging the **Iteration** functoid to a looping record in the source schema.</span></span>  
  
4.  <span data-ttu-id="3b45b-115">若要使用输出参数从**迭代**functoid，通过拖动创建一条输出链接**迭代**functoid 给目标架构中或通过将拖到目标架构中的字段的字段**迭代**functoid。</span><span class="sxs-lookup"><span data-stu-id="3b45b-115">To use the output parameter from the **Iteration** functoid, create an output link by dragging the **Iteration** functoid to a field in the destination schema, or by dragging a field in the destination schema to the **Iteration** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3b45b-116">目标架构中的相关字段的数据类型必须是数字或可转换为数字，使其匹配的输出数据类型**迭代**functoid。</span><span class="sxs-lookup"><span data-stu-id="3b45b-116">The data type of the relevant field in the destination schema must be numeric or convertible to numeric so that it matches the output data type of the **Iteration** functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b45b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b45b-117">See Also</span></span>  
 [<span data-ttu-id="3b45b-118">向地图添加高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="3b45b-118">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)