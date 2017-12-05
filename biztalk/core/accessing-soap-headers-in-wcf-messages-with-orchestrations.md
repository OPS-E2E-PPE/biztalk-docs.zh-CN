---
title: "访问在与业务流程的 WCF 消息的 SOAP 标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- orchestrations, WCF services
- WCF services, SOAP headers
- SOAP headers, WCF messages
ms.assetid: fe02fb02-18d6-4fc6-89e0-b06bdbfa5cb4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bfd1dd4e09071c3d7bcccf28878f19e13acad8a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="accessing-soap-headers-in-wcf-messages-with-orchestrations"></a><span data-ttu-id="2224d-102">使用业务流程访问 WCF 消息中的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="2224d-102">Accessing SOAP Headers in WCF Messages with Orchestrations</span></span>
<span data-ttu-id="2224d-103">若要访问在业务流程中的传入 WCF 消息的 SOAP 标头值，你可以使用上下文属性**WCF。InboundHeaders**。</span><span class="sxs-lookup"><span data-stu-id="2224d-103">To access the SOAP header values of incoming WCF messages in orchestrations, you use the context property **WCF.InboundHeaders**.</span></span> <span data-ttu-id="2224d-104">WCF 适配器将自定义 SOAP 标头和标准 SOAP 标头复制到入站消息中**WCF。InboundHeaders**属性。</span><span class="sxs-lookup"><span data-stu-id="2224d-104">The WCF adapters copy custom SOAP headers and standard SOAP headers in the inbound messages to the **WCF.InboundHeaders** property.</span></span> <span data-ttu-id="2224d-105">WCF 适配器还允许你选择你想要升级或以编程方式编写的上下文属性的属性。</span><span class="sxs-lookup"><span data-stu-id="2224d-105">The WCF adapters also allow you to select the properties you would like to promote or write to the context properties programmatically.</span></span> <span data-ttu-id="2224d-106">请参阅[发布 WCF 服务使用的 SOAP 标头](../core/soap-headers-with-published-wcf-services.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="2224d-106">See [SOAP Headers with Published WCF Services](../core/soap-headers-with-published-wcf-services.md) for more details.</span></span>  
  
 <span data-ttu-id="2224d-107">上下文属性中包含的值是一个包含与 XML 数据字符串\<**标头**\>根元素和传入的 SOAP 标头将复制作为子元素的\< **标头**\>元素。</span><span class="sxs-lookup"><span data-stu-id="2224d-107">The value contained in the context property is a string containing XML data with the \<**headers**\> root element, and the incoming SOAP headers are copied as child elements of the \<**headers**\> element.</span></span> <span data-ttu-id="2224d-108">访问此数据的最简单方法是使用中的 BizTalk 表达式编辑器**消息分配**或**表达式**形状，加载中的字符串**XmlDocument**，并使用若要访问特定字段的 XPath 查询。</span><span class="sxs-lookup"><span data-stu-id="2224d-108">The simplest way to access this data is to use the BizTalk Expression Editor in a **Message Assignment** or **Expression** shape, load the string in an **XmlDocument**, and use XPath queries to access specific fields.</span></span> <span data-ttu-id="2224d-109">有关创建 BizTalk 表达式编辑器中的 XML 文档的详细信息，请参阅[XLANG-s 语言](../core/xlang-s-language.md)。</span><span class="sxs-lookup"><span data-stu-id="2224d-109">For more information about creating XML documents in the BizTalk Expression Editor, see [XLANG-s Language](../core/xlang-s-language.md).</span></span>  
  
 <span data-ttu-id="2224d-110">下面的代码示例获取请求的 SOAP 标头中**消息分配**或**表达式**形状**WCF。InboundHeaders**属性：</span><span class="sxs-lookup"><span data-stu-id="2224d-110">The following code example gets the request SOAP header in a **Message Assignment** or **Expression** shape for the **WCF.InboundHeaders** property:</span></span>  
  
```  
stringVar = inboundMessageInstance(WCF.InboundHeaders);  
```  
  
 <span data-ttu-id="2224d-111">上下文属性与某一特定消息关联。</span><span class="sxs-lookup"><span data-stu-id="2224d-111">Context properties are associated with a particular message.</span></span> <span data-ttu-id="2224d-112">消息引擎不会将请求消息中的 SOAP 标头值自动映射到响应消息中。</span><span class="sxs-lookup"><span data-stu-id="2224d-112">The Messaging Engine does not automatically map the values of the SOAP headers from the request message to the response message.</span></span> <span data-ttu-id="2224d-113">创建时的 WCF 服务的响应消息，你必须专门设置通过 SOAP 标头值**WCF。OutboundCustomHeaders**属性。</span><span class="sxs-lookup"><span data-stu-id="2224d-113">When creating the response message for a WCF service, you must specifically set the SOAP header values through the **WCF.OutboundCustomHeaders** property.</span></span> <span data-ttu-id="2224d-114">以下命令为设置的 SOAP 标头上下文属性的最简单方法：</span><span class="sxs-lookup"><span data-stu-id="2224d-114">The following command is the simplest method of setting a SOAP header context property:</span></span>  
  
```  
outboundMessageInstance(WCF.OutbounCustomHeaders) = "<headers><Origination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Home</Origination><Destination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Work</Destination></headers>"  
```  
  
 <span data-ttu-id="2224d-115">此外可以通过创建设置上下文属性**XmlDocument**和写入的字符串值**XmlDocument**到上下文属性。</span><span class="sxs-lookup"><span data-stu-id="2224d-115">You can also set the context property by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span>  
  
 <span data-ttu-id="2224d-116">有关如何对访问 SOAP 标头与 WCF 适配器的详细信息，请参阅"使用自定义 SOAP 标头与 WCF 适配器"中的 SDK 示例在[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)。</span><span class="sxs-lookup"><span data-stu-id="2224d-116">For more information about how to access SOAP headers with the WCF adapters, see the SDK sample "Using Custom SOAP Headers with the WCF Adapters" at [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2224d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2224d-117">See Also</span></span>  
 <span data-ttu-id="2224d-118">[访问在与管道组件的 WCF 消息的 SOAP 标头](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="2224d-118">[Accessing SOAP Headers in WCF Messages with Pipeline Components](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md) </span></span>  
 <span data-ttu-id="2224d-119">[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="2224d-119">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="2224d-120">SOAP 标头与使用的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="2224d-120">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)