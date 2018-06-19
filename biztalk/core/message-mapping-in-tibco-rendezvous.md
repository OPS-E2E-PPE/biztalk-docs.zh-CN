---
title: 消息映射中 TIBCO 会合 |Microsoft 文档
description: 消息字段和 TIBCO 会合到 BizTalk 适配器中的 XML 消息映射
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 62793bec-f076-425c-b25e-c4be5bd93cc8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb80ea4f908aa50dc32755c333aa3ccf2ea4db91
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014948"
---
# <a name="message-mapping-in-tibco-rendezvous"></a><span data-ttu-id="cd690-103">TIBCO Rendezvous 中消息映射</span><span class="sxs-lookup"><span data-stu-id="cd690-103">Message Mapping in TIBCO Rendezvous</span></span>
<span data-ttu-id="cd690-104">TIBCO Rendezvous 消息由标头信息和一组消息字段组成。</span><span class="sxs-lookup"><span data-stu-id="cd690-104">TIBCO Rendezvous messages are composed of header information and a set of message fields.</span></span> <span data-ttu-id="cd690-105">标头信息直接映射到消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="cd690-105">The header information is directly mapped to message context properties.</span></span>  
  
## <a name="message-field-elements"></a><span data-ttu-id="cd690-106">消息字段元素</span><span class="sxs-lookup"><span data-stu-id="cd690-106">Message Field Elements</span></span>  
 <span data-ttu-id="cd690-107">消息字段由下列元素组成：</span><span class="sxs-lookup"><span data-stu-id="cd690-107">A message field is composed of the following elements:</span></span>  
  
|<span data-ttu-id="cd690-108">元素</span><span class="sxs-lookup"><span data-stu-id="cd690-108">Element</span></span>|<span data-ttu-id="cd690-109">Description</span><span class="sxs-lookup"><span data-stu-id="cd690-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd690-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="cd690-110">**Name**</span></span>|<span data-ttu-id="cd690-111">字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="cd690-111">Character string.</span></span> <span data-ttu-id="cd690-112">在消息中不必唯一。</span><span class="sxs-lookup"><span data-stu-id="cd690-112">Does not have to be unique in a message.</span></span>|  
|<span data-ttu-id="cd690-113">**Identifier**</span><span class="sxs-lookup"><span data-stu-id="cd690-113">**Identifier**</span></span>|<span data-ttu-id="cd690-114">短整数。</span><span class="sxs-lookup"><span data-stu-id="cd690-114">Short integer.</span></span> <span data-ttu-id="cd690-115">在消息中唯一。</span><span class="sxs-lookup"><span data-stu-id="cd690-115">Unique in a message.</span></span> <span data-ttu-id="cd690-116">隐式限制到 65535 之间的消息字段数。</span><span class="sxs-lookup"><span data-stu-id="cd690-116">Implicitly limits the number of message fields to 65535.</span></span> <span data-ttu-id="cd690-117">标识符的范围为消息 （或 sub 消息）。</span><span class="sxs-lookup"><span data-stu-id="cd690-117">The scope of the identifier is the message (or sub message).</span></span> <span data-ttu-id="cd690-118">相同的标识符可以用于两个子消息中，它们自身属于包含消息。</span><span class="sxs-lookup"><span data-stu-id="cd690-118">The same identifier can be used in two sub-messages, which are themselves part of a containing message.</span></span>|  
|<span data-ttu-id="cd690-119">**值**</span><span class="sxs-lookup"><span data-stu-id="cd690-119">**Value**</span></span>|<span data-ttu-id="cd690-120">消息字段数据。</span><span class="sxs-lookup"><span data-stu-id="cd690-120">The message field data.</span></span>|  
|<span data-ttu-id="cd690-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="cd690-121">**Count**</span></span>|<span data-ttu-id="cd690-122">项目数（数组情况下）</span><span class="sxs-lookup"><span data-stu-id="cd690-122">Number of items (in the case of an array)</span></span>|  
|<span data-ttu-id="cd690-123">**类型**</span><span class="sxs-lookup"><span data-stu-id="cd690-123">**Type**</span></span>|<span data-ttu-id="cd690-124">消息字段的类型。</span><span class="sxs-lookup"><span data-stu-id="cd690-124">The type of the message field.</span></span>|  
  
### <a name="mapping-process"></a><span data-ttu-id="cd690-125">映射进程</span><span class="sxs-lookup"><span data-stu-id="cd690-125">Mapping Process</span></span>  
 <span data-ttu-id="cd690-126">TIBCO Rendezvous 结构化消息按以下方式映射到 XML 元素：</span><span class="sxs-lookup"><span data-stu-id="cd690-126">TIBCO Rendezvous structured messages are mapped to XML elements in the following way:</span></span>  
  
-   <span data-ttu-id="cd690-127">**名称**用作元素名称。</span><span class="sxs-lookup"><span data-stu-id="cd690-127">**Name** is used as the element name.</span></span> <span data-ttu-id="cd690-128">TIBCO Rendezvous 字段名称可能包含在 XML 元素名称中使用时无效的字符。</span><span class="sxs-lookup"><span data-stu-id="cd690-128">The TIBCO Rendezvous field name may contain characters that are not valid for use in XML element names.</span></span> <span data-ttu-id="cd690-129">适配器在 XML 和 TIBCO Rendezvous 结构化消息之间生成有效的字符映射。</span><span class="sxs-lookup"><span data-stu-id="cd690-129">The adapter generates valid character mappings between XML and TIBCO Rendezvous structured messages.</span></span>  
  
-   <span data-ttu-id="cd690-130">**标识符**放入 'id' 属性。</span><span class="sxs-lookup"><span data-stu-id="cd690-130">**Identifier** is put into an ‘id’ attribute.</span></span>  
  
-   <span data-ttu-id="cd690-131">**值**包含正文的元素的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="cd690-131">**Value** contains a string representation that is the body of the element.</span></span>  
  
-   <span data-ttu-id="cd690-132">**计数**将被忽略。</span><span class="sxs-lookup"><span data-stu-id="cd690-132">**Count** is ignored.</span></span>  
  
-   <span data-ttu-id="cd690-133">**类型**信息放入所生成元素的 xsi: type 属性。</span><span class="sxs-lookup"><span data-stu-id="cd690-133">**Type** information is put into an xsi:type attribute for the generated element.</span></span>  
  
     <span data-ttu-id="cd690-134">有关详细信息，请参阅[Data Type Mapping for 接收 TIBCO 集合中的处理程序](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)。</span><span class="sxs-lookup"><span data-stu-id="cd690-134">For more information, see [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd690-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd690-135">See Also</span></span>  
 <span data-ttu-id="cd690-136">[TIBCO 会合概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="cd690-136">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="cd690-137">创建 TIBCO Rendezvou 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="cd690-137">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)