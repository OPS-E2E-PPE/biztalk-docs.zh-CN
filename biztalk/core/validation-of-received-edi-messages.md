---
title: "验证收到的 EDI 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c56a3c0-042e-4611-8131-d51098064f0f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcc48b343332ea6b402841ec5ed1f5c9af49b2dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validation-of-received-edi-messages"></a><span data-ttu-id="78578-102">验证收到的 EDI 消息</span><span class="sxs-lookup"><span data-stu-id="78578-102">Validation of Received EDI Messages</span></span>
<span data-ttu-id="78578-103">EDI 接收管道处理传入的消息时，将对信封和消息数据执行一系列验证。</span><span class="sxs-lookup"><span data-stu-id="78578-103">When the EDI receive pipeline processes an incoming message, it performs a series of validations on the envelope and message data.</span></span> <span data-ttu-id="78578-104">其中一些处理将始终执行，而有些处理将仅在您启用的情况下才执行。</span><span class="sxs-lookup"><span data-stu-id="78578-104">Some of these processes are always performed; some are performed only if you enable them.</span></span> <span data-ttu-id="78578-105">这些验证包括</span><span class="sxs-lookup"><span data-stu-id="78578-105">These validations include the following:</span></span>  
  
-   <span data-ttu-id="78578-106">**始终执行验证**:</span><span class="sxs-lookup"><span data-stu-id="78578-106">**The validations that are always performed are**:</span></span>  
  
    -   <span data-ttu-id="78578-107">验证交换信封的结构。</span><span class="sxs-lookup"><span data-stu-id="78578-107">Validation of the structure of the interchange envelope.</span></span>  
  
    -   <span data-ttu-id="78578-108">针对贸易合作伙伴协议（如果未定义任何协议，则为后备协议）进行的信封验证。</span><span class="sxs-lookup"><span data-stu-id="78578-108">Validation of the envelope against trading partner agreement (or fallback agreement if no agreement is defined).</span></span>  
  
    -   <span data-ttu-id="78578-109">根据控制架构执行信封的架构验证。</span><span class="sxs-lookup"><span data-stu-id="78578-109">Schema validation of the envelope against the control schema.</span></span>  
  
    -   <span data-ttu-id="78578-110">针对消息架构进行的事务集数据元素架构验证。</span><span class="sxs-lookup"><span data-stu-id="78578-110">Schema validation of the transaction-set data elements against the message schema.</span></span>  
  
    -   <span data-ttu-id="78578-111">根据 X12 标准提供的事务集-组映射验证单个组内事务集的类型。</span><span class="sxs-lookup"><span data-stu-id="78578-111">Validation of the types of transaction sets within a single group based on the transaction set -group mapping provided by X12 standards.</span></span>  
  
-   <span data-ttu-id="78578-112">**仅当启用时，才执行验证**:</span><span class="sxs-lookup"><span data-stu-id="78578-112">**The validations that are performed only if enabled are**:</span></span>  
  
    -   <span data-ttu-id="78578-113">对事务集数据元素执行 EDI 验证。</span><span class="sxs-lookup"><span data-stu-id="78578-113">EDI validation performed on transaction-set data elements.</span></span> <span data-ttu-id="78578-114">如果在协议属性中启用了此验证，则执行此验证。</span><span class="sxs-lookup"><span data-stu-id="78578-114">This is performed if enabled in the agreement properties.</span></span>  
  
    -   <span data-ttu-id="78578-115">对事务集数据元素执行扩展验证。</span><span class="sxs-lookup"><span data-stu-id="78578-115">Extended validation performed on transaction-set data elements.</span></span> <span data-ttu-id="78578-116">如果在协议属性中启用了此验证，则执行此验证。</span><span class="sxs-lookup"><span data-stu-id="78578-116">This is performed if enabled in the agreement properties.</span></span>  
  
    -   <span data-ttu-id="78578-117">对事务集数据元素进行跨字段验证（仅限 X12 编码消息）。</span><span class="sxs-lookup"><span data-stu-id="78578-117">Cross-field validation on transaction set data elements (X12-encoded messages only).</span></span> <span data-ttu-id="78578-118">如果启用消息架构中，执行此操作。</span><span class="sxs-lookup"><span data-stu-id="78578-118">This is performed if enabled in the message schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78578-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78578-119">See Also</span></span>  
 <span data-ttu-id="78578-120">[EDI 结构验证](../core/edi-structural-validation.md) </span><span class="sxs-lookup"><span data-stu-id="78578-120">[EDI Structural Validation](../core/edi-structural-validation.md) </span></span>  
 <span data-ttu-id="78578-121">[协议属性验证](../core/agreement-properties-validation.md) </span><span class="sxs-lookup"><span data-stu-id="78578-121">[Agreement Properties Validation](../core/agreement-properties-validation.md) </span></span>  
 <span data-ttu-id="78578-122">[EDI 类型 （数据元素） 验证](../core/edi-type-data-element-validation.md) </span><span class="sxs-lookup"><span data-stu-id="78578-122">[EDI Type (Data Element) Validation](../core/edi-type-data-element-validation.md) </span></span>  
 <span data-ttu-id="78578-123">[扩展 (BTS-XSD) 验证](../core/extended-bts-xsd-validation.md) </span><span class="sxs-lookup"><span data-stu-id="78578-123">[Extended (BTS-XSD) Validation](../core/extended-bts-xsd-validation.md) </span></span>  
 <span data-ttu-id="78578-124">[架构验证](../core/schema-validation2.md) </span><span class="sxs-lookup"><span data-stu-id="78578-124">[Schema Validation](../core/schema-validation2.md) </span></span>  
 [<span data-ttu-id="78578-125">交叉字段段验证</span><span class="sxs-lookup"><span data-stu-id="78578-125">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)