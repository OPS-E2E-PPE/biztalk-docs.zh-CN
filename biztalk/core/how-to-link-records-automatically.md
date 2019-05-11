---
title: 如何自动链接记录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc2926c7-07c2-45d1-afde-d3f894f6b88d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 489a826bb9251a3fcbfe6152363e06950cf9c1f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336953"
---
# <a name="how-to-link-records-automatically"></a><span data-ttu-id="adcd1-102">如何自动链接记录</span><span class="sxs-lookup"><span data-stu-id="adcd1-102">How to Link Records Automatically</span></span>
<span data-ttu-id="adcd1-103">BizTalk 映射器时，提供在实时协助下，通过快捷菜单，创建两个记录元素的源和目标架构之间的链接。</span><span class="sxs-lookup"><span data-stu-id="adcd1-103">The BizTalk Mapper provides you with just-in-time assistance, through a shortcut menu, when you create links between two record elements of source and destination schemas.</span></span> <span data-ttu-id="adcd1-104">本主题提供有关如何使用快捷菜单执行链接操作的信息。</span><span class="sxs-lookup"><span data-stu-id="adcd1-104">This topic provides information about how to use the shortcut menu to perform the linking operations.</span></span>  
  
 <span data-ttu-id="adcd1-105">可以按以下方式自动创建记录到记录的链接：</span><span class="sxs-lookup"><span data-stu-id="adcd1-105">You can create record-to-record links automatically in the following ways:</span></span>  
  
- <span data-ttu-id="adcd1-106">**直接链接。**</span><span class="sxs-lookup"><span data-stu-id="adcd1-106">**Direct Link.**</span></span> <span data-ttu-id="adcd1-107">使用此方法，BizTalk 映射器链接到目标架构中所选记录的源架构中的记录。</span><span class="sxs-lookup"><span data-stu-id="adcd1-107">Using this technique, the BizTalk Mapper links the record from source schema to the selected record in the destination schema.</span></span>  
  
- <span data-ttu-id="adcd1-108">**按结构链接。**</span><span class="sxs-lookup"><span data-stu-id="adcd1-108">**Link by Structure.**</span></span> <span data-ttu-id="adcd1-109">使用此方法，BizTalk 映射器尝试匹配**记录**并**字段**中的节点**记录**这些结构根据要链接的节点**记录**节点，而不管这些结构中的相应节点的名称。</span><span class="sxs-lookup"><span data-stu-id="adcd1-109">Using this technique, the BizTalk Mapper attempts to match the **Record** and **Field** nodes within the **Record** nodes being linked according to the structures of those **Record** nodes, regardless of names of the corresponding nodes within those structures.</span></span>  
  
- <span data-ttu-id="adcd1-110">**按名称进行链接。**</span><span class="sxs-lookup"><span data-stu-id="adcd1-110">**Link By Name.**</span></span> <span data-ttu-id="adcd1-111">使用此方法，BizTalk 映射器尝试匹配**记录**并**字段**中的节点**记录**的名称根据要链接的节点在相应节点，而不管其结构**记录**要链接的节点。</span><span class="sxs-lookup"><span data-stu-id="adcd1-111">Using this technique, the BizTalk Mapper attempts to match the **Record** and **Field** nodes within the **Record** nodes being linked according to the names of the corresponding nodes, regardless of their structure, within the **Record** nodes being linked.</span></span>  
  
- <span data-ttu-id="adcd1-112">**大容量复制。**</span><span class="sxs-lookup"><span data-stu-id="adcd1-112">**Mass Copy.**</span></span> <span data-ttu-id="adcd1-113">**批量复制**functoid，映射可使用包含的架构**任何**并**anyAttribute**元素。</span><span class="sxs-lookup"><span data-stu-id="adcd1-113">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="adcd1-114">有关 BizTalk 映射器中可用 functoid 的信息，请参阅[使用 Functoid 创建更复杂的映射](../core/using-functoids-to-create-more-complex-mappings.md)。</span><span class="sxs-lookup"><span data-stu-id="adcd1-114">For information about the functoids available in BizTalk Mapper, see [Using Functoids to Create More Complex Mappings](../core/using-functoids-to-create-more-complex-mappings.md).</span></span>  
  
  <span data-ttu-id="adcd1-115">若要使用的快捷菜单，链接必须来自子层次结构父节点和必须终止于另一个子层次结构父节点。</span><span class="sxs-lookup"><span data-stu-id="adcd1-115">To use the shortcut menu, a link must originate from a sub-hierarchy parent node and must end on another sub-hierarchy parent node.</span></span> <span data-ttu-id="adcd1-116">应在两个架构节点之间创建哪种类型的链接的快捷菜单帮助。</span><span class="sxs-lookup"><span data-stu-id="adcd1-116">The shortcut menu assists in what type of links should be created between the two schema nodes.</span></span> <span data-ttu-id="adcd1-117">下面是在快捷菜单上的可用选项的列表。</span><span class="sxs-lookup"><span data-stu-id="adcd1-117">The following is a list of options available on the shortcut menu.</span></span>  
  
