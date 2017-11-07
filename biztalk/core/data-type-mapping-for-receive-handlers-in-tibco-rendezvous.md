---
title: "数据类型映射，以接收来自 TIBCO 会合 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36908a94-3c0d-466e-aa49-f674ba4a26af
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcb17ceac0c323bba7a6f25cff0d07473b6d7fa3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="data-type-mapping-for-receive-handlers-in-tibco-rendezvous"></a><span data-ttu-id="db28f-102">TIBCO Rendezvous 中用于接收处理程序的数据类型映射</span><span class="sxs-lookup"><span data-stu-id="db28f-102">Data Type Mapping for Receive Handlers in TIBCO Rendezvous</span></span>
<span data-ttu-id="db28f-103">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器将 TIBCO RV 类型映射到 XML 架构类型，如下表中指定。</span><span class="sxs-lookup"><span data-stu-id="db28f-103">Microsoft BizTalk Adapter for TIBCO Rendezvous maps TIBCO RV types to XML Schema types as specified in the following table.</span></span>  
  
## <a name="tibco-rv-to-xml-data-type-mapping"></a><span data-ttu-id="db28f-104">TIBCO RV 到 XML 数据类型映射</span><span class="sxs-lookup"><span data-stu-id="db28f-104">TIBCO RV to XML Data Type Mapping</span></span>  
  
