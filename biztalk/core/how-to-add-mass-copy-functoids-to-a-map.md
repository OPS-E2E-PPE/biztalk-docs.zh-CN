---
title: 如何在向地图添加大容量复制 Functoid |Microsoft 文档
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
ms.openlocfilehash: 4cee6f2c53bbd3b3dbabe55f0160309532d0ebf3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247565"
---
# <a name="how-to-add-mass-copy-functoids-to-a-map"></a><span data-ttu-id="f8a63-102">如何向映射中添加“批量复制”Functoid</span><span class="sxs-lookup"><span data-stu-id="f8a63-102">How to Add Mass Copy Functoids to a Map</span></span>
<span data-ttu-id="f8a63-103">**大容量复制**functoid 使你使用包含的架构的映射**任何**和**anyAttribute**元素。</span><span class="sxs-lookup"><span data-stu-id="f8a63-103">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="f8a63-104">实际上，这些元素是 XML 架构定义语言为匹配未知结构或属性集而提供的通配符。</span><span class="sxs-lookup"><span data-stu-id="f8a63-104">These elements are, in essence, wildcards provided in the XML Schema definition language to match unknown structures or sets of attributes.</span></span>  
  
 <span data-ttu-id="f8a63-105">有关概念性信息**大容量复制**functoid，请参阅[大容量复制 Functoid](../core/mass-copy-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="f8a63-105">For conceptual information about the **Mass Copy** functoid, see [Mass Copy Functoid](../core/mass-copy-functoid.md).</span></span>  
  
### <a name="to-add-the-mass-copy-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="f8a63-106">向映射添加“批量复制”functoid 并对其进行配置</span><span class="sxs-lookup"><span data-stu-id="f8a63-106">To add the Mass Copy functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="f8a63-107">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。</span><span class="sxs-lookup"><span data-stu-id="f8a63-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="f8a63-108">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="f8a63-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="f8a63-109">拖动**大容量复制**functoid (![](../core/media/advmasscopy.gif "advmasscopy")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="f8a63-109">Drag the **Mass Copy** functoid (![](../core/media/advmasscopy.gif "advmasscopy")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8a63-110">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="f8a63-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="f8a63-111">如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。</span><span class="sxs-lookup"><span data-stu-id="f8a63-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8a63-112">如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。</span><span class="sxs-lookup"><span data-stu-id="f8a63-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="f8a63-113">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="f8a63-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="f8a63-114">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="f8a63-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="f8a63-115">若要建立的输入的参数**大容量复制**functoid，通过将一条记录拖到源架构中创建的输入的链接**大容量复制**functoid，或拖动**大容量复制** functoid 到源架构中的记录。</span><span class="sxs-lookup"><span data-stu-id="f8a63-115">To establish the input parameter for the **Mass Copy** functoid, create an input link by dragging a record from the source schema to the **Mass Copy** functoid, or dragging the **Mass Copy** functoid to a record in the source schema.</span></span>  
  
4.  <span data-ttu-id="f8a63-116">若要使用输出参数从**大容量复制**functoid，通过拖动创建一条输出链接**大容量复制**到记录在目标架构中，或通过将一条记录拖到目标架构中的 functoid**大容量复制**functoid。</span><span class="sxs-lookup"><span data-stu-id="f8a63-116">To use the output parameter from the **Mass Copy** functoid, create an output link by dragging the **Mass Copy** functoid to a record in the destination schema, or by dragging a record in the destination schema to the **Mass Copy** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f8a63-117">与其他 functoid，您不能使用的输出**大容量复制**functoid 作为另一个 functoid 的输入。</span><span class="sxs-lookup"><span data-stu-id="f8a63-117">Unlike other functoids, you cannot use the output of the **Mass Copy** functoid as input to another functoid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8a63-118">你可以插入和配置**大容量复制**通过链接两个 functoid 直接记录。</span><span class="sxs-lookup"><span data-stu-id="f8a63-118">You can insert and configure the **Mass Copy** functoid by linking two records directly.</span></span> <span data-ttu-id="f8a63-119">详细信息，请参阅"使用大容量复制 functoid 链接"部分中[如何自动链接记录](../core/how-to-link-records-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="f8a63-119">For more information, see the section “To link using a mass copy functoid” in [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a63-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8a63-120">See Also</span></span>  
 [<span data-ttu-id="f8a63-121">向地图添加高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="f8a63-121">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)