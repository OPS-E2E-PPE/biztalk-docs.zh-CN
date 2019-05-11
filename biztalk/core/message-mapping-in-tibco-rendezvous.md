---
title: 消息 TIBCO Rendezvous 中的映射 |Microsoft Docs
description: 消息字段和 TIBCO Rendezvous 的 BizTalk 适配器中的 xml 消息映射
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
ms.openlocfilehash: e8d3b287bc1475227231301275500fca32e90da6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65326205"
---
# <a name="message-mapping-in-tibco-rendezvous"></a><span data-ttu-id="bd07c-103">TIBCO Rendezvous 中消息映射</span><span class="sxs-lookup"><span data-stu-id="bd07c-103">Message Mapping in TIBCO Rendezvous</span></span>
<span data-ttu-id="bd07c-104">TIBCO Rendezvous 消息由标头信息和一组消息字段组成。</span><span class="sxs-lookup"><span data-stu-id="bd07c-104">TIBCO Rendezvous messages are composed of header information and a set of message fields.</span></span> <span data-ttu-id="bd07c-105">标头信息直接映射到消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="bd07c-105">The header information is directly mapped to message context properties.</span></span>  
  
## <a name="message-field-elements"></a><span data-ttu-id="bd07c-106">消息字段元素</span><span class="sxs-lookup"><span data-stu-id="bd07c-106">Message Field Elements</span></span>  
 <span data-ttu-id="bd07c-107">消息字段组成的以下元素：</span><span class="sxs-lookup"><span data-stu-id="bd07c-107">A message field is composed of the following elements:</span></span>  
  
|<span data-ttu-id="bd07c-108">元素</span><span class="sxs-lookup"><span data-stu-id="bd07c-108">Element</span></span>|<span data-ttu-id="bd07c-109">Description</span><span class="sxs-lookup"><span data-stu-id="bd07c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd07c-110">**名称**</span><span class="sxs-lookup"><span data-stu-id="bd07c-110">**Name**</span></span>|<span data-ttu-id="bd07c-111">字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="bd07c-111">Character string.</span></span> <span data-ttu-id="bd07c-112">无需一条消息中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bd07c-112">Does not have to be unique in a message.</span></span>|  
|<span data-ttu-id="bd07c-113">**Identifier**</span><span class="sxs-lookup"><span data-stu-id="bd07c-113">**Identifier**</span></span>|<span data-ttu-id="bd07c-114">短整数。</span><span class="sxs-lookup"><span data-stu-id="bd07c-114">Short integer.</span></span> <span data-ttu-id="bd07c-115">在消息中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="bd07c-115">Unique in a message.</span></span> <span data-ttu-id="bd07c-116">隐式限制到 65535 之间的消息字段数。</span><span class="sxs-lookup"><span data-stu-id="bd07c-116">Implicitly limits the number of message fields to 65535.</span></span> <span data-ttu-id="bd07c-117">标识符的作用域为消息 （或子消息）。</span><span class="sxs-lookup"><span data-stu-id="bd07c-117">The scope of the identifier is the message (or sub message).</span></span> <span data-ttu-id="bd07c-118">相同的标识符可以使用其自身是两个子消息中包含消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="bd07c-118">The same identifier can be used in two sub-messages, which are themselves part of a containing message.</span></span>|  
|<span data-ttu-id="bd07c-119">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="bd07c-119">**Value**</span></span>|<span data-ttu-id="bd07c-120">消息字段数据。</span><span class="sxs-lookup"><span data-stu-id="bd07c-120">The message field data.</span></span>|  
|<span data-ttu-id="bd07c-121">**Count**</span><span class="sxs-lookup"><span data-stu-id="bd07c-121">**Count**</span></span>|<span data-ttu-id="bd07c-122">（数组情况下） 的项目数</span><span class="sxs-lookup"><span data-stu-id="bd07c-122">Number of items (in the case of an array)</span></span>|  
|<span data-ttu-id="bd07c-123">**类型**</span><span class="sxs-lookup"><span data-stu-id="bd07c-123">**Type**</span></span>|<span data-ttu-id="bd07c-124">消息字段的类型。</span><span class="sxs-lookup"><span data-stu-id="bd07c-124">The type of the message field.</span></span>|  
  
### <a name="mapping-process"></a><span data-ttu-id="bd07c-125">映射过程</span><span class="sxs-lookup"><span data-stu-id="bd07c-125">Mapping Process</span></span>  
 <span data-ttu-id="bd07c-126">TIBCO Rendezvous 结构化消息按以下方式映射到 XML 元素：</span><span class="sxs-lookup"><span data-stu-id="bd07c-126">TIBCO Rendezvous structured messages are mapped to XML elements in the following way:</span></span>  
  
-   <span data-ttu-id="bd07c-127">**名称**用作元素名称。</span><span class="sxs-lookup"><span data-stu-id="bd07c-127">**Name** is used as the element name.</span></span> <span data-ttu-id="bd07c-128">TIBCO Rendezvous 字段名称可能包含无效的 XML 元素名称中使用的字符。</span><span class="sxs-lookup"><span data-stu-id="bd07c-128">The TIBCO Rendezvous field name may contain characters that are not valid for use in XML element names.</span></span> <span data-ttu-id="bd07c-129">适配器生成有效的字符 XML 和 TIBCO Rendezvous 之间的映射的结构化消息。</span><span class="sxs-lookup"><span data-stu-id="bd07c-129">The adapter generates valid character mappings between XML and TIBCO Rendezvous structured messages.</span></span>  
  
-   <span data-ttu-id="bd07c-130">**标识符**置于 id 属性中。</span><span class="sxs-lookup"><span data-stu-id="bd07c-130">**Identifier** is put into an ‘id’ attribute.</span></span>  
  
-   <span data-ttu-id="bd07c-131">**值**包含元素的正文的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="bd07c-131">**Value** contains a string representation that is the body of the element.</span></span>  
  
-   <span data-ttu-id="bd07c-132">**计数**将被忽略。</span><span class="sxs-lookup"><span data-stu-id="bd07c-132">**Count** is ignored.</span></span>  
  
-   <span data-ttu-id="bd07c-133">**类型**信息放入生成的元素的 xsi: type 属性。</span><span class="sxs-lookup"><span data-stu-id="bd07c-133">**Type** information is put into an xsi:type attribute for the generated element.</span></span>  
  
     <span data-ttu-id="bd07c-134">有关详细信息，请参阅[TIBCO Rendezvous 中的接收处理程序的数据类型映射](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)。</span><span class="sxs-lookup"><span data-stu-id="bd07c-134">For more information, see [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd07c-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd07c-135">See Also</span></span>  
 <span data-ttu-id="bd07c-136">[TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="bd07c-136">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="bd07c-137">创建 TIBCO Rendezvou 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="bd07c-137">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)