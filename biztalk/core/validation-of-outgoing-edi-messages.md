---
title: 验证对传出的 EDI 消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 491303c0-b585-409e-a289-a2f6f9f82469
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 946e90eb58c9b81e0cd7fa9bf2c02cc49af021ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287989"
---
# <a name="validation-of-outgoing-edi-messages"></a><span data-ttu-id="bd2bf-102">传出 EDI 消息的验证</span><span class="sxs-lookup"><span data-stu-id="bd2bf-102">Validation of Outgoing EDI Messages</span></span>
<span data-ttu-id="bd2bf-103">EDI 发送管道处理要发送的消息时，将对信封和消息数据执行一系列验证。</span><span class="sxs-lookup"><span data-stu-id="bd2bf-103">When the EDI send pipeline processes a message to be sent, it performs a series of validations on the envelope and message data.</span></span> <span data-ttu-id="bd2bf-104">其中一些处理将始终执行，而有些处理将仅在您启用的情况下才执行。</span><span class="sxs-lookup"><span data-stu-id="bd2bf-104">Some of these processes are always performed; some are performed only if you enable them.</span></span> <span data-ttu-id="bd2bf-105">这些验证包括</span><span class="sxs-lookup"><span data-stu-id="bd2bf-105">These validations include the following:</span></span>  
  
-   <span data-ttu-id="bd2bf-106">针对消息架构进行的事务集数据元素架构验证。</span><span class="sxs-lookup"><span data-stu-id="bd2bf-106">Schema validation of the transaction-set data elements against the message schema.</span></span> <span data-ttu-id="bd2bf-107">该验证将始终执行。</span><span class="sxs-lookup"><span data-stu-id="bd2bf-107">This is always performed.</span></span>  
  
-   <span data-ttu-id="bd2bf-108">对事务集数据元素进行跨字段验证（仅限 X12 编码消息）。</span><span class="sxs-lookup"><span data-stu-id="bd2bf-108">Cross-field validation on transaction set data elements (X12-encoded messages only).</span></span> <span data-ttu-id="bd2bf-109">如果在消息架构中启用了此验证，则执行此验证。</span><span class="sxs-lookup"><span data-stu-id="bd2bf-109">This is performed if it is enabled in the message schema.</span></span>  
  
-   <span data-ttu-id="bd2bf-110">对事务集数据元素执行 EDI 验证。</span><span class="sxs-lookup"><span data-stu-id="bd2bf-110">EDI validation performed on transaction-set data elements.</span></span> <span data-ttu-id="bd2bf-111">如果启用协议中的属性，执行此操作。</span><span class="sxs-lookup"><span data-stu-id="bd2bf-111">This is performed if enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="bd2bf-112">对事务集数据元素执行扩展验证。</span><span class="sxs-lookup"><span data-stu-id="bd2bf-112">Extended validation performed on transaction-set data elements.</span></span> <span data-ttu-id="bd2bf-113">如果启用协议中的属性，执行此操作。</span><span class="sxs-lookup"><span data-stu-id="bd2bf-113">This is performed if enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="bd2bf-114">按照 X12 标准验证基于事务集的单个组（组映射）内的事务集。</span><span class="sxs-lookup"><span data-stu-id="bd2bf-114">Validation of the transaction sets within a single group based on the transaction set – group mapping, according to X12 standards.</span></span> <span data-ttu-id="bd2bf-115">执行此操作仅当**入站批处理选项**属性设置为**保留交换-出错时暂停交换**或**保留交换-挂起事务在错误上设置**。</span><span class="sxs-lookup"><span data-stu-id="bd2bf-115">This is performed only when the **Inbound batch processing option** property is set to **Preserve Interchange - suspend Interchange on Error** or **Preserve Interchange - suspend Transaction Sets on Error**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd2bf-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd2bf-116">See Also</span></span>  
 <span data-ttu-id="bd2bf-117">[EDI 结构验证](../core/edi-structural-validation.md) </span><span class="sxs-lookup"><span data-stu-id="bd2bf-117">[EDI Structural Validation](../core/edi-structural-validation.md) </span></span>  
 <span data-ttu-id="bd2bf-118">[协议属性验证](../core/agreement-properties-validation.md) </span><span class="sxs-lookup"><span data-stu-id="bd2bf-118">[Agreement Properties Validation](../core/agreement-properties-validation.md) </span></span>  
 <span data-ttu-id="bd2bf-119">[EDI 类型 （数据元素） 验证](../core/edi-type-data-element-validation.md) </span><span class="sxs-lookup"><span data-stu-id="bd2bf-119">[EDI Type (Data Element) Validation](../core/edi-type-data-element-validation.md) </span></span>  
 <span data-ttu-id="bd2bf-120">[扩展 (BTS-XSD) 验证](../core/extended-bts-xsd-validation.md) </span><span class="sxs-lookup"><span data-stu-id="bd2bf-120">[Extended (BTS-XSD) Validation](../core/extended-bts-xsd-validation.md) </span></span>  
 <span data-ttu-id="bd2bf-121">[架构验证](../core/schema-validation2.md) </span><span class="sxs-lookup"><span data-stu-id="bd2bf-121">[Schema Validation](../core/schema-validation2.md) </span></span>  
 [<span data-ttu-id="bd2bf-122">交叉字段段验证</span><span class="sxs-lookup"><span data-stu-id="bd2bf-122">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)