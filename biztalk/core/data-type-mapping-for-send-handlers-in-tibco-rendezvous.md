---
title: TIBCO Rendezvous 中的数据类型用于发送处理程序映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa1a9233-8781-45a8-9c55-a18ecaa0f456
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57987751e57353820f243d914da08f2fc57a73c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352666"
---
# <a name="data-type-mapping-for-send-handlers-in-tibco-rendezvous"></a><span data-ttu-id="b5b36-102">用于 TIBCO Rendezvous 中的发送处理程序的数据类型映射</span><span class="sxs-lookup"><span data-stu-id="b5b36-102">Data Type Mapping for Send Handlers in TIBCO Rendezvous</span></span>
<span data-ttu-id="b5b36-103">从 XML 架构类型到 TIBCO 集合类型的映射是仅当 TIBCO 集合提供类型信息 (xsi: type =)。</span><span class="sxs-lookup"><span data-stu-id="b5b36-103">The mapping from XML schema types to TIBCO Rendezvous types is only possible if TIBCO Rendezvous provides type information (xsi:type=).</span></span> <span data-ttu-id="b5b36-104">如果可能，任何不受支持的类型将映射到字符串。</span><span class="sxs-lookup"><span data-stu-id="b5b36-104">Any unsupported types are mapped to strings if it is possible.</span></span> <span data-ttu-id="b5b36-105">如果映射不可能实现，或在端口配置中禁用该选项，则生成错误。</span><span class="sxs-lookup"><span data-stu-id="b5b36-105">If mapping is not possible, or if the option is disabled in the port configuration, an error is generated.</span></span>  
  
## <a name="xml-schema-to-tibco-rendezvous-data-type-mapping"></a><span data-ttu-id="b5b36-106">XML 架构到 TIBCO 集合数据类型映射</span><span class="sxs-lookup"><span data-stu-id="b5b36-106">XML Schema to TIBCO Rendezvous Data Type Mapping</span></span>  
 <span data-ttu-id="b5b36-107">下表显示可能的映射从 XML 架构类型到 TIBCO 集合类型。</span><span class="sxs-lookup"><span data-stu-id="b5b36-107">The following table shows the possible mapping from XML schema types to TIBCO Rendezvous types.</span></span>  
  
