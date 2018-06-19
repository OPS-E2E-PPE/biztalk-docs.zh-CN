---
title: 在管道组件中使用 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, code samples
- SOAP headers, creating
- SOAP headers, pipelines
- SOAP headers, properties
- pipelines, SOAP headers
- Web services, SOAP headers
- creating, SOAP headers
ms.assetid: 5b4a8902-e8f5-44a4-88f7-17f47a9deecd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c11b74aafe53150ced42d0c53a2e19a2c5080fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287269"
---
# <a name="using-soap-headers-in-pipeline-components"></a><span data-ttu-id="81e0f-102">在管道组件中使用 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="81e0f-102">Using SOAP Headers in Pipeline Components</span></span>
<span data-ttu-id="81e0f-103">若要访问在管道组件中的 SOAP 标头上下文属性，你使用组合的上下文属性名称和目标命名空间中所述[在业务流程中使用 SOAP 标头](../core/using-soap-headers-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="81e0f-103">To access the SOAP header context properties in pipeline components, you use a combination of the context property name and target namespace as discussed in [Using SOAP Headers in Orchestrations](../core/using-soap-headers-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="81e0f-104">下面的代码示例在发送管道组件的属性名称设置请求的 SOAP 标头**OrigDest**:</span><span class="sxs-lookup"><span data-stu-id="81e0f-104">The following code example sets the request SOAP header in a send pipeline component for a property name **OrigDest**:</span></span>  
  
```  
public IBaseMessage Execute(IPipelineContext pc, IBaseMessage inmsg)  
{  
   try  
      {  
       string stringVar = "<?xml version=\"1.0\"?>  
          <OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
             <Origination>Home</Origination>  
             <Destination>Work</Destination>  
          </OrigDest>";  
inmsg.Context.Write("OrigDest","http://schemas.microsoft.com/BizTalk/2003/SOAPHeader", stringVar);  
      }  
   catch (Exception ex)  
      {  
   throw new Exception("Pipeline component exception - " + ex.Message);  
      }  
return inmsg;  
}  
```  
  
 <span data-ttu-id="81e0f-105">有关管道组件的详细信息，请参阅[开发自定义管道组件](../core/developing-custom-pipeline-components.md)。</span><span class="sxs-lookup"><span data-stu-id="81e0f-105">For more information about pipeline components, see [Developing Custom Pipeline Components](../core/developing-custom-pipeline-components.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81e0f-106">当通过业务流程使用（调用）Web 服务时，SOAP 适配器仅支持直通样式的接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="81e0f-106">When you consume (call) Web services from an orchestration, the SOAP adapter only supports pass-through style receive and send pipelines.</span></span> <span data-ttu-id="81e0f-107">您可以使用自定义管道，但是无法包含修改消息正文部分的组件。</span><span class="sxs-lookup"><span data-stu-id="81e0f-107">You can use a custom pipeline, but it cannot contain components that modify the body parts of the message.</span></span> <span data-ttu-id="81e0f-108">这些组件包括 XML 组装器、XML 拆装器和 XML 验证器组件。</span><span class="sxs-lookup"><span data-stu-id="81e0f-108">These components include the XML Assembler, XML Disassembler, and XML Validator components.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e0f-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81e0f-109">See Also</span></span>  
 <span data-ttu-id="81e0f-110">[默认管道](../core/default-pipelines.md) </span><span class="sxs-lookup"><span data-stu-id="81e0f-110">[Default Pipelines](../core/default-pipelines.md) </span></span>  
 [<span data-ttu-id="81e0f-111">与使用的 Web 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="81e0f-111">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)