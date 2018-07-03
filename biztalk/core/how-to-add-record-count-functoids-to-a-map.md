---
title: 如何向映射添加记录计数 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fbfd2a0-fac5-49f1-bcbb-873c287cd278
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d5fda3565d2b7c3302b5ae3cb596bfed6781609
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980326"
---
# <a name="how-to-add-record-count-functoids-to-a-map"></a><span data-ttu-id="6d266-102">如何向映射添加记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="6d266-102">How to Add Record Count Functoids to a Map</span></span>
<span data-ttu-id="6d266-103">**记录计数**functoid，您可以在实例消息中生成一条记录出现次数的计数。</span><span class="sxs-lookup"><span data-stu-id="6d266-103">The **Record Count** functoid enables you to generate a count of the number of times a record occurs in an instance message.</span></span>  
  
 <span data-ttu-id="6d266-104">有关概念性信息**记录计数**functoid，请参阅[记录计数 Functoid](../core/record-count-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="6d266-104">For conceptual information about the **Record Count** functoid, see [Record Count Functoid](../core/record-count-functoid.md).</span></span>  
  
### <a name="to-add-the-record-count-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="6d266-105">向映射添加“记录计数”functoid 并对其进行配置</span><span class="sxs-lookup"><span data-stu-id="6d266-105">To add the Record Count functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="6d266-106">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。</span><span class="sxs-lookup"><span data-stu-id="6d266-106">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="6d266-107">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="6d266-107">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="6d266-108">拖动**记录计数**functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="6d266-108">Drag the **Record Count** functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6d266-109">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="6d266-109">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="6d266-110">如果希望将该 functoid 放置到其他网格页上，则需要先显示该网格页。</span><span class="sxs-lookup"><span data-stu-id="6d266-110">If you want to put the functoid onto a different grid page, you need to display the other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6d266-111">如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。</span><span class="sxs-lookup"><span data-stu-id="6d266-111">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="6d266-112">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="6d266-112">Functoids are executed from left to right.</span></span> <span data-ttu-id="6d266-113">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="6d266-113">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="6d266-114">若要建立输入的参数**记录计数**functoid 创建输入的链接： 将源架构中的循环记录**记录计数**functoid，或拖动**记录计数**至源架构中的循环记录。</span><span class="sxs-lookup"><span data-stu-id="6d266-114">To establish the input parameter for the **Record Count** functoid, create an input link by dragging a looping record from the source schema to the **Record Count** functoid, or dragging the **Record Count** functoid to a looping record in the source schema.</span></span>  
  
4. <span data-ttu-id="6d266-115">若要使用的输出参数**记录计数**functoid，创建输出链接： 将**记录计数**functoid 到目标架构中或将字段拖放目标中的字段架构**记录计数**functoid。</span><span class="sxs-lookup"><span data-stu-id="6d266-115">To use the output parameter from the **Record Count** functoid, create an output link by dragging the **Record Count** functoid to a field in the destination schema, or by dragging a field in the destination schema to the **Record Count** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6d266-116">与其他 functoid 的输出一样**记录计数**functoid 可以用作另一个 functoid 的输入。</span><span class="sxs-lookup"><span data-stu-id="6d266-116">As with other functoids, the output of the **Record Count** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d266-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d266-117">See Also</span></span>  
 [<span data-ttu-id="6d266-118">向映射添加高级 Functoid</span><span class="sxs-lookup"><span data-stu-id="6d266-118">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)