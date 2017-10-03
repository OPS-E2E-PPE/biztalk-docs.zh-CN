---
title: "配置链接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10050c28-0944-4073-afd2-54cd6c8d79a2
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3da50b626eeb65a137deb8a1a7ef4f2ee3e0609
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-links"></a><span data-ttu-id="d8855-102">配置链接</span><span class="sxs-lookup"><span data-stu-id="d8855-102">Configuring Links</span></span>

## <a name="overview"></a><span data-ttu-id="d8855-103">概述</span><span class="sxs-lookup"><span data-stu-id="d8855-103">Overview</span></span>
<span data-ttu-id="d8855-104">在显示的网格页中选择链接后，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口中将显示链接具有的属性。</span><span class="sxs-lookup"><span data-stu-id="d8855-104">Links have properties that are displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window when a link is selected in the displayed grid page.</span></span> <span data-ttu-id="d8855-105">有关与链接关联的属性的参考信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="d8855-105">For reference information about the properties associated with links, see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 

## <a name="source-target-and-label"></a><span data-ttu-id="d8855-106">源、 目标和标签</span><span class="sxs-lookup"><span data-stu-id="d8855-106">Source, target and label</span></span>  
 <span data-ttu-id="d8855-107">以下属性配置映射中的链接：</span><span class="sxs-lookup"><span data-stu-id="d8855-107">The following properties configure links in a map:</span></span>  
  
-   <span data-ttu-id="d8855-108">**源链接**。</span><span class="sxs-lookup"><span data-stu-id="d8855-108">**Source Links**.</span></span> <span data-ttu-id="d8855-109">你使用**源链接**属性配置将用于构造输出实例消息输入的实例消息中的数据的性质。</span><span class="sxs-lookup"><span data-stu-id="d8855-109">You use the **Source Links** property to configure the nature of the data from an input instance message that will be used to construct the output instance message.</span></span> <span data-ttu-id="d8855-110">默认并且最常用的选择是使用输入实例消息中的元素或属性的值。</span><span class="sxs-lookup"><span data-stu-id="d8855-110">The default, and most common choice, is to use the element or attribute value from the input instance message.</span></span> <span data-ttu-id="d8855-111">也可能进行其他选择，包括使用输入实例消息中的元素或属性的名称。</span><span class="sxs-lookup"><span data-stu-id="d8855-111">Other choices are possible, including the use of the name of the element or attribute from the input instance message.</span></span> <span data-ttu-id="d8855-112">有关此属性，并且其可用的选项的详细信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="d8855-112">For more information about this property and its available choices, see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
-   <span data-ttu-id="d8855-113">**目标链接**。</span><span class="sxs-lookup"><span data-stu-id="d8855-113">**Target Links**.</span></span> <span data-ttu-id="d8855-114">你使用**目标链接**属性来配置 BizTalk 映射程序匹配节点层次结构级别的方式。</span><span class="sxs-lookup"><span data-stu-id="d8855-114">You use the **Target Links** property to configure how BizTalk Mapper will match node-hierarchy levels.</span></span> <span data-ttu-id="d8855-115">默认情况下，创建输出实例消息时将平展源架构层次。</span><span class="sxs-lookup"><span data-stu-id="d8855-115">By default, source schema hierarchies are flattened as the output instance message is created.</span></span> <span data-ttu-id="d8855-116">也可以选择保留这些层次，并且从上到下或从下到上匹配链接。</span><span class="sxs-lookup"><span data-stu-id="d8855-116">You can also choose to have hierarchies preserved, matching links from either the top down or from the bottom up.</span></span> <span data-ttu-id="d8855-117">有关此属性，并且其可用的选项的详细信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="d8855-117">For more information about this property and its available choices, see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
-   <span data-ttu-id="d8855-118">**标签**。</span><span class="sxs-lookup"><span data-stu-id="d8855-118">**Label**.</span></span> <span data-ttu-id="d8855-119">你使用**标签**属性来创建链接比默认情况下使用的 XPath 值更具可读性的名称。</span><span class="sxs-lookup"><span data-stu-id="d8855-119">You use the **Label** property to create a more readable name for the link than the XPath value that is used by default.</span></span> <span data-ttu-id="d8855-120">在将链接用作表驱动循环的输入时，配置此属性尤其有帮助。</span><span class="sxs-lookup"><span data-stu-id="d8855-120">Configuring this property is especially helpful when the link is used as an input for table-driven looping.</span></span> <span data-ttu-id="d8855-121">有关此属性，并且其可用的选项，以及表驱动循环的详细信息，请参阅**链接属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="d8855-121">For more information about this property and its available choices, and about table-driven looping, see **Link Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> <span data-ttu-id="d8855-122">另请参阅[表循环和表提取程序 Functoid](../core/table-looping-and-table-extractor-functoids.md)分别。</span><span class="sxs-lookup"><span data-stu-id="d8855-122">Also see [Table Looping and Table Extractor Functoids](../core/table-looping-and-table-extractor-functoids.md), respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8855-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8855-123">See Also</span></span>  
  [<span data-ttu-id="d8855-124">如何编辑链接属性</span><span class="sxs-lookup"><span data-stu-id="d8855-124">How to Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)