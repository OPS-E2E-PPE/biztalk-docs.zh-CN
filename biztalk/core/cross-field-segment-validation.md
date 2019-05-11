---
title: 跨字段-段验证 |Microsoft Docs
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
ms.openlocfilehash: e842c9376a6f143bb0979930c3d4239a355904c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389842"
---
# <a name="cross-field-segment-validation"></a><span data-ttu-id="7ddd1-102">跨字段-段验证</span><span class="sxs-lookup"><span data-stu-id="7ddd1-102">Cross Field-Segment Validation</span></span>
<span data-ttu-id="7ddd1-103">EDI 接收管道和 EDI 发送管道可以对 X12 编码消息中的事务集数据元素执行跨字段/段验证。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-103">The EDI receive pipeline and EDI send pipeline can perform cross field/segment validation on transaction-set data elements in X12-encoded messages.</span></span> <span data-ttu-id="7ddd1-104">在 X12 中，此验证称为关系条件。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-104">This validation is called relational conditions in X12.</span></span> <span data-ttu-id="7ddd1-105">跨字段验证通过批注表示，并因此，与 EDI 验证。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-105">Cross field validation is expressed through annotations, and as a result, it is related to EDI validation.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="7ddd1-106">不支持 EDIFACT 依赖规则。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-106">does not support EDIFACT dependency rules.</span></span>  
  
 <span data-ttu-id="7ddd1-107">对于 X12 编码的消息，X12ConditionDesignator_Check 标志设置为"是"消息架构中启用此验证。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-107">For X12-encoded messages, you enable this validation by setting the X12ConditionDesignator_Check flag in the message schema to "Yes".</span></span> <span data-ttu-id="7ddd1-108">此标志为批注的架构"appinfo"部分中。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-108">This flag is in an annotation in the “appinfo” section of the schema.</span></span> <span data-ttu-id="7ddd1-109">默认情况下，此标志设置为"否"，并跨字段/段验证未启用适用于 X12 架构。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-109">By default this flag is set to "No" and cross field\segment validation is not enabled for X12 schemas.</span></span> <span data-ttu-id="7ddd1-110">对于 HIPAA 架构默认值设置为"是"并启用跨字段/段验证。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-110">For HIPAA schemas the default is set to “Yes” and cross field\segment validation is enabled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ddd1-111">跨字段/段验证是不同于 EDI 数据元素验证和扩展 (BTS-XSD) 验证。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-111">Cross-field/segment validation is distinct from both EDI data element validation and extended (BTS-XSD) validation.</span></span> <span data-ttu-id="7ddd1-112">而不执行跨字段/段验证，可以执行 EDI 数据元素验证和/或扩展的验证，而不执行 EDI 数据元素验证和/或扩展的验证，可以执行跨字段/段验证。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-112">EDI data element validation and/or extended validation can be performed without performing cross-field/segment validation, and cross-field/segment validation can be performed without performing EDI data element validation and/or extended validation.</span></span>  
  
 <span data-ttu-id="7ddd1-113">在 X12 的可选性包括必需 (M)、 可选 (O) 和关系 (R) （跨字段验证）。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-113">Optionality in X12 consists of Mandatory (M), Optional (O), and Relational (R) (cross field validation).</span></span> <span data-ttu-id="7ddd1-114">如果可选性为必需，复合类型中的至少一个组件数据元素必须是值。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-114">When the optionality is Mandatory, at least one component data element in composite types must be valued.</span></span>  
  
## <a name="x12-optionality"></a><span data-ttu-id="7ddd1-115">X12 可选性</span><span class="sxs-lookup"><span data-stu-id="7ddd1-115">X12 Optionality</span></span>  
 <span data-ttu-id="7ddd1-116">在 X12 中，跨字段/段验证针对关系可选性包括一系列检查架构中的规则中列出。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-116">In X12, cross field/segment validation for Relational optionality includes a series of checks listed in rules in the schema.</span></span> <span data-ttu-id="7ddd1-117">每个规则由以下元素中标识\<xs:annotation\>元素：</span><span class="sxs-lookup"><span data-stu-id="7ddd1-117">Each rule is identified by the following element in an \<xs:annotation\> element:</span></span>  
  
```  
<b:Rule subjects="X12ConditionDesignatorX_<relational_condition>"…>  
```  
  
 <span data-ttu-id="7ddd1-118">"规则"元素中的关系条件指示什么进行了验证，该规则。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-118">The relational condition in the “Rule” element indicates what is being validated by that rule.</span></span> <span data-ttu-id="7ddd1-119">此元素包括在其执行跨字段验证的使用者的列表。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-119">This element includes a list of subjects upon which the cross field validation is executed.</span></span> <span data-ttu-id="7ddd1-120">这些主题包括以下节点中：</span><span class="sxs-lookup"><span data-stu-id="7ddd1-120">The subjects are included in the following node:</span></span>  
  
