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
# <a name="accessing-soap-headers-in-wcf-messages-with-pipeline-components"></a>使用管道组件访问 WCF 消息中的 SOAP 标头
若要访问管道组件中的 WCF 适配器的 SOAP 标头，你使用的上下文的属性名称组合**InboundHeaders**，和的目标命名空间**http://schemas.microsoft.com/BizTalk/2006/01/适配器/WCF properties**。 WCF 适配器将自定义 SOAP 标头和标准 SOAP 标头复制到入站消息中**InboundHeaders**属性。 使用 WCF 适配器，您还可以以编程方式选择要以编程方式升级或写入至上下文属性的属性。 请参阅[发布 WCF 服务使用的 SOAP 标头](../core/soap-headers-with-published-wcf-services.md)有关详细信息。  
  
 上下文属性中包含的值是一个包含与 XML 数据字符串\<**标头**\>根元素和传入的 SOAP 标头将复制作为子元素的\< **标头**\>元素。 有关如何对访问 SOAP 标头与 WCF 适配器的详细信息，请参阅"使用自定义 SOAP 标头与 WCF 适配器"中的 SDK 示例在[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)。  
  
 自定义管道组件中的以下代码获取请求的 SOAP 标头中将接收管道组件**InboundHeaders**属性：  
  
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
  
 有关管道组件的详细信息，请参阅[开发自定义管道组件](../core/developing-custom-pipeline-components.md)。  
  
## <a name="see-also"></a>另请参阅  
 [访问在与业务流程的 WCF 消息的 SOAP 标头](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md)   
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [SOAP 标头与使用的 WCF 服务](../core/soap-headers-with-consumed-wcf-services.md)