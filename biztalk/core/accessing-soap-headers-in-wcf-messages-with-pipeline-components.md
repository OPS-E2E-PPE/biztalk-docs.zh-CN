---
title: 访问管道组件使用的 WCF 消息中的 SOAP 标头 |Microsoft Docs
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
ms.openlocfilehash: 97488def0187f64c9bdaf0190f891add747c77f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361895"
---
# <a name="accessing-soap-headers-in-wcf-messages-with-pipeline-components"></a>访问管道组件使用的 WCF 消息中的 SOAP 标头
若要访问管道组件中的 WCF 适配器的 SOAP 标头，您使用的上下文属性名称组合**InboundHeaders**，和目标命名空间 **http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties** 。 WCF 适配器将自定义 SOAP 标头和标准 SOAP 标头复制到的入站消息中**InboundHeaders**属性。 WCF 适配器还允许您以编程方式选择想要升级或写入至上下文属性以编程方式的属性。 请参阅[SOAP 标头发布 WCF 服务与](../core/soap-headers-with-published-wcf-services.md)的更多详细信息。  
  
 上下文属性中包含的值是一个包含 XML 数据字符串\<**标头**\>根元素和传入的 SOAP 标头复制为子元素的\< **标头**\>元素。 有关如何对访问 SOAP 标头用于 WCF 适配器的详细信息，请参阅 SDK 示例"使用自定义 SOAP 标头与 WCF 适配器"处[ http://go.microsoft.com/fwlink/?LinkId=79960 ](http://go.microsoft.com/fwlink/?LinkId=79960)。  
  
 自定义管道组件中的以下代码在接收管道组件中为获取请求 SOAP 标头**InboundHeaders**属性：  
  
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
  
## <a name="see-also"></a>请参阅  
 [访问 WCF 消息与业务流程中的 SOAP 标头](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md)   
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [SOAP 标头与使用的 WCF 服务](../core/soap-headers-with-consumed-wcf-services.md)