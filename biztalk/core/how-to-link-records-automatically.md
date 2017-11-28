---
title: "如何自动将记录的链接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc2926c7-07c2-45d1-afde-d3f894f6b88d
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc5ab4e18a291321247655101d32d2bf7e35ff92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-link-records-automatically"></a><span data-ttu-id="d0b2d-102">如何自动将记录的链接</span><span class="sxs-lookup"><span data-stu-id="d0b2d-102">How to Link Records Automatically</span></span>
<span data-ttu-id="d0b2d-103">当您在源架构和目标架构的两个记录元素之间创建链接时，BizTalk 映射器会通过快捷菜单为您提供实时帮助。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-103">The BizTalk Mapper provides you with just-in-time assistance, through a shortcut menu, when you create links between two record elements of source and destination schemas.</span></span> <span data-ttu-id="d0b2d-104">本主题提供了有关如何使用快捷菜单执行链接操作的信息。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-104">This topic provides information about how to use the shortcut menu to perform the linking operations.</span></span>  
  
 <span data-ttu-id="d0b2d-105">可以通过以下方式自动创建记录的链接：</span><span class="sxs-lookup"><span data-stu-id="d0b2d-105">You can create record-to-record links automatically in the following ways:</span></span>  
  
-   <span data-ttu-id="d0b2d-106">**直接链接。**</span><span class="sxs-lookup"><span data-stu-id="d0b2d-106">**Direct Link.**</span></span> <span data-ttu-id="d0b2d-107">使用该技术，BizTalk 映射器会将来自源架构的记录链接到目标架构中所选定的记录。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-107">Using this technique, the BizTalk Mapper links the record from source schema to the selected record in the destination schema.</span></span>  
  
-   <span data-ttu-id="d0b2d-108">**按结构链接。**</span><span class="sxs-lookup"><span data-stu-id="d0b2d-108">**Link by Structure.**</span></span> <span data-ttu-id="d0b2d-109">使用此技术，BizTalk 映射程序会尝试匹配**记录**和**字段**内的节点**记录**正被链接根据这些结构节点**记录**节点，而不考虑这些结构中的相应节点的名称。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-109">Using this technique, the BizTalk Mapper attempts to match the **Record** and **Field** nodes within the **Record** nodes being linked according to the structures of those **Record** nodes, regardless of names of the corresponding nodes within those structures.</span></span>  
  
-   <span data-ttu-id="d0b2d-110">**按名称的链接。**</span><span class="sxs-lookup"><span data-stu-id="d0b2d-110">**Link By Name.**</span></span> <span data-ttu-id="d0b2d-111">使用此技术，BizTalk 映射程序会尝试匹配**记录**和**字段**内的节点**记录**正被链接的名称根据节点在相应节点，而不考虑其结构**记录**正被链接的节点。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-111">Using this technique, the BizTalk Mapper attempts to match the **Record** and **Field** nodes within the **Record** nodes being linked according to the names of the corresponding nodes, regardless of their structure, within the **Record** nodes being linked.</span></span>  
  
-   <span data-ttu-id="d0b2d-112">**大容量复制。**</span><span class="sxs-lookup"><span data-stu-id="d0b2d-112">**Mass Copy.**</span></span> <span data-ttu-id="d0b2d-113">**大容量复制**functoid 使你使用包含的架构的映射**任何**和**anyAttribute**元素。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-113">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="d0b2d-114">在 BizTalk 映射程序中可用的 functoid 有关的信息，请参阅[创建更复杂的映射到使用 Functoid](../core/using-functoids-to-create-more-complex-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-114">For information about the functoids available in BizTalk Mapper, see [Using Functoids to Create More Complex Mappings](../core/using-functoids-to-create-more-complex-mappings.md).</span></span>  
  
 <span data-ttu-id="d0b2d-115">要使用快捷菜单，连接必须来自子层次结构母节点，并且必须终止于另一个子层次结构母节点。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-115">To use the shortcut menu, a link must originate from a sub-hierarchy parent node and must end on another sub-hierarchy parent node.</span></span> <span data-ttu-id="d0b2d-116">快捷菜单可帮助确定应当在两个架构节点之间创建哪种类型的链接。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-116">The shortcut menu assists in what type of links should be created between the two schema nodes.</span></span> <span data-ttu-id="d0b2d-117">以下是在快捷菜单上的可用选项的列表。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-117">The following is a list of options available on the shortcut menu.</span></span>  
  