|<span data-ttu-id="b5b36-108">XML 类型</span><span class="sxs-lookup"><span data-stu-id="b5b36-108">XML Type</span></span>|<span data-ttu-id="b5b36-109">TIBCO RV Type</span><span class="sxs-lookup"><span data-stu-id="b5b36-109">TIBCO RV Type</span></span>|  
|--------------|-------------------|  
||<span data-ttu-id="b5b36-110">TIBRVMSG_MSG</span><span class="sxs-lookup"><span data-stu-id="b5b36-110">TIBRVMSG_MSG</span></span>|  
||<span data-ttu-id="b5b36-111">TIBRVMSG_XML</span><span class="sxs-lookup"><span data-stu-id="b5b36-111">TIBRVMSG_XML</span></span>|  
|<span data-ttu-id="b5b36-112">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="b5b36-112">xsd:dateTime</span></span>|<span data-ttu-id="b5b36-113">TIBRVMSG_DATETIME</span><span class="sxs-lookup"><span data-stu-id="b5b36-113">TIBRVMSG_DATETIME</span></span>|  
|<span data-ttu-id="b5b36-114">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="b5b36-114">xsd:boolean</span></span>|<span data-ttu-id="b5b36-115">TIBRVMSG_BOOL</span><span class="sxs-lookup"><span data-stu-id="b5b36-115">TIBRVMSG_BOOL</span></span>|  
|<span data-ttu-id="b5b36-116">xsd:byte</span><span class="sxs-lookup"><span data-stu-id="b5b36-116">xsd:byte</span></span>|<span data-ttu-id="b5b36-117">TIBRVMSG_I8</span><span class="sxs-lookup"><span data-stu-id="b5b36-117">TIBRVMSG_I8</span></span>|  
|<span data-ttu-id="b5b36-118">xsd:short</span><span class="sxs-lookup"><span data-stu-id="b5b36-118">xsd:short</span></span>|<span data-ttu-id="b5b36-119">TIBRVMSG_I16</span><span class="sxs-lookup"><span data-stu-id="b5b36-119">TIBRVMSG_I16</span></span>|  
|<span data-ttu-id="b5b36-120">xsd:int</span><span class="sxs-lookup"><span data-stu-id="b5b36-120">xsd:int</span></span>|<span data-ttu-id="b5b36-121">TIBRVMSG_I32</span><span class="sxs-lookup"><span data-stu-id="b5b36-121">TIBRVMSG_I32</span></span>|  
|<span data-ttu-id="b5b36-122">xsd:long</span><span class="sxs-lookup"><span data-stu-id="b5b36-122">xsd:long</span></span>|<span data-ttu-id="b5b36-123">TIBRVMSG_I64</span><span class="sxs-lookup"><span data-stu-id="b5b36-123">TIBRVMSG_I64</span></span>|  
|<span data-ttu-id="b5b36-124">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="b5b36-124">xsd:unsignedByte</span></span>|<span data-ttu-id="b5b36-125">TIBRVMSG_U8</span><span class="sxs-lookup"><span data-stu-id="b5b36-125">TIBRVMSG_U8</span></span>|  
|<span data-ttu-id="b5b36-126">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="b5b36-126">xsd:unsignedShort</span></span>|<span data-ttu-id="b5b36-127">TIBRVMSG_U16</span><span class="sxs-lookup"><span data-stu-id="b5b36-127">TIBRVMSG_U16</span></span>|  
|<span data-ttu-id="b5b36-128">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="b5b36-128">xsd:unsignedInt</span></span>|<span data-ttu-id="b5b36-129">TIBRVMSG_U32</span><span class="sxs-lookup"><span data-stu-id="b5b36-129">TIBRVMSG_U32</span></span>|  
|<span data-ttu-id="b5b36-130">xsd:unsignedLong</span><span class="sxs-lookup"><span data-stu-id="b5b36-130">xsd:unsignedLong</span></span>|<span data-ttu-id="b5b36-131">TIBRVMSG_U64</span><span class="sxs-lookup"><span data-stu-id="b5b36-131">TIBRVMSG_U64</span></span>|  
|<span data-ttu-id="b5b36-132">xsd:float</span><span class="sxs-lookup"><span data-stu-id="b5b36-132">xsd:float</span></span>|<span data-ttu-id="b5b36-133">TIBRVMSG_F32</span><span class="sxs-lookup"><span data-stu-id="b5b36-133">TIBRVMSG_F32</span></span>|  
|<span data-ttu-id="b5b36-134">xsd:double</span><span class="sxs-lookup"><span data-stu-id="b5b36-134">xsd:double</span></span>|<span data-ttu-id="b5b36-135">TIBRVMSG_F64</span><span class="sxs-lookup"><span data-stu-id="b5b36-135">TIBRVMSG_F64</span></span>|  
|<span data-ttu-id="b5b36-136">tibrv:IPaddress</span><span class="sxs-lookup"><span data-stu-id="b5b36-136">tibrv:IPaddress</span></span>|<span data-ttu-id="b5b36-137">TIBRVMSG_IPADDR32</span><span class="sxs-lookup"><span data-stu-id="b5b36-137">TIBRVMSG_IPADDR32</span></span>|  
|<span data-ttu-id="b5b36-138">tibrv:IPport</span><span class="sxs-lookup"><span data-stu-id="b5b36-138">tibrv:IPport</span></span>|<span data-ttu-id="b5b36-139">TIBRVMSG_IPPORT16</span><span class="sxs-lookup"><span data-stu-id="b5b36-139">TIBRVMSG_IPPORT16</span></span>|  
|<span data-ttu-id="b5b36-140">tibrv:arrayOfByte</span><span class="sxs-lookup"><span data-stu-id="b5b36-140">tibrv:arrayOfByte</span></span>|<span data-ttu-id="b5b36-141">TIBRVMSG_I8ARRAY</span><span class="sxs-lookup"><span data-stu-id="b5b36-141">TIBRVMSG_I8ARRAY</span></span>|  
|<span data-ttu-id="b5b36-142">tibrv:arrayOfShort</span><span class="sxs-lookup"><span data-stu-id="b5b36-142">tibrv:arrayOfShort</span></span>|<span data-ttu-id="b5b36-143">TIBRVMSG_I16ARRAY</span><span class="sxs-lookup"><span data-stu-id="b5b36-143">TIBRVMSG_I16ARRAY</span></span>|  
|<span data-ttu-id="b5b36-144">tibrv:arrayOfInt</span><span class="sxs-lookup"><span data-stu-id="b5b36-144">tibrv:arrayOfInt</span></span>|<span data-ttu-id="b5b36-145">TIBRVMSG_I32ARRAY</span><span class="sxs-lookup"><span data-stu-id="b5b36-145">TIBRVMSG_I32ARRAY</span></span>|  
|<span data-ttu-id="b5b36-146">tibrv:arrayOfLong</span><span class="sxs-lookup"><span data-stu-id="b5b36-146">tibrv:arrayOfLong</span></span>|<span data-ttu-id="b5b36-147">TIBRVMSG_I64ARRAY</span><span class="sxs-lookup"><span data-stu-id="b5b36-147">TIBRVMSG_I64ARRAY</span></span>|  
|<span data-ttu-id="b5b36-148">tibrv:arrayOfUnsignedByte</span><span class="sxs-lookup"><span data-stu-id="b5b36-148">tibrv:arrayOfUnsignedByte</span></span>|<span data-ttu-id="b5b36-149">TIBRVMSG_U8ARRAY</span><span class="sxs-lookup"><span data-stu-id="b5b36-149">TIBRVMSG_U8ARRAY</span></span>|  
|<span data-ttu-id="b5b36-150">tibrv:arrayOfUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="b5b36-150">tibrv:arrayOfUnsignedShort</span></span>|<span data-ttu-id="b5b36-151">TIBRVMSG_U16ARRAY</span><span class="sxs-lookup"><span data-stu-id="b5b36-151">TIBRVMSG_U16ARRAY</span></span>|  
|<span data-ttu-id="b5b36-152">tibrv:arrayOfUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="b5b36-152">tibrv:arrayOfUnsignedInt</span></span>|<span data-ttu-id="b5b36-153">TIBRVMSG_U32ARRAY</span><span class="sxs-lookup"><span data-stu-id="b5b36-153">TIBRVMSG_U32ARRAY</span></span>|  
|<span data-ttu-id="b5b36-154">tibrv:arrayOfUnsignedLong</span><span class="sxs-lookup"><span data-stu-id="b5b36-154">tibrv:arrayOfUnsignedLong</span></span>|<span data-ttu-id="b5b36-155">TIBRVMSG_U64ARRAY</span><span class="sxs-lookup"><span data-stu-id="b5b36-155">TIBRVMSG_U64ARRAY</span></span>|  
|<span data-ttu-id="b5b36-156">tibrv:arrayOfFloat</span><span class="sxs-lookup"><span data-stu-id="b5b36-156">tibrv:arrayOfFloat</span></span>|<span data-ttu-id="b5b36-157">TIBRVMSG_F32ARRAY</span><span class="sxs-lookup"><span data-stu-id="b5b36-157">TIBRVMSG_F32ARRAY</span></span>|  
|<span data-ttu-id="b5b36-158">tibrv:arrayOfDouble</span><span class="sxs-lookup"><span data-stu-id="b5b36-158">tibrv:arrayOfDouble</span></span>|<span data-ttu-id="b5b36-159">TIBRVMSG_F64ARRAY</span><span class="sxs-lookup"><span data-stu-id="b5b36-159">TIBRVMSG_F64ARRAY</span></span>|  
|<span data-ttu-id="b5b36-160">其他任何内容-具有调试消息</span><span class="sxs-lookup"><span data-stu-id="b5b36-160">Anything else - with a debug message</span></span>|<span data-ttu-id="b5b36-161">TIBRVMSG_STRING 日志。</span><span class="sxs-lookup"><span data-stu-id="b5b36-161">TIBRVMSG_STRING the log.</span></span>|  
  
 <span data-ttu-id="b5b36-162">因为用于 TIBCO Rendezvous 的 BizTalk 适配器不具有访问架构，在从 BizTalk Server 传输到 TIBCO 集合时，必须提供 XML`xsi:type`任何非字符串字段的特性。</span><span class="sxs-lookup"><span data-stu-id="b5b36-162">Because BizTalk Adapter for TIBCO Rendezvous does not have access to a schema, when you transmit from BizTalk Server to TIBCO Rendezvous, you must provide the XML `xsi:type` attribute for any non-string field.</span></span> <span data-ttu-id="b5b36-163">适配器使用该信息生成 TIBCO Rendezvous 消息中的相应消息字段类型。</span><span class="sxs-lookup"><span data-stu-id="b5b36-163">The adapter uses that information to generate the appropriate message field type in the TIBCO Rendezvous message.</span></span>  
  
