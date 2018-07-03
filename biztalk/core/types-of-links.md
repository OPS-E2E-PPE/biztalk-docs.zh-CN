---
title: 类型的链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compiler directives, links
- elastic links [maps]
- maps, links
- BizTalk Mapper, links
- partial links [maps]
- fixed links [maps]
ms.assetid: 348fae77-2e25-4b79-93bb-d42f3d18a3f7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f2eb8d5546698cc611072ccff1e9f0bf4abf9a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009606"
---
# <a name="types-of-links"></a><span data-ttu-id="13503-102">类型的链接</span><span class="sxs-lookup"><span data-stu-id="13503-102">Types of Links</span></span>
<span data-ttu-id="13503-103">以下列表概括列出了 BizTalk 映射器中各种类型的可用链接：</span><span class="sxs-lookup"><span data-stu-id="13503-103">The following list summarizes the various types of links available in BizTalk Mapper:</span></span>  
  
- <span data-ttu-id="13503-104">**弹性链接。**</span><span class="sxs-lookup"><span data-stu-id="13503-104">**Elastic links.**</span></span> <span data-ttu-id="13503-105">术语“弹性”适用于在连接链接的两端之前所创建的链接。</span><span class="sxs-lookup"><span data-stu-id="13503-105">The term elastic applies to a link as it is being created, before both ends of the link are connected.</span></span> <span data-ttu-id="13503-106">例如，如果从源架构内的字段中拖动一个链接，但尚未将其连接到目标架构中的对应字段，则该链接为弹性链接。</span><span class="sxs-lookup"><span data-stu-id="13503-106">For example, if you are dragging a link from a field in the source schema, but you have not yet connected it to its corresponding field in the destination schema, the link is elastic.</span></span> <span data-ttu-id="13503-107">完成连接后，弹性链接将变为固定链接。</span><span class="sxs-lookup"><span data-stu-id="13503-107">As you complete the connection, the elastic link becomes a fixed link.</span></span>  
  
   <span data-ttu-id="13503-108">可以将链接的一个终结点拖到另一个节点或 functoid。</span><span class="sxs-lookup"><span data-stu-id="13503-108">You can drag one endpoint of a link to another node or a functoid.</span></span> <span data-ttu-id="13503-109">有关链接替换的详细信息，请参阅[如何创建链接](../core/how-to-create-links.md)。</span><span class="sxs-lookup"><span data-stu-id="13503-109">For more information about link replacement, see [How to Create Links](../core/how-to-create-links.md).</span></span>  
  
- <span data-ttu-id="13503-110">**固定链接。**</span><span class="sxs-lookup"><span data-stu-id="13503-110">**Fixed Links.**</span></span> <span data-ttu-id="13503-111">术语“固定”适用于已显式构造为表示值从源实例消息到目标实例消息的移动，或至少为该移动的一部分的链接。</span><span class="sxs-lookup"><span data-stu-id="13503-111">The term fixed applies to a link that you have explicitly constructed to represent the movement of a value from a source instance message to a destination instance message, or at least a part of that movement.</span></span> <span data-ttu-id="13503-112">固定的直接连接的链接**记录**或**字段**节点到源架构中的**记录**或**字段**目标中的节点架构表示数据的直接复制在运行时。</span><span class="sxs-lookup"><span data-stu-id="13503-112">Fixed links that directly connect a **Record** or **Field** node in the source schema to a **Record** or **Field** node in the destination schema represent a straight copying of data at run time.</span></span> <span data-ttu-id="13503-113">一端或另一端连接到 functoid 的固定链接，表示在运行时数据从输入实例消息到输出实例消息的移动的一部分。</span><span class="sxs-lookup"><span data-stu-id="13503-113">Fixed links connecting to a functoid at one end or the other represent part of the movement of data from an input instance message to an output instance message at run time.</span></span> <span data-ttu-id="13503-114">以上这几个链接组合在一起，可完成源架构与目标架构之间的链接，并表示数据项的整个移动。</span><span class="sxs-lookup"><span data-stu-id="13503-114">Several of these together, completing the link between the source and destination schemas, represent the entire movement of an item of data.</span></span>  
  
- <span data-ttu-id="13503-115">**部分链接。**</span><span class="sxs-lookup"><span data-stu-id="13503-115">**Partial links.**</span></span> <span data-ttu-id="13503-116">部分术语适用于链接用于你当前无法看到的确切**记录**或**字段**它们连接到源或目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="13503-116">The term partial applies to links for which you cannot currently see the exact **Record** or **Field** node to which they are connected in the source or destination schemas.</span></span> <span data-ttu-id="13503-117">发生这种情况时**记录**或**字段**节点附加到没有显示，因为其祖先节点之一处于折叠状态中的架构的树表示形式。</span><span class="sxs-lookup"><span data-stu-id="13503-117">This occurs when the **Record** or **Field** node to which they are attached is not shown because one of its ancestor nodes is collapsed in the tree representation of the schema.</span></span> <span data-ttu-id="13503-118">有关部分链接的详细信息，请参阅[如何优化链接显示](../core/how-to-optimize-the-display-of-links.md)。</span><span class="sxs-lookup"><span data-stu-id="13503-118">For more information about partial links, see [How to Optimize the Display of Links](../core/how-to-optimize-the-display-of-links.md).</span></span>  
  
- <span data-ttu-id="13503-119">**编译器链接。**</span><span class="sxs-lookup"><span data-stu-id="13503-119">**Compiler links.**</span></span> <span data-ttu-id="13503-120">术语“编译器”适用于在生成 BizTalk 项目时 BizTalk 映射器自动创建的链接。</span><span class="sxs-lookup"><span data-stu-id="13503-120">The term compiler applies to links that BizTalk Mapper creates automatically when you build a BizTalk project.</span></span> <span data-ttu-id="13503-121">例如，如果配置表驱动循环，则编译器链接将显示源架构中的记录和字段与目标架构中的记录和字段之间的关系和链接。</span><span class="sxs-lookup"><span data-stu-id="13503-121">For example, if you configure table-driven looping, the compiler links show the relationship and the links between the records and fields in the source schema and the records and fields in the destination schema.</span></span> <span data-ttu-id="13503-122">此类型的链接可由编译器指令自动生成，也可由用户指定。</span><span class="sxs-lookup"><span data-stu-id="13503-122">This type of link can be generated automatically by compiler directives, or it can be user-directed.</span></span>  
  
  <span data-ttu-id="13503-123">默认情况下，BizTalk 映射器将使用不同颜色的线条来显示这些不同类型的链接，以便帮助您区分映射的详细信息。</span><span class="sxs-lookup"><span data-stu-id="13503-123">BizTalk Mapper, by default, displays these various types of links using different colored lines to help you distinguish the detail of your maps.</span></span> <span data-ttu-id="13503-124">您可以更改用于这些不同种类链接的颜色**选项**命令**工具**菜单。</span><span class="sxs-lookup"><span data-stu-id="13503-124">You can change the colors used for these different kinds of links with the **Options** command on the **Tools** menu.</span></span> <span data-ttu-id="13503-125">有关如何更改颜色呈现不同类别链接的详细信息，请参阅[如何自定义颜色和字体在 BizTalk 映射器](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md)。</span><span class="sxs-lookup"><span data-stu-id="13503-125">For more information about how change in color renders different categories of links, see [How to Customize Colors and Font in BizTalk Mapper](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13503-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="13503-126">See Also</span></span>  
 [<span data-ttu-id="13503-127">使用链接指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="13503-127">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)