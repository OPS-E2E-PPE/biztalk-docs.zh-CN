---
title: 其他平面文件属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c88ad2f-b5a8-46e6-b1b8-61ce6ba910d1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cab0391fd8ffb8388d113301f7a3655f703c2c77
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360734"
---
# <a name="additional-flat-file-properties"></a><span data-ttu-id="bfff8-102">其他平面文件属性</span><span class="sxs-lookup"><span data-stu-id="bfff8-102">Additional Flat File Properties</span></span>

## <a name="hidden-properties"></a><span data-ttu-id="bfff8-103">隐藏的属性</span><span class="sxs-lookup"><span data-stu-id="bfff8-103">Hidden properties</span></span>
<span data-ttu-id="bfff8-104">下表列出了不会出现在架构编辑器中的其他平面文件节点属性。</span><span class="sxs-lookup"><span data-stu-id="bfff8-104">The following table lists additional flat file node properties that do not appear in the Schema Editor.</span></span> <span data-ttu-id="bfff8-105">使用这些属性需要手动编辑在文本编辑器中的架构文件。</span><span class="sxs-lookup"><span data-stu-id="bfff8-105">Using these properties requires hand editing the schema file in a text editor.</span></span>  

|<span data-ttu-id="bfff8-106">属性</span><span class="sxs-lookup"><span data-stu-id="bfff8-106">Property</span></span>|<span data-ttu-id="bfff8-107">值</span><span class="sxs-lookup"><span data-stu-id="bfff8-107">Values</span></span>|<span data-ttu-id="bfff8-108">默认值</span><span class="sxs-lookup"><span data-stu-id="bfff8-108">Default Value</span></span>|<span data-ttu-id="bfff8-109">Description</span><span class="sxs-lookup"><span data-stu-id="bfff8-109">Description</span></span>|  
|--------------|------------|-------------------|-----------------|  
|<span data-ttu-id="bfff8-110">suppress_empty_nodes</span><span class="sxs-lookup"><span data-stu-id="bfff8-110">suppress_empty_nodes</span></span>|<span data-ttu-id="bfff8-111">**true** 或 **false**</span><span class="sxs-lookup"><span data-stu-id="bfff8-111">**true** or **false**</span></span>|<span data-ttu-id="bfff8-112">**false**</span><span class="sxs-lookup"><span data-stu-id="bfff8-112">**false**</span></span>|<span data-ttu-id="bfff8-113">指示在解析程序生成的 XML 实例数据后删除空 XML 节点。</span><span class="sxs-lookup"><span data-stu-id="bfff8-113">Indicates whether or not to remove empty XML nodes after the parser generates XML instance data.</span></span>|  
|<span data-ttu-id="bfff8-114">generate_empty_nodes</span><span class="sxs-lookup"><span data-stu-id="bfff8-114">generate_empty_nodes</span></span>|<span data-ttu-id="bfff8-115">**true** 或 **false**</span><span class="sxs-lookup"><span data-stu-id="bfff8-115">**true** or **false**</span></span>|<span data-ttu-id="bfff8-116">**true**</span><span class="sxs-lookup"><span data-stu-id="bfff8-116">**true**</span></span>|<span data-ttu-id="bfff8-117">在 XML 实例数据中生成空节点的现有记录。</span><span class="sxs-lookup"><span data-stu-id="bfff8-117">Generate empty nodes for records that exist in the XML instance data.</span></span>|  
|<span data-ttu-id="bfff8-118">parser_optimization</span><span class="sxs-lookup"><span data-stu-id="bfff8-118">parser_optimization</span></span>|<span data-ttu-id="bfff8-119">**速度**或**复杂性**</span><span class="sxs-lookup"><span data-stu-id="bfff8-119">**speed** or **complexity**</span></span>|<span data-ttu-id="bfff8-120">**speed**</span><span class="sxs-lookup"><span data-stu-id="bfff8-120">**speed**</span></span>|<span data-ttu-id="bfff8-121">优化速度缩短解析时间有关，但需要处理某些数据多义性问题。</span><span class="sxs-lookup"><span data-stu-id="bfff8-121">Optimizing for speed decreases the parsing time but at the cost of dealing with some ambiguities in data.</span></span> <span data-ttu-id="bfff8-122">针对复杂度进行优化处理更广泛的多义性问题，但会影响处理速度。</span><span class="sxs-lookup"><span data-stu-id="bfff8-122">Optimizing for complexity handles a wider range of ambiguities but at the cost of processing speed.</span></span>|  
|<span data-ttu-id="bfff8-123">lookahead_depth</span><span class="sxs-lookup"><span data-stu-id="bfff8-123">lookahead_depth</span></span>|<span data-ttu-id="bfff8-124">任何正整数;零 (0) 表示 lookahead 无限制。</span><span class="sxs-lookup"><span data-stu-id="bfff8-124">Any positive integer; zero (0) indicates infinite lookahead.</span></span>|<span data-ttu-id="bfff8-125">3</span><span class="sxs-lookup"><span data-stu-id="bfff8-125">3</span></span>|<span data-ttu-id="bfff8-126">向前查找匹配的数据的方式。</span><span class="sxs-lookup"><span data-stu-id="bfff8-126">How far to look ahead for matching data.</span></span>|  
|<span data-ttu-id="bfff8-127">allow_early_termination</span><span class="sxs-lookup"><span data-stu-id="bfff8-127">allow_early_termination</span></span>|<span data-ttu-id="bfff8-128">**true** 或 **false**</span><span class="sxs-lookup"><span data-stu-id="bfff8-128">**true** or **false**</span></span>|<span data-ttu-id="bfff8-129">**false**</span><span class="sxs-lookup"><span data-stu-id="bfff8-129">**false**</span></span>|<span data-ttu-id="bfff8-130">指示位置记录是否可以提前终止 (**，则返回 true**) 或必须包含所有记录的字段的数据 (**false**)。</span><span class="sxs-lookup"><span data-stu-id="bfff8-130">Indicates whether positional records can terminate early (**true**) or must contain data for all record fields (**false**).</span></span>|  
|<span data-ttu-id="bfff8-131">early_terminate_optional_fields</span><span class="sxs-lookup"><span data-stu-id="bfff8-131">early_terminate_optional_fields</span></span>|<span data-ttu-id="bfff8-132">**true** 或 **false**</span><span class="sxs-lookup"><span data-stu-id="bfff8-132">**true** or **false**</span></span>|<span data-ttu-id="bfff8-133">**false**</span><span class="sxs-lookup"><span data-stu-id="bfff8-133">**false**</span></span>|<span data-ttu-id="bfff8-134">允许提前终止可选尾部字段 (**，则返回 true**)。</span><span class="sxs-lookup"><span data-stu-id="bfff8-134">Enable early termination of optional trailing fields (**true**).</span></span> <span data-ttu-id="bfff8-135">如果在 BizTalk 编辑器中打开现有架构无此批注，则将使用默认值设置为添加到它此批注 (**false**)。</span><span class="sxs-lookup"><span data-stu-id="bfff8-135">If the existing schema without this annotation is opened in the BizTalk Editor, this annotation will be added to it with the default value set to (**false**).</span></span> <span data-ttu-id="bfff8-136">**注意：** 时，early_terminate_optional_fields 批注才会生效在 allow_early_termination 设置为"true"。</span><span class="sxs-lookup"><span data-stu-id="bfff8-136">**Note:**  The early_terminate_optional_fields annotation only takes effect if the allow_early_termination is set to "true".</span></span>|  

 <span data-ttu-id="bfff8-137">所有这些属性是属性**是 /annotation/appinfo/schemaInfo**元素。</span><span class="sxs-lookup"><span data-stu-id="bfff8-137">All of these properties are attributes of the **/annotation/appinfo/schemaInfo** element.</span></span>  

 <span data-ttu-id="bfff8-138">当**parser_optimization**设置为**复杂性**，同一个组或记录中的许多可选节点时，您可能必须根据架构验证失败。</span><span class="sxs-lookup"><span data-stu-id="bfff8-138">When **parser_optimization** is set to **complexity**, you may have validation failures against a schema when there are many optional nodes in the same group or record.</span></span> <span data-ttu-id="bfff8-139">可能需要设置**lookahead_depth**为零 (0) 以避免出现验证错误。</span><span class="sxs-lookup"><span data-stu-id="bfff8-139">You may need to set **lookahead_depth** to zero (0) to avoid validation errors.</span></span>  

## <a name="see-also"></a><span data-ttu-id="bfff8-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfff8-140">See Also</span></span>  
- [<span data-ttu-id="bfff8-141">节点属性</span><span class="sxs-lookup"><span data-stu-id="bfff8-141">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="bfff8-142">**平面文件架构的补充节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="bfff8-142">**Supplemental Node Properties for Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
