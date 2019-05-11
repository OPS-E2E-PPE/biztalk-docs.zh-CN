---
title: 访问 WCF 消息与业务流程中的 SOAP 标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- orchestrations, WCF services
- WCF services, SOAP headers
- SOAP headers, WCF messages
ms.assetid: fe02fb02-18d6-4fc6-89e0-b06bdbfa5cb4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 747e92359bf894eb96229cc8e1f1d227db8d5cb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361877"
---
# <a name="accessing-soap-headers-in-wcf-messages-with-orchestrations"></a><span data-ttu-id="ccd4d-102">访问 WCF 消息与业务流程中的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="ccd4d-102">Accessing SOAP Headers in WCF Messages with Orchestrations</span></span>
<span data-ttu-id="ccd4d-103">若要访问的业务流程中传入 WCF 消息的 SOAP 标头值，使用上下文属性**WCF。InboundHeaders**。</span><span class="sxs-lookup"><span data-stu-id="ccd4d-103">To access the SOAP header values of incoming WCF messages in orchestrations, you use the context property **WCF.InboundHeaders**.</span></span> <span data-ttu-id="ccd4d-104">WCF 适配器将自定义 SOAP 标头和标准 SOAP 标头复制到的入站消息中**WCF。InboundHeaders**属性。</span><span class="sxs-lookup"><span data-stu-id="ccd4d-104">The WCF adapters copy custom SOAP headers and standard SOAP headers in the inbound messages to the **WCF.InboundHeaders** property.</span></span> <span data-ttu-id="ccd4d-105">WCF 适配器还可以选择你想要升级或写入至上下文属性以编程方式的属性。</span><span class="sxs-lookup"><span data-stu-id="ccd4d-105">The WCF adapters also allow you to select the properties you would like to promote or write to the context properties programmatically.</span></span> <span data-ttu-id="ccd4d-106">请参阅[SOAP 标头发布 WCF 服务与](../core/soap-headers-with-published-wcf-services.md)的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="ccd4d-106">See [SOAP Headers with Published WCF Services](../core/soap-headers-with-published-wcf-services.md) for more details.</span></span>  
  
 <span data-ttu-id="ccd4d-107">上下文属性中包含的值是一个包含 XML 数据字符串\<**标头**\>根元素和传入的 SOAP 标头复制为子元素的\< **标头**\>元素。</span><span class="sxs-lookup"><span data-stu-id="ccd4d-107">The value contained in the context property is a string containing XML data with the \<**headers**\> root element, and the incoming SOAP headers are copied as child elements of the \<**headers**\> element.</span></span> <span data-ttu-id="ccd4d-108">若要访问此数据的最简单方法是使用 BizTalk 表达式编辑器在**消息赋值**或**表达式**形状中，加载中的字符串**XmlDocument**，并使用若要访问特定字段的 XPath 查询。</span><span class="sxs-lookup"><span data-stu-id="ccd4d-108">The simplest way to access this data is to use the BizTalk Expression Editor in a **Message Assignment** or **Expression** shape, load the string in an **XmlDocument**, and use XPath queries to access specific fields.</span></span> <span data-ttu-id="ccd4d-109">有关在 BizTalk 表达式编辑器中创建 XML 文档的详细信息，请参阅[xlang-s 语言](../core/xlang-s-language.md)。</span><span class="sxs-lookup"><span data-stu-id="ccd4d-109">For more information about creating XML documents in the BizTalk Expression Editor, see [XLANG-s Language](../core/xlang-s-language.md).</span></span>  
  
 <span data-ttu-id="ccd4d-110">下面的代码示例获取请求 SOAP 标头**消息赋值**或**表达式**形状**WCF。InboundHeaders**属性：</span><span class="sxs-lookup"><span data-stu-id="ccd4d-110">The following code example gets the request SOAP header in a **Message Assignment** or **Expression** shape for the **WCF.InboundHeaders** property:</span></span>  
  
```  
stringVar = inboundMessageInstance(WCF.InboundHeaders);  
```  
  
 <span data-ttu-id="ccd4d-111">上下文属性与某一特定消息关联。</span><span class="sxs-lookup"><span data-stu-id="ccd4d-111">Context properties are associated with a particular message.</span></span> <span data-ttu-id="ccd4d-112">消息引擎不会自动映射从请求消息的 SOAP 标头到响应消息的值。</span><span class="sxs-lookup"><span data-stu-id="ccd4d-112">The Messaging Engine does not automatically map the values of the SOAP headers from the request message to the response message.</span></span> <span data-ttu-id="ccd4d-113">在创建 WCF 服务的响应消息时，必须专门设置 SOAP 标头值通过**WCF。OutboundCustomHeaders**属性。</span><span class="sxs-lookup"><span data-stu-id="ccd4d-113">When creating the response message for a WCF service, you must specifically set the SOAP header values through the **WCF.OutboundCustomHeaders** property.</span></span> <span data-ttu-id="ccd4d-114">以下命令为设置的 SOAP 标头上下文属性的最简单方法：</span><span class="sxs-lookup"><span data-stu-id="ccd4d-114">The following command is the simplest method of setting a SOAP header context property:</span></span>  
  
```  
outboundMessageInstance(WCF.OutbounCustomHeaders) = "<headers><Origination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Home</Origination><Destination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Work</Destination></headers>"  
```  
  
 <span data-ttu-id="ccd4d-115">此外可以通过创建设置上下文属性**XmlDocument**和的字符串值写入**XmlDocument**为上下文属性。</span><span class="sxs-lookup"><span data-stu-id="ccd4d-115">You can also set the context property by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span>  
  
 <span data-ttu-id="ccd4d-116">有关如何对访问 SOAP 标头用于 WCF 适配器的详细信息，请参阅 SDK 示例"使用自定义 SOAP 标头与 WCF 适配器"处[ http://go.microsoft.com/fwlink/?LinkId=79960 ](http://go.microsoft.com/fwlink/?LinkId=79960)。</span><span class="sxs-lookup"><span data-stu-id="ccd4d-116">For more information about how to access SOAP headers with the WCF adapters, see the SDK sample "Using Custom SOAP Headers with the WCF Adapters" at [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd4d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ccd4d-117">See Also</span></span>  
 <span data-ttu-id="ccd4d-118">[访问管道组件使用的 WCF 消息中的 SOAP 标头](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md) </span><span class="sxs-lookup"><span data-stu-id="ccd4d-118">[Accessing SOAP Headers in WCF Messages with Pipeline Components](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md) </span></span>  
 <span data-ttu-id="ccd4d-119">[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ccd4d-119">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="ccd4d-120">SOAP 标头与使用的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="ccd4d-120">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)