## <a name="message-mapping-example"></a><span data-ttu-id="b5b36-164">消息映射示例</span><span class="sxs-lookup"><span data-stu-id="b5b36-164">Message Mapping Example</span></span>  
 <span data-ttu-id="b5b36-165">下面的示例演示如何映射到 TIBCO Rendezvous 从 BizTalk Server 消息。</span><span class="sxs-lookup"><span data-stu-id="b5b36-165">The following example demonstrates mapping a message from BizTalk Server to TIBCO Rendezvous.</span></span> <span data-ttu-id="b5b36-166">请参阅有关如何映射类型信息的数据类型映射表。</span><span class="sxs-lookup"><span data-stu-id="b5b36-166">Refer to the data type mapping table for information about how types are mapped.</span></span>  
  
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
  
 <span data-ttu-id="b5b36-167">在前面的消息生成为结构化 TIBCO Rendezvous 消息后，它会具有六个字段的顶级 TibcoMsg 实例。</span><span class="sxs-lookup"><span data-stu-id="b5b36-167">After the previous message is generated as a structured TIBCO Rendezvous message, it would be a top-level TibcoMsg instance with six fields.</span></span> <span data-ttu-id="b5b36-168">最后一个字段是子消息，两个字段组成的数组类型 (item 元素不映射到 TIBCO 集合消息字段，但一个类型的消息字段中的元素`array`)。</span><span class="sxs-lookup"><span data-stu-id="b5b36-168">The last fields are a sub-message, composed of two fields of array types (the 'item' elements are not mapped to TIBCO Rendezvous Message fields, but to elements in one Message Field of type `array`).</span></span> <span data-ttu-id="b5b36-169">无类型的 MarketCap 字段将作为字符串消息字段发送。</span><span class="sxs-lookup"><span data-stu-id="b5b36-169">The MarketCap field, having no type specification, would be sent as a string message field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b36-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5b36-170">See Also</span></span>  
 [<span data-ttu-id="b5b36-171">创建 TIBCO Rendezvous 发送处理程序</span><span class="sxs-lookup"><span data-stu-id="b5b36-171">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)