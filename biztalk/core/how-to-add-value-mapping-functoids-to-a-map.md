---
title: 如何将值映射 Functoid 向映射添加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc70067a-67a1-4a0e-95e5-b0cb327d2cee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e4ba1b22b7db156717c2f40e91117562e879caa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996254"
---
# <a name="how-to-add-value-mapping-functoids-to-a-map"></a><span data-ttu-id="44bb0-102">如何向映射添加“值映射”Functoid</span><span class="sxs-lookup"><span data-stu-id="44bb0-102">How to Add Value Mapping Functoids to a Map</span></span>
<span data-ttu-id="44bb0-103">**值映射**functoid 在其第一个参数为 true，则返回其第二个参数的值。</span><span class="sxs-lookup"><span data-stu-id="44bb0-103">The **Value Mapping** functoid returns the value of its second parameter if its first parameter is true.</span></span> <span data-ttu-id="44bb0-104">该 functoid 通常用于将字段的属性更改为记录的属性。</span><span class="sxs-lookup"><span data-stu-id="44bb0-104">A common use of the functoid is to change the attributes of a field into the attributes of a record.</span></span>  
  
 <span data-ttu-id="44bb0-105">有关概念性信息**值映射**functoid，请参阅[值映射 Functoid](../core/value-mapping-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="44bb0-105">For conceptual information about the **Value Mapping** functoid, see [Value Mapping Functoid](../core/value-mapping-functoid.md).</span></span>  
  
### <a name="to-add-the-value-mapping-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="44bb0-106">向映射添加“值映射”functoid 并对其进行配置</span><span class="sxs-lookup"><span data-stu-id="44bb0-106">To add the Value Mapping functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="44bb0-107">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。</span><span class="sxs-lookup"><span data-stu-id="44bb0-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="44bb0-108">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="44bb0-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="44bb0-109">拖动**值映射**functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="44bb0-109">Drag the **Value Mapping** functoid (![](../core/media/bts-tls-valmap.gif "bts_tls_valmap")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="44bb0-110">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="44bb0-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="44bb0-111">如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。</span><span class="sxs-lookup"><span data-stu-id="44bb0-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="44bb0-112">如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。</span><span class="sxs-lookup"><span data-stu-id="44bb0-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="44bb0-113">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="44bb0-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="44bb0-114">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="44bb0-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="44bb0-115">若要建立的第一个输入的参数**值映射**functoid 创建输入的链接： 将**值映射**到源架构中的记录或字段节点或另一个 functoid 到 functoid其左侧，具有布尔数据类型，并且，将生成的输入的值为"true"或"false"。</span><span class="sxs-lookup"><span data-stu-id="44bb0-115">To establish the first input parameter for the **Value Mapping** functoid, create an input link by dragging the **Value Mapping** functoid to a record or field node in the source schema, or to another functoid to its left, that has a Boolean data type and that will produce an input value of "true" or "false".</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="44bb0-116">也可以拖动相反方向拖动到布尔值的源**值映射**functoid。</span><span class="sxs-lookup"><span data-stu-id="44bb0-116">You can also drag in the opposite direction, dragging the source of the Boolean value to the **Value Mapping** functoid.</span></span>  
  
4. <span data-ttu-id="44bb0-117">若要建立第二个输入的参数**值映射**functoid 创建输入的链接： 将**值映射**在源架构中，或通过将一条记录的记录或字段节点到 functoid或源架构中的字段节点**值映射**functoid。</span><span class="sxs-lookup"><span data-stu-id="44bb0-117">To establish the second input parameter for the **Value Mapping** functoid, create an input link by dragging the **Value Mapping** functoid to a record or field node in the source schema, or by dragging a record or field node in the source schema to the **Value Mapping** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="44bb0-118">第二个输入参数**值映射**functoid 也可以从另一个 functoid 的输出至其左侧。</span><span class="sxs-lookup"><span data-stu-id="44bb0-118">The second input parameter to the **Value Mapping** functoid can also be from the output of another functoid to its left.</span></span> <span data-ttu-id="44bb0-119">通过将某个相关 functoid 拖至另一个相关 functoid，可以创建表示此类输入源的链接。</span><span class="sxs-lookup"><span data-stu-id="44bb0-119">Create the links that represent such sources of input by dragging one of the relevant functoids to the other relevant functoid.</span></span>  
  
5. <span data-ttu-id="44bb0-120">若要使用的输出参数**值映射**functoid，创建输出链接： 将**值映射**到的记录或字段在目标架构中，或通过拖动的记录字段的 functoid目标架构**值映射**functoid。</span><span class="sxs-lookup"><span data-stu-id="44bb0-120">To use the output parameter from the **Value Mapping** functoid, create an output link by dragging the **Value Mapping** functoid to a record or field in the destination schema, or by dragging a record field in the destination schema to the **Value Mapping** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="44bb0-121">与其他 functoid 的输出一样**值映射**functoid 可以用作另一个 functoid 的输入。</span><span class="sxs-lookup"><span data-stu-id="44bb0-121">As with other functoids, the output of the **Value Mapping** functoid can serve as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44bb0-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="44bb0-122">See Also</span></span>  
 [<span data-ttu-id="44bb0-123">向映射添加高级 Functoid</span><span class="sxs-lookup"><span data-stu-id="44bb0-123">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)