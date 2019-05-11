---
title: 数据类型映射，以接收来自 TIBCO Rendezvous |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36908a94-3c0d-466e-aa49-f674ba4a26af
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f064021c58e2d870df8e1110a07ce42d0dc9ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389958"
---
# <a name="data-type-mapping-for-receive-handlers-in-tibco-rendezvous"></a><span data-ttu-id="27e92-102">数据类型映射中 TIBCO Rendezvous 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="27e92-102">Data Type Mapping for Receive Handlers in TIBCO Rendezvous</span></span>
<span data-ttu-id="27e92-103">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器将 TIBCO RV 类型映射到下表中指定的 XML 架构类型。</span><span class="sxs-lookup"><span data-stu-id="27e92-103">Microsoft BizTalk Adapter for TIBCO Rendezvous maps TIBCO RV types to XML Schema types as specified in the following table.</span></span>  
  
## <a name="tibco-rv-to-xml-data-type-mapping"></a><span data-ttu-id="27e92-104">TIBCO RV 到 XML 数据类型映射</span><span class="sxs-lookup"><span data-stu-id="27e92-104">TIBCO RV to XML Data Type Mapping</span></span>  
  
|<span data-ttu-id="27e92-105">TIBCO RV Type</span><span class="sxs-lookup"><span data-stu-id="27e92-105">TIBCO RV Type</span></span>|<span data-ttu-id="27e92-106">XML 架构类型</span><span class="sxs-lookup"><span data-stu-id="27e92-106">XML Schema Type</span></span>|<span data-ttu-id="27e92-107">注释</span><span class="sxs-lookup"><span data-stu-id="27e92-107">Comments</span></span>|  
|-------------------|---------------------|--------------|  
|<span data-ttu-id="27e92-108">TIBRVMSG_MSG</span><span class="sxs-lookup"><span data-stu-id="27e92-108">TIBRVMSG_MSG</span></span>|<span data-ttu-id="27e92-109">tibrv:message</span><span class="sxs-lookup"><span data-stu-id="27e92-109">tibrv:message</span></span>|<span data-ttu-id="27e92-110">从整个消息构造完整的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="27e92-110">Complete XML document constructed from entire message.</span></span>|  
|<span data-ttu-id="27e92-111">TIBRVMSG_XML</span><span class="sxs-lookup"><span data-stu-id="27e92-111">TIBRVMSG_XML</span></span>|<span data-ttu-id="27e92-112">tibrv:rawxml</span><span class="sxs-lookup"><span data-stu-id="27e92-112">tibrv:rawxml</span></span>|<span data-ttu-id="27e92-113">构造的 （不由适配器解释） 的字节数组从 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="27e92-113">XML Document constructed from the array of bytes (not interpreted by the adapter).</span></span>|  
|<span data-ttu-id="27e92-114">TIBRVMSG_DATETIME</span><span class="sxs-lookup"><span data-stu-id="27e92-114">TIBRVMSG_DATETIME</span></span>|<span data-ttu-id="27e92-115">xsd:dateTime</span><span class="sxs-lookup"><span data-stu-id="27e92-115">xsd:dateTime</span></span>|<span data-ttu-id="27e92-116">适配器使用 System.Xml.XmlConvert 类 XML 架构之间进行转换`dateTime`和`System.DateTime`实例。</span><span class="sxs-lookup"><span data-stu-id="27e92-116">The adapter uses the System.Xml.XmlConvert class to convert between XML Schema `dateTime` and `System.DateTime` instances.</span></span>|  
|<span data-ttu-id="27e92-117">TIBRVMSG_OPAQUE</span><span class="sxs-lookup"><span data-stu-id="27e92-117">TIBRVMSG_OPAQUE</span></span>|<span data-ttu-id="27e92-118">xsd:base64Binary</span><span class="sxs-lookup"><span data-stu-id="27e92-118">xsd:base64Binary</span></span>||  
|<span data-ttu-id="27e92-119">TIBRVMSG_STRING</span><span class="sxs-lookup"><span data-stu-id="27e92-119">TIBRVMSG_STRING</span></span>|<span data-ttu-id="27e92-120">xsd:string</span><span class="sxs-lookup"><span data-stu-id="27e92-120">xsd:string</span></span>||  
|<span data-ttu-id="27e92-121">TIBRVMSG_BOOL</span><span class="sxs-lookup"><span data-stu-id="27e92-121">TIBRVMSG_BOOL</span></span>|<span data-ttu-id="27e92-122">xsd:boolean</span><span class="sxs-lookup"><span data-stu-id="27e92-122">xsd:boolean</span></span>||  
|<span data-ttu-id="27e92-123">TIBRVMSG_I8</span><span class="sxs-lookup"><span data-stu-id="27e92-123">TIBRVMSG_I8</span></span>|<span data-ttu-id="27e92-124">xsd:byte</span><span class="sxs-lookup"><span data-stu-id="27e92-124">xsd:byte</span></span>||  
|<span data-ttu-id="27e92-125">TIBRVMSG_I16</span><span class="sxs-lookup"><span data-stu-id="27e92-125">TIBRVMSG_I16</span></span>|<span data-ttu-id="27e92-126">xsd:short</span><span class="sxs-lookup"><span data-stu-id="27e92-126">xsd:short</span></span>||  
|<span data-ttu-id="27e92-127">TIBRVMSG_I32</span><span class="sxs-lookup"><span data-stu-id="27e92-127">TIBRVMSG_I32</span></span>|<span data-ttu-id="27e92-128">xsd:int</span><span class="sxs-lookup"><span data-stu-id="27e92-128">xsd:int</span></span>||  
|<span data-ttu-id="27e92-129">TIBRVMSG_I64</span><span class="sxs-lookup"><span data-stu-id="27e92-129">TIBRVMSG_I64</span></span>|<span data-ttu-id="27e92-130">xsd:long</span><span class="sxs-lookup"><span data-stu-id="27e92-130">xsd:long</span></span>||  
|<span data-ttu-id="27e92-131">TIBRVMSG_U8</span><span class="sxs-lookup"><span data-stu-id="27e92-131">TIBRVMSG_U8</span></span>|<span data-ttu-id="27e92-132">xsd:unsignedByte</span><span class="sxs-lookup"><span data-stu-id="27e92-132">xsd:unsignedByte</span></span>||  
|<span data-ttu-id="27e92-133">TIBRVMSG_U16</span><span class="sxs-lookup"><span data-stu-id="27e92-133">TIBRVMSG_U16</span></span>|<span data-ttu-id="27e92-134">xsd:unsignedShort</span><span class="sxs-lookup"><span data-stu-id="27e92-134">xsd:unsignedShort</span></span>||  
|<span data-ttu-id="27e92-135">TIBRVMSG_U32</span><span class="sxs-lookup"><span data-stu-id="27e92-135">TIBRVMSG_U32</span></span>|<span data-ttu-id="27e92-136">xsd:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="27e92-136">xsd:unsignedInt</span></span>||  
|<span data-ttu-id="27e92-137">TIBRVMSG_U64</span><span class="sxs-lookup"><span data-stu-id="27e92-137">TIBRVMSG_U64</span></span>|<span data-ttu-id="27e92-138">xsd:unsignedLong</span><span class="sxs-lookup"><span data-stu-id="27e92-138">xsd:unsignedLong</span></span>||  
|<span data-ttu-id="27e92-139">TIBRVMSG_F32</span><span class="sxs-lookup"><span data-stu-id="27e92-139">TIBRVMSG_F32</span></span>|<span data-ttu-id="27e92-140">xsd:float</span><span class="sxs-lookup"><span data-stu-id="27e92-140">xsd:float</span></span>||  
|<span data-ttu-id="27e92-141">TIBRVMSG_F64</span><span class="sxs-lookup"><span data-stu-id="27e92-141">TIBRVMSG_F64</span></span>|<span data-ttu-id="27e92-142">xsd:double</span><span class="sxs-lookup"><span data-stu-id="27e92-142">xsd:double</span></span>||  
|<span data-ttu-id="27e92-143">TIBRVMSG_IPADDR32</span><span class="sxs-lookup"><span data-stu-id="27e92-143">TIBRVMSG_IPADDR32</span></span>|<span data-ttu-id="27e92-144">tibrv:IPaddress</span><span class="sxs-lookup"><span data-stu-id="27e92-144">tibrv:IPaddress</span></span>|<span data-ttu-id="27e92-145">`System.Net.IPAddress.ToString( )` 用于生成输出。</span><span class="sxs-lookup"><span data-stu-id="27e92-145">`System.Net.IPAddress.ToString( )` is used to generate the output.</span></span> <span data-ttu-id="27e92-146">内容是以网络字节顺序。</span><span class="sxs-lookup"><span data-stu-id="27e92-146">Content is in network byte order.</span></span> <span data-ttu-id="27e92-147">Tostring （） 将负责的。</span><span class="sxs-lookup"><span data-stu-id="27e92-147">ToString() takes care of that.</span></span>|  
|<span data-ttu-id="27e92-148">TIBRVMSG_IPPORT16</span><span class="sxs-lookup"><span data-stu-id="27e92-148">TIBRVMSG_IPPORT16</span></span>|<span data-ttu-id="27e92-149">tibrv:IPport</span><span class="sxs-lookup"><span data-stu-id="27e92-149">tibrv:IPport</span></span>|<span data-ttu-id="27e92-150">内容以网络字节顺序</span><span class="sxs-lookup"><span data-stu-id="27e92-150">Content is in network byte order</span></span>|  
|<span data-ttu-id="27e92-151">TIBRVMSG_I8ARRAY</span><span class="sxs-lookup"><span data-stu-id="27e92-151">TIBRVMSG_I8ARRAY</span></span>|<span data-ttu-id="27e92-152">tibrv:arrayOfByte</span><span class="sxs-lookup"><span data-stu-id="27e92-152">tibrv:arrayOfByte</span></span>|<span data-ttu-id="27e92-153">tibrv 架构命名空间随适配器提供。</span><span class="sxs-lookup"><span data-stu-id="27e92-153">'tibrv' schema namespace is provided with the adapter.</span></span>|  
|<span data-ttu-id="27e92-154">TIBRVMSG_I16ARRAY</span><span class="sxs-lookup"><span data-stu-id="27e92-154">TIBRVMSG_I16ARRAY</span></span>|<span data-ttu-id="27e92-155">tibrv:arrayOfShort</span><span class="sxs-lookup"><span data-stu-id="27e92-155">tibrv:arrayOfShort</span></span>||  
|<span data-ttu-id="27e92-156">TIBRVMSG_I32ARRAY</span><span class="sxs-lookup"><span data-stu-id="27e92-156">TIBRVMSG_I32ARRAY</span></span>|<span data-ttu-id="27e92-157">tibrv:arrayOfInt</span><span class="sxs-lookup"><span data-stu-id="27e92-157">tibrv:arrayOfInt</span></span>||  
|<span data-ttu-id="27e92-158">TIBRVMSG_I64ARRAY</span><span class="sxs-lookup"><span data-stu-id="27e92-158">TIBRVMSG_I64ARRAY</span></span>|<span data-ttu-id="27e92-159">tibrv:arrayOfLong</span><span class="sxs-lookup"><span data-stu-id="27e92-159">tibrv:arrayOfLong</span></span>||  
|<span data-ttu-id="27e92-160">TIBRVMSG_U8ARRAY</span><span class="sxs-lookup"><span data-stu-id="27e92-160">TIBRVMSG_U8ARRAY</span></span>|<span data-ttu-id="27e92-161">tibrv:arrayOfUnsignedByte</span><span class="sxs-lookup"><span data-stu-id="27e92-161">tibrv:arrayOfUnsignedByte</span></span>||  
|<span data-ttu-id="27e92-162">TIBRVMSG_U16ARRAY</span><span class="sxs-lookup"><span data-stu-id="27e92-162">TIBRVMSG_U16ARRAY</span></span>|<span data-ttu-id="27e92-163">tibrv:arrayOfUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="27e92-163">tibrv:arrayOfUnsignedShort</span></span>||  
|<span data-ttu-id="27e92-164">TIBRVMSG_U32ARRAY</span><span class="sxs-lookup"><span data-stu-id="27e92-164">TIBRVMSG_U32ARRAY</span></span>|<span data-ttu-id="27e92-165">tibrv:arrayOfUnsignedInt</span><span class="sxs-lookup"><span data-stu-id="27e92-165">tibrv:arrayOfUnsignedInt</span></span>||  
|<span data-ttu-id="27e92-166">TIBRVMSG_U64ARRAY</span><span class="sxs-lookup"><span data-stu-id="27e92-166">TIBRVMSG_U64ARRAY</span></span>|<span data-ttu-id="27e92-167">tibrv:arrayOfUnsignedLong</span><span class="sxs-lookup"><span data-stu-id="27e92-167">tibrv:arrayOfUnsignedLong</span></span>||  
|<span data-ttu-id="27e92-168">TIBRVMSG_F32ARRAY</span><span class="sxs-lookup"><span data-stu-id="27e92-168">TIBRVMSG_F32ARRAY</span></span>|<span data-ttu-id="27e92-169">tibrv:arrayOfFloat</span><span class="sxs-lookup"><span data-stu-id="27e92-169">tibrv:arrayOfFloat</span></span>||  
|<span data-ttu-id="27e92-170">TIBRVMSG_F64ARRAY</span><span class="sxs-lookup"><span data-stu-id="27e92-170">TIBRVMSG_F64ARRAY</span></span>|<span data-ttu-id="27e92-171">tibrv:arrayOfDouble</span><span class="sxs-lookup"><span data-stu-id="27e92-171">tibrv:arrayOfDouble</span></span>||  
  
 <span data-ttu-id="27e92-172">TIBCO Rendezvous 数组不同于一系列具有相同名称的字段。</span><span class="sxs-lookup"><span data-stu-id="27e92-172">TIBCO Rendezvous arrays differ from a sequence of fields with the same name.</span></span> <span data-ttu-id="27e92-173">例如，在 TIBCO Rendezvous 消息中，它是有效的数组具有 70,000 元素，但并不有效具有 70,000 字段。</span><span class="sxs-lookup"><span data-stu-id="27e92-173">For example, in a TIBCO Rendezvous message, it is valid to have an array with 70,000 elements, but it is not valid to have 70,000 fields.</span></span>  
  
 <span data-ttu-id="27e92-174">上表中的数组类型的架构如下所示：</span><span class="sxs-lookup"><span data-stu-id="27e92-174">The schema for the array types in the previous table looks like this:</span></span>  
  
