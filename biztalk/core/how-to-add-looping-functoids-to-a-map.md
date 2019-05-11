---
title: 如何添加循环 Functoid 映射到 |Microsoft Docs
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
ms.openlocfilehash: 2621287c35a60f57c4706e0901c7f786166d6cee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343269"
---
# <a name="how-to-add-looping-functoids-to-a-map"></a><span data-ttu-id="84a07-102">如何添加循环 Functoid 映射</span><span class="sxs-lookup"><span data-stu-id="84a07-102">How to Add Looping Functoids to a Map</span></span>

## <a name="overview"></a><span data-ttu-id="84a07-103">概述</span><span class="sxs-lookup"><span data-stu-id="84a07-103">Overview</span></span>
<span data-ttu-id="84a07-104">**循环**functoid 将多个记录或源架构中的字段合并到目标架构中的单个记录。</span><span class="sxs-lookup"><span data-stu-id="84a07-104">The **Looping** functoid combines multiple records or fields in the source schema into a single record in the destination schema.</span></span>  

 <span data-ttu-id="84a07-105">有关概念性信息**循环**functoid，请参阅[循环 Functoid](../core/looping-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="84a07-105">For conceptual information about the **Looping** functoid, see [Looping Functoid](../core/looping-functoid.md).</span></span>  

 <span data-ttu-id="84a07-106">某些情况下，某些 functoid 可能不会按预期方式与在映射中使用时**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="84a07-106">Under certain conditions, some functoids might not behave as expected when they are used in a map with a **Looping** functoid.</span></span> <span data-ttu-id="84a07-107">如果此类某个 functoid 符合以下条件，此操作未生成预期的结果：</span><span class="sxs-lookup"><span data-stu-id="84a07-107">If such a functoid meets the following conditions, it does not produce the expected results:</span></span>  

-   <span data-ttu-id="84a07-108">Functoid 具有多个输入的链接。</span><span class="sxs-lookup"><span data-stu-id="84a07-108">The functoid has more than one input link.</span></span>  

-   <span data-ttu-id="84a07-109">两个或多个 functoid 输入链接链接到输入记录的子字段**循环**functoid，这些子字段不是同级。</span><span class="sxs-lookup"><span data-stu-id="84a07-109">Two or more of the functoid input links are linked to child fields of the input records to the **Looping** functoid, where the child fields are not siblings.</span></span>  

-   <span data-ttu-id="84a07-110">Functoid 具有一个输出链接，链接到的输出记录的子字段链接**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="84a07-110">The functoid has an output link that is linked to a child field of the output record of the **Looping** functoid.</span></span>  

## <a name="add-the-looping-functoid-to-a-map-and-configure-it"></a><span data-ttu-id="84a07-111">向映射添加循环 functoid 并对其进行配置</span><span class="sxs-lookup"><span data-stu-id="84a07-111">Add the Looping functoid to a map and configure it</span></span>  

1. <span data-ttu-id="84a07-112">与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。</span><span class="sxs-lookup"><span data-stu-id="84a07-112">With the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox active, click the **Advanced Functoids** tab to select that category of functoids.</span></span>  

    <span data-ttu-id="84a07-113">将显示所选类别的高级 functoid 列表。</span><span class="sxs-lookup"><span data-stu-id="84a07-113">The list of advanced functoids in the chosen category appears.</span></span>  

2. <span data-ttu-id="84a07-114">拖动**循环**functoid 从工具箱拖至网格页上的适当位置。</span><span class="sxs-lookup"><span data-stu-id="84a07-114">Drag the **Looping** functoid from the Toolbox to the appropriate location on a grid page.</span></span>  

    <span data-ttu-id="84a07-115">![](../core/media/bts-tls-looping.gif "bts_tls_looping")</span><span class="sxs-lookup"><span data-stu-id="84a07-115">![](../core/media/bts-tls-looping.gif "bts_tls_looping")</span></span>  
   <span data-ttu-id="84a07-116">循环 functoid</span><span class="sxs-lookup"><span data-stu-id="84a07-116">Looping functoid</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="84a07-117">该 functoid 将放置上显示的网格页。</span><span class="sxs-lookup"><span data-stu-id="84a07-117">The functoid will be placed on the displayed grid page.</span></span> <span data-ttu-id="84a07-118">如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该其他网格页。</span><span class="sxs-lookup"><span data-stu-id="84a07-118">If you want to put the functoid onto a different grid page, you need to display that other grid page first.</span></span>  
   > 
   >  <span data-ttu-id="84a07-119">如果构造一起使用多个 functoid 的映射，您需要考虑它们的左右位置关系。</span><span class="sxs-lookup"><span data-stu-id="84a07-119">If you are constructing a map using more than one functoid together, you need to consider their relative left to right placement.</span></span> <span data-ttu-id="84a07-120">从左向右执行 Functoid。</span><span class="sxs-lookup"><span data-stu-id="84a07-120">Functoids are executed from left to right.</span></span> <span data-ttu-id="84a07-121">Functoid 的输出只能输入到其右侧的另一个 functoid。</span><span class="sxs-lookup"><span data-stu-id="84a07-121">The output of a functoid can only be input to another functoid that is farther to the right.</span></span>  

3. <span data-ttu-id="84a07-122">若要建立的输入的参数的**循环**functoid 创建输入的链接： 将一条记录或字段从源架构**循环**functoid，或拖动**循环** functoid 到记录或源架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="84a07-122">To establish the input parameters for the **Looping** functoid, create an input link by dragging a record or field from the source schema to the **Looping** functoid, or dragging the **Looping** functoid to a record or field in the source schema.</span></span> <span data-ttu-id="84a07-123">根据需要包含所有相关输入的记录或字段添加到重复**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="84a07-123">Repeat as required to include all of the relevant input records or fields to the **Looping** functoid.</span></span>  

4. <span data-ttu-id="84a07-124">若要使用的输出参数**循环**functoid，创建输出链接： 将**循环**到的记录或字段在目标架构中，或通过拖动的记录或字段中的 functoid目标架构**循环**functoid。</span><span class="sxs-lookup"><span data-stu-id="84a07-124">To use the output parameter from the **Looping** functoid, create an output link by dragging the **Looping** functoid to a record or field in the destination schema, or by dragging a record or field in the destination schema to the **Looping** functoid.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="84a07-125">与其他许多 functoid 的输出不同**循环**functoid 只能链接到目标架构的元素。</span><span class="sxs-lookup"><span data-stu-id="84a07-125">Unlike many other functoids, the output of the **Looping** functoid can only be linked to an element of the destination schema.</span></span>  

## <a name="see-also"></a><span data-ttu-id="84a07-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="84a07-126">See Also</span></span>  
- [<span data-ttu-id="84a07-127">向映射添加高级 Functoid</span><span class="sxs-lookup"><span data-stu-id="84a07-127">Adding Advanced Functoids to a Map</span></span>](../core/adding-advanced-functoids-to-a-map.md)   
- <span data-ttu-id="84a07-128">**循环 Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="84a07-128">**Looping Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
