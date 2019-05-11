---
title: IBaseMessage 接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10bfb95c-aef5-46ba-ba0e-9961833f27a3
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 009c9df42e8dbce58f3b731932ef4077693f0f63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382812"
---
# <a name="ibasemessage-interface"></a>IBaseMessage 接口
当接收适配器接受传入数据包通过其协议时，它使用**IBaseMessage**接口，以创建一条消息将传递给消息引擎。 使用此接口来表示所有消息。  
  
 一条消息有一个或多个消息部分由**IBaseMessagePart**接口。 每个消息部分已通过其数据的引用**IStream**接口指针。 表示将消息上下文及其**IBaseMessageContext**接口。 下图说明了 BizTalk 消息对象模型。  
  
 ![](../core/media/ibasemessagestructure.gif "IBaseMessageStructure")  
  
 消息上下文是一个字典，其中为键属性名称和属性命名空间的组合。 这会阻止来自不同源，例如，类似的命名属性之间的冲突[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统属性和自定义适配器属性。 这些属性的值是在.NET 类型的**对象**，但这些属性实际上是变体。  
  
 每个部分具有一个部分上下文，也是一个字典，但不支持命名空间的概念。 部分上下文的值是指该部分数据的元数据。 这就**Charset**属性，它指定用于对消息编码的字符集。  
  
 属性可能会写入到和从消息上下文中读取。 它们还可能会提升要用于消息路由。 正在升级的意味着将其随消息流动的元数据的一部分。 使用升级的属性，其值以在创建发送端口和业务流程的筛选器表达式中使用。 下游组件和业务流程中的用户代码可能会读取升级的属性，并还写入新值。  
  
 与现有订阅匹配已提升的属性并将其用于将消息路由后，该属性被降级，以防止循环订阅匹配。 降级的属性将保留在消息上下文，因为元数据但会失去升级的状态。  
  
 **实现提示：** 在运行时将消息上下文属性加载到内存。 过大的数据应不会写入消息上下文因为这可能会影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持大消息。 对象可能会被序列化到消息上下文中实现**IPersistStream**接口。 此外，升级的属性仅限于 255 个字符。  
  
 始终应使用消息工厂来创建新消息。  下面的代码段演示了如何从适配器接收到的数据流中创建新的 BizTalk 消息。  
  
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