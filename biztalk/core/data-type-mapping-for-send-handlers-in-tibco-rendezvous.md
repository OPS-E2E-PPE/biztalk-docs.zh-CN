---
title: "TIBCO 集合中的数据类型的发送处理程序映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML schemas, mapping to Redevous types
- message mapping, examples
- XML schemas, schema types
- data type mapping, send handlers
- examples, message mapping
- send handlers, data type mapping
ms.assetid: fa1a9233-8781-45a8-9c55-a18ecaa0f456
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6c54cb7ae684aa2f617ca615ed55703e331de46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-mapping-for-send-handlers-in-tibco-rendezvous"></a><span data-ttu-id="2316b-102">TIBCO Rendezvous 中用于发送处理程序的数据类型映射</span><span class="sxs-lookup"><span data-stu-id="2316b-102">Data Type Mapping for Send Handlers in TIBCO Rendezvous</span></span>
<span data-ttu-id="2316b-103">仅当 TIBCO 集合提供类型信息 (xsi:type=) 时，从 XML 架构类型到 TIBCO 集合类型的映射才有可能。</span><span class="sxs-lookup"><span data-stu-id="2316b-103">The mapping from XML schema types to TIBCO Rendezvous types is only possible if TIBCO Rendezvous provides type information (xsi:type=).</span></span> <span data-ttu-id="2316b-104">如果可能，会将任何不受支持的类型映射到字符串。</span><span class="sxs-lookup"><span data-stu-id="2316b-104">Any unsupported types are mapped to strings if it is possible.</span></span> <span data-ttu-id="2316b-105">如果映射不可能，或者该选项已在端口配置中被禁用，则会生成错误。</span><span class="sxs-lookup"><span data-stu-id="2316b-105">If mapping is not possible, or if the option is disabled in the port configuration, an error is generated.</span></span>  
  
## <a name="xml-schema-to-tibco-rendezvous-data-type-mapping"></a><span data-ttu-id="2316b-106">XML 架构到 TIBCO 集合数据类型映射</span><span class="sxs-lookup"><span data-stu-id="2316b-106">XML Schema to TIBCO Rendezvous Data Type Mapping</span></span>  
 <span data-ttu-id="2316b-107">下表显示从 XML 架构类型到 TIBCO 集合类型的可能映射。</span><span class="sxs-lookup"><span data-stu-id="2316b-107">The following table shows the possible mapping from XML schema types to TIBCO Rendezvous types.</span></span>  
  
