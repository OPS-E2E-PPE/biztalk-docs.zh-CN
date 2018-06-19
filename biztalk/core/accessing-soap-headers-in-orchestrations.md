---
title: 访问在业务流程中的 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, properties
- orchestrations, SOAP headers
ms.assetid: 91fe053a-3f16-497c-b4bb-5fb54bec62e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 516b2bcc57bef507a028f30c61fd329a5fd7a598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225917"
---
# <a name="accessing-soap-headers-in-orchestrations"></a><span data-ttu-id="5d660-102">访问在业务流程中的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="5d660-102">Accessing SOAP Headers in Orchestrations</span></span>
<span data-ttu-id="5d660-103">对于已定义的和未知的 SOAP 标头，您可以在业务流程中访问 SOAP 标头上下文属性。</span><span class="sxs-lookup"><span data-stu-id="5d660-103">You can access the SOAP header context properties in orchestrations for defined and unknown SOAP headers.</span></span> <span data-ttu-id="5d660-104">有关属性架构和上下文属性的详细信息，请参阅[属性架构](../core/property-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="5d660-104">For more information about property schemas and context properties, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
## <a name="defined-soap-header-context-properties"></a><span data-ttu-id="5d660-105">已定义的 SOAP 标头上下文属性</span><span class="sxs-lookup"><span data-stu-id="5d660-105">Defined SOAP header context properties</span></span>  
 <span data-ttu-id="5d660-106">在业务流程中的定义的 SOAP 标头上下文属性需要属性架构。</span><span class="sxs-lookup"><span data-stu-id="5d660-106">The defined SOAP header context properties in orchestrations require a property schema.</span></span> <span data-ttu-id="5d660-107">属性架构必须具有的目标命名空间**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**，和**属性架构基**属性设置为**MessageContextPropertyBase**。</span><span class="sxs-lookup"><span data-stu-id="5d660-107">The property schema must have the target namespace **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**, and the **Property Schema Base** property set to **MessageContextPropertyBase**.</span></span> <span data-ttu-id="5d660-108">属性架构中的每个根元素名称必须与定义的 SOAP 标头的根元素名称匹配。</span><span class="sxs-lookup"><span data-stu-id="5d660-108">Each root element name in the property schema must match the root element name of the defined SOAP header.</span></span> <span data-ttu-id="5d660-109">然后，就可以访问使用属性架构和属性名称的命名空间的上下文属性的值。</span><span class="sxs-lookup"><span data-stu-id="5d660-109">You can then access the values of the context properties using the namespace of the property schema and the property name.</span></span> <span data-ttu-id="5d660-110">属性架构的命名空间是上面列出的目标命名空间不同。</span><span class="sxs-lookup"><span data-stu-id="5d660-110">The namespace of the property schema is different from the target namespace listed above.</span></span> <span data-ttu-id="5d660-111">尽管属性架构的命名空间可以是任意字符串，它通常默认项目的名称。</span><span class="sxs-lookup"><span data-stu-id="5d660-111">Although the namespace of the property schema can be any string, it usually defaults to the name of the project.</span></span>  
  
 <span data-ttu-id="5d660-112">下面的示例演示访问属性架构命名空间中，SOAP 标头上下文属性**SOAPHeader**，及属性名称**OrigDest**:</span><span class="sxs-lookup"><span data-stu-id="5d660-112">The following example shows accessing the SOAP header context property for a property schema namespace, **SOAPHeader**, and the property name **OrigDest**:</span></span>  
  
```  
stringVar = requestMessageInstance(SOAPHeader.OrigDest);  
```  
  
> [!NOTE]
>  <span data-ttu-id="5d660-113">已定义的 SOAP 标头被视为“in”或“out”标头。</span><span class="sxs-lookup"><span data-stu-id="5d660-113">Defined SOAP headers are treated either as "in" or "out" headers.</span></span> <span data-ttu-id="5d660-114">如果向导为请求和响应消息定义的 SOAP 标头相同，则该向导不会在响应中自动返回传入值。</span><span class="sxs-lookup"><span data-stu-id="5d660-114">If the wizard defines the same SOAP header for the request and response message, the wizard does not automatically return the incoming value in the response.</span></span> <span data-ttu-id="5d660-115">您必须将请求消息的 SOAP 标头上下文属性显式复制到响应消息的 SOAP 标头上下文属性中。</span><span class="sxs-lookup"><span data-stu-id="5d660-115">You must explicity copy the SOAP header context property of the request message to the SOAP header context property of the response message.</span></span>  
  
## <a name="copying-soap-header-context-property-of-incoming-message"></a><span data-ttu-id="5d660-116">复制传入消息的 SOAP 标头上下文属性</span><span class="sxs-lookup"><span data-stu-id="5d660-116">Copying SOAP header context property of incoming message</span></span>  
 <span data-ttu-id="5d660-117">您可以将传入消息的 SOAP 标头上下文属性复制到响应消息的相同 SOAP 标头上下文属性中。</span><span class="sxs-lookup"><span data-stu-id="5d660-117">You can copy the SOAP header context property of an incoming message to the same SOAP header context property of the response message.</span></span>  
  
 <span data-ttu-id="5d660-118">下面的示例显示了如何复制 SOAP 标头上下文属性：</span><span class="sxs-lookup"><span data-stu-id="5d660-118">The following example shows copying the SOAP header context property:</span></span>  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = RequestMessageInstance(SOAPHeader.OrigDest);  
```  
  
 <span data-ttu-id="5d660-119">为 SOAP 响应创建 SOAP 标头时，必须确保您已正确创建 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="5d660-119">When you create SOAP headers for the SOAP response, you ensure that you create your SOAP headers correctly.</span></span> <span data-ttu-id="5d660-120">SOAP 适配器不验证 SOAP 标头上下文属性的内容。</span><span class="sxs-lookup"><span data-stu-id="5d660-120">The SOAP adapter does not verify the contents of the SOAP header context properties.</span></span> <span data-ttu-id="5d660-121">如果响应 SOAP 标头的值错误，则 SOAP 适配器不会将此响应消息发送给 Web Services 的使用者。</span><span class="sxs-lookup"><span data-stu-id="5d660-121">If the values of the response SOAP headers are incorrect, the SOAP adapter cannot send the response message to the consumer of your Web service.</span></span>  
  
## <a name="unknown-soap-header-context-property"></a><span data-ttu-id="5d660-122">未知的 SOAP 标头上下文属性</span><span class="sxs-lookup"><span data-stu-id="5d660-122">Unknown SOAP header context property</span></span>  
 <span data-ttu-id="5d660-123">未知的 SOAP 标头上下文属性不需要属性架构。</span><span class="sxs-lookup"><span data-stu-id="5d660-123">The unknown SOAP header context property does not require a property schema.</span></span> <span data-ttu-id="5d660-124">你可以访问此全局上下文属性**SOAP。UnknownHeaders**。</span><span class="sxs-lookup"><span data-stu-id="5d660-124">You can access this global context property **SOAP.UnknownHeaders**.</span></span>  
  
 <span data-ttu-id="5d660-125">下面的示例演示访问未知的 SOAP 标头上下文属性**SOAP。UnknownHeaders**:</span><span class="sxs-lookup"><span data-stu-id="5d660-125">The following example shows accessing the unknown SOAP header context property **SOAP.UnknownHeaders**:</span></span>  
  
```  
stringVar = RequestMessageInstance(SOAP.UnknownHeaders);  
```  
  
 <span data-ttu-id="5d660-126">上下文属性中包含的值是包含 XML 数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="5d660-126">The values contained in the context properties are strings containing XML data.</span></span> <span data-ttu-id="5d660-127">访问此数据的最简单方法是使用中的 BizTalk 表达式编辑器**消息分配**或**表达式**的形状，然后加载中的字符串**XmlDocument**和使用若要访问特定字段的 XPATH 查询。</span><span class="sxs-lookup"><span data-stu-id="5d660-127">The simplest way to access this data is to use the BizTalk Expression Editor in a **Message Assignment** or **Expression** shape and load the string in an **XmlDocument** and use XPATH queries to access specific fields.</span></span> <span data-ttu-id="5d660-128">创建 BizTalk 表达式编辑器中的 XML 文档的详细信息，请参阅[XLANG-s 语言](../core/xlang-s-language.md)。</span><span class="sxs-lookup"><span data-stu-id="5d660-128">For more information creating XML documents in the BizTalk Expression Editor, see [XLANG-s Language](../core/xlang-s-language.md).</span></span>  
  
 <span data-ttu-id="5d660-129">上下文属性与某一特定消息关联。</span><span class="sxs-lookup"><span data-stu-id="5d660-129">Context properties are associated with a particular message.</span></span> <span data-ttu-id="5d660-130">消息引擎不会自动映射已知从请求消息到响应消息的 SOAP 头的值。</span><span class="sxs-lookup"><span data-stu-id="5d660-130">The Messaging Engine does not automatically map the values of known SOAP headers from the request message to the response message.</span></span> <span data-ttu-id="5d660-131">在创建 Web 服务的响应消息时，你必须专门设置的 SOAP 标头值。</span><span class="sxs-lookup"><span data-stu-id="5d660-131">When creating the response message for a Web service, you must specifically set the SOAP header values.</span></span> <span data-ttu-id="5d660-132">以下命令为设置的 SOAP 标头上下文属性的最简单方法：</span><span class="sxs-lookup"><span data-stu-id="5d660-132">The following command is the simplest method of setting a SOAP header context property:</span></span>  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = "<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination xmlns=\"\">Home</Origination><Destination xmlns=\"\">Work</Destination> </OrigDest>"  
```  
  
 <span data-ttu-id="5d660-133">你还可以通过创建实现此**XmlDocument**和写入的字符串值**XmlDocument**到上下文属性。</span><span class="sxs-lookup"><span data-stu-id="5d660-133">You can also achieve this by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d660-134">如果**SOAP。UnknownHeaders**属性为 null，则 BizTalk 自动返回接收到 SOAP 响应 SOAP 请求中的未知标头。</span><span class="sxs-lookup"><span data-stu-id="5d660-134">If the **SOAP.UnknownHeaders** property is null, BizTalk automatically returns the unknown headers received in the SOAP request to the SOAP response.</span></span> <span data-ttu-id="5d660-135">如果**SOAP。UnknownHeaders**的响应消息的上下文属性不为 null，则 BizTalk SOAP 响应中返回该值。</span><span class="sxs-lookup"><span data-stu-id="5d660-135">If the **SOAP.UnknownHeaders** context property on the response message is not null, then BizTalk returns that value to the SOAP response.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d660-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d660-136">See Also</span></span>  
 [<span data-ttu-id="5d660-137">与发布的 Web 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="5d660-137">SOAP Headers with Published Web Services</span></span>](../core/soap-headers-with-published-web-services.md)