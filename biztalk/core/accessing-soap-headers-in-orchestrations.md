---
title: 访问在业务流程中的 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, properties
- orchestrations, SOAP headers
ms.assetid: 91fe053a-3f16-497c-b4bb-5fb54bec62e5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 516b2bcc57bef507a028f30c61fd329a5fd7a598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225917"
---
# <a name="accessing-soap-headers-in-orchestrations"></a>访问在业务流程中的 SOAP 标头
对于已定义的和未知的 SOAP 标头，您可以在业务流程中访问 SOAP 标头上下文属性。 有关属性架构和上下文属性的详细信息，请参阅[属性架构](../core/property-schemas.md)。  
  
## <a name="defined-soap-header-context-properties"></a>已定义的 SOAP 标头上下文属性  
 在业务流程中的定义的 SOAP 标头上下文属性需要属性架构。 属性架构必须具有的目标命名空间**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**，和**属性架构基**属性设置为**MessageContextPropertyBase**。 属性架构中的每个根元素名称必须与定义的 SOAP 标头的根元素名称匹配。 然后，就可以访问使用属性架构和属性名称的命名空间的上下文属性的值。 属性架构的命名空间是上面列出的目标命名空间不同。 尽管属性架构的命名空间可以是任意字符串，它通常默认项目的名称。  
  
 下面的示例演示访问属性架构命名空间中，SOAP 标头上下文属性**SOAPHeader**，及属性名称**OrigDest**:  
  
```  
stringVar = requestMessageInstance(SOAPHeader.OrigDest);  
```  
  
> [!NOTE]
>  已定义的 SOAP 标头被视为“in”或“out”标头。 如果向导为请求和响应消息定义的 SOAP 标头相同，则该向导不会在响应中自动返回传入值。 您必须将请求消息的 SOAP 标头上下文属性显式复制到响应消息的 SOAP 标头上下文属性中。  
  
## <a name="copying-soap-header-context-property-of-incoming-message"></a>复制传入消息的 SOAP 标头上下文属性  
 您可以将传入消息的 SOAP 标头上下文属性复制到响应消息的相同 SOAP 标头上下文属性中。  
  
 下面的示例显示了如何复制 SOAP 标头上下文属性：  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = RequestMessageInstance(SOAPHeader.OrigDest);  
```  
  
 为 SOAP 响应创建 SOAP 标头时，必须确保您已正确创建 SOAP 标头。 SOAP 适配器不验证 SOAP 标头上下文属性的内容。 如果响应 SOAP 标头的值错误，则 SOAP 适配器不会将此响应消息发送给 Web Services 的使用者。  
  
## <a name="unknown-soap-header-context-property"></a>未知的 SOAP 标头上下文属性  
 未知的 SOAP 标头上下文属性不需要属性架构。 你可以访问此全局上下文属性**SOAP。UnknownHeaders**。  
  
 下面的示例演示访问未知的 SOAP 标头上下文属性**SOAP。UnknownHeaders**:  
  
```  
stringVar = RequestMessageInstance(SOAP.UnknownHeaders);  
```  
  
 上下文属性中包含的值是包含 XML 数据的字符串。 访问此数据的最简单方法是使用中的 BizTalk 表达式编辑器**消息分配**或**表达式**的形状，然后加载中的字符串**XmlDocument**和使用若要访问特定字段的 XPATH 查询。 创建 BizTalk 表达式编辑器中的 XML 文档的详细信息，请参阅[XLANG-s 语言](../core/xlang-s-language.md)。  
  
 上下文属性与某一特定消息关联。 消息引擎不会自动映射已知从请求消息到响应消息的 SOAP 头的值。 在创建 Web 服务的响应消息时，你必须专门设置的 SOAP 标头值。 以下命令为设置的 SOAP 标头上下文属性的最简单方法：  
  
```  
ResponseMessageInstance(SOAPHeader.OrigDest) = "<?xml version="1.0" encoding="utf-16"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination xmlns=\"\">Home</Origination><Destination xmlns=\"\">Work</Destination> </OrigDest>"  
```  
  
 你还可以通过创建实现此**XmlDocument**和写入的字符串值**XmlDocument**到上下文属性。  
  
> [!NOTE]
>  如果**SOAP。UnknownHeaders**属性为 null，则 BizTalk 自动返回接收到 SOAP 响应 SOAP 请求中的未知标头。 如果**SOAP。UnknownHeaders**的响应消息的上下文属性不为 null，则 BizTalk SOAP 响应中返回该值。  
  
## <a name="see-also"></a>另请参阅  
 [与发布的 Web 服务的 SOAP 标头](../core/soap-headers-with-published-web-services.md)