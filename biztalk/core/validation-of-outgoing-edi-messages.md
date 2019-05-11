---
title: 验证传出 EDI 消息 |Microsoft Docs
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
ms.openlocfilehash: 01e0afed109f3ea03e863e2813ca4f58d289eaa0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295658"
---
# <a name="validation-of-outgoing-edi-messages"></a><span data-ttu-id="142b8-102">验证传出 EDI 消息</span><span class="sxs-lookup"><span data-stu-id="142b8-102">Validation of Outgoing EDI Messages</span></span>
<span data-ttu-id="142b8-103">当 EDI 发送管道处理要发送的消息时，它对信封和消息数据执行一系列验证。</span><span class="sxs-lookup"><span data-stu-id="142b8-103">When the EDI send pipeline processes a message to be sent, it performs a series of validations on the envelope and message data.</span></span> <span data-ttu-id="142b8-104">始终执行这些过程的一些;一些执行只能在启用它们。</span><span class="sxs-lookup"><span data-stu-id="142b8-104">Some of these processes are always performed; some are performed only if you enable them.</span></span> <span data-ttu-id="142b8-105">这些验证包括：</span><span class="sxs-lookup"><span data-stu-id="142b8-105">These validations include the following:</span></span>  
  
-   <span data-ttu-id="142b8-106">针对消息架构进行的事务集数据元素架构验证。</span><span class="sxs-lookup"><span data-stu-id="142b8-106">Schema validation of the transaction-set data elements against the message schema.</span></span> <span data-ttu-id="142b8-107">始终执行此操作。</span><span class="sxs-lookup"><span data-stu-id="142b8-107">This is always performed.</span></span>  
  
-   <span data-ttu-id="142b8-108">跨字段验证对事务集数据元素 （仅 X12 编码消息）。</span><span class="sxs-lookup"><span data-stu-id="142b8-108">Cross-field validation on transaction set data elements (X12-encoded messages only).</span></span> <span data-ttu-id="142b8-109">如果启用消息架构中，执行此操作。</span><span class="sxs-lookup"><span data-stu-id="142b8-109">This is performed if it is enabled in the message schema.</span></span>  
  
-   <span data-ttu-id="142b8-110">对事务集数据元素执行 EDI 验证。</span><span class="sxs-lookup"><span data-stu-id="142b8-110">EDI validation performed on transaction-set data elements.</span></span> <span data-ttu-id="142b8-111">如果协议中启用属性，执行此操作。</span><span class="sxs-lookup"><span data-stu-id="142b8-111">This is performed if enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="142b8-112">对事务集数据元素执行扩展的验证。</span><span class="sxs-lookup"><span data-stu-id="142b8-112">Extended validation performed on transaction-set data elements.</span></span> <span data-ttu-id="142b8-113">如果协议中启用属性，执行此操作。</span><span class="sxs-lookup"><span data-stu-id="142b8-113">This is performed if enabled in agreement properties.</span></span>  
  
-   <span data-ttu-id="142b8-114">验证事务集内基于事务集-组映射，根据 X12 的单个组标准。</span><span class="sxs-lookup"><span data-stu-id="142b8-114">Validation of the transaction sets within a single group based on the transaction set – group mapping, according to X12 standards.</span></span> <span data-ttu-id="142b8-115">执行此操作时，才**入站批处理选项**属性设置为**保留交换-出错时挂起交换**或**保留交换-挂起事务出错时设置**。</span><span class="sxs-lookup"><span data-stu-id="142b8-115">This is performed only when the **Inbound batch processing option** property is set to **Preserve Interchange - suspend Interchange on Error** or **Preserve Interchange - suspend Transaction Sets on Error**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142b8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="142b8-116">See Also</span></span>  
 <span data-ttu-id="142b8-117">[EDI 结构验证](../core/edi-structural-validation.md) </span><span class="sxs-lookup"><span data-stu-id="142b8-117">[EDI Structural Validation](../core/edi-structural-validation.md) </span></span>  
 <span data-ttu-id="142b8-118">[协议属性验证](../core/agreement-properties-validation.md) </span><span class="sxs-lookup"><span data-stu-id="142b8-118">[Agreement Properties Validation](../core/agreement-properties-validation.md) </span></span>  
 <span data-ttu-id="142b8-119">[EDI 类型 （数据元素） 验证](../core/edi-type-data-element-validation.md) </span><span class="sxs-lookup"><span data-stu-id="142b8-119">[EDI Type (Data Element) Validation](../core/edi-type-data-element-validation.md) </span></span>  
 <span data-ttu-id="142b8-120">[扩展 (BTS-XSD) 验证](../core/extended-bts-xsd-validation.md) </span><span class="sxs-lookup"><span data-stu-id="142b8-120">[Extended (BTS-XSD) Validation](../core/extended-bts-xsd-validation.md) </span></span>  
 <span data-ttu-id="142b8-121">[架构验证](../core/schema-validation2.md) </span><span class="sxs-lookup"><span data-stu-id="142b8-121">[Schema Validation](../core/schema-validation2.md) </span></span>  
 [<span data-ttu-id="142b8-122">跨字段-段验证</span><span class="sxs-lookup"><span data-stu-id="142b8-122">Cross Field-Segment Validation</span></span>](../core/cross-field-segment-validation.md)