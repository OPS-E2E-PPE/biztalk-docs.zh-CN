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
# <a name="accessing-soap-headers-in-wcf-messages-with-orchestrations"></a>访问 WCF 消息与业务流程中的 SOAP 标头
若要访问的业务流程中传入 WCF 消息的 SOAP 标头值，使用上下文属性**WCF。InboundHeaders**。 WCF 适配器将自定义 SOAP 标头和标准 SOAP 标头复制到的入站消息中**WCF。InboundHeaders**属性。 WCF 适配器还可以选择你想要升级或写入至上下文属性以编程方式的属性。 请参阅[SOAP 标头发布 WCF 服务与](../core/soap-headers-with-published-wcf-services.md)的更多详细信息。  
  
 上下文属性中包含的值是一个包含 XML 数据字符串\<**标头**\>根元素和传入的 SOAP 标头复制为子元素的\< **标头**\>元素。 若要访问此数据的最简单方法是使用 BizTalk 表达式编辑器在**消息赋值**或**表达式**形状中，加载中的字符串**XmlDocument**，并使用若要访问特定字段的 XPath 查询。 有关在 BizTalk 表达式编辑器中创建 XML 文档的详细信息，请参阅[xlang-s 语言](../core/xlang-s-language.md)。  
  
 下面的代码示例获取请求 SOAP 标头**消息赋值**或**表达式**形状**WCF。InboundHeaders**属性：  
  
```  
stringVar = inboundMessageInstance(WCF.InboundHeaders);  
```  
  
 上下文属性与某一特定消息关联。 消息引擎不会自动映射从请求消息的 SOAP 标头到响应消息的值。 在创建 WCF 服务的响应消息时，必须专门设置 SOAP 标头值通过**WCF。OutboundCustomHeaders**属性。 以下命令为设置的 SOAP 标头上下文属性的最简单方法：  
  
```  
outboundMessageInstance(WCF.OutbounCustomHeaders) = "<headers><Origination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Home</Origination><Destination xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">Work</Destination></headers>"  
```  
  
 此外可以通过创建设置上下文属性**XmlDocument**和的字符串值写入**XmlDocument**为上下文属性。  
  
 有关如何对访问 SOAP 标头用于 WCF 适配器的详细信息，请参阅 SDK 示例"使用自定义 SOAP 标头与 WCF 适配器"处[ http://go.microsoft.com/fwlink/?LinkId=79960 ](http://go.microsoft.com/fwlink/?LinkId=79960)。  
  
## <a name="see-also"></a>请参阅  
 [访问管道组件使用的 WCF 消息中的 SOAP 标头](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md)   
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [SOAP 标头与使用的 WCF 服务](../core/soap-headers-with-consumed-wcf-services.md)