---
title: WCF 接收适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 86d7f307a9c7dae45e81e8c9c1e5bcf57a6ef6b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266391"
---
# <a name="wcf-receive-adapter"></a>WCF 接收适配器
WCF 接收适配器使您可以接收 WCF 服务请求。  
  
## <a name="extracting-the-biztalk-message-body-from-the-soap-message"></a>从 SOAP 消息提取 BizTalk 消息正文  
 可以使用以下选项之一从 SOAP 消息中提取入站的 BizTalk 消息正文：  
  
- 提取 SOAP Body 元素的内容  
  
- 提取整个 SOAP 信封  
  
- 使用 XPath 表达式提取 SOAP 信封内的元素的内容  
  
  在传输属性对话框中，可以配置这些选项。  
  
#### <a name="extract-the-content-of-the-soap-body-element"></a>提取 SOAP Body 元素的内容  
 选中此选项后，SOAP Body 元素内部内容是从 SOAP 消息中读取并放置到 BizTalk 消息的正文部分。  
  
#### <a name="extract-the-entire-soap-envelope"></a>提取整个 SOAP 信封  
 选择此选项，包括标记的整个 SOAP envelope 放置到 BizTalk 消息的正文部分。  
  
#### <a name="extract-the-content-of-the-element-by-using-an-xpath-expression"></a>使用 XPath 表达式提取元素的内容  
 选中此选项后，根据 XPath 表达式定位的 SOAP Body 元素内的元素的内部内容放置到 BizTalk 消息的正文部分。 正文元素中的数据的其余部分将被忽略。 此外需要指定节点编码 — 示例中，XML、 Base64、 Hex 或字符串编码。  
  
> [!NOTE]
>  选择 XML 编码时，是根据 XPath 表达式定位外部元素的内容并将其放置到正文部分。  
  
## <a name="handling-web-services-headers"></a>处理 Web Services 标头  
 接收适配器将 BizTalk 消息上下文，能够轻松地访问标准 Web services 标头的子集和路由基于这些标头的值。 下表列出了将由接收适配器保存到消息上下文上的属性。 在以下命名空间定义的属性： http://www.w3.org/2005/addressing和 http://schemas.microsoft.com/BizTalk/2006/Adapters/WCF-properties。  
  
|Header|BizTalk 属性名称|是否升级？|  
|------------|---------------------------|------------------|  
|操作|操作|是|  
|MessageID|MessageID|否|  
|若要|若要|是|  
|ReplyTo/Address|ReplyTo|是|  
|从地址|From|是|  
|序列/标识符|SequenceId|是|  
|Sequence/MessageNumber|SequenceNumber|是|  
|Sequence/LastMessage|SequenceLastMessage|是|  
|\<soap:Header\>|InboundHeaders|否|  
  
## <a name="see-also"></a>请参阅  
 [指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF 发送适配器](../core/wcf-send-adapter.md)   
 [WCF 适配器概述](../core/what-are-the-wcf-adapters.md)