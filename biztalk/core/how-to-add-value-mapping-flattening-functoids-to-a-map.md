---
title: 如何将值映射 （平展） Functoid 向映射添加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00a447c3-58d0-42ab-a5c4-417ee7800a6b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b630b586e1252d0afb244deb77ab3e4c7bfaf30
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343058"
---
# <a name="how-to-add-value-mapping-flattening-functoids-to-a-map"></a><span data-ttu-id="33c27-102">如何添加值映射 （平展） Functoid 映射到</span><span class="sxs-lookup"><span data-stu-id="33c27-102">How to Add Value Mapping (Flattening) Functoids to a Map</span></span>
<span data-ttu-id="33c27-103">**值映射 （平展）** functoid，可通过将多个记录转换为单个记录平展输入的实例消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="33c27-103">The **Value Mapping (Flattening)** functoid enables you to flatten a portion of an input instance message by converting multiple records into a single record.</span></span> <span data-ttu-id="33c27-104">在转换 Microsoft Commerce Server 目录时通常执行此操作。</span><span class="sxs-lookup"><span data-stu-id="33c27-104">This is a common operation in converting Microsoft Commerce Server catalogs.</span></span>  
  
 <span data-ttu-id="33c27-105">有关概念性信息**值映射 （平展）** functoid，请参阅[值映射 （平展） Functoid](../core/value-mapping-flattening-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="33c27-105">For conceptual information about the **Value Mapping (Flattening)** functoid, see [Value Mapping (Flattening) Functoid](../core/value-mapping-flattening-functoid.md).</span></span>  
  
### <a name="to-add-the-value-mapping-flattening-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="33c27-106">向映射添加值映射 （平展） functoid 并将其配置</span><span class="sxs-lookup"><span data-stu-id="33c27-106">To add the Value Mapping (Flattening) functoid to a map and configure it</span></span>  
  
1. <span data-ttu-id="33c27-107">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。</span><span class="sxs-lookup"><span data-stu-id="33c27-107">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
    <span data-ttu-id="33c27-108">将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="33c27-108">The list of advanced functoids in the chosen category appears.</span></span>  
  
2. <span data-ttu-id="33c27-109">拖动**值映射 （平展）** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="33c27-109">Drag the **Value Mapping (Flattening)** functoid (![](../core/media/bts-tls-valmapflat.gif "bts_tls_valmapflat")) from the Toolbox to the appropriate location on a grid page.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="33c27-110">该 functoid 将放置上显示的网格页。</span><span class="sxs-lookup"><span data-stu-id="33c27-110">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="33c27-111">如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。</span><span class="sxs-lookup"><span data-stu-id="33c27-111">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="33c27-112">如果构造一起使用多个 functoid 的映射，您需要考虑它们的左右位置关系。</span><span class="sxs-lookup"><span data-stu-id="33c27-112">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="33c27-113">从左向右执行 Functoid。</span><span class="sxs-lookup"><span data-stu-id="33c27-113">Functoids are executed from left to right.</span></span> <span data-ttu-id="33c27-114">Functoid 的输出只能输入到其右侧的另一个 functoid。</span><span class="sxs-lookup"><span data-stu-id="33c27-114">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3. <span data-ttu-id="33c27-115">若要建立的第一个输入的参数**值映射 （平展）** functoid 创建输入的链接： 将**值映射 （平展）** 源中的记录或字段节点到 functoid架构，或其左侧的另一个 functoid，具有布尔数据类型，并且，将生成的输入的值为"true"或"false。</span><span class="sxs-lookup"><span data-stu-id="33c27-115">To establish the first input parameter for the **Value Mapping (Flattening)** functoid, create an input link by dragging the **Value Mapping (Flattening)** functoid to a record or field node in the source schema, or to another functoid to its left, that has a Boolean data type and that will produce an input value of "true" or "false."</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="33c27-116">也可以拖动相反方向拖动到布尔值的源**值映射 （平展）** functoid。</span><span class="sxs-lookup"><span data-stu-id="33c27-116">You can also drag in the opposite direction, dragging the source of the Boolean value to the **Value Mapping (Flattening)** functoid.</span></span>  
  
4. <span data-ttu-id="33c27-117">若要建立第二个输入的参数**值映射 （平展）** functoid 创建输入的链接： 将**值映射 （平展）** 源中的记录或字段节点到 functoid架构，或者将记录或字段节点拖到源架构中**值映射 （平展）** functoid，或插入一个常量。</span><span class="sxs-lookup"><span data-stu-id="33c27-117">To establish the second input parameter for the **Value Mapping (Flattening)** functoid, create an input link by dragging the **Value Mapping (Flattening)** functoid to a record or field node in the source schema, or by dragging a record or field node in the source schema to the **Value Mapping (Flattening)** functoid, or insert a constant.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="33c27-118">第二个输入参数**值映射 （平展）** functoid 也可以从另一个 functoid 的输出至其左侧。</span><span class="sxs-lookup"><span data-stu-id="33c27-118">The second input parameter to the **Value Mapping (Flattening)** functoid can also be from the output of another functoid to its left.</span></span> <span data-ttu-id="33c27-119">创建链接表示此类通过将一个相关 functoid 拖至其他相关 functoid 的输入源。</span><span class="sxs-lookup"><span data-stu-id="33c27-119">Create the links the represent such sources of input by dragging one of the relevant functoids to the other relevant functoid.</span></span>  
  
5. <span data-ttu-id="33c27-120">若要使用的输出参数**值映射 （平展）** functoid，创建输出链接： 将**值映射 （平展）** functoid 到的记录或字段在目标架构中，或通过拖动到目标架构中的记录字段**值映射 （平展）** functoid。</span><span class="sxs-lookup"><span data-stu-id="33c27-120">To use the output parameter from the **Value Mapping (Flattening)** functoid, create an output link by dragging the **Value Mapping (Flattening)** functoid to a record or field in the destination schema, or by dragging a record field in the destination schema to the **Value Mapping (Flattening)** functoid.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="33c27-121">与其他 functoid 的输出一样**值映射 （平展）** functoid 可以用作另一个 functoid 的输入。</span><span class="sxs-lookup"><span data-stu-id="33c27-121">As with other functoids, the output of the **Value Mapping (Flattening)** functoid can be used as input to another functoid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c27-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="33c27-122">See Also</span></span>  
 [<span data-ttu-id="33c27-123">向映射添加高级 Functoid</span><span class="sxs-lookup"><span data-stu-id="33c27-123">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)