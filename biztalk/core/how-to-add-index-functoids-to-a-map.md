---
title: 如何在向地图添加索引 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbfccfcc-c333-422f-b40b-13ca4152e588
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6695f7830dcc35fbb0100c012cff10fa207f1ae2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247669"
---
# <a name="how-to-add-index-functoids-to-a-map"></a><span data-ttu-id="31914-102">如何向映射添加“索引”Functoid</span><span class="sxs-lookup"><span data-stu-id="31914-102">How to Add Index Functoids to a Map</span></span>
<span data-ttu-id="31914-103">**索引**functoid 使您能够选择从特定的循环记录序列中记录的信息。</span><span class="sxs-lookup"><span data-stu-id="31914-103">The **Index** functoid enables you to select information from a specific record in a series of looping records.</span></span> <span data-ttu-id="31914-104">每个**索引**functoid 从单个字段中选择信息。</span><span class="sxs-lookup"><span data-stu-id="31914-104">Each **Index** functoid selects information from a single field.</span></span>  
  
 <span data-ttu-id="31914-105">有关概念性信息**索引**functoid，请参阅[索引 Functoid](../core/index-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="31914-105">For conceptual information about the **Index** functoid, see [Index Functoid](../core/index-functoid.md).</span></span>  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="31914-106">向映射添加“索引”functoid 并对其进行配置</span><span class="sxs-lookup"><span data-stu-id="31914-106">To add the Index functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="31914-107">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。</span><span class="sxs-lookup"><span data-stu-id="31914-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="31914-108">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="31914-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="31914-109">拖动**索引**functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="31914-109">Drag the **Index** functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31914-110">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="31914-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="31914-111">如果希望将该 functoid 放置到其他网格页上，则需要先显示该网格页。</span><span class="sxs-lookup"><span data-stu-id="31914-111">If you want to put the functoid onto a different grid page, you need to display the other grid page first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31914-112">如果你在构造结合使用多个 functoid 的映射，你需要考虑它们相对的从左到右位置。</span><span class="sxs-lookup"><span data-stu-id="31914-112">If you are constructing a map using more than one functoid together, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="31914-113">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="31914-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="31914-114">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="31914-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="31914-115">若要建立的字段输入的参数**索引**functoid，通过将循环记录中的字段拖到源架构中创建的输入的链接**索引**functoid，或拖动**索引**functoid 到源架构中的循环记录中的字段。</span><span class="sxs-lookup"><span data-stu-id="31914-115">To establish the field input parameter for the **Index** functoid, create an input link by dragging a field within a looping record from the source schema to the **Index** functoid, or dragging the **Index** functoid to a field within the looping record in the source schema.</span></span>  
  
4.  <span data-ttu-id="31914-116">若要建立在至少一个索引中的输入的参数**索引**functoid，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="31914-116">To establish at least one index input parameter for the **Index** functoid, perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="31914-117">与**索引**functoid 选择，单击省略号 (**...**) 与关联的按钮**输入参数**中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="31914-117">With the **Index** functoid selected, click the ellipsis (**...**) button associated with the **Input Parameters** property in the **Properties** window.</span></span>  
  
    2.  <span data-ttu-id="31914-118">在**配置索引 Functoid**对话框中，单击![将常量的输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮。</span><span class="sxs-lookup"><span data-stu-id="31914-118">In the **Configure Index Functoid** dialog box, click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button.</span></span>  
  
    3.  <span data-ttu-id="31914-119">在编辑框中，键入数值形式的索引输入参数。</span><span class="sxs-lookup"><span data-stu-id="31914-119">In the edit box, type the index input parameter as a numeric value.</span></span> <span data-ttu-id="31914-120">根据需要重复操作，如果其他索引值是必需的然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="31914-120">Repeat as necessary if additional index values are required, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="31914-121">若要使用输出参数从**索引**functoid，通过拖动创建一条输出链接**索引**向字段在目标架构中，或通过将目标架构中的字段拖到functoid**索引**functoid。</span><span class="sxs-lookup"><span data-stu-id="31914-121">To use the output parameter from the **Index** functoid, create an output link by dragging the **Index** functoid to a field in the destination schema, or by dragging a field in the destination schema to the **Index** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="31914-122">其他 functoid 的输出与**索引**functoid 可以用作输入另一个 functoid。</span><span class="sxs-lookup"><span data-stu-id="31914-122">As with other functoids, the output of the **Index** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31914-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31914-123">See Also</span></span>  
 [<span data-ttu-id="31914-124">向地图添加高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="31914-124">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)