|<span data-ttu-id="d0b2d-118">映射来源</span><span class="sxs-lookup"><span data-stu-id="d0b2d-118">Map from</span></span>|<span data-ttu-id="d0b2d-119">映射到</span><span class="sxs-lookup"><span data-stu-id="d0b2d-119">Map to</span></span>|<span data-ttu-id="d0b2d-120">链接行为</span><span class="sxs-lookup"><span data-stu-id="d0b2d-120">Link Behavior</span></span>|  
|--------------|------------|-------------------|  
|<span data-ttu-id="d0b2d-121">字段</span><span class="sxs-lookup"><span data-stu-id="d0b2d-121">Field</span></span>|<span data-ttu-id="d0b2d-122">字段</span><span class="sxs-lookup"><span data-stu-id="d0b2d-122">Field</span></span>|<span data-ttu-id="d0b2d-123">直接链接</span><span class="sxs-lookup"><span data-stu-id="d0b2d-123">Direct link</span></span>|  
|<span data-ttu-id="d0b2d-124">录制</span><span class="sxs-lookup"><span data-stu-id="d0b2d-124">Record</span></span>|<span data-ttu-id="d0b2d-125">字段</span><span class="sxs-lookup"><span data-stu-id="d0b2d-125">Field</span></span>|<span data-ttu-id="d0b2d-126">直接链接</span><span class="sxs-lookup"><span data-stu-id="d0b2d-126">Direct link</span></span>|  
|<span data-ttu-id="d0b2d-127">字段</span><span class="sxs-lookup"><span data-stu-id="d0b2d-127">Field</span></span>|<span data-ttu-id="d0b2d-128">录制</span><span class="sxs-lookup"><span data-stu-id="d0b2d-128">Record</span></span>|<span data-ttu-id="d0b2d-129">直接链接</span><span class="sxs-lookup"><span data-stu-id="d0b2d-129">Direct link</span></span>|  
|<span data-ttu-id="d0b2d-130">录制</span><span class="sxs-lookup"><span data-stu-id="d0b2d-130">Record</span></span>|<span data-ttu-id="d0b2d-131">录制</span><span class="sxs-lookup"><span data-stu-id="d0b2d-131">Record</span></span>|<span data-ttu-id="d0b2d-132">此时将出现快捷菜单</span><span class="sxs-lookup"><span data-stu-id="d0b2d-132">Shortcut menu appears</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="d0b2d-133">先决条件</span><span class="sxs-lookup"><span data-stu-id="d0b2d-133">Prerequisites</span></span>  
 <span data-ttu-id="d0b2d-134">这些操作需要 BizTalk 映射器正在运行。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-134">These operations require that the BizTalk Mapper is running.</span></span>  
  
### <a name="to-link-the-record-elements-directly"></a><span data-ttu-id="d0b2d-135">若要直接链接记录元素，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0b2d-135">To link the record elements directly</span></span>  
  
1.  <span data-ttu-id="d0b2d-136">通过鼠标拖动源架构中的子层次结构母节点，然后将其放到目标架构中的子层次结构母节点。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-136">Drag the mouse from a sub-hierarchy parent node in source schema, and then drop it to the sub-hierarchy parent node in the target schema.</span></span>  
  