|<span data-ttu-id="adcd1-118">从映射</span><span class="sxs-lookup"><span data-stu-id="adcd1-118">Map from</span></span>|<span data-ttu-id="adcd1-119">将映射到</span><span class="sxs-lookup"><span data-stu-id="adcd1-119">Map to</span></span>|<span data-ttu-id="adcd1-120">链接行为</span><span class="sxs-lookup"><span data-stu-id="adcd1-120">Link Behavior</span></span>|  
|--------------|------------|-------------------|  
|<span data-ttu-id="adcd1-121">字段</span><span class="sxs-lookup"><span data-stu-id="adcd1-121">Field</span></span>|<span data-ttu-id="adcd1-122">字段</span><span class="sxs-lookup"><span data-stu-id="adcd1-122">Field</span></span>|<span data-ttu-id="adcd1-123">直接链接</span><span class="sxs-lookup"><span data-stu-id="adcd1-123">Direct link</span></span>|  
|<span data-ttu-id="adcd1-124">录制</span><span class="sxs-lookup"><span data-stu-id="adcd1-124">Record</span></span>|<span data-ttu-id="adcd1-125">字段</span><span class="sxs-lookup"><span data-stu-id="adcd1-125">Field</span></span>|<span data-ttu-id="adcd1-126">直接链接</span><span class="sxs-lookup"><span data-stu-id="adcd1-126">Direct link</span></span>|  
|<span data-ttu-id="adcd1-127">字段</span><span class="sxs-lookup"><span data-stu-id="adcd1-127">Field</span></span>|<span data-ttu-id="adcd1-128">录制</span><span class="sxs-lookup"><span data-stu-id="adcd1-128">Record</span></span>|<span data-ttu-id="adcd1-129">直接链接</span><span class="sxs-lookup"><span data-stu-id="adcd1-129">Direct link</span></span>|  
|<span data-ttu-id="adcd1-130">录制</span><span class="sxs-lookup"><span data-stu-id="adcd1-130">Record</span></span>|<span data-ttu-id="adcd1-131">录制</span><span class="sxs-lookup"><span data-stu-id="adcd1-131">Record</span></span>|<span data-ttu-id="adcd1-132">将出现快捷菜单</span><span class="sxs-lookup"><span data-stu-id="adcd1-132">Shortcut menu appears</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="adcd1-133">先决条件</span><span class="sxs-lookup"><span data-stu-id="adcd1-133">Prerequisites</span></span>  
 <span data-ttu-id="adcd1-134">这些操作需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="adcd1-134">These operations require that the BizTalk Mapper is running.</span></span>  
  
### <a name="to-link-the-record-elements-directly"></a><span data-ttu-id="adcd1-135">若要直接链接记录元素</span><span class="sxs-lookup"><span data-stu-id="adcd1-135">To link the record elements directly</span></span>  
  
1.  <span data-ttu-id="adcd1-136">鼠标拖动源架构中的子层次结构母节点并将它放到目标架构中的子层次结构父节点。</span><span class="sxs-lookup"><span data-stu-id="adcd1-136">Drag the mouse from a sub-hierarchy parent node in source schema, and then drop it to the sub-hierarchy parent node in the target schema.</span></span>  
  
2.  <span data-ttu-id="adcd1-137">在快捷菜单上，单击**直接链接**。</span><span class="sxs-lookup"><span data-stu-id="adcd1-137">On the shortcut menu, click **Direct Link**.</span></span> <span data-ttu-id="adcd1-138">下图显示了使其不显示从所选的源节点到目标节点的直接链接。</span><span class="sxs-lookup"><span data-stu-id="adcd1-138">The following figure shows a direct link appearing from the selected source node to the target node.</span></span>  
  
     <span data-ttu-id="adcd1-139">![从源节点到目标节点的直接链接](../core/media/linkrecordelements-directly.gif "Linkrecordelements_directly")</span><span class="sxs-lookup"><span data-stu-id="adcd1-139">![Direct link from source node to target node](../core/media/linkrecordelements-directly.gif "Linkrecordelements_directly")</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="adcd1-140">您可以放置子层次结构父节点的直接链接到目标架构中的非-子层次结构母节点的源架构中。</span><span class="sxs-lookup"><span data-stu-id="adcd1-140">You can place a direct link from a sub-hierarchy parent node in source schema to a non-sub-hierarchy parent node in target schema.</span></span> <span data-ttu-id="adcd1-141">下图显示了"Root"中的直接链接为父节点到"Record1"的源架构中的是"Root"目标架构中的子级。</span><span class="sxs-lookup"><span data-stu-id="adcd1-141">The following figure shows a direct link from “Root” that is a parent node in source schema to “Record1” that is a child to “Root” in target schema.</span></span>  
  
     <span data-ttu-id="adcd1-142">![直接链接记录元素](../core/media/linkrecordelements-directly2.gif "Linkrecordelements_directly2")</span><span class="sxs-lookup"><span data-stu-id="adcd1-142">![Linking record elements directly](../core/media/linkrecordelements-directly2.gif "Linkrecordelements_directly2")</span></span>  
  
