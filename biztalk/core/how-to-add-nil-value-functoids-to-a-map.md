---
title: 如何在向地图添加 Nil 值 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b2e193ed-fe5c-4b12-aab8-ff2d81fd45e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cc7d8b0035161b4a2126ace021072ffcd1d17e8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248205"
---
# <a name="how-to-add-nil-value-functoids-to-a-map"></a><span data-ttu-id="51404-102">如何向映射中添加“Nil 值”Functoid</span><span class="sxs-lookup"><span data-stu-id="51404-102">How to Add Nil Value Functoids to a Map</span></span>
<span data-ttu-id="51404-103">**Nil 值**functoid 设置到的目标节点的值**Nil**。</span><span class="sxs-lookup"><span data-stu-id="51404-103">The **Nil Value** functoid sets the value of the destination node to **Nil**.</span></span>  
  
 <span data-ttu-id="51404-104">有关概念性信息**Nil 值**functoid，请参阅[Nil 值 Functoid](../core/nil-value-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="51404-104">For conceptual information about the **Nil Value** functoid, see [Nil Value Functoid](../core/nil-value-functoid.md).</span></span>  
  
## <a name="add-the-nil-value-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="51404-105">在向地图添加 Nil 值 functoid，并将其配置</span><span class="sxs-lookup"><span data-stu-id="51404-105">Add the Nil Value functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="51404-106">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。</span><span class="sxs-lookup"><span data-stu-id="51404-106">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span> <span data-ttu-id="51404-107">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="51404-107">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="51404-108">拖动**Nil 值**functoid (![Nil 值 functoid](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="51404-108">Drag the **Nil Value** functoid (![Nil Value functoid](../core/media/advanced-nil-value-functoid.gif "advanced_nil_value_functoid")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51404-109">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="51404-109">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="51404-110">如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。</span><span class="sxs-lookup"><span data-stu-id="51404-110">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
    >
    >  <span data-ttu-id="51404-111">如果你在构造的地图，使用多个 functoid，你需要考虑它们相对的从左到右位置。</span><span class="sxs-lookup"><span data-stu-id="51404-111">If you are constructing a map that uses more than one functoid, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="51404-112">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="51404-112">Functoids are executed from left to right.</span></span> <span data-ttu-id="51404-113">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="51404-113">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="51404-114">**Nil 值**functoid 可以具有零到一个输入参数。</span><span class="sxs-lookup"><span data-stu-id="51404-114">The **Nil Value** functoid can have zero to one input parameters.</span></span> <span data-ttu-id="51404-115">如果没有此 functoid 没有输入的参数，将目标节点设置为**Nil**。</span><span class="sxs-lookup"><span data-stu-id="51404-115">If there is no input parameter for this functoid, the target node is set to **Nil**.</span></span> <span data-ttu-id="51404-116">若要建立的输入的参数**Nil 值**functoid，通过将输出拖从其他创建输入的链接**逻辑**functoid 或从输入的实例消息中的变量布尔字段。</span><span class="sxs-lookup"><span data-stu-id="51404-116">To establish the input parameter for the **Nil Value** functoid, create an input link by dragging the output from some other **Logical** functoid or from a variable Boolean field in the input instance message.</span></span>  
  
4.  <span data-ttu-id="51404-117">若要使用输出参数从**Nil 值**functoid，通过拖动创建一条输出链接**Nil 值**functoid 记录或目标架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="51404-117">To use the output parameter from the **Nil Value** functoid, create an output link by dragging the **Nil Value** functoid to a record or field in the destination schema.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51404-118">其他 functoid 的输出与**Nil 值**functoid 可以用作输入另一个 functoid。</span><span class="sxs-lookup"><span data-stu-id="51404-118">As with other functoids, the output of the **Nil Value** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51404-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51404-119">See Also</span></span>  
-  <span data-ttu-id="51404-120">**Nil 值 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="51404-120">**Nil Value Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>   
-  [<span data-ttu-id="51404-121">向地图添加高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="51404-121">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)