```  
…  
<xsd:complexType name='arrayOfShort'>  
<xsd:sequence>  
<xsd:element name="item" type="xsd:short"/>  
</xsd:sequence>  
</xsd:complexType>  
  
```  
  
 <span data-ttu-id="27e92-175">在消息中的数组元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="27e92-175">An array element in a message looks like this:</span></span>  
  
```  
<someElement xsi:type='tibrv:arrayOfShort'>  
<item>100</item>  
<item>200</item>  
<item>300</item>  
<item>400</item>  
<item>500</item>  
</someElement>  
  
```  
  
 <span data-ttu-id="27e92-176">Ipaddress 架构如下所示：</span><span class="sxs-lookup"><span data-stu-id="27e92-176">The schema for the IPaddress looks like this:</span></span>  
  
```  
<xsd:simpleType name='IPaddress'>  
  
 <xsd:restriction base="xs:string">  
   <xsd:minLength value="7" />  
   <xsd:maxLength value="15" />  
  
 </xsd:restriction>  
       </xsd:simpleType>   
</xsd:simpleType>  
  
```  
  
 <span data-ttu-id="27e92-177">Ipport 架构如下所示：</span><span class="sxs-lookup"><span data-stu-id="27e92-177">The schema for the IPport looks like this:</span></span>  
  
```  
<xsd:simpleType name='IPport'>  
  
<xsd:restriction base='xsd:ushort'>  
</xsd:simpleType>  
```  
  
## <a name="see-also"></a><span data-ttu-id="27e92-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="27e92-178">See Also</span></span>  
 <span data-ttu-id="27e92-179">[TIBCO Rendezvous 中消息映射](../core/message-mapping-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="27e92-179">[Message Mapping in TIBCO Rendezvous](../core/message-mapping-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="27e92-180">创建 TIBCO Rendezvou 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="27e92-180">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)