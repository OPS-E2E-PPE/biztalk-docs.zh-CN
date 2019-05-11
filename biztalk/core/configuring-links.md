---
title: 配置链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10050c28-0944-4073-afd2-54cd6c8d79a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb50ad367a8e1f72de0f567aaeb46ea07a933f22
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355317"
---
# <a name="configuring-links"></a><span data-ttu-id="051a8-102">配置链接</span><span class="sxs-lookup"><span data-stu-id="051a8-102">Configuring Links</span></span>

## <a name="overview"></a><span data-ttu-id="051a8-103">概述</span><span class="sxs-lookup"><span data-stu-id="051a8-103">Overview</span></span>
<span data-ttu-id="051a8-104">链接具有的属性中显示的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]时显示的网格页中选择链接属性窗口。</span><span class="sxs-lookup"><span data-stu-id="051a8-104">Links have properties that are displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window when a link is selected in the displayed grid page.</span></span> <span data-ttu-id="051a8-105">有关与链接关联的属性的参考信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="051a8-105">For reference information about the properties associated with links, see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 

## <a name="source-target-and-label"></a><span data-ttu-id="051a8-106">源、 目标和标签</span><span class="sxs-lookup"><span data-stu-id="051a8-106">Source, target and label</span></span>  
 <span data-ttu-id="051a8-107">以下属性配置映射中的链接：</span><span class="sxs-lookup"><span data-stu-id="051a8-107">The following properties configure links in a map:</span></span>  
  
- <span data-ttu-id="051a8-108">**源链接**。</span><span class="sxs-lookup"><span data-stu-id="051a8-108">**Source Links**.</span></span> <span data-ttu-id="051a8-109">您使用**源链接**属性可以配置将用于构造输出实例消息的输入的实例消息中的数据的性质。</span><span class="sxs-lookup"><span data-stu-id="051a8-109">You use the **Source Links** property to configure the nature of the data from an input instance message that will be used to construct the output instance message.</span></span> <span data-ttu-id="051a8-110">默认值，并且最常用的选择是使用输入的实例消息中的元素或属性值。</span><span class="sxs-lookup"><span data-stu-id="051a8-110">The default, and most common choice, is to use the element or attribute value from the input instance message.</span></span> <span data-ttu-id="051a8-111">其他选择是名称的有可能，包括使用输入的实例消息中的属性的元素。</span><span class="sxs-lookup"><span data-stu-id="051a8-111">Other choices are possible, including the use of the name of the element or attribute from the input instance message.</span></span> <span data-ttu-id="051a8-112">有关此属性及其可用选项的详细信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="051a8-112">For more information about this property and its available choices, see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
- <span data-ttu-id="051a8-113">**目标链接**。</span><span class="sxs-lookup"><span data-stu-id="051a8-113">**Target Links**.</span></span> <span data-ttu-id="051a8-114">您使用**目标链接**属性可以配置 BizTalk 映射器匹配节点层次结构级别的方式。</span><span class="sxs-lookup"><span data-stu-id="051a8-114">You use the **Target Links** property to configure how BizTalk Mapper will match node-hierarchy levels.</span></span> <span data-ttu-id="051a8-115">默认情况下，创建输出实例消息将平展源架构层次结构。</span><span class="sxs-lookup"><span data-stu-id="051a8-115">By default, source schema hierarchies are flattened as the output instance message is created.</span></span> <span data-ttu-id="051a8-116">您还可以选择保留，这些层次匹配链接向下顶部或从下到上。</span><span class="sxs-lookup"><span data-stu-id="051a8-116">You can also choose to have hierarchies preserved, matching links from either the top down or from the bottom up.</span></span> <span data-ttu-id="051a8-117">有关此属性及其可用选项的详细信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="051a8-117">For more information about this property and its available choices, see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
- <span data-ttu-id="051a8-118">**标签**。</span><span class="sxs-lookup"><span data-stu-id="051a8-118">**Label**.</span></span> <span data-ttu-id="051a8-119">您使用**标签**属性来创建比默认情况下使用的 XPath 值更具可读性的链接名称。</span><span class="sxs-lookup"><span data-stu-id="051a8-119">You use the **Label** property to create a more readable name for the link than the XPath value that is used by default.</span></span> <span data-ttu-id="051a8-120">当作为输入的表驱动循环使用该链接时，配置此属性将非常有用。</span><span class="sxs-lookup"><span data-stu-id="051a8-120">Configuring this property is especially helpful when the link is used as an input for table-driven looping.</span></span> <span data-ttu-id="051a8-121">有关此属性及其可用选项，以及表驱动循环的详细信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="051a8-121">For more information about this property and its available choices, and about table-driven looping, see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="051a8-122">另请参阅[表循环和表提取程序 Functoid](../core/table-looping-and-table-extractor-functoids.md)分别。</span><span class="sxs-lookup"><span data-stu-id="051a8-122">Also see [Table Looping and Table Extractor Functoids](../core/table-looping-and-table-extractor-functoids.md), respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="051a8-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="051a8-123">See Also</span></span>  
  [<span data-ttu-id="051a8-124">如何编辑链接属性</span><span class="sxs-lookup"><span data-stu-id="051a8-124">How to Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)