---
title: "如何使用 MessageBox 直接绑定端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1839184b-408e-4ac6-94a4-a0eb708183f6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82fbe52d46847bdaa7caffbb4402ce8d380a73f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-messagebox-direct-bound-ports"></a>如何使用 MessageBox 直接绑定端口
MessageBox 直接绑定的端口，可以直接在没有显式的接收方 MessageBox 数据库丢弃的消息并订阅满足特定条件的消息，而不是来自特定发件人的消息。  
  
 在消息框上发送消息直接绑定的端口是等效于将消息发布到消息总线 — 在这种情况下，到 MessageBox 数据库。 对于任何已发布的消息，可存在任意数目的订户；并且，如果在您发布消息时没有任何订户对此消息感兴趣，将引发“找不到订阅”异常。 如果你在使用特定的接收人的需求的 MessageBox 直接绑定端口通过发送消息，你可能想要将属性设置为中的特定值**消息分配**你预期的订阅服务器，若要寻找的形状。 你可以设置基于预定义的 BizTalk Server 属性定义或你自己的属性定义的属性。 例如：  
  
```  
myMessage(PropertyNamespace.PropertyName) = "My Property")  
```  
  
 接收任何消息通过 MessageBox 直接绑定端口相当于使用筛选器条件消息总线订阅。 消息的收件人可以是服务的任何类型的消息，可以订阅其中包括业务流程，并发送端口。 激活**接收**形状订阅是消息类型和筛选器表达式中，和非激活**接收**形状订阅是消息类型和相关设置。 每个**接收**形状始终包括作为其订阅的一部分的消息类型。  
  
> [!NOTE]
>  如果已激活，则必须使用筛选器表达式**接收**接收的消息的类型的形状**System.Xml.XmlDocument**或**Microsoft.XLANGs.BaseTypes.Any**与订阅定义的路由直接绑定的端口。  
  
 如果你未指定任何筛选器条件中激活**接收**形状连接到 MessageBox 直接绑定端口，则订阅将类似于以下：  
  
```  
http://schemas.microsoft.com/BizTalk/2003/system-properties.ReceivePortID == {2F6A80E1-2518-4A69-9C28-401C2DB1CBF6} And  
http://schemas.microsoft.com/BizTalk/2003/system-properties.MessageType == http://MyMessageType  
```  
  
 在前面的示例中，MessageBox 直接绑定接收端口将接收每条消息为配置的端口的操作的消息类型相匹配。  
  
> [!NOTE]
>  当使用 MessageBox 直接绑定接收端口时，您应使筛选尽可能具体。 如果你不一定要筛选器足够具体，您的业务流程可能会收到不需要的消息。  
  
 若要配置的 MessageBox 直接绑定的端口，选择**端口之间的路由将定义消息框数据库中的传入消息的筛选器表达式**在端口配置向导。  
  
 如何使用 MessageBox 直接绑定的端口的示例，请参阅"直接绑定到 MessageBox 数据库中业务流程"中的 SDK 示例在[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="see-also"></a>另请参阅  
 [如何使用自关联 Direct 绑定端口](../core/how-to-use-self-correlating-direct-bound-ports.md)   
 [如何直接使用合作伙伴业务流程绑定端口](../core/how-to-use-partner-orchestration-direct-bound-ports.md)