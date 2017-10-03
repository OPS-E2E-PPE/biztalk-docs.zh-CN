---
title: "如何添加值映射到图 Functoid |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc70067a-67a1-4a0e-95e5-b0cb327d2cee
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47e463489332c3a1d2887dab5f7bd734fdd20af5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-value-mapping-functoids-to-a-map"></a><span data-ttu-id="01e4f-102">如何向映射添加“值映射”Functoid</span><span class="sxs-lookup"><span data-stu-id="01e4f-102">How to Add Value Mapping Functoids to a Map</span></span>
<span data-ttu-id="01e4f-103">**值映射**functoid 返回其第二个参数的值，如果其第一个参数为 true。</span><span class="sxs-lookup"><span data-stu-id="01e4f-103">The **Value Mapping** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="01e4f-104">该 functoid 通常用于将字段的属性更改为记录的属性。</span><span class="sxs-lookup"><span data-stu-id="01e4f-104">A common use of the functoid is to change the attributes of a field into the attributes of a record.</span></span>  
  
 <span data-ttu-id="01e4f-105">有关概念性信息**值映射**functoid，请参阅[值映射 Functoid](../core/value-mapping-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="01e4f-105">For conceptual information about the **Value Mapping** functoid, see [Value Mapping Functoid](../core/value-mapping-functoid.md).</span></span>  
  
### <a name="to-add-the-value-mapping-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="01e4f-106">向映射添加“值映射”functoid 并对其进行配置</span><span class="sxs-lookup"><span data-stu-id="01e4f-106">To add the Value Mapping functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="01e4f-107">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。</span><span class="sxs-lookup"><span data-stu-id="01e4f-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="01e4f-108">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="01e4f-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="01e4f-109">拖动**值映射**functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="01e4f-109">Drag the **Value Mapping** functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01e4f-110">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="01e4f-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="01e4f-111">如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。</span><span class="sxs-lookup"><span data-stu-id="01e4f-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01e4f-112">如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。</span><span class="sxs-lookup"><span data-stu-id="01e4f-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="01e4f-113">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="01e4f-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="01e4f-114">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="01e4f-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="01e4f-115">若要建立的第一个输入的参数**值映射**functoid，通过拖动创建输入的链接**值映射**functoid 到源架构中的记录或字段节点或到另一个 functoid其左侧，具有 Boolean 数据类型以及将产生的输入的值为"true"或"false"。</span><span class="sxs-lookup"><span data-stu-id="01e4f-115">To establish the first input parameter for the **Value Mapping** functoid, create an input link by dragging the **Value Mapping** functoid to a record or field node in the source schema, or to another functoid to its left, that has a Boolean data type and that will produce an input value of "true" or "false".</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01e4f-116">你也可以拖动相反的方向，拖动到的布尔值的源**值映射**functoid。</span><span class="sxs-lookup"><span data-stu-id="01e4f-116">You can also drag in the opposite direction, dragging the source of the Boolean value to the **Value Mapping** functoid.</span></span>  
  
4.  <span data-ttu-id="01e4f-117">若要建立的第二个输入的参数**值映射**functoid，通过拖动创建输入的链接**值映射**到记录或字段节点中，在源架构中，或通过拖动记录 functoid或源架构中的字段节点**值映射**functoid。</span><span class="sxs-lookup"><span data-stu-id="01e4f-117">To establish the second input parameter for the **Value Mapping** functoid, create an input link by dragging the **Value Mapping** functoid to a record or field node in the source schema, or by dragging a record or field node in the source schema to the **Value Mapping** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01e4f-118">第二个输入参数**值映射**functoid 也可以从另一个 functoid 输出其左侧。</span><span class="sxs-lookup"><span data-stu-id="01e4f-118">The second input parameter to the **Value Mapping** functoid can also be from the output of another functoid to its left.</span></span> <span data-ttu-id="01e4f-119">通过将某个相关 functoid 拖至另一个相关 functoid，可以创建表示此类输入源的链接。</span><span class="sxs-lookup"><span data-stu-id="01e4f-119">Create the links that represent such sources of input by dragging one of the relevant functoids to the other relevant functoid.</span></span>  
  
5.  <span data-ttu-id="01e4f-120">若要使用输出参数从**值映射**functoid，通过拖动创建一条输出链接**值映射**记录或字段在目标架构中，或通过将记录字段中拖动 functoid目标架构**值映射**functoid。</span><span class="sxs-lookup"><span data-stu-id="01e4f-120">To use the output parameter from the **Value Mapping** functoid, create an output link by dragging the **Value Mapping** functoid to a record or field in the destination schema, or by dragging a record field in the destination schema to the **Value Mapping** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01e4f-121">其他 functoid 的输出与**值映射**functoid 可用作另一个 functoid 的输入。</span><span class="sxs-lookup"><span data-stu-id="01e4f-121">As with other functoids, the output of the **Value Mapping** functoid can serve as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01e4f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01e4f-122">See Also</span></span>  
 [<span data-ttu-id="01e4f-123">向地图添加高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="01e4f-123">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)