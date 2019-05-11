---
title: 如何向映射添加索引 Functoid |Microsoft Docs
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
ms.openlocfilehash: ab94f8c3b922f6847fdeff9c514025b5718336c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343281"
---
# <a name="how-to-add-index-functoids-to-a-map"></a><span data-ttu-id="ef83b-102">如何向映射添加索引 Functoid</span><span class="sxs-lookup"><span data-stu-id="ef83b-102">How to Add Index Functoids to a Map</span></span>
<span data-ttu-id="ef83b-103">**索引**functoid，您可以选择从一系列循环记录中的特定记录的信息。</span><span class="sxs-lookup"><span data-stu-id="ef83b-103">The **Index** functoid enables you to select information from a specific record in a series of looping records.</span></span> <span data-ttu-id="ef83b-104">每个**索引**functoid 从单个字段中选择信息。</span><span class="sxs-lookup"><span data-stu-id="ef83b-104">Each **Index** functoid selects information from a single field.</span></span>  
  
 <span data-ttu-id="ef83b-105">有关概念性信息**索引**functoid，请参阅[索引 Functoid](../core/index-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="ef83b-105">For conceptual information about the **Index** functoid, see [Index Functoid](../core/index-functoid.md).</span></span>  
  
### <a name="to-add-the-index-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="ef83b-106">向映射添加索引 functoid 并将其配置</span><span class="sxs-lookup"><span data-stu-id="ef83b-106">To add the Index functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="ef83b-107">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。</span><span class="sxs-lookup"><span data-stu-id="ef83b-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="ef83b-108">将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="ef83b-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="ef83b-109">拖动**索引**functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="ef83b-109">Drag the **Index** functoid (![](../core/media/bts-tls-index.gif "bts_tls_index")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ef83b-110">该 functoid 将放置上显示的网格页。</span><span class="sxs-lookup"><span data-stu-id="ef83b-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="ef83b-111">如果你想要将该 functoid 放置到其他网格页上，您需要首先显示的其他网格页。</span><span class="sxs-lookup"><span data-stu-id="ef83b-111">If you want to put the functoid onto a different grid page, you need to display the other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ef83b-112">如果构造一起使用多个 functoid 的映射，您需要考虑其相对的从左到右位置。</span><span class="sxs-lookup"><span data-stu-id="ef83b-112">If you are constructing a map using more than one functoid together, you need to consider their relative left-to-right placement.</span></span> <span data-ttu-id="ef83b-113">从左向右执行 Functoid。</span><span class="sxs-lookup"><span data-stu-id="ef83b-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="ef83b-114">Functoid 的输出只能输入到其右侧的另一个 functoid。</span><span class="sxs-lookup"><span data-stu-id="ef83b-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="ef83b-115">若要建立字段输入的参数**索引**functoid，通过将循环记录中的字段拖到源架构中创建输入的链接**索引**functoid，或拖动**索引**至源架构中的循环记录中的字段。</span><span class="sxs-lookup"><span data-stu-id="ef83b-115">To establish the field input parameter for the **Index** functoid, create an input link by dragging a field within a looping record from the source schema to the **Index** functoid, or dragging the **Index** functoid to a field within the looping record in the source schema.</span></span>  
  
4. <span data-ttu-id="ef83b-116">若要建立至少一个索引输入的参数**索引**functoid，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ef83b-116">To establish at least one index input parameter for the **Index** functoid, perform the following steps:</span></span>  
  
   1.  <span data-ttu-id="ef83b-117">与**索引**functoid 选择，单击省略号 (**...**) 按钮与相关联**输入参数**中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="ef83b-117">With the **Index** functoid selected, click the ellipsis (**...**) button associated with the **Input Parameters** property in the **Properties** window.</span></span>  
  
   2.  <span data-ttu-id="ef83b-118">在中**配置索引 Functoid**对话框中，单击![将常数输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮。</span><span class="sxs-lookup"><span data-stu-id="ef83b-118">In the **Configure Index Functoid** dialog box, click the ![Adding constant input parameters to a functoid](../core/media/add-input-parameters.gif "Add_input_parameters") button.</span></span>  
  
   3.  <span data-ttu-id="ef83b-119">在编辑框中，键入为数字值的索引输入的参数。</span><span class="sxs-lookup"><span data-stu-id="ef83b-119">In the edit box, type the index input parameter as a numeric value.</span></span> <span data-ttu-id="ef83b-120">如果其他索引值是必需的然后单击根据需要重复**确定**。</span><span class="sxs-lookup"><span data-stu-id="ef83b-120">Repeat as necessary if additional index values are required, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="ef83b-121">若要使用的输出参数**索引**functoid，创建输出链接： 将**索引**functoid 到目标架构中或通过将目标架构中的字段拖至的字段**索引**functoid。</span><span class="sxs-lookup"><span data-stu-id="ef83b-121">To use the output parameter from the **Index** functoid, create an output link by dragging the **Index** functoid to a field in the destination schema, or by dragging a field in the destination schema to the **Index** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ef83b-122">与其他 functoid 的输出一样**索引**functoid 可以用作另一个 functoid 的输入。</span><span class="sxs-lookup"><span data-stu-id="ef83b-122">As with other functoids, the output of the **Index** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef83b-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef83b-123">See Also</span></span>  
 [<span data-ttu-id="ef83b-124">向映射添加高级 Functoid</span><span class="sxs-lookup"><span data-stu-id="ef83b-124">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)