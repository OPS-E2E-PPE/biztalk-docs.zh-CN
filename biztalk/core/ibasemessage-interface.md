---
title: "IBaseMessage 接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10bfb95c-aef5-46ba-ba0e-9961833f27a3
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7de478b27105ee6c01d582aa9b728bd0496d0487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ibasemessage-interface"></a>IBaseMessage 接口
当接收适配器接受传入的数据包通过其协议时，它会使用**IBaseMessage**接口可创建要传递给 the Messaging Engine 一条消息。 所有消息都是使用这个接口传递的。  
  
 一条消息具有一个或多个消息部分由**IBaseMessagePart**接口。 每个消息部分有对通过其数据的引用**IStream**接口指针。 一条消息的上下文都由其**IBaseMessageContext**接口。 下图阐释了 BizTalk 消息对象模型。  
  
 ![](../core/media/ibasemessagestructure.gif "IBaseMessageStructure")  
  
 消息上下文是一个字典，以属性名称和属性命名空间的组合为键。 这会阻止来自不同源，例如，类似名称的属性之间的冲突[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统属性和自定义适配器属性。 这些属性的值是.NET 类型的**对象**，但这些属性实际上是变体。  
  
 每个部分均有一个部分上下文，同样也是字典，但没有命名空间这个概念。 部分上下文的值为元数据，指向该部分数据。 此示例是**Charset**指定用于编码消息的字符集的属性。  
  
 属性可以写入消息上下文，也可以从消息上下文中读取。 还可以升级属性，以用于消息路由。 升级意味着将其作为元数据的一部分随消息流动。 属性经升级后，其值可用于对发送端口和业务流程创建筛选器表达式。 业务流程中的下游组件和用户代码可读取升级属性，还可以对属性赋新值。  
  
 升级属性与现有订阅匹配完毕并用于路由消息后，该属性将被降级，以防止发生循环订阅匹配。 降级属性仍作为元数据留在消息上下文中，但会失去升级状态。  
  
 **实现提示：**消息上下文属性都在运行时加载到内存。 非常大片的数据应不会写入消息上下文因为这可能会中断[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持大消息。 可能将对象序列化到消息上下文提供其实现**IPersistStream**接口。 同样，升级属性的长度也限制在 255 个字符之内。  
  
 应始终应当使用消息工厂来创建新消息。  下面的代码段演示了如何用适配器接收的数据流来创建新的 BizTalk 消息。  
  
```  
using Microsoft.BizTalk.Message.Interop;  
  
IBaseMessage CreateMessage( Stream s, IBaseMessageFactory msgFactory )  
{  
IBaseMessage msg = null;  
IBaseMessagePart part = msgFactory.CreateMessagePart();  
part.Data = s;  
msg = msgFactory.CreateMessage();  
msg.AddPart("body", part, true);  
return msg;  
}  
```