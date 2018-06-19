---
title: 在与管道组件的 WCF 消息中使用 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, SOAP headers
- SOAP headers, pipeline components
- SOAP headers, WCF services
- WCF services, SOAP headers
ms.assetid: b02f2913-4948-4de9-bc59-73bab40aa1a0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce166c5d05b8ce48f513420e247e8f35ca1d509
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973835"
---
# <a name="using-soap-headers-in-wcf-messages-with-pipeline-components"></a>将 WCF 消息中的 SOAP 标头用于管道组件
可以用管道组件中的 WCF 适配器设置自定义 SOAP 标头。 你使用的上下文的属性名称组合**OutboundCustomHeaders**，和的目标命名空间**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**。 当你使用**OutboundCustomHeaders**属性，该属性必须具有\<**标头**\>作为根元素的元素。 所有自定义 SOAP 标头必须放置在\<**标头**\>元素。 如果自定义 SOAP 标头的值为空字符串，则必须分配\<**标头**\>\</**标头**\>或\<**标头**/ \>到**OutboundCustomHeaders**属性。 有关如何使用 WCF 适配器使用 SOAP 标头的详细信息，请参阅 SDK 示例中，使用自定义 SOAP 标头与 WCF 适配器中，从[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)。  
  
 下面的代码示例在名为的属性的发送管道组件设置自定义 SOAP 标头**OutboundCustomHeaders**:  
  
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
  
 有关管道组件的详细信息，请参阅[开发自定义管道组件](../core/developing-custom-pipeline-components.md)。  
  
> [!NOTE]
>  您不能设置 WCF 基础结构用于 Web Services 标准（例如 WS-Addressing、WS-Security 和 WS-AtomicTransaction）的标准 SOAP 标头。  
  
## <a name="see-also"></a>另请参阅  
 [在与业务流程的 WCF 消息中使用 SOAP 标头](../core/using-soap-headers-in-wcf-messages-with-orchestrations.md)   
 [与使用的 WCF 服务的 SOAP 标头](../core/soap-headers-with-consumed-wcf-services.md)   
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [SOAP 标头与已发布的 WCF 服务](../core/soap-headers-with-published-wcf-services.md)