2.  <span data-ttu-id="d0b2d-137">在快捷菜单上，单击**直接链接**。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-137">On the shortcut menu, click **Direct Link**.</span></span> <span data-ttu-id="d0b2d-138">下表显示了从所选的源节点到目标节点中出现的直接链接。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-138">The following figure shows a direct link appearing from the selected source node to the target node.</span></span>  
  
     <span data-ttu-id="d0b2d-139">![从源节点指向目标节点的直接链接](../core/media/linkrecordelements-directly.gif "Linkrecordelements_directly")</span><span class="sxs-lookup"><span data-stu-id="d0b2d-139">![Direct link from source node to target node](../core/media/linkrecordelements-directly.gif "Linkrecordelements_directly")</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d0b2d-140">您可以将源架构中子层次结构母节点中的直接链接，置于目标架构中的非子层次结构母节点中。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-140">You can place a direct link from a sub-hierarchy parent node in source schema to a non-sub-hierarchy parent node in target schema.</span></span> <span data-ttu-id="d0b2d-141">下表显示了作为源架构中母节点的“Root”到作为目标架构中子“Root”的“Record1”的直接链接。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-141">The following figure shows a direct link from “Root” that is a parent node in source schema to “Record1” that is a child to “Root” in target schema.</span></span>  
  
     <span data-ttu-id="d0b2d-142">![将记录元素直接链接](../core/media/linkrecordelements-directly2.gif "Linkrecordelements_directly2")</span><span class="sxs-lookup"><span data-stu-id="d0b2d-142">![Linking record elements directly](../core/media/linkrecordelements-directly2.gif "Linkrecordelements_directly2")</span></span>  
  
### <a name="to-link-the-record-elements-by-structure"></a><span data-ttu-id="d0b2d-143">若要通过结构链接记录元素，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0b2d-143">To link the record elements by structure</span></span>  
  
1.  <span data-ttu-id="d0b2d-144">通过鼠标拖动源架构中的子层次结构母节点，然后将其放到目标架构中的子层次结构母节点。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-144">Drag the mouse from a sub-hierarchy parent node in source schema, and then drop it to the sub-hierarchy parent node in the target schema.</span></span>  
  
