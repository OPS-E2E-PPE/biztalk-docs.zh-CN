---
title: 验证收到的 EDI 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c56a3c0-042e-4611-8131-d51098064f0f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1af8946cf94747f74db25d1854d2157a36370cbc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292594"
---
# <a name="validation-of-received-edi-messages"></a><span data-ttu-id="d805a-102">验证收到的 EDI 消息</span><span class="sxs-lookup"><span data-stu-id="d805a-102">Validation of Received EDI Messages</span></span>
<span data-ttu-id="d805a-103">当 EDI 接收管道处理传入的消息时，它对信封和消息数据执行一系列验证。</span><span class="sxs-lookup"><span data-stu-id="d805a-103">When the EDI receive pipeline processes an incoming message, it performs a series of validations on the envelope and message data.</span></span> <span data-ttu-id="d805a-104">始终执行这些过程的一些;一些执行只能在启用它们。</span><span class="sxs-lookup"><span data-stu-id="d805a-104">Some of these processes are always performed; some are performed only if you enable them.</span></span> <span data-ttu-id="d805a-105">这些验证包括：</span><span class="sxs-lookup"><span data-stu-id="d805a-105">These validations include the following:</span></span>  
  
-   <span data-ttu-id="d805a-106">**始终执行的验证**:</span><span class="sxs-lookup"><span data-stu-id="d805a-106">**The validations that are always performed are**:</span></span>  
  
    -   <span data-ttu-id="d805a-107">验证交换信封的结构。</span><span class="sxs-lookup"><span data-stu-id="d805a-107">Validation of the structure of the interchange envelope.</span></span>  
  
    -   <span data-ttu-id="d805a-108">针对贸易合作伙伴协议 （或如果未定义协议的后备协议） 的信封验证。</span><span class="sxs-lookup"><span data-stu-id="d805a-108">Validation of the envelope against trading partner agreement (or fallback agreement if no agreement is defined).</span></span>  
  
    -   <span data-ttu-id="d805a-109">针对控制架构进行的信封架构验证。</span><span class="sxs-lookup"><span data-stu-id="d805a-109">Schema validation of the envelope against the control schema.</span></span>  
  
    -   <span data-ttu-id="d805a-110">针对消息架构进行的事务集数据元素架构验证。</span><span class="sxs-lookup"><span data-stu-id="d805a-110">Schema validation of the transaction-set data elements against the message schema.</span></span>  
  
    -   <span data-ttu-id="d805a-111">验证类型的事务集内基于事务的单个组设置-组映射提供的 X12 标准。</span><span class="sxs-lookup"><span data-stu-id="d805a-111">Validation of the types of transaction sets within a single group based on the transaction set -group mapping provided by X12 standards.</span></span>  
  
-   <span data-ttu-id="d805a-112">**仅当启用时，才会执行的验证**:</span><span class="sxs-lookup"><span data-stu-id="d805a-112">**The validations that are performed only if enabled are**:</span></span>  
  
    -   <span data-ttu-id="d805a-113">对事务集数据元素执行 EDI 验证。</span><span class="sxs-lookup"><span data-stu-id="d805a-113">EDI validation performed on transaction-set data elements.</span></span> <span data-ttu-id="d805a-114">如果在协议属性中启用了，执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d805a-114">This is performed if enabled in the agreement properties.</span></span>  
  
    -   <span data-ttu-id="d805a-115">对事务集数据元素执行扩展的验证。</span><span class="sxs-lookup"><span data-stu-id="d805a-115">Extended validation performed on transaction-set data elements.</span></span> <span data-ttu-id="d805a-116">如果在协议属性中启用了，执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d805a-116">This is performed if enabled in the agreement properties.</span></span>  
  
    -   <span data-ttu-id="d805a-117">跨字段验证对事务集数据元素 （仅 X12 编码消息）。</span><span class="sxs-lookup"><span data-stu-id="d805a-117">Cross-field validation on transaction set data elements (X12-encoded messages only).</span></span> <span data-ttu-id="d805a-118">如果启用消息架构中，执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d805a-118">This is performed if enabled in the message schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d805a-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d805a-119">See Also</span></span>  
 <span data-ttu-id="d805a-120">[EDI 结构验证](../core/edi-structural-validation.md) </span><span class="sxs-lookup"><span data-stu-id="d805a-120">[EDI Structural Validation](../core/edi-structural-validation.md) </span></span>  
 <span data-ttu-id="d805a-121">[协议属性验证](../core/agreement-properties-validation.md) </span><span class="sxs-lookup"><span data-stu-id="d805a-121">[Agreement Properties Validation](../core/agreement-properties-validation.md) </span></span>  
 <span data-ttu-id="d805a-122">[EDI 类型 （数据元素） 验证](../core/edi-type-data-element-validation.md) </span><span class="sxs-lookup"><span data-stu-id="d805a-122">[EDI Type (Data Element) Validation](../core/edi-type-data-element-validation.md) </span></span>  
 <span data-ttu-id="d805a-123">[扩展 (BTS-XSD) 验证](../core/extended-bts-xsd-validation.md) </span><span class="sxs-lookup"><span data-stu-id="d805a-123">[Extended (BTS-XSD) Validation](../core/extended-bts-xsd-validation.md) </span></span>  
 <span data-ttu-id="d805a-124">[架构验证](../core/schema-validation2.md) </span><span class="sxs-lookup"><span data-stu-id="d805a-124">[Schema Validation](../core/schema-validation2.md) </span></span>  
 [<span data-ttu-id="d805a-125">跨字段-段验证</span><span class="sxs-lookup"><span data-stu-id="d805a-125">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)