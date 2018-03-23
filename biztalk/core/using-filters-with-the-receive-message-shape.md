---
title: 使用筛选器与接收消息形状 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filters, receive messages
- messages, filters
ms.assetid: 5310039b-6719-4971-933a-2da0573fb5e7
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1434e9704e073cfef1503ef550409e6d6414bb7c
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="using-filters-with-the-receive-message-shape"></a>使用接收消息形状使用筛选器
筛选器表达式是可应用于业务流程接收形状的可选参数，它将“激活”属性的值指定为 True。 如果指定了某一筛选器表达式，则只有当传入消息与该筛选器表达式中指定的条件匹配时，才会激活业务流程。 如果没有指定任何筛选器表达式，则业务流程订阅的任何传入消息都将激活该业务流程。  
  
 若要创建某一筛选器表达式，可以将表达式左侧的传入消息的属性与该表达式右侧的常量进行比较。 您还可以通过将 AND 和 OR 运算符应用于两个或多个表达式，创建复合表达式。 还可以将筛选器表达式保留为空，在此情况下，将会接受所有消息。  
  
 筛选器表达式可能如下：  
  
```  
InvoiceSchema.Quantity >= 1000  
```  
  
 在此示例中，将一个传入消息提供给业务流程。 该业务流程没有激活 **接收** 形状 ( **激活** 属性设置为 **True** ，以便收到某些消息会导致业务流程会) 与前面的筛选器表达式应用于它。 传入的消息应该具有属性的命名空间中调用数量 **InvoiceSchema**。 该业务流程只接受 1000 或更多项的发票，因此，运行时引擎将在该业务流程运行前检查传入的消息。  
  
 下表显示您可以在筛选器表达式中使用的运算符。  
  
|运算符|Description|示例|  
|--------------|-----------------|-------------|  
|==|等于|ReqMsg(Total) == 100|  
|!=|不等于|ReqMsg(Total) != 100|  
|<|小于|ReqMsg(Total) \< 100|  
|>|大于|ReqMsg(Total) > 100|  
|<=|小于或等于|ReqMsg(Total) \<= 100|  
|>=|大于或等于|ReqMsg(Total) > = 100|  
|存在|存在|ReqMsg(Description) exists|  
  
> [!NOTE]
>  在筛选表达式中的字符串值括在引号中，例如︰ reqmsg （description) ="采购订单状态"。 不能在筛选器表达式中使用字符值。  
  
> [!NOTE]
>  如果您的激活接收与某一直接绑定端口相关联，并且随后发送与在您的筛选器中测试的属性具有相同值的相同类型的消息，将会造成无限循环。 消息将发送到 MessageBox，在那里将会再次挑选它，因为该消息与筛选器条件匹配。 为了避免这一问题，您应该或者筛选不同属性，发送不同类型的消息，或者确保在发送出同一类型的消息前更改该属性的值。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置接收形状](../core/how-to-configure-the-receive-shape.md)   
 [在业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)   
 [使用可分辨的字段和属性字段](../core/using-distinguished-fields-and-property-fields.md)   
 [在业务流程中使用消息](../core/using-messages-in-orchestrations.md)