---
title: "为出站的参与方解析编写 AS2 上下文属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 808d63d9-076d-4eed-8420-aee12b130fee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c89804c42554825e387d01ff592e3a628e8225b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="writing-as2-context-properties-for-outbound-party-resolution"></a>写入 AS2 上下文属性以进行出站参与方解析
可以使用 AS2To 上下文属性或 `Http.UserHttpHeaders` 上下文属性中的 AS2To 属性来执行出站 AS2 消息的协议解析。 但是，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在收到 AS2 消息后不会将 AS2To 属性写入上下文。 如果要对 AS2To 或 UserHttpHeaders 上下文属性执行协议解析，您必须写入一个自定义业务流程或自定义管道组件来执行此解析。 只有在发送端口未与此协议链接的情况下才需要进行此解析。  
  
 在自定义业务流程中，可以使用下面的代码将 AS2-To 附加到现有 `Http.UserHttpHeaders` 上下文属性的开头：  
  
```  
Message_1(Http.UserHttpHeaders) = “AS2-To: MyPartner\r\n” + Message_1(Http.UserHttpHeaders);  
```  
  
 在自定义管道组件中，可以使用下面的代码将 AS2-To 附加到现有 `Http.UserHttpHeaders` 上下文属性的开头。 您需要在 As2Encoder 组件处理消息前将 AS2-To 附加到 `Http.UserHttpHeaders` 上下文属性。  
  
```  
string strName="UserHttpHeaders";  
string strValue = "AS2-To: MyPartner\r\n" + (string)baseMessage.Context.Read(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties");  
baseMessage.Context.Write(strName, "http://schemas.microsoft.com/BizTalk/2003/http-properties", strValue);  
```  
  
 有关详细信息将提升`EDIIntAS.AS2To`属性或`BTS.UseHttpHeaders`属性为上下文，请参阅"提升 AS2 标头上下文属性"中[通过文件发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)。  
  
 对于你可以将其添加到要写入从 HTTP 标头的自定义管道组件的代码。UserHttpHeaders 上下文属性为消息，请参阅[通过文件发送端口发送 AS2 消息](../core/sending-an-as2-message-over-a-file-send-port.md)。  
  
## <a name="see-also"></a>另请参阅  
 [开发和配置 BizTalk Server AS2 解决方案](../core/developing-and-configuring-biztalk-server-as2-solutions.md)