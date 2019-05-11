---
title: WCF 发送适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, headers
- serializing, SOAP messages
- WCF adapters, extracting information
- messages, extracting information
- SOAP messages, serializing
- WCF adapters, message bodies
- send adapters, WCF adapters
- Web services, headers
- WCF adapters, send adapters
ms.assetid: 226a020a-2e12-41fe-a4a2-6683d9e98219
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc48f4da993c4e19c0053342c56b00deff16ead1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266247"
---
# <a name="wcf-send-adapter"></a>WCF 发送适配器
WCF 发送适配器可以调用 WCF 服务通过无类型约定。  
  
## <a name="specifying-the-wcf-message-body"></a>指定 WCF 消息正文  
 需要从 BizTalk Server 发送的消息正文可以插入到 SOAP 消息中，使用以下选项之一：  
  
- 提取 BizTalk 消息正文的内容  
  
- 通过使用模板中指定的内容  
  
  可以在发送端口传输属性对话框中配置这些选项。  
  
#### <a name="extract-the-content-of-the-biztalk-message-body"></a>提取 BizTalk 消息正文的内容  
 选中此选项后，BizTalk 消息正文的内容插入到出站 WCF 消息正文的 SOAP Body 元素。  
  
#### <a name="specify-the-content-by-using-the-template"></a>通过使用模板中指定的内容  
 选中此选项后，BizTalk 消息正文位于出站 WCF 消息正文的给定 XML 模板下的 SOAP 正文元素中。  
  
## <a name="serializing-the-biztalk-message-into-a-soap-message"></a>BizTalk 消息序列化为 SOAP 消息  
 发送适配器序列化为 BizTalk 消息的 SOAP 消息发送出去之前。消息序列化期间适用以下规则：  
  
-   如果 BizTalk 消息是多部分消息，则使用仅正文部分。  
  
-   如果 BizTalk 消息包含整个 SOAP 信封，然后将其包装到另一个 SOAP 信封。  
  
-   如果 BizTalk 消息包含任意 XML 数据，然后 BizTalk 消息放置到 SOAP 正文元素。  
  
## <a name="handling-web-services-headers"></a>处理 Web Services 标头  
 在 BizTalk Server 不具有发送操作期间控制 Web services 标准标头。 这些标头是设置并由 WCF 处理。 可以修改 BizTalk Server 应用程序的唯一标准标头是 **： 操作**标头。 如果上下文属性**操作**指定适配器命名空间，则 WCF 发送适配器将使用的属性的值来设置**操作**对 SOAP 消息。  
  
> [!NOTE]
>  对于动态发送端口，如果**操作**中指定**OutboundHeaders**，为设置的上下文属性**WCF。操作**将被忽略。  
  
## <a name="specifying-the-btsisdynamicsend-context-property"></a>指定 BTS。IsDynamicSend 上下文属性  
 WCF 发送适配器缓存发送端口的配置。 如果**BTS。IsDynamicSend**属性设置为 true，则 WCF 发送适配器将不使用缓存的配置，而改为所有配置信息从都读取消息的出站消息上下文属性。 静态发送端口，WCF 发送适配器将使用**BTS。SPLastUpdatedTime**，上次修改对象指的是静态发送端口设置的时间，以检测是否存在任何配置更改的静态发送端口。 以这种方式 WCF 发送适配器不需要从每个消息上下文中读取的所有设置。  
  
 如果你想要重写静态发送端口属性而不**WCF。操作**发送管道中的属性，则需要设置**BTS。IsDynamicSend**属性设置为 true，以便即使的上次更新时间戳，则 WCF 发送适配器将使用缓存的配置未更改。  
  
## <a name="see-also"></a>请参阅  
 [指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF 接收适配器](../core/wcf-receive-adapter.md)   
 [WCF 适配器有哪些？](../core/what-are-the-wcf-adapters.md)   
 [如何使用消息上下文属性](../core/how-to-use-message-context-properties.md)