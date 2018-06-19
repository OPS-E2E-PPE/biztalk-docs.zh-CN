---
title: 在与业务流程的 WCF 消息中使用 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, SOAP headers [WCF services]
- WCF services, orchestrations
- WCF services, SOAP headers
ms.assetid: 31c01e35-a2a6-4ea9-bdf4-6d4311268dbe
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e8248ec62e75a058566eefef1942e1f82061dbb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972907"
---
# <a name="using-soap-headers-in-wcf-messages-with-orchestrations"></a>在与业务流程的 WCF 消息中使用 SOAP 标头
若要在业务流程中发送传出的 WCF 消息的自定义 SOAP 标头，你可以使用上下文属性**WCF。OutboundCustomHeaders**。 WCF 适配器将自定义 SOAP 标头与 WCF 基础结构用于 Web 服务标准（如 WS-Addressing、WS-Security 和 WS-AtomicTransaction）的标准 SOAP 标头合并在一起进行发送。 当你使用**OutboundCustomHeaders**属性，该属性必须具有\<**标头**\>作为根元素的元素。 所有自定义 SOAP 标头必须放置在\<**标头**\>元素。 如果自定义 SOAP 标头的值为空字符串，则必须分配\<**标头**\>\</**标头**\>或\<**标头**/ \>到**OutboundCustomHeaders**属性。  
  
 对于业务流程，SOAP 标头上下文属性均设置为包含 XML 数据的字符串。 使用 BizTalk 表达式编辑器中设置这些字符串**消息分配**或**表达式**形状。 有关如何使用 WCF 适配器使用 SOAP 标头的详细信息，请参阅 SDK 示例中，使用自定义 SOAP 标头与 WCF 适配器中，从[http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)。  
  
 下面的示例（来自消息赋值或表达式形状）显示了用于设置上下文属性的字符串：  
  
```  
outboundMessageInstance(WCF.OutboundCustomHeaders) = "<headers><Origination>Home</Origination><Destination>Work</Destination></headers>"  
```  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a>创建用于设置上下文属性的 XmlDocument  
 你可以设置**WCF。OutboundCustomHeaders**通过创建上下文属性**XmlDocument**和写入的字符串值**XmlDocument**到上下文属性。 声明类型的变量的**XMLDocument**并将 XML 数据分配。  
  
 下面的示例演示声明类型的变量的**XMLDocument**和分配的 XML 数据：  
  
```  
xmlDoc.LoadXml("<headers><Origination>Home</Origination><Destination>Work</Destination></headers>");  
```  
  
 下面的示例显示了如何设置上下文属性：  
  
```  
RequestMessageInstance(WCF.OutboundCustomHeaders) = xmlDoc.OuterXml;  
```  
  
 有关使用 BizTalk 表达式编辑器的详细信息，请参阅[表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)。 有关调用[!INCLUDE[btsDotNet](../includes/btsdotnet-md.md)]类，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
## <a name="see-also"></a>另请参阅  
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [与使用的 WCF 服务的 SOAP 标头](../core/soap-headers-with-consumed-wcf-services.md)   
 [SOAP 标头与已发布的 WCF 服务](../core/soap-headers-with-published-wcf-services.md)