---
title: 记录到记录的链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a3fa4d7-5689-4f55-af1b-369defa37037
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91108b194a186488867ff083c0129570b5fd9477
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398036"
---
# <a name="record-to-record-linking"></a><span data-ttu-id="8337f-102">记录到记录链接</span><span class="sxs-lookup"><span data-stu-id="8337f-102">Record-to-Record Linking</span></span>

## <a name="overview"></a><span data-ttu-id="8337f-103">概述</span><span class="sxs-lookup"><span data-stu-id="8337f-103">Overview</span></span>
<span data-ttu-id="8337f-104">在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以使用 BizTalk 映射器创建多个同时在源和目标架构的相似部分之间的链接。</span><span class="sxs-lookup"><span data-stu-id="8337f-104">In Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can use BizTalk Mapper to create multiple links between similar portions of the source and destination schemas at the same time.</span></span> <span data-ttu-id="8337f-105">在以前版本的 BizTalk Server，您必须分别创建此类链接一次一个。</span><span class="sxs-lookup"><span data-stu-id="8337f-105">In previous versions of BizTalk Server, you had to create such links individually, one at a time.</span></span> <span data-ttu-id="8337f-106">有两种不同类型的记录到记录的链接，在源和目标架构链接的记录，按如下所示的结构的相似性的程度上基于每个适用于不同方案：</span><span class="sxs-lookup"><span data-stu-id="8337f-106">There are two distinct types of record-to-record linking, each appropriate to different scenarios based on the degree of similarity of the structures of the source and destination schema records being linked, as follows:</span></span>  
  
-   <span data-ttu-id="8337f-107">**结构链接。**</span><span class="sxs-lookup"><span data-stu-id="8337f-107">**Structure linking.**</span></span> <span data-ttu-id="8337f-108">使用结构链接时在源和目标架构中所链接的记录结构是相同或非常相似。</span><span class="sxs-lookup"><span data-stu-id="8337f-108">Use structure linking when the structure of the records being linked in your source and destination schemas are the same or very similar.</span></span>  
  
-   <span data-ttu-id="8337f-109">**名称匹配链接。**</span><span class="sxs-lookup"><span data-stu-id="8337f-109">**Name-matching linking.**</span></span> <span data-ttu-id="8337f-110">使用名称匹配链接时仍类似，在源和目标架构中链接的记录的结构和匹配的记录和字段名称，但结构性异常多于结构链接具有可处理量。</span><span class="sxs-lookup"><span data-stu-id="8337f-110">Use name-matching linking when the structure of the records being linked in your source and destination schemas are still similar, and with matching record and field names, but with more structural exceptions than are workable with structure linking.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8337f-111">记录到记录的链接适用于链接仅在使用配置的值复制**源链接**属性。</span><span class="sxs-lookup"><span data-stu-id="8337f-111">Record-to-record linking applies to value-copy linking only, as configured using the **Source Links** property.</span></span>  
  