|<span data-ttu-id="2316b-108">XML 类型</span><span class="sxs-lookup"><span data-stu-id="2316b-108">XML Type</span></span>|<span data-ttu-id="2316b-109">TIBCO RV 类型</span><span class="sxs-lookup"><span data-stu-id="2316b-109">TIBCO RV Type</span></span>|  
|--------------|-------------------|  
||<span data-ttu-id="2316b-110">TIBRVMSG_MSG</span><span class="sxs-lookup"><span data-stu-id="2316b-110">TIBRVMSG_MSG</span></span>|  
||<span data-ttu-id="2316b-111">TIBRVMSG_XML</span><span class="sxs-lookup"><span data-stu-id="2316b-111">TIBRVMSG_XML</span></span>|  
|<span data-ttu-id="2316b-112">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="2316b-112">xsd:dateTime</span></span>|<span data-ttu-id="2316b-113">TIBRVMSG_DATETIME</span><span class="sxs-lookup"><span data-stu-id="2316b-113">TIBRVMSG_DATETIME</span></span>|  
|<span data-ttu-id="2316b-114">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="2316b-114">xsd:boolean</span></span>|<span data-ttu-id="2316b-115">TIBRVMSG_BOOL</span><span class="sxs-lookup"><span data-stu-id="2316b-115">TIBRVMSG_BOOL</span></span>|  
|<span data-ttu-id="2316b-116">xsd:byte</span><span class="sxs-lookup"><span data-stu-id="2316b-116">xsd:byte</span></span>|<span data-ttu-id="2316b-117">TIBRVMSG_I8</span><span class="sxs-lookup"><span data-stu-id="2316b-117">TIBRVMSG_I8</span></span>|  
|<span data-ttu-id="2316b-118">xsd:short</span><span class="sxs-lookup"><span data-stu-id="2316b-118">xsd:short</span></span>|<span data-ttu-id="2316b-119">TIBRVMSG_I16</span><span class="sxs-lookup"><span data-stu-id="2316b-119">TIBRVMSG_I16</span></span>|  
|<span data-ttu-id="2316b-120">xsd:int</span><span class="sxs-lookup"><span data-stu-id="2316b-120">xsd:int</span></span>|<span data-ttu-id="2316b-121">TIBRVMSG_I32</span><span class="sxs-lookup"><span data-stu-id="2316b-121">TIBRVMSG_I32</span></span>|  
|<span data-ttu-id="2316b-122">xsd:long</span><span class="sxs-lookup"><span data-stu-id="2316b-122">xsd:long</span></span>|<span data-ttu-id="2316b-123">TIBRVMSG_I64</span><span class="sxs-lookup"><span data-stu-id="2316b-123">TIBRVMSG_I64</span></span>|  
|<span data-ttu-id="2316b-124">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="2316b-124">xsd:unsignedByte</span></span>|<span data-ttu-id="2316b-125">TIBRVMSG_U8</span><span class="sxs-lookup"><span data-stu-id="2316b-125">TIBRVMSG_U8</span></span>|  
|<span data-ttu-id="2316b-126">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="2316b-126">xsd:unsignedShort</span></span>|<span data-ttu-id="2316b-127">TIBRVMSG_U16</span><span class="sxs-lookup"><span data-stu-id="2316b-127">TIBRVMSG_U16</span></span>|  
|<span data-ttu-id="2316b-128">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="2316b-128">xsd:unsignedInt</span></span>|<span data-ttu-id="2316b-129">TIBRVMSG_U32</span><span class="sxs-lookup"><span data-stu-id="2316b-129">TIBRVMSG_U32</span></span>|  
|<span data-ttu-id="2316b-130">xsd:unsignedLong</span><span class="sxs-lookup"><span data-stu-id="2316b-130">xsd:unsignedLong</span></span>|<span data-ttu-id="2316b-131">TIBRVMSG_U64</span><span class="sxs-lookup"><span data-stu-id="2316b-131">TIBRVMSG_U64</span></span>|  
|<span data-ttu-id="2316b-132">xsd:float</span><span class="sxs-lookup"><span data-stu-id="2316b-132">xsd:float</span></span>|<span data-ttu-id="2316b-133">TIBRVMSG_F32</span><span class="sxs-lookup"><span data-stu-id="2316b-133">TIBRVMSG_F32</span></span>|  
|<span data-ttu-id="2316b-134">xsd:double</span><span class="sxs-lookup"><span data-stu-id="2316b-134">xsd:double</span></span>|<span data-ttu-id="2316b-135">TIBRVMSG_F64</span><span class="sxs-lookup"><span data-stu-id="2316b-135">TIBRVMSG_F64</span></span>|  
|<span data-ttu-id="2316b-136">tibrv:IPaddress</span><span class="sxs-lookup"><span data-stu-id="2316b-136">tibrv:IPaddress</span></span>|<span data-ttu-id="2316b-137">TIBRVMSG_IPADDR32</span><span class="sxs-lookup"><span data-stu-id="2316b-137">TIBRVMSG_IPADDR32</span></span>|  
|<span data-ttu-id="2316b-138">tibrv:IPport</span><span class="sxs-lookup"><span data-stu-id="2316b-138">tibrv:IPport</span></span>|<span data-ttu-id="2316b-139">TIBRVMSG_IPPORT16</span><span class="sxs-lookup"><span data-stu-id="2316b-139">TIBRVMSG_IPPORT16</span></span>|  
|<span data-ttu-id="2316b-140">tibrv:arrayOfByte</span><span class="sxs-lookup"><span data-stu-id="2316b-140">tibrv:arrayOfByte</span></span>|<span data-ttu-id="2316b-141">TIBRVMSG_I8ARRAY</span><span class="sxs-lookup"><span data-stu-id="2316b-141">TIBRVMSG_I8ARRAY</span></span>|  
|<span data-ttu-id="2316b-142">tibrv:arrayOfShort</span><span class="sxs-lookup"><span data-stu-id="2316b-142">tibrv:arrayOfShort</span></span>|<span data-ttu-id="2316b-143">TIBRVMSG_I16ARRAY</span><span class="sxs-lookup"><span data-stu-id="2316b-143">TIBRVMSG_I16ARRAY</span></span>|  
|<span data-ttu-id="2316b-144">tibrv:arrayOfInt</span><span class="sxs-lookup"><span data-stu-id="2316b-144">tibrv:arrayOfInt</span></span>|<span data-ttu-id="2316b-145">TIBRVMSG_I32ARRAY</span><span class="sxs-lookup"><span data-stu-id="2316b-145">TIBRVMSG_I32ARRAY</span></span>|  
|<span data-ttu-id="2316b-146">tibrv:arrayOfLong</span><span class="sxs-lookup"><span data-stu-id="2316b-146">tibrv:arrayOfLong</span></span>|<span data-ttu-id="2316b-147">TIBRVMSG_I64ARRAY</span><span class="sxs-lookup"><span data-stu-id="2316b-147">TIBRVMSG_I64ARRAY</span></span>|  
|<span data-ttu-id="2316b-148">tibrv:arrayOfUnsignedByte</span><span class="sxs-lookup"><span data-stu-id="2316b-148">tibrv:arrayOfUnsignedByte</span></span>|<span data-ttu-id="2316b-149">TIBRVMSG_U8ARRAY</span><span class="sxs-lookup"><span data-stu-id="2316b-149">TIBRVMSG_U8ARRAY</span></span>|  
|<span data-ttu-id="2316b-150">tibrv:arrayOfUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="2316b-150">tibrv:arrayOfUnsignedShort</span></span>|<span data-ttu-id="2316b-151">TIBRVMSG_U16ARRAY</span><span class="sxs-lookup"><span data-stu-id="2316b-151">TIBRVMSG_U16ARRAY</span></span>|  
|<span data-ttu-id="2316b-152">tibrv:arrayOfUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="2316b-152">tibrv:arrayOfUnsignedInt</span></span>|<span data-ttu-id="2316b-153">TIBRVMSG_U32ARRAY</span><span class="sxs-lookup"><span data-stu-id="2316b-153">TIBRVMSG_U32ARRAY</span></span>|  
|<span data-ttu-id="2316b-154">tibrv:arrayOfUnsignedLong</span><span class="sxs-lookup"><span data-stu-id="2316b-154">tibrv:arrayOfUnsignedLong</span></span>|<span data-ttu-id="2316b-155">TIBRVMSG_U64ARRAY</span><span class="sxs-lookup"><span data-stu-id="2316b-155">TIBRVMSG_U64ARRAY</span></span>|  
|<span data-ttu-id="2316b-156">tibrv:arrayOfFloat</span><span class="sxs-lookup"><span data-stu-id="2316b-156">tibrv:arrayOfFloat</span></span>|<span data-ttu-id="2316b-157">TIBRVMSG_F32ARRAY</span><span class="sxs-lookup"><span data-stu-id="2316b-157">TIBRVMSG_F32ARRAY</span></span>|  
|<span data-ttu-id="2316b-158">tibrv:arrayOfDouble</span><span class="sxs-lookup"><span data-stu-id="2316b-158">tibrv:arrayOfDouble</span></span>|<span data-ttu-id="2316b-159">TIBRVMSG_F64ARRAY</span><span class="sxs-lookup"><span data-stu-id="2316b-159">TIBRVMSG_F64ARRAY</span></span>|  
|<span data-ttu-id="2316b-160">其他任何内容 - 具有调试消息</span><span class="sxs-lookup"><span data-stu-id="2316b-160">Anything else - with a debug message</span></span>|<span data-ttu-id="2316b-161">TIBRVMSG_STRING 日志。</span><span class="sxs-lookup"><span data-stu-id="2316b-161">TIBRVMSG_STRING the log.</span></span>|  
  
 <span data-ttu-id="2316b-162">由于 TIBCO 集合的 BizTalk 适配器没有对架构的访问权限，因此当您从 BizTalk Server 传输到 TIBCO 集合时，必须为任何非字符串字段提供 XML `xsi:type` 属性。</span><span class="sxs-lookup"><span data-stu-id="2316b-162">Because BizTalk Adapter for TIBCO Rendezvous does not have access to a schema, when you transmit from BizTalk Server to TIBCO Rendezvous, you must provide the XML `xsi:type` attribute for any non-string field.</span></span> <span data-ttu-id="2316b-163">适配器使用该信息生成 TIBCO 集合消息中的相应消息字段类型。</span><span class="sxs-lookup"><span data-stu-id="2316b-163">The adapter uses that information to generate the appropriate message field type in the TIBCO Rendezvous message.</span></span>  
  
