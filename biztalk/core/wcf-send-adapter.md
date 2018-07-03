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
ms.openlocfilehash: b7f36bca73ebd178d8d4052bfbcfa837c0d548ab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020666"
---
# <a name="wcf-send-adapter"></a>WCF 发送适配器
WCF 发送适配器允许您通过无类型的协定调用 WCF 服务。  
  
## <a name="specifying-the-wcf-message-body"></a>指定 WCF 消息正文  
 可以通过使用下列选项之一将需要从 BizTalk Server 发送的消息正文插入到 SOAP 消息中：  
  
- 提取 BizTalk 消息正文的内容  
  
- 通过使用模板中指定的内容  
  
  您可以在“发送端口传输属性”对话框中配置这些选项。  
  
#### <a name="extract-the-content-of-the-biztalk-message-body"></a>提取 BizTalk 消息正文的内容  
 当选中此选项时，BizTalk 消息正文的内容会插入到出站 WCF 消息正文的 SOAP 正文元素中。  
  
#### <a name="specify-the-content-by-using-the-template"></a>通过使用模板指定内容  
 当选中此选项时，会将 BizTalk 消息正文放置到出站 WCF 消息正文的给定的 XML 模板下的 SOAP 正文元素中。  
  
## <a name="serializing-the-biztalk-message-into-a-soap-message"></a>将 BizTalk 消息序列化到 SOAP 消息中  
 在发出 BizTalk 消息之前，发送适配器会将 BizTalk 消息序列化到 SOAP 消息中。在消息的序列化过程中，以下规则适用：  
  
-   如果 BizTalk 消息是由多个部分组成的消息，则只会使用正文部分。  
  
-   如果 BizTalk 消息包含整个 SOAP 信封，则会将其包装到另一个 SOAP 信封中。  
  
-   如果 BizTalk 消息包含任意 XML 数据，则会将 BizTalk 消息放置到 SOAP 正文元素中。  
  
## <a name="handling-web-services-headers"></a>处理 Web Services 标头  
 在发送操作期间，BizTalk Server 无法控制 Web Services 标准标头。 这些标头会通过 WCF 进行设置和处理。 可以修改 BizTalk Server 应用程序的唯一标准标头是 **： 操作**标头。 如果上下文属性**操作**指定适配器命名空间，则 WCF 发送适配器将使用的属性的值来设置**操作**对 SOAP 消息。  
  
> [!NOTE]
>  对于动态发送端口，如果**操作**中指定**OutboundHeaders**，为设置的上下文属性**WCF。操作**将被忽略。  
  
## <a name="specifying-the-btsisdynamicsend-context-property"></a>指定 BTS.IsDynamicSend 上下文属性  
 WCF 发送适配器缓存发送端口的配置。 如果**BTS。IsDynamicSend**属性设置为 true，则 WCF 发送适配器将不使用缓存的配置，而改为所有配置信息从都读取消息的出站消息上下文属性。 静态发送端口，WCF 发送适配器将使用**BTS。SPLastUpdatedTime**，上次修改对象指的是静态发送端口设置的时间，以检测是否存在任何配置更改的静态发送端口。 这样，WCF 发送适配器就不需要从每个消息上下文中读取所有设置。  
  
 如果你想要重写静态发送端口属性而不**WCF。操作**发送管道中的属性，则需要设置**BTS。IsDynamicSend**属性设置为 true，以便即使的上次更新时间戳，则 WCF 发送适配器将使用缓存的配置未更改。  
  
## <a name="see-also"></a>请参阅  
 [指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [WCF 接收适配器](../core/wcf-receive-adapter.md)   
 [WCF 适配器有哪些？](../core/what-are-the-wcf-adapters.md)   
 [如何使用消息上下文属性](../core/how-to-use-message-context-properties.md)