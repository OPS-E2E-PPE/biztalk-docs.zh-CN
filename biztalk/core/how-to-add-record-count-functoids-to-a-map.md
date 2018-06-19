---
title: 如何在向地图添加记录计数 Functoid |Microsoft 文档
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
ms.openlocfilehash: cd315a637b3efd069361dfa2d780cff179559da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247661"
---
# <a name="how-to-add-record-count-functoids-to-a-map"></a><span data-ttu-id="81e61-102">如何在向地图添加记录计数 Functoid</span><span class="sxs-lookup"><span data-stu-id="81e61-102">How to Add Record Count Functoids to a Map</span></span>
<span data-ttu-id="81e61-103">**记录计数**functoid，可以对实例消息中生成的记录出现的次数计数。</span><span class="sxs-lookup"><span data-stu-id="81e61-103">The **Record Count** functoid enables you to generate a count of the number of times a record occurs in an instance message.</span></span>  
  
 <span data-ttu-id="81e61-104">有关概念性信息**记录计数**functoid，请参阅[记录计数 Functoid](../core/record-count-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="81e61-104">For conceptual information about the **Record Count** functoid, see [Record Count Functoid](../core/record-count-functoid.md).</span></span>  
  
### <a name="to-add-the-record-count-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="81e61-105">向映射添加“记录计数”functoid 并对其进行配置</span><span class="sxs-lookup"><span data-stu-id="81e61-105">To add the Record Count functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="81e61-106">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。</span><span class="sxs-lookup"><span data-stu-id="81e61-106">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="81e61-107">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="81e61-107">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="81e61-108">拖动**记录计数**functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="81e61-108">Drag the **Record Count** functoid (![](../core/media/bts-tls-recordcount.gif "bts_tls_recordcount")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="81e61-109">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="81e61-109">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="81e61-110">如果希望将该 functoid 放置到其他网格页上，则需要先显示该网格页。</span><span class="sxs-lookup"><span data-stu-id="81e61-110">If you want to put the functoid onto a different grid page, you need to display the other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="81e61-111">如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。</span><span class="sxs-lookup"><span data-stu-id="81e61-111">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="81e61-112">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="81e61-112">Functoids are executed from left to right.</span></span> <span data-ttu-id="81e61-113">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="81e61-113">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="81e61-114">若要建立的输入的参数**记录计数**functoid，通过将循环记录拖到源架构中创建的输入的链接**记录计数**functoid，或拖动**记录计数**functoid 到源架构中的循环记录。</span><span class="sxs-lookup"><span data-stu-id="81e61-114">To establish the input parameter for the **Record Count** functoid, create an input link by dragging a looping record from the source schema to the **Record Count** functoid, or dragging the **Record Count** functoid to a looping record in the source schema.</span></span>  
  
4.  <span data-ttu-id="81e61-115">若要使用输出参数从**记录计数**functoid，通过拖动创建一条输出链接**记录计数**functoid 给目标架构中或通过将字段拖到目标中的字段将架构与**记录计数**functoid。</span><span class="sxs-lookup"><span data-stu-id="81e61-115">To use the output parameter from the **Record Count** functoid, create an output link by dragging the **Record Count** functoid to a field in the destination schema, or by dragging a field in the destination schema to the **Record Count** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="81e61-116">其他 functoid 的输出与**记录计数**functoid 可以用作输入另一个 functoid。</span><span class="sxs-lookup"><span data-stu-id="81e61-116">As with other functoids, the output of the **Record Count** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e61-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81e61-117">See Also</span></span>  
 [<span data-ttu-id="81e61-118">向地图添加高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="81e61-118">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)