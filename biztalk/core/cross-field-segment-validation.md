---
title: 交叉字段段验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e757b4f-71fe-44d5-9580-c8b1c8eb2366
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efd3a0b5f68ded39fbf5cc88a4ba8aac6725602e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969395"
---
# <a name="cross-field-segment-validation"></a><span data-ttu-id="575c2-102">交叉字段段验证</span><span class="sxs-lookup"><span data-stu-id="575c2-102">Cross Field-Segment Validation</span></span>
<span data-ttu-id="575c2-103">EDI 接收管道和 EDI 发送管道可对 X12 编码消息中的事务集数据元素执行跨字段/段验证。</span><span class="sxs-lookup"><span data-stu-id="575c2-103">The EDI receive pipeline and EDI send pipeline can perform cross field/segment validation on transaction-set data elements in X12-encoded messages.</span></span> <span data-ttu-id="575c2-104">在 X12 中这种验证称为关系条件。</span><span class="sxs-lookup"><span data-stu-id="575c2-104">This validation is called relational conditions in X12.</span></span> <span data-ttu-id="575c2-105">跨字段验证通过批注表示，因此它与 EDI 验证有关。</span><span class="sxs-lookup"><span data-stu-id="575c2-105">Cross field validation is expressed through annotations, and as a result, it is related to EDI validation.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="575c2-106"> 不支持 EDIFACT 依赖规则。</span><span class="sxs-lookup"><span data-stu-id="575c2-106"> does not support EDIFACT dependency rules.</span></span>  
  
 <span data-ttu-id="575c2-107">对于 X12 编码的消息，可通过将消息架构中的 X12ConditionDesignator_Check 标记设置为“Yes”来启用此验证。</span><span class="sxs-lookup"><span data-stu-id="575c2-107">For X12-encoded messages, you enable this validation by setting the X12ConditionDesignator_Check flag in the message schema to "Yes".</span></span> <span data-ttu-id="575c2-108">该标记位于该架构“appinfo”部分的批注中。</span><span class="sxs-lookup"><span data-stu-id="575c2-108">This flag is in an annotation in the “appinfo” section of the schema.</span></span> <span data-ttu-id="575c2-109">默认情况下，该标记设置为“No”，且不为 X12 架构启用跨字段/段验证。</span><span class="sxs-lookup"><span data-stu-id="575c2-109">By default this flag is set to "No" and cross field\segment validation is not enabled for X12 schemas.</span></span> <span data-ttu-id="575c2-110">对于 HIPAA 架构默认值设置为"是"并验证启用跨 field\segment。</span><span class="sxs-lookup"><span data-stu-id="575c2-110">For HIPAA schemas the default is set to “Yes” and cross field\segment validation is enabled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="575c2-111">跨字段/段验证与 EDI 数据元素验证和扩展 (BTS-XSD) 验证都不同。</span><span class="sxs-lookup"><span data-stu-id="575c2-111">Cross-field/segment validation is distinct from both EDI data element validation and extended (BTS-XSD) validation.</span></span> <span data-ttu-id="575c2-112">可在不执行跨字段/段验证的情况下执行 EDI 数据元素验证和/或扩展验证，也可在不执行 EDI 数据元素验证和/或扩展验证的情况下执行跨字段/段验证。</span><span class="sxs-lookup"><span data-stu-id="575c2-112">EDI data element validation and/or extended validation can be performed without performing cross-field/segment validation, and cross-field/segment validation can be performed without performing EDI data element validation and/or extended validation.</span></span>  
  
 <span data-ttu-id="575c2-113">X12 的可选性包括必需 (M)、可选 (O) 和关系 (R)（跨字段验证）。</span><span class="sxs-lookup"><span data-stu-id="575c2-113">Optionality in X12 consists of Mandatory (M), Optional (O), and Relational (R) (cross field validation).</span></span> <span data-ttu-id="575c2-114">如果可选性为必需，则必须至少对复合类型中的一个组件数据元素赋值。</span><span class="sxs-lookup"><span data-stu-id="575c2-114">When the optionality is Mandatory, at least one component data element in composite types must be valued.</span></span>  
  
## <a name="x12-optionality"></a><span data-ttu-id="575c2-115">X12 可选性</span><span class="sxs-lookup"><span data-stu-id="575c2-115">X12 Optionality</span></span>  
 <span data-ttu-id="575c2-116">在 X12 中，针对关系可选性的跨字段/段验证包括架构的规则中列出的一系列检查。</span><span class="sxs-lookup"><span data-stu-id="575c2-116">In X12, cross field/segment validation for Relational optionality includes a series of checks listed in rules in the schema.</span></span> <span data-ttu-id="575c2-117">每个规则由以下元素中\<xs:annotation\>元素：</span><span class="sxs-lookup"><span data-stu-id="575c2-117">Each rule is identified by the following element in an \<xs:annotation\> element:</span></span>  
  
```  
<b:Rule subjects="X12ConditionDesignatorX_<relational_condition>"…>  
```  
  
 <span data-ttu-id="575c2-118">"规则"元素中的关系条件表示什么进行了验证，该规则。</span><span class="sxs-lookup"><span data-stu-id="575c2-118">The relational condition in the “Rule” element indicates what is being validated by that rule.</span></span> <span data-ttu-id="575c2-119">该元素包含对其执行跨字段验证的主题的列表。</span><span class="sxs-lookup"><span data-stu-id="575c2-119">This element includes a list of subjects upon which the cross field validation is executed.</span></span> <span data-ttu-id="575c2-120">这些主题包括在下面的节点中：</span><span class="sxs-lookup"><span data-stu-id="575c2-120">The subjects are included in the following node:</span></span>  
  
