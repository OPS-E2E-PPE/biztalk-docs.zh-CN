---
title: "记录移动链接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a3fa4d7-5689-4f55-af1b-369defa37037
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac6abc3d27ad3ee2f135e3ff5c8c1749fcae5f4a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="record-to-record-linking"></a><span data-ttu-id="fa8bb-102">到记录链接</span><span class="sxs-lookup"><span data-stu-id="fa8bb-102">Record-to-Record Linking</span></span>

## <a name="overview"></a><span data-ttu-id="fa8bb-103">概述</span><span class="sxs-lookup"><span data-stu-id="fa8bb-103">Overview</span></span>
<span data-ttu-id="fa8bb-104">在 Microsoft 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你可以使用 BizTalk 映射程序多个之间创建链接的源和目标架构在同一时间类似部分。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-104">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use BizTalk Mapper to create multiple links between similar portions of the source and destination schemas at the same time.</span></span> <span data-ttu-id="fa8bb-105">在以前版本的 BizTalk Server 中，只能一次一个地分别创建此类链接。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-105">In previous versions of BizTalk Server, you had to create such links individually, one at a time.</span></span> <span data-ttu-id="fa8bb-106">有两种不同类型的记录将链接，在正被链接，，如下所示的源和目标架构记录的结构的相似性的程度上基于每个适用于不同方案的：</span><span class="sxs-lookup"><span data-stu-id="fa8bb-106">There are two distinct types of record-to-record linking, each appropriate to different scenarios based on the degree of similarity of the structures of the source and destination schema records being linked, as follows:</span></span>  
  
-   <span data-ttu-id="fa8bb-107">**链接的结构。**</span><span class="sxs-lookup"><span data-stu-id="fa8bb-107">**Structure linking.**</span></span> <span data-ttu-id="fa8bb-108">如果源架构和目标架构中所链接记录的结构相同或非常相似，则使用结构链接。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-108">Use structure linking when the structure of the records being linked in your source and destination schemas are the same or very similar.</span></span>  
  
-   <span data-ttu-id="fa8bb-109">**名称匹配链接。**</span><span class="sxs-lookup"><span data-stu-id="fa8bb-109">**Name-matching linking.**</span></span> <span data-ttu-id="fa8bb-110">如果源架构和目标架构中链接的记录也具有相似结构，并具有匹配的记录和字段名称，但结构性异常多于结构链接的可处理量，则使用名称匹配链接。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-110">Use name-matching linking when the structure of the records being linked in your source and destination schemas are still similar, and with matching record and field names, but with more structural exceptions than are workable with structure linking.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fa8bb-111">记录的链接将应用于链接仅在使用配置的值复制**源链接**属性。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-111">Record-to-record linking applies to value-copy linking only, as configured using the **Source Links** property.</span></span>  
  
## <a name="record-to-record-linking-structure-links"></a><span data-ttu-id="fa8bb-112">记录的链接： 结构链接</span><span class="sxs-lookup"><span data-stu-id="fa8bb-112">Record-to-Record Linking: Structure Links</span></span>  
 <span data-ttu-id="fa8bb-113">如果源架构和目标架构中要链接的记录具有相同或几乎完全相同的结构，请使用结构链接。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-113">Use structure linking when the structure of the records that you want to link in your source and destination schemas is the same or almost exactly the same.</span></span>  
  
 <span data-ttu-id="fa8bb-114">如果架构的结构完全相同，则只需在每个架构的根节点处添加一个链接。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-114">If the structure of your schemas is exactly the same, you need only add one link at the root node of each schema.</span></span> <span data-ttu-id="fa8bb-115">在快捷菜单中，选择所需的链接模式。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-115">In the shortcut menu, select the desired mode of linking.</span></span>  
  
 <span data-ttu-id="fa8bb-116">如果架构中特定记录的结构完全相同，则只需在这两个架构的这些记录间添加一个链接。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-116">If the structure of particular records in your schemas is exactly the same, you need only add one link between those records in each schema.</span></span> <span data-ttu-id="fa8bb-117">在快捷菜单中，选择所需的链接模式。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-117">In the shortcut menu, select the desired mode of linking.</span></span>  
  
 <span data-ttu-id="fa8bb-118">有关如何配置记录到记录的信息作为使用任一结构链接链接或名称匹配链接，请参阅[自动链接记录](../core/how-to-link-records-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-118">For information about how to configure record-to-record linking as using either structure linking or name-matching linking, see [Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa8bb-119">结构链接是记录到记录的链接的默认类型。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-119">Structure links are the default type of record-to-record linking.</span></span>  
  
## <a name="record-to-record-linking-name-matching-links"></a><span data-ttu-id="fa8bb-120">记录的链接： 名称匹配的链接</span><span class="sxs-lookup"><span data-stu-id="fa8bb-120">Record-to-Record Linking: Name-Matching Links</span></span>  
 <span data-ttu-id="fa8bb-121">如果源架构和目标架构中要链接的记录结构非常相似但又不完全相同，请使用名称匹配链接。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-121">Use name-matching links when the structure of the records that you want to link in your source and destination schemas is very similar, but not exactly the same.</span></span> <span data-ttu-id="fa8bb-122">例如，源架构或目标架构在要链接的节点中可能比另一个架构具有更多的从属记录或字段。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-122">For example, the source or destination schema might have more subordinate records or fields within the nodes to be linked than in the other schema.</span></span>  
  
 <span data-ttu-id="fa8bb-123">若要创建具有几乎匹配的结构，包括整个架构 （如果适用），你源和目标架构的部分之间的名称匹配链接创建从子层次结构的父节点发起和结束在另一台的链接子层次结构的父节点。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-123">To create a name-matching link between portions of your source and destination schemas that have nearly matching structures, including the entire schemas where applicable, create a link originating from a sub-hierarchy parent node and ending on another sub-hierarchy parent node.</span></span> <span data-ttu-id="fa8bb-124">在快捷菜单中，选择所需的模式。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-124">In the shortcut menu, select the desired mode.</span></span> <span data-ttu-id="fa8bb-125">链接这些节点后，将自动为源架构和目标架构中具有相同名称以及相同子结构的所有从属记录和字段创建链接。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-125">After you link the nodes, links are automatically created for all of the subordinate records and fields in the source and destination schemas that are named the same and have the same substructure.</span></span>  
  
 <span data-ttu-id="fa8bb-126">有关如何配置记录到记录的信息作为使用任一结构链接链接或名称匹配链接，请参阅[自动链接记录](../core/how-to-link-records-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="fa8bb-126">For information about how to configure record-to-record linking as using either structure linking or name-matching linking, see [Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa8bb-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa8bb-127">See Also</span></span>  
 <span data-ttu-id="fa8bb-128">[自动将记录的链接](../core/how-to-link-records-automatically.md) </span><span class="sxs-lookup"><span data-stu-id="fa8bb-128">[Link Records Automatically](../core/how-to-link-records-automatically.md) </span></span>  
 [<span data-ttu-id="fa8bb-129">编辑链接属性</span><span class="sxs-lookup"><span data-stu-id="fa8bb-129">Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)