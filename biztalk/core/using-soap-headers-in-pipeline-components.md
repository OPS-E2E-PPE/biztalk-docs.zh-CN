---
title: "在管道组件中使用 SOAP 标头 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c11b74aafe53150ced42d0c53a2e19a2c5080fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-soap-headers-in-pipeline-components"></a>在管道组件中使用 SOAP 标头
若要访问在管道组件中的 SOAP 标头上下文属性，你使用组合的上下文属性名称和目标命名空间中所述[在业务流程中使用 SOAP 标头](../core/using-soap-headers-in-orchestrations.md)。  
  
 下面的代码示例在发送管道组件的属性名称设置请求的 SOAP 标头**OrigDest**:  
  
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
  
 有关管道组件的详细信息，请参阅[开发自定义管道组件](../core/developing-custom-pipeline-components.md)。  
  
> [!NOTE]
>  当通过业务流程使用（调用）Web 服务时，SOAP 适配器仅支持直通样式的接收和发送管道。 您可以使用自定义管道，但是无法包含修改消息正文部分的组件。 这些组件包括 XML 组装器、XML 拆装器和 XML 验证器组件。  
  
## <a name="see-also"></a>另请参阅  
 [默认管道](../core/default-pipelines.md)   
 [与使用的 Web 服务的 SOAP 标头](../core/soap-headers-with-consumed-web-services.md)