## <a name="record-to-record-linking-structure-links"></a><span data-ttu-id="8337f-112">记录到记录链接：结构链接</span><span class="sxs-lookup"><span data-stu-id="8337f-112">Record-to-Record Linking: Structure Links</span></span>  
 <span data-ttu-id="8337f-113">使用结构链接时要在源和目标架构中链接的记录的结构不相同或几乎完全相同。</span><span class="sxs-lookup"><span data-stu-id="8337f-113">Use structure linking when the structure of the records that you want to link in your source and destination schemas is the same or almost exactly the same.</span></span>  
  
 <span data-ttu-id="8337f-114">如果您的架构的结构完全相同，只需每个架构的根节点处添加一个链接。</span><span class="sxs-lookup"><span data-stu-id="8337f-114">If the structure of your schemas is exactly the same, you need only add one link at the root node of each schema.</span></span> <span data-ttu-id="8337f-115">在快捷菜单中，选择所需的链接模式。</span><span class="sxs-lookup"><span data-stu-id="8337f-115">In the shortcut menu, select the desired mode of linking.</span></span>  
  
 <span data-ttu-id="8337f-116">如果您的架构中特定记录的结构完全相同，只需添加这些记录中每个架构之间的一个链接。</span><span class="sxs-lookup"><span data-stu-id="8337f-116">If the structure of particular records in your schemas is exactly the same, you need only add one link between those records in each schema.</span></span> <span data-ttu-id="8337f-117">在快捷菜单中，选择所需的链接模式。</span><span class="sxs-lookup"><span data-stu-id="8337f-117">In the shortcut menu, select the desired mode of linking.</span></span>  
  
 <span data-ttu-id="8337f-118">有关如何配置记录到记录的信息链接作为使用结构链接或名称匹配链接，请参阅[自动链接记录](../core/how-to-link-records-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="8337f-118">For information about how to configure record-to-record linking as using either structure linking or name-matching linking, see [Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8337f-119">结构链接是记录到记录的链接的默认类型。</span><span class="sxs-lookup"><span data-stu-id="8337f-119">Structure links are the default type of record-to-record linking.</span></span>  
  
## <a name="record-to-record-linking-name-matching-links"></a><span data-ttu-id="8337f-120">记录到记录链接：名称匹配链接</span><span class="sxs-lookup"><span data-stu-id="8337f-120">Record-to-Record Linking: Name-Matching Links</span></span>  
 <span data-ttu-id="8337f-121">使用名称匹配链接时要在源和目标架构中链接的记录结构非常相似，但又不完全相同。</span><span class="sxs-lookup"><span data-stu-id="8337f-121">Use name-matching links when the structure of the records that you want to link in your source and destination schemas is very similar, but not exactly the same.</span></span> <span data-ttu-id="8337f-122">例如，源或目标架构可能有多个从属记录或要比其他架构中链接的节点中的字段。</span><span class="sxs-lookup"><span data-stu-id="8337f-122">For example, the source or destination schema might have more subordinate records or fields within the nodes to be linked than in the other schema.</span></span>  
  
 <span data-ttu-id="8337f-123">若要创建具有近似匹配结构，包括整个架构，如果适用，在源和目标架构的部分之间的名称匹配链接创建链接来自子层次结构父节点和在另一台结束子层次结构父节点。</span><span class="sxs-lookup"><span data-stu-id="8337f-123">To create a name-matching link between portions of your source and destination schemas that have nearly matching structures, including the entire schemas where applicable, create a link originating from a sub-hierarchy parent node and ending on another sub-hierarchy parent node.</span></span> <span data-ttu-id="8337f-124">在快捷菜单中，选择所需的模式。</span><span class="sxs-lookup"><span data-stu-id="8337f-124">In the shortcut menu, select the desired mode.</span></span> <span data-ttu-id="8337f-125">链接这些节点后，链接会自动创建的所有从属记录和已命名相同，并且具有相同子结构的源和目标架构中的字段。</span><span class="sxs-lookup"><span data-stu-id="8337f-125">After you link the nodes, links are automatically created for all of the subordinate records and fields in the source and destination schemas that are named the same and have the same substructure.</span></span>  
  
 <span data-ttu-id="8337f-126">有关如何配置记录到记录的信息链接作为使用结构链接或名称匹配链接，请参阅[自动链接记录](../core/how-to-link-records-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="8337f-126">For information about how to configure record-to-record linking as using either structure linking or name-matching linking, see [Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8337f-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="8337f-127">See Also</span></span>  
 <span data-ttu-id="8337f-128">[自动链接记录](../core/how-to-link-records-automatically.md) </span><span class="sxs-lookup"><span data-stu-id="8337f-128">[Link Records Automatically](../core/how-to-link-records-automatically.md) </span></span>  
 [<span data-ttu-id="8337f-129">编辑链接属性</span><span class="sxs-lookup"><span data-stu-id="8337f-129">Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)