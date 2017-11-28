---
title: "在与业务流程的 WCF 消息中使用 SOAP 标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- WCF services, orchestrations
- WCF services, SOAP headers
ms.assetid: 31c01e35-a2a6-4ea9-bdf4-6d4311268dbe
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7492ac6e1f8e43559fa921f9ddd3b60d644fe5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers-in-wcf-messages-with-orchestrations"></a><span data-ttu-id="b6568-102">在与业务流程的 WCF 消息中使用 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="b6568-102">Using SOAP Headers in WCF Messages with Orchestrations</span></span>
<span data-ttu-id="b6568-103">若要在业务流程中发送传出的 WCF 消息的自定义 SOAP 标头，你可以使用上下文属性**WCF。OutboundCustomHeaders**。</span><span class="sxs-lookup"><span data-stu-id="b6568-103">To send the custom SOAP headers with outgoing WCF messages in orchestrations, you use the context property, **WCF.OutboundCustomHeaders**.</span></span> <span data-ttu-id="b6568-104">WCF 适配器将自定义 SOAP 标头与 WCF 基础结构用于 Web 服务标准（如 WS-Addressing、WS-Security 和 WS-AtomicTransaction）的标准 SOAP 标头合并在一起进行发送。</span><span class="sxs-lookup"><span data-stu-id="b6568-104">The WCF adapters send the custom SOAP headers combined with the standard SOAP headers that the WCF infrastructure uses for Web services standards such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span> <span data-ttu-id="b6568-105">当你使用**OutboundCustomHeaders**属性，该属性必须具有\<**标头**> 元素作为根元素。</span><span class="sxs-lookup"><span data-stu-id="b6568-105">When you use the **OutboundCustomHeaders** property, the property must have the \<**headers**> element as the root element.</span></span> <span data-ttu-id="b6568-106">所有自定义 SOAP 标头必须放置在\<**标头**> 元素。</span><span class="sxs-lookup"><span data-stu-id="b6568-106">All of the custom SOAP headers must be placed inside the \<**headers**> element.</span></span> <span data-ttu-id="b6568-107">如果自定义 SOAP 标头的值为空字符串，则必须分配\<**标头**>\</**标头**> 或\< **标头**/ > 到**OutboundCustomHeaders**属性。</span><span class="sxs-lookup"><span data-stu-id="b6568-107">If the custom SOAP header value is an empty string, you must assign \<**headers**>\</**headers**> or \<**headers**/> to the **OutboundCustomHeaders** property.</span></span>  
  
 <span data-ttu-id="b6568-108">对于业务流程，SOAP 标头上下文属性均设置为包含 XML 数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="b6568-108">For orchestrations, the SOAP header context properties are set to strings that contain XML data.</span></span> <span data-ttu-id="b6568-109">使用 BizTalk 表达式编辑器中设置这些字符串**消息分配**或**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="b6568-109">You set these strings by using BizTalk Expression Editor in a **Message Assignment** or **Expression** shape.</span></span> <span data-ttu-id="b6568-110">有关如何使用 WCF 适配器使用 SOAP 标头的详细信息，请参阅 SDK 示例中，使用自定义 SOAP 标头与 WCF 适配器中，从[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)。</span><span class="sxs-lookup"><span data-stu-id="b6568-110">For more information about how to use SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
 <span data-ttu-id="b6568-111">下面的示例（来自消息赋值或表达式形状）显示了用于设置上下文属性的字符串：</span><span class="sxs-lookup"><span data-stu-id="b6568-111">The following example (from a Message Assignment or an Expression shape) shows the string setting the context property:</span></span>  
  
```  
outboundMessageInstance(WCF.OutboundCustomHeaders) = "<headers><Origination>Home</Origination><Destination>Work</Destination></headers>"  
```  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a><span data-ttu-id="b6568-112">创建用于设置上下文属性的 XmlDocument</span><span class="sxs-lookup"><span data-stu-id="b6568-112">Creating an XmlDocument to set context properties</span></span>  
 <span data-ttu-id="b6568-113">你可以设置**WCF。OutboundCustomHeaders**通过创建上下文属性**XmlDocument**和写入的字符串值**XmlDocument**到上下文属性。</span><span class="sxs-lookup"><span data-stu-id="b6568-113">You can set the **WCF.OutboundCustomHeaders** context property by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span> <span data-ttu-id="b6568-114">声明类型的变量的**XMLDocument**并将 XML 数据分配。</span><span class="sxs-lookup"><span data-stu-id="b6568-114">You declare a variable of type **XMLDocument** and assign the XML data.</span></span>  
  
 <span data-ttu-id="b6568-115">下面的示例演示声明类型的变量的**XMLDocument**和分配的 XML 数据：</span><span class="sxs-lookup"><span data-stu-id="b6568-115">The following example shows declaring a variable of type **XMLDocument** and assigning the XML data:</span></span>  
  
```  
xmlDoc.LoadXml("<headers><Origination>Home</Origination><Destination>Work</Destination></headers>");  
```  
  
 <span data-ttu-id="b6568-116">下面的示例显示了如何设置上下文属性：</span><span class="sxs-lookup"><span data-stu-id="b6568-116">The following example shows setting the context property:</span></span>  
  
```  
RequestMessageInstance(WCF.OutboundCustomHeaders) = xmlDoc.OuterXml;  
```  
  
 <span data-ttu-id="b6568-117">有关使用 BizTalk 表达式编辑器的详细信息，请参阅[表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="b6568-117">For more information about using BizTalk Expression Editor, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span> <span data-ttu-id="b6568-118">有关调用[!INCLUDE[btsDotNet](../includes/btsdotnet-md.md)]类，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。</span><span class="sxs-lookup"><span data-stu-id="b6568-118">For more information about calling [!INCLUDE[btsDotNet](../includes/btsdotnet-md.md)] classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6568-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6568-119">See Also</span></span>  
 <span data-ttu-id="b6568-120">[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b6568-120">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 <span data-ttu-id="b6568-121">[与使用的 WCF 服务的 SOAP 标头](../core/soap-headers-with-consumed-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="b6568-121">[SOAP Headers with Consumed WCF Services](../core/soap-headers-with-consumed-wcf-services.md) </span></span>  
 [<span data-ttu-id="b6568-122">与已发布的 WCF 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="b6568-122">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)