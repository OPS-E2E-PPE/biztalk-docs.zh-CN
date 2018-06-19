---
title: 如何添加循环到图 Functoid |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b24051b7-3e79-4a49-8249-a057c048ddae
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa380b4a92de685ad8dc19c27a98f6578d12dc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248725"
---
# <a name="how-to-add-looping-functoids-to-a-map"></a><span data-ttu-id="d07fc-102">如何向映射添加“循环”Functoid</span><span class="sxs-lookup"><span data-stu-id="d07fc-102">How to Add Looping Functoids to a Map</span></span>

## <a name="overview"></a><span data-ttu-id="d07fc-103">概述</span><span class="sxs-lookup"><span data-stu-id="d07fc-103">Overview</span></span>
<span data-ttu-id="d07fc-104">**循环**functoid 将多个记录或源架构中的字段合并到目标架构中的单个记录。</span><span class="sxs-lookup"><span data-stu-id="d07fc-104">The **Looping** functoid combines multiple records or fields in the source schema into a single record in the destination schema.</span></span>  
  
 <span data-ttu-id="d07fc-105">有关概念性信息**循环**functoid，请参阅[循环 Functoid](../core/looping-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="d07fc-105">For conceptual information about the **Looping** functoid, see [Looping Functoid](../core/looping-functoid.md).</span></span>  
  
 <span data-ttu-id="d07fc-106">某些情况下，某些 functoid 可能不会按预期在映射中使用时**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="d07fc-106">Under certain conditions, some functoids might not behave as expected when they are used in a map with a **Looping** functoid.</span></span> <span data-ttu-id="d07fc-107">如果此类 functoid 满足以下条件，它不会不会产生预期的结果：</span><span class="sxs-lookup"><span data-stu-id="d07fc-107">If such a functoid meets the following conditions, it does not produce the expected results:</span></span>  
  
-   <span data-ttu-id="d07fc-108">functoid 具有多个输入链接。</span><span class="sxs-lookup"><span data-stu-id="d07fc-108">The functoid has more than one input link.</span></span>  
  
-   <span data-ttu-id="d07fc-109">两个或多个 functoid 输入链接链接到的输入记录的子字段**循环**functoid，子字段不是同级。</span><span class="sxs-lookup"><span data-stu-id="d07fc-109">Two or more of the functoid input links are linked to child fields of the input records to the **Looping** functoid, where the child fields are not siblings.</span></span>  
  
-   <span data-ttu-id="d07fc-110">Functoid 具有一条输出链接链接到的输出记录的子字段**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="d07fc-110">The functoid has an output link that is linked to a child field of the output record of the **Looping** functoid.</span></span>  
  
## <a name="add-the-looping-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="d07fc-111">在向地图添加循环 functoid，并将其配置</span><span class="sxs-lookup"><span data-stu-id="d07fc-111">Add the Looping functoid to a map and configure it</span></span>  
  
1.  <span data-ttu-id="d07fc-112">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。</span><span class="sxs-lookup"><span data-stu-id="d07fc-112">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  
  
     <span data-ttu-id="d07fc-113">此时，将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="d07fc-113">The list of advanced functoids in the chosen category appears.</span></span>  
  
2.  <span data-ttu-id="d07fc-114">拖动**循环**functoid 从工具箱拖到网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="d07fc-114">Drag the **Looping** functoid from the Toolbox to the appropriate location on a grid page.</span></span>  
  
     ![](../core/media/bts-tls-looping.gif "bts_tls_looping")  
<span data-ttu-id="d07fc-115">循环 functoid</span><span class="sxs-lookup"><span data-stu-id="d07fc-115">Looping functoid</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d07fc-116">该 functoid 将放置到显示的网格页上。</span><span class="sxs-lookup"><span data-stu-id="d07fc-116">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="d07fc-117">如果你想要将 functoid 放到不同的网格页面上，你需要首先显示其他网格该页。</span><span class="sxs-lookup"><span data-stu-id="d07fc-117">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
    > 
    >  <span data-ttu-id="d07fc-118">如果是构造使用多个 functoid 的映射，则需要考虑它们的左右位置关系。</span><span class="sxs-lookup"><span data-stu-id="d07fc-118">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="d07fc-119">Functoid 是按照从左到右的顺序执行的。</span><span class="sxs-lookup"><span data-stu-id="d07fc-119">Functoids are executed from left to right.</span></span> <span data-ttu-id="d07fc-120">一个 functoid 的输出只能输入到其右侧的另一个 functoid 中。</span><span class="sxs-lookup"><span data-stu-id="d07fc-120">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  
  
3.  <span data-ttu-id="d07fc-121">若要建立的输入的参数**循环**functoid，通过拖动记录创建输入的链接，或从源架构字段**循环**functoid，或拖动**循环** functoid 记录或源架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="d07fc-121">To establish the input parameters for the **Looping** functoid, create an input link by dragging a record or field from the source schema to the **Looping** functoid, or dragging the **Looping** functoid to a record or field in the source schema.</span></span> <span data-ttu-id="d07fc-122">根据需要包含的所有相关的输入的记录或字段以重复**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="d07fc-122">Repeat as required to include all of the relevant input records or fields to the **Looping** functoid.</span></span>  
  
4.  <span data-ttu-id="d07fc-123">若要使用输出参数从**循环**functoid，通过拖动创建一条输出链接**循环**functoid 记录或字段在目标架构中，或通过拖动的记录或中的字段目标架构**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="d07fc-123">To use the output parameter from the **Looping** functoid, create an output link by dragging the **Looping** functoid to a record or field in the destination schema, or by dragging a record or field in the destination schema to the **Looping** functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d07fc-124">与许多其他 functoid 的输出不同**循环**functoid 只能链接目标架构中的元素。</span><span class="sxs-lookup"><span data-stu-id="d07fc-124">Unlike many other functoids, the output of the **Looping** functoid can only be linked to an element of the destination schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d07fc-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d07fc-125">See Also</span></span>  
-  [<span data-ttu-id="d07fc-126">向地图添加高级的 Functoid</span><span class="sxs-lookup"><span data-stu-id="d07fc-126">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)   
-  <span data-ttu-id="d07fc-127">**循环 Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="d07fc-127">**Looping Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>