|<span data-ttu-id="db28f-105">TIBCO RV 类型</span><span class="sxs-lookup"><span data-stu-id="db28f-105">TIBCO RV Type</span></span>|<span data-ttu-id="db28f-106">XML 架构类型</span><span class="sxs-lookup"><span data-stu-id="db28f-106">XML Schema Type</span></span>|<span data-ttu-id="db28f-107">注释</span><span class="sxs-lookup"><span data-stu-id="db28f-107">Comments</span></span>|  
|-------------------|---------------------|--------------|  
|<span data-ttu-id="db28f-108">TIBRVMSG_MSG</span><span class="sxs-lookup"><span data-stu-id="db28f-108">TIBRVMSG_MSG</span></span>|<span data-ttu-id="db28f-109">tibrv:message</span><span class="sxs-lookup"><span data-stu-id="db28f-109">tibrv:message</span></span>|<span data-ttu-id="db28f-110">从整个消息构造的完全 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="db28f-110">Complete XML document constructed from entire message.</span></span>|  
|<span data-ttu-id="db28f-111">TIBRVMSG_XML</span><span class="sxs-lookup"><span data-stu-id="db28f-111">TIBRVMSG_XML</span></span>|<span data-ttu-id="db28f-112">tibrv:rawxml</span><span class="sxs-lookup"><span data-stu-id="db28f-112">tibrv:rawxml</span></span>|<span data-ttu-id="db28f-113">从字节数组构造的 XML 文档（不由适配器解释）。</span><span class="sxs-lookup"><span data-stu-id="db28f-113">XML Document constructed from the array of bytes (not interpreted by the adapter).</span></span>|  
|<span data-ttu-id="db28f-114">TIBRVMSG_DATETIME</span><span class="sxs-lookup"><span data-stu-id="db28f-114">TIBRVMSG_DATETIME</span></span>|<span data-ttu-id="db28f-115">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="db28f-115">xsd:dateTime</span></span>|<span data-ttu-id="db28f-116">适配器使用 System.Xml.XmlConvert 类在 XML 架构 `dateTime` 和 `System.DateTime` 实例之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="db28f-116">The adapter uses the System.Xml.XmlConvert class to convert between XML Schema `dateTime` and `System.DateTime` instances.</span></span>|  
|<span data-ttu-id="db28f-117">TIBRVMSG_OPAQUE</span><span class="sxs-lookup"><span data-stu-id="db28f-117">TIBRVMSG_OPAQUE</span></span>|<span data-ttu-id="db28f-118">xsd:base64Binary</span><span class="sxs-lookup"><span data-stu-id="db28f-118">xsd:base64Binary</span></span>||  
|<span data-ttu-id="db28f-119">TIBRVMSG_STRING</span><span class="sxs-lookup"><span data-stu-id="db28f-119">TIBRVMSG_STRING</span></span>|<span data-ttu-id="db28f-120">xsd:string</span><span class="sxs-lookup"><span data-stu-id="db28f-120">xsd:string</span></span>||  
|<span data-ttu-id="db28f-121">TIBRVMSG_BOOL</span><span class="sxs-lookup"><span data-stu-id="db28f-121">TIBRVMSG_BOOL</span></span>|<span data-ttu-id="db28f-122">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="db28f-122">xsd:boolean</span></span>||  
|<span data-ttu-id="db28f-123">TIBRVMSG_I8</span><span class="sxs-lookup"><span data-stu-id="db28f-123">TIBRVMSG_I8</span></span>|<span data-ttu-id="db28f-124">xsd:byte</span><span class="sxs-lookup"><span data-stu-id="db28f-124">xsd:byte</span></span>||  
|<span data-ttu-id="db28f-125">TIBRVMSG_I16</span><span class="sxs-lookup"><span data-stu-id="db28f-125">TIBRVMSG_I16</span></span>|<span data-ttu-id="db28f-126">xsd:short</span><span class="sxs-lookup"><span data-stu-id="db28f-126">xsd:short</span></span>||  
|<span data-ttu-id="db28f-127">TIBRVMSG_I32</span><span class="sxs-lookup"><span data-stu-id="db28f-127">TIBRVMSG_I32</span></span>|<span data-ttu-id="db28f-128">xsd:int</span><span class="sxs-lookup"><span data-stu-id="db28f-128">xsd:int</span></span>||  
|<span data-ttu-id="db28f-129">TIBRVMSG_I64</span><span class="sxs-lookup"><span data-stu-id="db28f-129">TIBRVMSG_I64</span></span>|<span data-ttu-id="db28f-130">xsd:long</span><span class="sxs-lookup"><span data-stu-id="db28f-130">xsd:long</span></span>||  
|<span data-ttu-id="db28f-131">TIBRVMSG_U8</span><span class="sxs-lookup"><span data-stu-id="db28f-131">TIBRVMSG_U8</span></span>|<span data-ttu-id="db28f-132">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="db28f-132">xsd:unsignedByte</span></span>||  
|<span data-ttu-id="db28f-133">TIBRVMSG_U16</span><span class="sxs-lookup"><span data-stu-id="db28f-133">TIBRVMSG_U16</span></span>|<span data-ttu-id="db28f-134">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="db28f-134">xsd:unsignedShort</span></span>||  
|<span data-ttu-id="db28f-135">TIBRVMSG_U32</span><span class="sxs-lookup"><span data-stu-id="db28f-135">TIBRVMSG_U32</span></span>|<span data-ttu-id="db28f-136">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="db28f-136">xsd:unsignedInt</span></span>||  
|<span data-ttu-id="db28f-137">TIBRVMSG_U64</span><span class="sxs-lookup"><span data-stu-id="db28f-137">TIBRVMSG_U64</span></span>|<span data-ttu-id="db28f-138">xsd:unsignedLong</span><span class="sxs-lookup"><span data-stu-id="db28f-138">xsd:unsignedLong</span></span>||  
|<span data-ttu-id="db28f-139">TIBRVMSG_F32</span><span class="sxs-lookup"><span data-stu-id="db28f-139">TIBRVMSG_F32</span></span>|<span data-ttu-id="db28f-140">xsd:float</span><span class="sxs-lookup"><span data-stu-id="db28f-140">xsd:float</span></span>||  
|<span data-ttu-id="db28f-141">TIBRVMSG_F64</span><span class="sxs-lookup"><span data-stu-id="db28f-141">TIBRVMSG_F64</span></span>|<span data-ttu-id="db28f-142">xsd:double</span><span class="sxs-lookup"><span data-stu-id="db28f-142">xsd:double</span></span>||  
|<span data-ttu-id="db28f-143">TIBRVMSG_IPADDR32</span><span class="sxs-lookup"><span data-stu-id="db28f-143">TIBRVMSG_IPADDR32</span></span>|<span data-ttu-id="db28f-144">tibrv:IPaddress</span><span class="sxs-lookup"><span data-stu-id="db28f-144">tibrv:IPaddress</span></span>|<span data-ttu-id="db28f-145">`System.Net.IPAddress.ToString( )` 用于生成输出。</span><span class="sxs-lookup"><span data-stu-id="db28f-145">`System.Net.IPAddress.ToString( )` is used to generate the output.</span></span> <span data-ttu-id="db28f-146">内容以网络字节顺序进行排列。</span><span class="sxs-lookup"><span data-stu-id="db28f-146">Content is in network byte order.</span></span> <span data-ttu-id="db28f-147">ToString() 对其进行处理。</span><span class="sxs-lookup"><span data-stu-id="db28f-147">ToString() takes care of that.</span></span>|  
|<span data-ttu-id="db28f-148">TIBRVMSG_IPPORT16</span><span class="sxs-lookup"><span data-stu-id="db28f-148">TIBRVMSG_IPPORT16</span></span>|<span data-ttu-id="db28f-149">tibrv:IPport</span><span class="sxs-lookup"><span data-stu-id="db28f-149">tibrv:IPport</span></span>|<span data-ttu-id="db28f-150">内容以网络字节顺序进行排列</span><span class="sxs-lookup"><span data-stu-id="db28f-150">Content is in network byte order</span></span>|  
|<span data-ttu-id="db28f-151">TIBRVMSG_I8ARRAY</span><span class="sxs-lookup"><span data-stu-id="db28f-151">TIBRVMSG_I8ARRAY</span></span>|<span data-ttu-id="db28f-152">tibrv:arrayOfByte</span><span class="sxs-lookup"><span data-stu-id="db28f-152">tibrv:arrayOfByte</span></span>|<span data-ttu-id="db28f-153">“tibrv”架构命名空间随适配器提供。</span><span class="sxs-lookup"><span data-stu-id="db28f-153">'tibrv' schema namespace is provided with the adapter.</span></span>|  
|<span data-ttu-id="db28f-154">TIBRVMSG_I16ARRAY</span><span class="sxs-lookup"><span data-stu-id="db28f-154">TIBRVMSG_I16ARRAY</span></span>|<span data-ttu-id="db28f-155">tibrv:arrayOfShort</span><span class="sxs-lookup"><span data-stu-id="db28f-155">tibrv:arrayOfShort</span></span>||  
|<span data-ttu-id="db28f-156">TIBRVMSG_I32ARRAY</span><span class="sxs-lookup"><span data-stu-id="db28f-156">TIBRVMSG_I32ARRAY</span></span>|<span data-ttu-id="db28f-157">tibrv:arrayOfInt</span><span class="sxs-lookup"><span data-stu-id="db28f-157">tibrv:arrayOfInt</span></span>||  
|<span data-ttu-id="db28f-158">TIBRVMSG_I64ARRAY</span><span class="sxs-lookup"><span data-stu-id="db28f-158">TIBRVMSG_I64ARRAY</span></span>|<span data-ttu-id="db28f-159">tibrv:arrayOfLong</span><span class="sxs-lookup"><span data-stu-id="db28f-159">tibrv:arrayOfLong</span></span>||  
|<span data-ttu-id="db28f-160">TIBRVMSG_U8ARRAY</span><span class="sxs-lookup"><span data-stu-id="db28f-160">TIBRVMSG_U8ARRAY</span></span>|<span data-ttu-id="db28f-161">tibrv:arrayOfUnsignedByte</span><span class="sxs-lookup"><span data-stu-id="db28f-161">tibrv:arrayOfUnsignedByte</span></span>||  
|<span data-ttu-id="db28f-162">TIBRVMSG_U16ARRAY</span><span class="sxs-lookup"><span data-stu-id="db28f-162">TIBRVMSG_U16ARRAY</span></span>|<span data-ttu-id="db28f-163">tibrv:arrayOfUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="db28f-163">tibrv:arrayOfUnsignedShort</span></span>||  
|<span data-ttu-id="db28f-164">TIBRVMSG_U32ARRAY</span><span class="sxs-lookup"><span data-stu-id="db28f-164">TIBRVMSG_U32ARRAY</span></span>|<span data-ttu-id="db28f-165">tibrv:arrayOfUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="db28f-165">tibrv:arrayOfUnsignedInt</span></span>||  
|<span data-ttu-id="db28f-166">TIBRVMSG_U64ARRAY</span><span class="sxs-lookup"><span data-stu-id="db28f-166">TIBRVMSG_U64ARRAY</span></span>|<span data-ttu-id="db28f-167">tibrv:arrayOfUnsignedLong</span><span class="sxs-lookup"><span data-stu-id="db28f-167">tibrv:arrayOfUnsignedLong</span></span>||  
|<span data-ttu-id="db28f-168">TIBRVMSG_F32ARRAY</span><span class="sxs-lookup"><span data-stu-id="db28f-168">TIBRVMSG_F32ARRAY</span></span>|<span data-ttu-id="db28f-169">tibrv:arrayOfFloat</span><span class="sxs-lookup"><span data-stu-id="db28f-169">tibrv:arrayOfFloat</span></span>||  
|<span data-ttu-id="db28f-170">TIBRVMSG_F64ARRAY</span><span class="sxs-lookup"><span data-stu-id="db28f-170">TIBRVMSG_F64ARRAY</span></span>|<span data-ttu-id="db28f-171">tibrv:arrayOfDouble</span><span class="sxs-lookup"><span data-stu-id="db28f-171">tibrv:arrayOfDouble</span></span>||  
  
 <span data-ttu-id="db28f-172">TIBCO Rendezvous 数组不同于具有相同名称的字段序列。</span><span class="sxs-lookup"><span data-stu-id="db28f-172">TIBCO Rendezvous arrays differ from a sequence of fields with the same name.</span></span> <span data-ttu-id="db28f-173">例如，在 TIBCO Rendezvous 消息中，具有 70,000 元素的数组是有效的，但是具有 70,000 字段则无效。</span><span class="sxs-lookup"><span data-stu-id="db28f-173">For example, in a TIBCO Rendezvous message, it is valid to have an array with 70,000 elements, but it is not valid to have 70,000 fields.</span></span>  
  
 <span data-ttu-id="db28f-174">上表中数组类型的架构如下所示：</span><span class="sxs-lookup"><span data-stu-id="db28f-174">The schema for the array types in the previous table looks like this:</span></span>  
  
