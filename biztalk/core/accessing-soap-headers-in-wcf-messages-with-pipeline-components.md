---
title: 访问在与管道组件的 WCF 消息的 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, WCF services
- WCF services, pipeline components
- pipeline components, SOAP headers
- SOAP headers, pipeline components
- WCF services, SOAP headers
- SOAP headers, WCF messages
ms.assetid: 5e24afa3-b2e6-472e-8890-a47b59573304
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8bc9c2c17172cb29ee75bfbfc4aaee841848fa
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965099"
---
# <a name="accessing-soap-headers-in-wcf-messages-with-pipeline-components"></a><span data-ttu-id="02186-102">使用管道组件访问 WCF 消息中的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="02186-102">Accessing SOAP Headers in WCF Messages with Pipeline Components</span></span>
<span data-ttu-id="02186-103">若要访问管道组件中的 WCF 适配器的 SOAP 标头，你使用的上下文的属性名称组合**InboundHeaders**，和的目标命名空间**http://schemas.microsoft.com/BizTalk/2006/01/适配器/WCF properties**。</span><span class="sxs-lookup"><span data-stu-id="02186-103">To access the SOAP headers with the WCF adapters in pipeline components, you use a combination of the context property name, **InboundHeaders**, and the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**.</span></span> <span data-ttu-id="02186-104">WCF 适配器将自定义 SOAP 标头和标准 SOAP 标头复制到入站消息中**InboundHeaders**属性。</span><span class="sxs-lookup"><span data-stu-id="02186-104">The WCF adapters copy custom SOAP headers and standard SOAP headers in the inbound messages to the **InboundHeaders** property.</span></span> <span data-ttu-id="02186-105">使用 WCF 适配器，您还可以以编程方式选择要以编程方式升级或写入至上下文属性的属性。</span><span class="sxs-lookup"><span data-stu-id="02186-105">The WCF adapters also allow you to programmatically select the properties you would like to promote or write to the context properties programmatically.</span></span> <span data-ttu-id="02186-106">请参阅[发布 WCF 服务使用的 SOAP 标头](../core/soap-headers-with-published-wcf-services.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="02186-106">See [SOAP Headers with Published WCF Services](../core/soap-headers-with-published-wcf-services.md) for more details.</span></span>  
  
 <span data-ttu-id="02186-107">上下文属性中包含的值是一个包含与 XML 数据字符串\<**标头**\>根元素和传入的 SOAP 标头将复制作为子元素的\< **标头**\>元素。</span><span class="sxs-lookup"><span data-stu-id="02186-107">The value contained in the context property is a string containing XML data with the \<**headers**\> root element, and the incoming SOAP headers are copied as child elements of the \<**headers**\> element.</span></span> <span data-ttu-id="02186-108">有关如何对访问 SOAP 标头与 WCF 适配器的详细信息，请参阅"使用自定义 SOAP 标头与 WCF 适配器"中的 SDK 示例在[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)。</span><span class="sxs-lookup"><span data-stu-id="02186-108">For more information about how to access SOAP headers with the WCF adapters, see the SDK sample "Using Custom SOAP Headers with the WCF Adapters" at [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
 <span data-ttu-id="02186-109">自定义管道组件中的以下代码获取请求的 SOAP 标头中将接收管道组件**InboundHeaders**属性：</span><span class="sxs-lookup"><span data-stu-id="02186-109">The following code from a custom pipeline component gets the request SOAP header in a receive pipeline component for the **InboundHeaders** property:</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
   {  
   string stringVar = inmsg.Context.Read("InboundHeaders",    "http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties").ToString();  
   }  
   catch (Exception ex)  
   {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
   }  
return inmsg;  
}  
```  
  
 <span data-ttu-id="02186-110">有关管道组件的详细信息，请参阅[开发自定义管道组件](../core/developing-custom-pipeline-components.md)。</span><span class="sxs-lookup"><span data-stu-id="02186-110">For more information about pipeline components, see [Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02186-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02186-111">See Also</span></span>  
 <span data-ttu-id="02186-112">[访问在与业务流程的 WCF 消息的 SOAP 标头](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="02186-112">[Accessing SOAP Headers in WCF Messages with Orchestrations](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md) </span></span>  
 <span data-ttu-id="02186-113">[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="02186-113">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="02186-114">SOAP 标头与使用的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="02186-114">SOAP Headers with Consumed WCF Services</span></span>](../core/soap-headers-with-consumed-wcf-services.md)