```  
<b:Subject name="<subject>"/>  
```  
  
 <span data-ttu-id="7ddd1-121">下表显示了 X12 关系条件：</span><span class="sxs-lookup"><span data-stu-id="7ddd1-121">The following table shows the X12 relational conditions:</span></span>  
  
|<span data-ttu-id="7ddd1-122">细分类</span><span class="sxs-lookup"><span data-stu-id="7ddd1-122">Subclassification</span></span>|<span data-ttu-id="7ddd1-123">关系条件</span><span class="sxs-lookup"><span data-stu-id="7ddd1-123">Relational Condition</span></span>|<span data-ttu-id="7ddd1-124">Description</span><span class="sxs-lookup"><span data-stu-id="7ddd1-124">Description</span></span>|  
|-----------------------|--------------------------|-----------------|  
|<span data-ttu-id="7ddd1-125">配对</span><span class="sxs-lookup"><span data-stu-id="7ddd1-125">Paired</span></span>|<span data-ttu-id="7ddd1-126">X12ConditionDesignatorX_Paired</span><span class="sxs-lookup"><span data-stu-id="7ddd1-126">X12ConditionDesignatorX_Paired</span></span>|<span data-ttu-id="7ddd1-127">如果存在任何关系条件中指定的主题元素，则必须存在所有指定的主题元素。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-127">If any of the subject elements specified in the relational condition is present, then all of the subject elements specified must be present.</span></span>|  
|<span data-ttu-id="7ddd1-128">Required</span><span class="sxs-lookup"><span data-stu-id="7ddd1-128">Required</span></span>|<span data-ttu-id="7ddd1-129">X12ConditionDesignatorX_Required</span><span class="sxs-lookup"><span data-stu-id="7ddd1-129">X12ConditionDesignatorX_Required</span></span>|<span data-ttu-id="7ddd1-130">至少一个在关系条件中指定的主题元素必须存在。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-130">At least one of the subject elements specified in the relational condition must be present.</span></span>|  
|<span data-ttu-id="7ddd1-131">排除</span><span class="sxs-lookup"><span data-stu-id="7ddd1-131">Exclusion</span></span>|<span data-ttu-id="7ddd1-132">X12ConditionDesignatorX_Exclusion</span><span class="sxs-lookup"><span data-stu-id="7ddd1-132">X12ConditionDesignatorX_Exclusion</span></span>|<span data-ttu-id="7ddd1-133">不能超过一的关系条件中指定的主题元素可能会出现。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-133">Not more than one of the subject elements specified in the relational condition may be present.</span></span>|  
|<span data-ttu-id="7ddd1-134">条件</span><span class="sxs-lookup"><span data-stu-id="7ddd1-134">Conditional</span></span>|<span data-ttu-id="7ddd1-135">X12ConditionDesignatorX_Conditional</span><span class="sxs-lookup"><span data-stu-id="7ddd1-135">X12ConditionDesignatorX_Conditional</span></span>|<span data-ttu-id="7ddd1-136">如果存在在关系条件中指定的第一个主题元素，则所有其他主题元素必须存在。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-136">If the first subject element specified in the relational condition is present, then all other subject elements must be present.</span></span> <span data-ttu-id="7ddd1-137">未指定在条件中的第一个元素的元素的任意或全部可能出现不带要求的第一个元素必须存在。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-137">Any or all of the elements not specified as the first element in the condition may appear without requiring that the first element be present.</span></span> <span data-ttu-id="7ddd1-138">在条件中元素的顺序不需要的数据段中的数据元素的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-138">The order of the elements in the condition does not have to be the same as the order of the data elements in the data segments.</span></span>|  
|<span data-ttu-id="7ddd1-139">列表条件</span><span class="sxs-lookup"><span data-stu-id="7ddd1-139">List Conditional</span></span>|<span data-ttu-id="7ddd1-140">X12ConditionDesignatorX_List 条件</span><span class="sxs-lookup"><span data-stu-id="7ddd1-140">X12ConditionDesignatorX_List Conditional</span></span>|<span data-ttu-id="7ddd1-141">如果存在在关系条件中指定的第一个主题元素，则必须存在至少一个其他主题元素。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-141">If the first subject element specified in the relational condition is present, then at least one of the remaining subject elements must be present.</span></span> <span data-ttu-id="7ddd1-142">未指定在条件中的第一个元素的元素的任意或全部可能出现不带要求的第一个元素必须存在。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-142">Any or all of the elements not specified as the first element in the condition may appear without requiring that the first element be present.</span></span> <span data-ttu-id="7ddd1-143">在条件中元素的顺序不需要的数据段中的数据元素的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="7ddd1-143">The order of the elements in the condition does not have to be the same as the order of the data elements in the data segments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ddd1-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ddd1-144">See Also</span></span>  
 [<span data-ttu-id="7ddd1-145">EDI 消息验证</span><span class="sxs-lookup"><span data-stu-id="7ddd1-145">EDI Message Validation</span></span>](../core/edi-message-validation.md)