---
title: "在与管道组件的 WCF 消息中使用 SOAP 标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, SOAP headers
- SOAP headers, pipeline components
- SOAP headers, WCF services
- WCF services, SOAP headers
ms.assetid: b02f2913-4948-4de9-bc59-73bab40aa1a0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf40cf5a81188dae0174199f16229daf61115796
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers-in-wcf-messages-with-pipeline-components"></a><span data-ttu-id="630c0-102">将 WCF 消息中的 SOAP 标头用于管道组件</span><span class="sxs-lookup"><span data-stu-id="630c0-102">Using SOAP Headers in WCF Messages with Pipeline Components</span></span>
<span data-ttu-id="630c0-103">可以用管道组件中的 WCF 适配器设置自定义 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="630c0-103">You can set the custom SOAP headers with the WCF adapters in pipeline components.</span></span> <span data-ttu-id="630c0-104">你使用的上下文的属性名称组合**OutboundCustomHeaders**，和的目标命名空间**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**。</span><span class="sxs-lookup"><span data-stu-id="630c0-104">You use a combination of the context property name, **OutboundCustomHeaders**, and the target namespace **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**.</span></span> <span data-ttu-id="630c0-105">当你使用**OutboundCustomHeaders**属性，该属性必须具有\<**标头**> 元素作为根元素。</span><span class="sxs-lookup"><span data-stu-id="630c0-105">When you use the **OutboundCustomHeaders** property, the property must have the \<**headers**> element as the root element.</span></span> <span data-ttu-id="630c0-106">所有自定义 SOAP 标头必须放置在\<**标头**> 元素。</span><span class="sxs-lookup"><span data-stu-id="630c0-106">All of the custom SOAP headers must be placed inside the \<**headers**> element.</span></span> <span data-ttu-id="630c0-107">如果自定义 SOAP 标头的值为空字符串，则必须分配\<**标头**>\</**标头**> 或\< **标头**/ > 到**OutboundCustomHeaders**属性。</span><span class="sxs-lookup"><span data-stu-id="630c0-107">If the custom SOAP header value is an empty string, you must assign \<**headers**>\</**headers**> or \<**headers**/> to the **OutboundCustomHeaders** property.</span></span> <span data-ttu-id="630c0-108">有关如何使用 WCF 适配器使用 SOAP 标头的详细信息，请参阅 SDK 示例中，使用自定义 SOAP 标头与 WCF 适配器中，从[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)。</span><span class="sxs-lookup"><span data-stu-id="630c0-108">For more information about how to use SOAP headers with the WCF adapters, see the SDK sample, Using Custom SOAP Headers with the WCF Adapters, from [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960).</span></span>  
  
 <span data-ttu-id="630c0-109">下面的代码示例在名为的属性的发送管道组件设置自定义 SOAP 标头**OutboundCustomHeaders**:</span><span class="sxs-lookup"><span data-stu-id="630c0-109">The following code example sets custom SOAP headers in a send pipeline component for a property named **OutboundCustomHeaders**:</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
      {  
       string stringVar = "<headers>  
             <Origination>Home</Origination>  
             <Destination>Work</Destination>  
          </headers>";  
inmsg.Context.Write("OutboundCustomHeaders","http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties", stringVar);  
      }  
   catch (Exception ex)  
      {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
      }  
return inmsg;  
}  
```  
  
 <span data-ttu-id="630c0-110">有关管道组件的详细信息，请参阅[开发自定义管道组件](../core/developing-custom-pipeline-components.md)。</span><span class="sxs-lookup"><span data-stu-id="630c0-110">For more information about pipeline components, see [Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="630c0-111">您不能设置 WCF 基础结构用于 Web Services 标准（例如 WS-Addressing、WS-Security 和 WS-AtomicTransaction）的标准 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="630c0-111">You must not set the standard SOAP headers that the WCF infrastructure uses for Web services standards such as WS-Addressing, WS-Security, and WS-AtomicTransaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="630c0-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="630c0-112">See Also</span></span>  
 <span data-ttu-id="630c0-113">[在与业务流程的 WCF 消息中使用 SOAP 标头](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="630c0-113">[Using SOAP Headers in WCF Messages with Orchestrations](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md) </span></span>  
 <span data-ttu-id="630c0-114">[与使用的 WCF 服务的 SOAP 标头](../core/soap-headers-with-consumed-wcf-services.md) </span><span class="sxs-lookup"><span data-stu-id="630c0-114">[SOAP Headers with Consumed WCF Services](../core/soap-headers-with-consumed-wcf-services.md) </span></span>  
 <span data-ttu-id="630c0-115">[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md) </span><span class="sxs-lookup"><span data-stu-id="630c0-115">[WCF Adapters Property Schema and Properties](../core/wcf-adapters-property-schema-and-properties.md) </span></span>  
 [<span data-ttu-id="630c0-116">与已发布的 WCF 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="630c0-116">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)