```  
…  
<xsd:complexType name='arrayOfShort'>  
<xsd:sequence>  
<xsd:element name="item" type="xsd:short"/>  
</xsd:sequence>  
</xsd:complexType>  
  
```  
  
 <span data-ttu-id="db28f-175">消息中数组元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="db28f-175">An array element in a message looks like this:</span></span>  
  
```  
<someElement xsi:type='tibrv:arrayOfShort'>  
<item>100</item>  
<item>200</item>  
<item>300</item>  
<item>400</item>  
<item>500</item>  
</someElement>  
  
```  
  
 <span data-ttu-id="db28f-176">IPaddress 架构如下所示：</span><span class="sxs-lookup"><span data-stu-id="db28f-176">The schema for the IPaddress looks like this:</span></span>  
  
```  
<xsd:simpleType name='IPaddress'>  
  
 <xsd:restriction base="xs:string">  
   <xsd:minLength value="7" />  
   <xsd:maxLength value="15" />  
  
 </xsd:restriction>  
       </xsd:simpleType>   
</xsd:simpleType>  
  
```  
  
 <span data-ttu-id="db28f-177">IPport 架构如下所示：</span><span class="sxs-lookup"><span data-stu-id="db28f-177">The schema for the IPport looks like this:</span></span>  
  
```  
<xsd:simpleType name='IPport'>  
  
<xsd:restriction base='xsd:ushort'>  
</xsd:simpleType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="db28f-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db28f-178">See Also</span></span>  
 <span data-ttu-id="db28f-179">[TIBCO 集合中的消息映射](../core/message-mapping-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="db28f-179">[Message Mapping in TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="db28f-180">创建 TIBCO Rendezvou 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="db28f-180">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)