2.  <span data-ttu-id="d0b2d-145">在快捷菜单上，单击**按结构链接**。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-145">On the shortcut menu, click **Link by Structure**.</span></span> <span data-ttu-id="d0b2d-146">BizTalk 映射程序匹配**记录**和**字段**内的节点**记录**节点正被链接的那些结构根据**记录**节点，而不考虑这些结构中的相应节点的名称。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-146">The BizTalk Mapper matches the **Record** and **Field** nodes within the **Record** nodes being linked according to the structure of those **Record** nodes, regardless of names of the corresponding nodes within those structures.</span></span>  
  
     <span data-ttu-id="d0b2d-147">![链接记录元素) (&#95; 通过结构](../core/media/linkrecordelements-bystructure.gif "Linkrecordelements_bystructure")</span><span class="sxs-lookup"><span data-stu-id="d0b2d-147">![Link record elements&#95;by structure](../core/media/linkrecordelements-bystructure.gif "Linkrecordelements_bystructure")</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d0b2d-148">当您尝试通过结构将源架构中的子层次结构母节点链接到目标架构中的非子层次结构母节点，BizTalk 映射器会将源母节点的子项分别映射到目标母节点的子项。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-148">When you try to link a sub-hierarchy parent node in source schema to a non-sub-hierarchy parent node in target schema, by structure, the BizTalk Mapper maps the children of the source parent node to the children of the target parent node, respectively.</span></span> <span data-ttu-id="d0b2d-149">下图显示了通过结构进行链接。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-149">The following figure shows the linking by structure.</span></span>  
  
     <span data-ttu-id="d0b2d-150">![将记录的元素链接结构](../core/media/linkrecordelements-bystructure2.gif "Linkrecordelements_bystructure2")</span><span class="sxs-lookup"><span data-stu-id="d0b2d-150">![Linking record elements by structure](../core/media/linkrecordelements-bystructure2.gif "Linkrecordelements_bystructure2")</span></span>  
  
### <a name="to-link-the-record-elements-by-name"></a><span data-ttu-id="d0b2d-151">若要通过名称链接记录元素，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0b2d-151">To link the record elements by name</span></span>  
  
1.  <span data-ttu-id="d0b2d-152">通过鼠标拖动源架构中的子层次结构母节点，然后将其放到目标架构中的子层次结构母节点。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-152">Drag the mouse from a sub-hierarchy parent node in source schema, and then drop it to the sub-hierarchy parent node in the target schema.</span></span>  
  
2.  <span data-ttu-id="d0b2d-153">在快捷菜单上，单击**按名称链接**。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-153">On the shortcut menu, click **Link by Name**.</span></span> <span data-ttu-id="d0b2d-154">BizTalk 映射程序尝试匹配**记录**和**字段**内的节点**记录**正被链接根据相应的节点，而不考虑的名称的节点其结构中**记录**要链接的节点。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-154">The BizTalk Mapper attempts to match the **Record** and **Field** nodes within the **Record** nodes being linked according to the names of the corresponding nodes, regardless of their structure, within the **Record** nodes to which you are linking.</span></span>  
  
     <span data-ttu-id="d0b2d-155">![按名称链接记录元素](../core/media/linkrecordelements-byname.gif "Linkrecordelements_byname")</span><span class="sxs-lookup"><span data-stu-id="d0b2d-155">![Linking record elements by name](../core/media/linkrecordelements-byname.gif "Linkrecordelements_byname")</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="d0b2d-156">您可以将源架构中子层次结构母节点中的直接链接，链接到目标架构中的非子层次结构母节点。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-156">You can link a sub-hierarchy parent node in source schema to a non-sub-hierarchy parent node in target schema, by name.</span></span> <span data-ttu-id="d0b2d-157">BizTalk 映射器会匹配源节点的子项名称和目标节点的子项名称</span><span class="sxs-lookup"><span data-stu-id="d0b2d-157">The BizTalk Mapper matches the names of the children of source node with the children of target node.</span></span> <span data-ttu-id="d0b2d-158">如果它找到了完全相同的子项，则会在各自的子项之间建立链接。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-158">If it finds identical children, then a link is established between the respective children.</span></span> <span data-ttu-id="d0b2d-159">下图说明了这一概念。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-159">The following figure explains this concept.</span></span>  
  
## <a name="to-link-using-a-mass-copy-functoid"></a><span data-ttu-id="d0b2d-160">要使用一个批量复制 functoid 链接</span><span class="sxs-lookup"><span data-stu-id="d0b2d-160">To link using a mass copy functoid</span></span>  
 <span data-ttu-id="d0b2d-161">**大容量复制**functoid 使你使用包含的架构的映射**任何**和**anyAttribute**元素。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-161">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="d0b2d-162">实际上，这些元素是 XML 架构定义语言为匹配未知结构或属性而提供的通配符。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-162">These elements are, in essence, wildcards provided in the XML Schema definition language to match unknown structures or attributes.</span></span>  
  
 <span data-ttu-id="d0b2d-163">除了处理具有未知的结构、 数据**大容量复制**functoid，可简化架构开发： 仅将处理的架构部分需要在详细信息中指定。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-163">In addition to handling data with unknown structure, the **Mass Copy** functoid enables you to simplify schema development: only the portions of a schema that will be processed need to be specified in detail.</span></span>  
  
 <span data-ttu-id="d0b2d-164">![将记录的元素链接通过大容量复制 functoid](../core/media/linkrecordelements-masscopyfunctoid.gif "Linkrecordelements_MassCopyfunctoid")</span><span class="sxs-lookup"><span data-stu-id="d0b2d-164">![Linking record elements by Mass Copy functoid](../core/media/linkrecordelements-masscopyfunctoid.gif "Linkrecordelements_MassCopyfunctoid")</span></span>  
  
 <span data-ttu-id="d0b2d-165">有关详细信息**大容量复制**functoid，请参阅[大容量复制 Functoid](../core/mass-copy-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="d0b2d-165">For more information about the **Mass Copy** functoid, see [Mass Copy Functoid](../core/mass-copy-functoid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0b2d-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0b2d-166">See Also</span></span>  
 <span data-ttu-id="d0b2d-167">[使用链接以指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="d0b2d-167">[Using Links to Specify Record and Field Mappings](../core/using-links-to-specify-record-and-field-mappings.md) </span></span>  
 [<span data-ttu-id="d0b2d-168">如何在向地图添加大容量复制 Functoid</span><span class="sxs-lookup"><span data-stu-id="d0b2d-168">How to Add Mass Copy Functoids to a Map</span></span>](../core/how-to-add-mass-copy-functoids-to-a-map.md)