## <a name="message-mapping-example"></a><span data-ttu-id="2316b-164">消息映射示例</span><span class="sxs-lookup"><span data-stu-id="2316b-164">Message Mapping Example</span></span>  
 <span data-ttu-id="2316b-165">下面的示例演示从 BizTalk Server 到 TIBCO 集合的消息映射。</span><span class="sxs-lookup"><span data-stu-id="2316b-165">The following example demonstrates mapping a message from BizTalk Server to TIBCO Rendezvous.</span></span> <span data-ttu-id="2316b-166">有关如何映射类型的信息，请参考数据类型映射表。</span><span class="sxs-lookup"><span data-stu-id="2316b-166">Refer to the data type mapping table for information about how types are mapped.</span></span>  
  
```  
<ns:QuoteUpdate xmlns:xsi http://www.w3.org/2001/XMLSchema-instance"  
xmlns:xsd http://www.w3.org/2001/XMLSchema"  
xmlns:tibrv="http://schemas.microsoft.com/TibcoRendezvous/Types"  
xmlns:ns="some namespace for this message [value not important, unless the schema is also used for receive ports]">  
  
<ns:SymbolName id=1 xsi:type="xsd:string">MSFT</ns:SymbolName>  
  
<ns:LastTrade id=2 xsi:type="xsd:double">28.40</ns:LastTrade>   
<ns:DayLow id=3 xsi:type="xsd:double">28.25</ns:DayLow>  
  
```  
  