### <a name="to-link-the-record-elements-by-structure"></a><span data-ttu-id="adcd1-143">若要通过结构链接记录元素</span><span class="sxs-lookup"><span data-stu-id="adcd1-143">To link the record elements by structure</span></span>  
  
1.  <span data-ttu-id="adcd1-144">鼠标拖动源架构中的子层次结构母节点并将它放到目标架构中的子层次结构父节点。</span><span class="sxs-lookup"><span data-stu-id="adcd1-144">Drag the mouse from a sub-hierarchy parent node in source schema, and then drop it to the sub-hierarchy parent node in the target schema.</span></span>  
  
2.  <span data-ttu-id="adcd1-145">在快捷菜单上，单击**按结构链接**。</span><span class="sxs-lookup"><span data-stu-id="adcd1-145">On the shortcut menu, click **Link by Structure**.</span></span> <span data-ttu-id="adcd1-146">BizTalk 映射器会匹配**记录**并**字段**中的节点**记录**这些结构根据要链接的节点**记录**节点，而不管这些结构中的相应节点的名称。</span><span class="sxs-lookup"><span data-stu-id="adcd1-146">The BizTalk Mapper matches the **Record** and **Field** nodes within the **Record** nodes being linked according to the structure of those **Record** nodes, regardless of names of the corresponding nodes within those structures.</span></span>  
  
     <span data-ttu-id="adcd1-147">![链接记录元素&#95;结构](../core/media/linkrecordelements-bystructure.gif "Linkrecordelements_bystructure")</span><span class="sxs-lookup"><span data-stu-id="adcd1-147">![Link record elements&#95;by structure](../core/media/linkrecordelements-bystructure.gif "Linkrecordelements_bystructure")</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="adcd1-148">当尝试通过结构将源架构中的子层次结构母节点链接到目标架构中的非-子层次结构母节点时，BizTalk 映射器将映射源父节点的子级到目标母节点的子级分别。</span><span class="sxs-lookup"><span data-stu-id="adcd1-148">When you try to link a sub-hierarchy parent node in source schema to a non-sub-hierarchy parent node in target schema, by structure, the BizTalk Mapper maps the children of the source parent node to the children of the target parent node, respectively.</span></span> <span data-ttu-id="adcd1-149">下图显示了通过结构进行链接。</span><span class="sxs-lookup"><span data-stu-id="adcd1-149">The following figure shows the linking by structure.</span></span>  
  
     <span data-ttu-id="adcd1-150">![按结构链接记录元素](../core/media/linkrecordelements-bystructure2.gif "Linkrecordelements_bystructure2")</span><span class="sxs-lookup"><span data-stu-id="adcd1-150">![Linking record elements by structure](../core/media/linkrecordelements-bystructure2.gif "Linkrecordelements_bystructure2")</span></span>  
  
### <a name="to-link-the-record-elements-by-name"></a><span data-ttu-id="adcd1-151">若要按名称链接记录元素</span><span class="sxs-lookup"><span data-stu-id="adcd1-151">To link the record elements by name</span></span>  
  
1.  <span data-ttu-id="adcd1-152">鼠标拖动源架构中的子层次结构母节点并将它放到目标架构中的子层次结构父节点。</span><span class="sxs-lookup"><span data-stu-id="adcd1-152">Drag the mouse from a sub-hierarchy parent node in source schema, and then drop it to the sub-hierarchy parent node in the target schema.</span></span>  
  
2.  <span data-ttu-id="adcd1-153">在快捷菜单上，单击**按名称链接**。</span><span class="sxs-lookup"><span data-stu-id="adcd1-153">On the shortcut menu, click **Link by Name**.</span></span> <span data-ttu-id="adcd1-154">BizTalk 映射器将尝试匹配**记录**并**字段**中的节点**记录**根据相应节点，而不考虑的名称要链接的节点其结构，在**记录**要链接的节点。</span><span class="sxs-lookup"><span data-stu-id="adcd1-154">The BizTalk Mapper attempts to match the **Record** and **Field** nodes within the **Record** nodes being linked according to the names of the corresponding nodes, regardless of their structure, within the **Record** nodes to which you are linking.</span></span>  
  
     <span data-ttu-id="adcd1-155">![按名称链接记录元素](../core/media/linkrecordelements-byname.gif "Linkrecordelements_byname")</span><span class="sxs-lookup"><span data-stu-id="adcd1-155">![Linking record elements by name](../core/media/linkrecordelements-byname.gif "Linkrecordelements_byname")</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="adcd1-156">按名称，可以将源架构中的子层次结构母节点链接到目标架构中的非-子层次结构母节点。</span><span class="sxs-lookup"><span data-stu-id="adcd1-156">You can link a sub-hierarchy parent node in source schema to a non-sub-hierarchy parent node in target schema, by name.</span></span> <span data-ttu-id="adcd1-157">BizTalk 映射器与目标节点的子级相匹配的源节点的子级的名称。</span><span class="sxs-lookup"><span data-stu-id="adcd1-157">The BizTalk Mapper matches the names of the children of source node with the children of target node.</span></span> <span data-ttu-id="adcd1-158">如果找到完全相同的子项，然后在各自的子项之间建立链接。</span><span class="sxs-lookup"><span data-stu-id="adcd1-158">If it finds identical children, then a link is established between the respective children.</span></span> <span data-ttu-id="adcd1-159">下图说明了这一概念。</span><span class="sxs-lookup"><span data-stu-id="adcd1-159">The following figure explains this concept.</span></span>  
  
## <a name="to-link-using-a-mass-copy-functoid"></a><span data-ttu-id="adcd1-160">若要使用的批量复制 functoid 链接</span><span class="sxs-lookup"><span data-stu-id="adcd1-160">To link using a mass copy functoid</span></span>  
 <span data-ttu-id="adcd1-161">**批量复制**functoid，映射可使用包含的架构**任何**并**anyAttribute**元素。</span><span class="sxs-lookup"><span data-stu-id="adcd1-161">The **Mass Copy** functoid enables your maps to use schemas that include **any** and **anyAttribute** elements.</span></span> <span data-ttu-id="adcd1-162">从本质上讲，这些元素是 XML 架构定义语言为匹配未知的结构或属性中提供的通配符。</span><span class="sxs-lookup"><span data-stu-id="adcd1-162">These elements are, in essence, wildcards provided in the XML Schema definition language to match unknown structures or attributes.</span></span>  
  
 <span data-ttu-id="adcd1-163">除了处理未知结构的数据**批量复制**functoid，您可以简化架构开发： 需详细指定仅将处理的架构部分。</span><span class="sxs-lookup"><span data-stu-id="adcd1-163">In addition to handling data with unknown structure, the **Mass Copy** functoid enables you to simplify schema development: only the portions of a schema that will be processed need to be specified in detail.</span></span>  
  
 <span data-ttu-id="adcd1-164">![按批量复制 functoid 链接记录元素](../core/media/linkrecordelements-masscopyfunctoid.gif "Linkrecordelements_MassCopyfunctoid")</span><span class="sxs-lookup"><span data-stu-id="adcd1-164">![Linking record elements by Mass Copy functoid](../core/media/linkrecordelements-masscopyfunctoid.gif "Linkrecordelements_MassCopyfunctoid")</span></span>  
  
 <span data-ttu-id="adcd1-165">有关详细信息**批量复制**functoid，请参阅[批量复制 Functoid](../core/mass-copy-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="adcd1-165">For more information about the **Mass Copy** functoid, see [Mass Copy Functoid](../core/mass-copy-functoid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adcd1-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="adcd1-166">See Also</span></span>  
 <span data-ttu-id="adcd1-167">[使用链接指定记录和字段映射](../core/using-links-to-specify-record-and-field-mappings.md) </span><span class="sxs-lookup"><span data-stu-id="adcd1-167">[Using Links to Specify Record and Field Mappings](../core/using-links-to-specify-record-and-field-mappings.md) </span></span>  
 [<span data-ttu-id="adcd1-168">如何向映射添加批量复制 Functoid</span><span class="sxs-lookup"><span data-stu-id="adcd1-168">How to Add Mass Copy Functoids to a Map</span></span>](../core/how-to-add-mass-copy-functoids-to-a-map.md)