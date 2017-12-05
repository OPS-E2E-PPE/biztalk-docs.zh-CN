---
title: "WCF 接收适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, headers
- receive adapters, Web service headers
- SOAP messages, extracting information
- SOAP messages, WCF adapters
- WCF adapters, receive adapters
- messages, SOAP
- receive adapters, WCF adapters
- Web services, headers
- headers [messages]
- SOAP messages, receive adapters
ms.assetid: 6b3d5df1-5d9d-4240-a98f-ea29c3272e38
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdd4d6335723d068333403b4c9d811d96db058e9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="wcf-receive-adapter"></a>WCF 接收适配器
WCF 接收适配器允许您接收 WCF 服务请求。  
  
## <a name="extracting-the-biztalk-message-body-from-the-soap-message"></a>从 SOAP 消息中提取 BizTalk 消息正文  
 可使用下列选项之一从 SOAP 消息中提取入站 BizTalk 消息正文：  
  
-   提取 SOAP Body 元素的内容  
  
-   提取整个 SOAP 信封  
  
-   使用 XPath 表达式提取 SOAP 信封内部的元素的内容  
  
 您可以在“传输属性”对话框中配置这些选项。  
  
#### <a name="extract-the-content-of-the-soap-body-element"></a>提取 SOAP 正文元素的内容  
 当选中此选项时，将从 SOAP 消息读取 SOAP Body 元素的内部内容，并将其放置到 BizTalk 消息的正文部分中。  
  
#### <a name="extract-the-entire-soap-envelope"></a>提取整个 SOAP 信封  
 当选中此选项时，整个 SOAP 信封（包括标记）都将被放置到 BizTalk 消息的正文部分中。  
  
#### <a name="extract-the-content-of-the-element-by-using-an-xpath-expression"></a>使用 XPath 表达式提取元素的内容  
 当选中此选项时，根据 XPath 表达式定位的 SOAP Body 元素内部的元素内部内容将被放置到 BizTalk 消息的正文部分中， 并忽略 Body 元素中的其余数据。 你还需要指定节点编码-示例中，XML，Base64、 十六进制或字符串编码。  
  
> [!NOTE]
>  当选择 XML 编码时，将根据 XPath 表达式定位元素的外部内容，并将其放置到正文部分中。  
  
## <a name="handling-web-services-headers"></a>处理 Web Services 标头  
 接收适配器将标准 Web Services 标头的一部分升级为 BizTalk 消息上下文，以便基于这些标头的值进行更方便的访问和路由。 下表列出了接收适配器将保存为消息上下文的属性。 在以下命名空间下定义的属性： http://www.w3.org/2005/addressing and http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-properties。  
  
|标题|BizTalk 属性名称|是否升级？|  
|------------|---------------------------|------------------|  
|操作|操作|是|  
|MessageID|MessageID|是|  
|若要|若要|是|  
|ReplyTo/Address|ReplyTo|是|  
|From/Address|From|是|  
|Sequence/Identifier|SequenceId|是|  
|Sequence/MessageNumber|SequenceNumber|是|  
|Sequence/LastMessage|SequenceLastMessage|是|  
|\<soap： 标头\>|InboundHeaders|是|  
  
## <a name="see-also"></a>另请参阅  
 [为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF 发送适配器](../core/wcf-send-adapter.md)   
 [WCF 适配器概述](../core/what-are-the-wcf-adapters.md)