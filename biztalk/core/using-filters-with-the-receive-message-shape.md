---
title: 接收消息形状中使用筛选器 |Microsoft Docs
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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58c0ed34645fc7b576a76092c676d4eb4c390020
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246424"
---
# <a name="using-filters-with-the-receive-message-shape"></a>接收消息形状中使用筛选器
筛选器表达式是一个可选参数，可以应用于业务流程接收形状指定值的激活属性，则返回 True。 如果指定了筛选器表达式然后业务流程将仅激活如果传入消息与筛选器表达式中指定的条件相匹配。 如果不指定任何筛选器表达式，则业务流程订阅任何传入消息将激活业务流程。  
  
 若要创建筛选器表达式，进行比较的表达式右侧的常量表达式左侧的传入消息的属性。 此外可以创建复合表达式，通过应用 AND 和 OR 运算符对两个或多个表达式。 您也可以将空白筛选器表达式中，在这种情况下将接受所有消息。  
  
 筛选器表达式可能如下所示：  
  
```  
InvoiceSchema.Quantity >= 1000  
```  
  
 在此示例中，传入消息，提供给业务流程。 业务流程具有激活**接收**形状 (**激活**属性设置为**True** ，以便收到某些消息将导致业务流程，以运行) 与前面的筛选器表达式应用于它。 传入消息都必须具有属性的命名空间中名为 Quantity **InvoiceSchema**。 业务流程接受仅为 1000年或多个项的发票，因此其运行前，运行时引擎将检查传入的消息。  
  
 下表显示了可以使用筛选器表达式中的多个运算符。  
  
|运算符|Description|示例|  
|--------------|-----------------|-------------|  
|==|等于|ReqMsg(Total) == 100|  
|!=|不等于|ReqMsg(Total) != 100|  
|<|小于|ReqMsg(Total) \< 100|  
|>|大于|ReqMsg(Total) > 100|  
|<=|小于或等于|ReqMsg(Total) \<= 100|  
|>=|大于或等于|ReqMsg(Total) >= 100|  
|存在|存在|Reqmsg （description） 存在|  
  
> [!NOTE]
>  在筛选表达式中的字符串值括在引号中，例如：Reqmsg （description) ="Purchase Order Status"。 不能在筛选器表达式中使用的字符值。  
  
> [!NOTE]
>  如果您的激活接收程序与直接绑定端口，并随后发送具有相同的值在筛选器中测试的属性的相同类型的消息，将创建一个无限循环。 该消息将转到 MessageBox，其中它将会再次挑选由于它匹配的筛选条件。 若要避免此问题，应该对不同属性进行筛选、 可以发送不同类型的消息，或确保将相同类型的消息发送之前更改属性的值。  
  
## <a name="see-also"></a>请参阅  
 [如何配置接收形状](../core/how-to-configure-the-receive-shape.md)   
 [业务流程中使用的相关性](../core/using-correlations-in-orchestrations.md)   
 [使用可分辨的字段和属性字段](../core/using-distinguished-fields-and-property-fields.md)   
 [在业务流程中使用消息](../core/using-messages-in-orchestrations.md)