---
title: 如何向映射添加批量复制 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cff63fc-8f34-4bd0-8501-a8401bde6349
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52d79dc07c884d284fe4f6985453b86bb91b0660
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022139"
---
# <a name="how-to-add-mass-copy-functoids-to-a-map"></a><span data-ttu-id="96618-102">如何向映射中添加“批量复制”Functoid</span><span class="sxs-lookup"><span data-stu-id="96618-102">How to Add Mass Copy Functoids to a Map</span></span>
<span data-ttu-id="96618-103">**批量复制**functoid，映射可使用包含的架构**任何**并**anyAttribute**元素。</span><span class="sxs-lookup"><span data-stu-id="96618-103">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="96618-104">实际上，这些元素是 XML 架构定义语言为匹配未知结构或属性集而提供的通配符。</span><span class="sxs-lookup"><span data-stu-id="96618-104">These elements are, in essence, wildcards provided in the XML Schema definition language to match unknown structures or sets of attributes.</span></span>  
  
 <span data-ttu-id="96618-105">有关概念性信息**批量复制**functoid，请参阅[批量复制 Functoid](../core/mass-copy-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="96618-105">For conceptual information about the **Mass Copy** functoid, see [Mass Copy Functoid](../core/mass-copy-functoid.md).</span></span>  
  
### <a name="to-add-the-mass-copy-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="96618-106">向映射添加“批量复制”functoid 并对其进行配置</span><span class="sxs-lookup"><span data-stu-id="96618-106">To add the Mass Copy functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="96618-107">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。</span><span class="sxs-lookup"><span data-stu-id="96618-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="96618-108">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="96618-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="96618-109">拖动**批量复制**functoid (![](../core/media/advmasscopy.gif "advmasscopy")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="96618-109">Drag the **Mass Copy** functoid (![](../core/media/advmasscopy.gif "advmasscopy")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="96618-110">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="96618-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="96618-111">如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。</span><span class="sxs-lookup"><span data-stu-id="96618-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="96618-112">如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。</span><span class="sxs-lookup"><span data-stu-id="96618-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="96618-113">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="96618-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="96618-114">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="96618-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="96618-115">若要建立输入的参数**批量复制**functoid，通过拖动源架构中的一条记录创建输入的链接**批量复制**functoid，或拖动**批量复制**至源架构中的记录。</span><span class="sxs-lookup"><span data-stu-id="96618-115">To establish the input parameter for the **Mass Copy** functoid, create an input link by dragging a record from the source schema to the **Mass Copy** functoid, or dragging the **Mass Copy** functoid to a record in the source schema.</span></span>  
  
4. <span data-ttu-id="96618-116">若要使用的输出参数**批量复制**functoid，创建输出链接： 将**批量复制**至目标架构中或通过将一条记录拖到目标架构中的记录**批量复制**functoid。</span><span class="sxs-lookup"><span data-stu-id="96618-116">To use the output parameter from the **Mass Copy** functoid, create an output link by dragging the **Mass Copy** functoid to a record in the destination schema, or by dragging a record in the destination schema to the **Mass Copy** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="96618-117">与其他 functoid 不同，您不能使用的输出**批量复制**作为另一个 functoid 的输入的 functoid。</span><span class="sxs-lookup"><span data-stu-id="96618-117">Unlike other functoids, you cannot use the output of the **Mass Copy** functoid as input to another functoid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96618-118">可以插入和配置**批量复制**直接记录通过将两个链接的 functoid。</span><span class="sxs-lookup"><span data-stu-id="96618-118">You can insert and configure the **Mass Copy** functoid by linking two records directly.</span></span> <span data-ttu-id="96618-119">详细信息，请参阅"使用一个批量复制 functoid 链接"部分中[如何自动链接记录](../core/how-to-link-records-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="96618-119">For more information, see the section “To link using a mass copy functoid” in [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96618-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="96618-120">See Also</span></span>  
 [<span data-ttu-id="96618-121">向映射添加高级 Functoid</span><span class="sxs-lookup"><span data-stu-id="96618-121">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)