|||  
|-|-|  
|`<ns:DayHigh`|`id=4 xsi:type="xsd:double">28.40</ns:DayHigh>`|  
|`<ns:MarketCap`|`id=10>262575234981</ns:MarketCap>`|  
|`<ns:Bids`|`id=100 xsi:type="tibrv:message">`|  
  
```  
<ns:TopBids id=1 xsi:type="tibrv:arrayOfDouble">  
<item>28.40</item>  
<item>28.39</item>  
<item>28.39</item>  
<item>28.39</item>  
<item>28.38</item>  
  
</ns:TopBids>  
  
<ns:BidsSize id=2 xsi:type="tibrv:arrayOfLong">  
<item>500</item>  
<item>1000</item>  
<item>100</item>  
<item>100</item>  
<item>2000</item>  
  
</ns:BidsSize>  
</ns:Bids>  
</ns:QuoteUpdate>  
  
```  
  
 <span data-ttu-id="2316b-167">将以前的消息生成为结构化的 TIBCO 集合消息之后，该消息将成为具有六个字段的顶级 TibcoMsg 实例。</span><span class="sxs-lookup"><span data-stu-id="2316b-167">After the previous message is generated as a structured TIBCO Rendezvous message, it would be a top-level TibcoMsg instance with six fields.</span></span> <span data-ttu-id="2316b-168">最后字段是子消息，由两个数组类型的字段组成（“item”元素未映射到 TIBCO 集合消息字段，而是映射到类型为 `array` 的一个消息字段中的元素）。</span><span class="sxs-lookup"><span data-stu-id="2316b-168">The last fields are a sub-message, composed of two fields of array types (the 'item' elements are not mapped to TIBCO Rendezvous Message fields, but to elements in one Message Field of type `array`).</span></span> <span data-ttu-id="2316b-169">未指定类型的 MarketCap 字段将作为字符串消息字段发送。</span><span class="sxs-lookup"><span data-stu-id="2316b-169">The MarketCap field, having no type specification, would be sent as a string message field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2316b-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2316b-170">See Also</span></span>  
 [<span data-ttu-id="2316b-171">创建 TIBCO 会合发送处理程序</span><span class="sxs-lookup"><span data-stu-id="2316b-171">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)