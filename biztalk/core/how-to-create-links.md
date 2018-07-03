---
title: 如何创建链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 670b831f-be03-4612-93d5-a894f7bb3c11
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7315b4cd568c6107dcab25cf1fe471428b58da8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014742"
---
# <a name="how-to-create-links"></a><span data-ttu-id="62b82-102">如何创建链接</span><span class="sxs-lookup"><span data-stu-id="62b82-102">How to Create Links</span></span>
<span data-ttu-id="62b82-103">创建从链接**记录**或**字段**节点在源架构中的**记录**或**字段**目标架构中的节点是最基本创建映射过程中的活动。</span><span class="sxs-lookup"><span data-stu-id="62b82-103">Creating a link from a **Record** or **Field** node in a source schema to a **Record** or **Field** node in a destination schema is the most basic activity in creating maps.</span></span> <span data-ttu-id="62b82-104">本主题为此活动的不同用法（包括创建指向和来自 functoid 的链接）提供了分步说明。</span><span class="sxs-lookup"><span data-stu-id="62b82-104">This topic provides step-by-step instructions for several variations of this activity, including creating links to and from functoids.</span></span> <span data-ttu-id="62b82-105">有关使用 functoid 的其他信息，请参阅[使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="62b82-105">For additional information about working with functoids, see [Using Functoids to Create More Complex Mappings](../core/using-functoids-to-create-more-complex-mappings.md).</span></span>  
  
 <span data-ttu-id="62b82-106">本主题中的说明假定您已经打开了一个 BizTalk 映射，并且已为该映射选择了源架构和目标架构。</span><span class="sxs-lookup"><span data-stu-id="62b82-106">The instructions in this topic assume you already have a BizTalk map open, and that you have chosen source and destination schemas for the map.</span></span> <span data-ttu-id="62b82-107">有关打开映射和选择的映射架构的详细信息，请参阅[管理映射中的项目](../core/managing-maps-within-projects.md)。</span><span class="sxs-lookup"><span data-stu-id="62b82-107">For more information about opening maps and choosing schemas for the map, see [Managing Maps Within Projects](../core/managing-maps-within-projects.md).</span></span>  
  
### <a name="to-create-links-between-field-and-record-nodes"></a><span data-ttu-id="62b82-108">创建“字段”与“记录”节点之间的链接</span><span class="sxs-lookup"><span data-stu-id="62b82-108">To create links between Field and Record nodes</span></span>  
  
1. <span data-ttu-id="62b82-109">在 BizTalk 映射器中拖动**字段**或**记录**到源架构树中的节点**字段**或**记录**目标架构中的节点树。</span><span class="sxs-lookup"><span data-stu-id="62b82-109">In BizTalk Mapper, drag a **Field** or **Record** node from the source schema tree to a **Field** or **Record** node in the destination schema tree.</span></span>  
  
    <span data-ttu-id="62b82-110">**-或者-**</span><span class="sxs-lookup"><span data-stu-id="62b82-110">**- Or -**</span></span>  
  
2. <span data-ttu-id="62b82-111">在 BizTalk 映射器中拖动**字段**或**记录**到目标架构树中的节点**字段**或**记录**源架构中的节点树。</span><span class="sxs-lookup"><span data-stu-id="62b82-111">In BizTalk Mapper, drag a **Field** or **Record** node from the destination schema tree to a **Field** or **Record** node in the source schema tree.</span></span>  
  
   <span data-ttu-id="62b82-112">创建链接时，应注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="62b82-112">There are several things to consider when creating links:</span></span>  
  
-   <span data-ttu-id="62b82-113">数据类型**字段**或**记录**源架构树中的节点应与匹配的数据类型**字段**或者**记录**它的节点链接的目标架构树中。</span><span class="sxs-lookup"><span data-stu-id="62b82-113">The data type of a **Field** or **Record** node in the source schema tree should match the data type of a **Field** or **Record** node to which it is linked in the destination schema tree.</span></span>  
  
-   <span data-ttu-id="62b82-114">如果**字段**或**记录**源架构中的节点是可选的和特定的源实例消息不包含相应元素或属性，BizTalk 映射器不会创建相应元素或属性在目标实例消息中，即使**字段**或**记录**节点具有相互映射中的直接链接。</span><span class="sxs-lookup"><span data-stu-id="62b82-114">If a **Field** or **Record** node in the source schema is optional, and a particular source instance message does not contain the corresponding element or attribute, BizTalk Mapper will not create a corresponding element or attribute in the destination instance message, even if the **Field** or **Record** nodes have a direct link between them in the map.</span></span>  
  
-   <span data-ttu-id="62b82-115">不能链接到**字段**或**记录**具有与之关联的常数值的目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="62b82-115">You cannot link to a **Field** or **Record** node in the destination schema that has a constant value associated with it.</span></span> <span data-ttu-id="62b82-116">但是，你可以链接到所需**字段**或**记录**有与之关联的默认值的目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="62b82-116">On the other hand, you can link to a required **Field** or **Record** node in the destination schema that has a default value associated with it.</span></span> <span data-ttu-id="62b82-117">但是请注意，在测试映射时将使用该默认值。</span><span class="sxs-lookup"><span data-stu-id="62b82-117">Note, however, that when you test the map, the default value will be used.</span></span>  
  
-   <span data-ttu-id="62b82-118">不能创建一个链接，面向或源自**任何元素**，**任何属性**，**序列组**，或者**选择组**节点。</span><span class="sxs-lookup"><span data-stu-id="62b82-118">You cannot create a link to or from the **Any Element**, **Any Attribute**, **Sequence Group**, or **Choice Group** nodes.</span></span> <span data-ttu-id="62b82-119">有关这些类型的节点的详细信息，请参阅以下主题，请参阅[Any 元素节点](../core/any-element-nodes.md)，[序列组节点](../core/sequence-group-nodes.md)或[所选组节点](../core/choice-group-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="62b82-119">For more information about these types of nodes, see the following topics, see [Any Element Nodes](../core/any-element-nodes.md), [Sequence Group Nodes](../core/sequence-group-nodes.md) or [Choice Group Nodes](../core/choice-group-nodes.md).</span></span>  
  
-   <span data-ttu-id="62b82-120">可能需要展开架构树以查看要映射的字段。</span><span class="sxs-lookup"><span data-stu-id="62b82-120">You may need to expand the schema trees to view the fields that you want to map.</span></span> <span data-ttu-id="62b82-121">有关详细信息，请参阅[如何展开和折叠架构树](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)。</span><span class="sxs-lookup"><span data-stu-id="62b82-121">For more information, see [How to Expand and Collapse the Schema Trees](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx).</span></span>  
  
#### <a name="to-create-links-between-record-or-field-nodes-and-functoids"></a><span data-ttu-id="62b82-122">创建“记录”或“字段”节点与 functoid 之间的链接</span><span class="sxs-lookup"><span data-stu-id="62b82-122">To create links between Record or Field nodes and functoids</span></span>  
  
1.  <span data-ttu-id="62b82-123">在 BizTalk 映射器中拖动**记录**或**字段**到网格页的 functoid 将源或目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="62b82-123">In BizTalk Mapper, drag a **Record** or **Field** node from the source or destination schema to a functoid in a grid page.</span></span>  
  
     <span data-ttu-id="62b82-124">**-或者-**</span><span class="sxs-lookup"><span data-stu-id="62b82-124">**- Or -**</span></span>  
  
2.  <span data-ttu-id="62b82-125">将提取 functoid 拖至网格页中**记录**或**字段**源或目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="62b82-125">Drag the functoid from a grid page to a **Record** or **Field** node in the source or destination schema.</span></span>  
  
     <span data-ttu-id="62b82-126">当创建之间的链接**记录**或**字段**源架构和 functoid 中的节点，创建该 functoid 的输入。</span><span class="sxs-lookup"><span data-stu-id="62b82-126">When you create a link between a **Record** or **Field** node in the source schema and a functoid, you are creating an input to that functoid.</span></span> <span data-ttu-id="62b82-127">当创建之间的链接**记录**或**字段**目标架构和 functoid 中的节点，您要从该 functoid 创建输出。</span><span class="sxs-lookup"><span data-stu-id="62b82-127">When you create a link between a **Record** or **Field** node in the destination schema and a functoid, you are creating an output from that functoid.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="62b82-128">您不能 functoid 之间的链接和一个**Any 元素**节点或**任何属性**节点。</span><span class="sxs-lookup"><span data-stu-id="62b82-128">You cannot link between a functoid and an **Any Element** node or an **Any Attribute** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62b82-129">必须首先添加一个 functoid 到网格页后，才能添加之间的链接**记录**或**字段**节点与该 functoid。</span><span class="sxs-lookup"><span data-stu-id="62b82-129">You must first add a functoid to a grid page before you can add a link between a **Record** or **Field** node and that functoid.</span></span> <span data-ttu-id="62b82-130">有关将 functoid 添加到网格页的详细信息，请参阅[如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="62b82-130">For more information about adding functoids to a grid page, see [How to Add Basic Functoids to a Map](../core/how-to-add-basic-functoids-to-a-map.md).</span></span> <span data-ttu-id="62b82-131">另请参阅[向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)。</span><span class="sxs-lookup"><span data-stu-id="62b82-131">Also see [Adding Advanced Functoids to a Map](../core/adding-advanced-functoids-to-a-map.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62b82-132">不能链接到**字段**具有与之关联的常数值的目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="62b82-132">You cannot link to a **Field** node in the destination schema that has a constant value associated with it.</span></span> <span data-ttu-id="62b82-133">但是，你可以链接到所需**字段**有与之关联的默认值的目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="62b82-133">On the other hand, you can link to a required **Field** node in the destination schema that has a default value associated with it.</span></span> <span data-ttu-id="62b82-134">但是请注意，在测试映射时将使用该默认值。</span><span class="sxs-lookup"><span data-stu-id="62b82-134">Note, however, that when you test the map, the default value will be used.</span></span>  
  
#### <a name="to-create-links-between-functoids"></a><span data-ttu-id="62b82-135">创建 functoid 之间的链接</span><span class="sxs-lookup"><span data-stu-id="62b82-135">To create links between functoids</span></span>  
  
-   <span data-ttu-id="62b82-136">在 BizTalk 映射器中，将一个 functoid 拖至网格页中的另一个 functoid。</span><span class="sxs-lookup"><span data-stu-id="62b82-136">In BizTalk Mapper, drag one functoid to another functoid in a grid page.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62b82-137">链接在网格页中是按照从左到右的顺序进行处理的。</span><span class="sxs-lookup"><span data-stu-id="62b82-137">Links are processed left-to-right in a grid page.</span></span> <span data-ttu-id="62b82-138">不能创建从一个 functoid 到直接位于其上方或下方的另一个 functoid 的链接。</span><span class="sxs-lookup"><span data-stu-id="62b82-138">You cannot make a link from one functoid to another functoid directly above or below it.</span></span> <span data-ttu-id="62b82-139">functoid 之间的链接被解释为链接表示从左侧的 functoid 输出并输入到右侧的 functoid。</span><span class="sxs-lookup"><span data-stu-id="62b82-139">Links between functoids are interpreted such that a link signifies output from the functoid to the left and input to the functoid to the right.</span></span>  
  
### <a name="to-change-the-endpoint-of-a-link"></a><span data-ttu-id="62b82-140">更改链接的终结点</span><span class="sxs-lookup"><span data-stu-id="62b82-140">To change the endpoint of a link</span></span>  
 <span data-ttu-id="62b82-141">在映射中，您可以将链接的终结点拖放到另一个节点或 functoid 上。</span><span class="sxs-lookup"><span data-stu-id="62b82-141">In a map, you can drag an endpoint of a link and drop it over another node or functoid.</span></span>  
  
 <span data-ttu-id="62b82-142">更改链接的终结点：</span><span class="sxs-lookup"><span data-stu-id="62b82-142">To change the endpoint of a link:</span></span>  
  
1. <span data-ttu-id="62b82-143">单击您要为其更改源或目标节点/functoid 的链接。</span><span class="sxs-lookup"><span data-stu-id="62b82-143">Click the link for which you want to change the source or destination node/functoid.</span></span> <span data-ttu-id="62b82-144">该链接的终结点变为粗体。</span><span class="sxs-lookup"><span data-stu-id="62b82-144">The endpoints of the link become bold.</span></span>  
  
2. <span data-ttu-id="62b82-145">在任何粗体终结点上按下鼠标键并将该链接拖动到所需的节点/functoid。</span><span class="sxs-lookup"><span data-stu-id="62b82-145">Hold down the mouse key on any of the bold endpoints and drag the link to the desired node/functoid.</span></span> <span data-ttu-id="62b82-146">这会将链接从以前的节点/functoid 更改为新节点/functoid。</span><span class="sxs-lookup"><span data-stu-id="62b82-146">This changes the linking from the previous node/functoid to the new node/functoid.</span></span>  
  
   <span data-ttu-id="62b82-147">但是，对于无效链接，您无法执行此操作，如：</span><span class="sxs-lookup"><span data-stu-id="62b82-147">However, you cannot perform this operation for invalid linking, such as:</span></span>  
  
-   <span data-ttu-id="62b82-148">添加链接作为日期/时间 functoid 的输入链接。</span><span class="sxs-lookup"><span data-stu-id="62b82-148">Adding a link as an input to Date/Time functoids.</span></span> <span data-ttu-id="62b82-149">日期/时间 functoid 不需要任何输入链接。</span><span class="sxs-lookup"><span data-stu-id="62b82-149">The Date/Time functoids do not need any input links.</span></span>  
  
-   <span data-ttu-id="62b82-150">复制中间 functoid 中的链接。</span><span class="sxs-lookup"><span data-stu-id="62b82-150">Duplicating links from intermediate functoids.</span></span>  
  
     <span data-ttu-id="62b82-151">如果您将 Node1 链接到 Node2，并且还将 Node1 链接到 Node3，则不能拖动 Node2 上链接的终结点以进行更改并链接到 Node3。</span><span class="sxs-lookup"><span data-stu-id="62b82-151">If you link Node1 to Node2, and also from Node1 to Node3, you cannot drag the endpoint of the link at Node2 to change and link to Node3.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62b82-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="62b82-152">See Also</span></span>  
 [<span data-ttu-id="62b82-153">使用链接指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="62b82-153">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)