```  
<b:Subject name="<subject>"/>  
```  
  
 <span data-ttu-id="575c2-121">下表显示了 X12 关系条件：</span><span class="sxs-lookup"><span data-stu-id="575c2-121">The following table shows the X12 relational conditions:</span></span>  
  
|<span data-ttu-id="575c2-122">子分类</span><span class="sxs-lookup"><span data-stu-id="575c2-122">Subclassification</span></span>|<span data-ttu-id="575c2-123">关系条件</span><span class="sxs-lookup"><span data-stu-id="575c2-123">Relational Condition</span></span>|<span data-ttu-id="575c2-124">Description</span><span class="sxs-lookup"><span data-stu-id="575c2-124">Description</span></span>|  
|-----------------------|--------------------------|-----------------|  
|<span data-ttu-id="575c2-125">成对</span><span class="sxs-lookup"><span data-stu-id="575c2-125">Paired</span></span>|<span data-ttu-id="575c2-126">X12ConditionDesignatorX_Paired</span><span class="sxs-lookup"><span data-stu-id="575c2-126">X12ConditionDesignatorX_Paired</span></span>|<span data-ttu-id="575c2-127">如果存在在关系条件中指定的任何主题元素，则指定的所有主题元素都必须存在。</span><span class="sxs-lookup"><span data-stu-id="575c2-127">If any of the subject elements specified in the relational condition is present, then all of the subject elements specified must be present.</span></span>|  
|<span data-ttu-id="575c2-128">必需</span><span class="sxs-lookup"><span data-stu-id="575c2-128">Required</span></span>|<span data-ttu-id="575c2-129">X12ConditionDesignatorX_Required</span><span class="sxs-lookup"><span data-stu-id="575c2-129">X12ConditionDesignatorX_Required</span></span>|<span data-ttu-id="575c2-130">必须至少存在一个在关系条件中指定的主题元素。</span><span class="sxs-lookup"><span data-stu-id="575c2-130">At least one of the subject elements specified in the relational condition must be present.</span></span>|  
|<span data-ttu-id="575c2-131">排除</span><span class="sxs-lookup"><span data-stu-id="575c2-131">Exclusion</span></span>|<span data-ttu-id="575c2-132">X12ConditionDesignatorX_Exclusion</span><span class="sxs-lookup"><span data-stu-id="575c2-132">X12ConditionDesignatorX_Exclusion</span></span>|<span data-ttu-id="575c2-133">可以至多存在一个在关系条件中指定的主题元素。</span><span class="sxs-lookup"><span data-stu-id="575c2-133">Not more than one of the subject elements specified in the relational condition may be present.</span></span>|  
|<span data-ttu-id="575c2-134">条件</span><span class="sxs-lookup"><span data-stu-id="575c2-134">Conditional</span></span>|<span data-ttu-id="575c2-135">X12ConditionDesignatorX_Conditional</span><span class="sxs-lookup"><span data-stu-id="575c2-135">X12ConditionDesignatorX_Conditional</span></span>|<span data-ttu-id="575c2-136">如果存在在关系条件中指定的第一个主题元素，则所有其他主题元素都必须存在。</span><span class="sxs-lookup"><span data-stu-id="575c2-136">If the first subject element specified in the relational condition is present, then all other subject elements must be present.</span></span> <span data-ttu-id="575c2-137">任何或所有未指定为条件中第一个元素的元素都可以在不要求存在第一个元素的情况下出现。</span><span class="sxs-lookup"><span data-stu-id="575c2-137">Any or all of the elements not specified as the first element in the condition may appear without requiring that the first element be present.</span></span> <span data-ttu-id="575c2-138">条件中的元素的顺序不需要与数据段中的数据元素的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="575c2-138">The order of the elements in the condition does not have to be the same as the order of the data elements in the data segments.</span></span>|  
|<span data-ttu-id="575c2-139">列表条件</span><span class="sxs-lookup"><span data-stu-id="575c2-139">List Conditional</span></span>|<span data-ttu-id="575c2-140">X12ConditionDesignatorX_List Conditional</span><span class="sxs-lookup"><span data-stu-id="575c2-140">X12ConditionDesignatorX_List Conditional</span></span>|<span data-ttu-id="575c2-141">如果存在在关系条件中指定的第一个主题元素，则必须至少存在一个其他主题元素。</span><span class="sxs-lookup"><span data-stu-id="575c2-141">If the first subject element specified in the relational condition is present, then at least one of the remaining subject elements must be present.</span></span> <span data-ttu-id="575c2-142">任何或所有未指定为条件中第一个元素的元素都可以在不要求存在第一个元素的情况下出现。</span><span class="sxs-lookup"><span data-stu-id="575c2-142">Any or all of the elements not specified as the first element in the condition may appear without requiring that the first element be present.</span></span> <span data-ttu-id="575c2-143">条件中的元素的顺序不需要与数据段中的数据元素的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="575c2-143">The order of the elements in the condition does not have to be the same as the order of the data elements in the data segments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="575c2-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="575c2-144">See Also</span></span>  
 [<span data-ttu-id="575c2-145">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="575c2-145">EDI Message Validation</span></span>](../core/edi-message-validation.md)