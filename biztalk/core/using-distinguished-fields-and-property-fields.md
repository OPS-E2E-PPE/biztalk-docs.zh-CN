---
title: "使用可分辨的字段和属性字段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, distinquished fields
- messages, properties
ms.assetid: 264ee15e-be9a-4ba2-9c61-a1570b20378e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b5d5ee3b29c068b3a37d248b9fb20f07bdfbb2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="using-distinguished-fields-and-property-fields"></a>使用可分辨的字段和属性字段
可分辨字段是具有特殊作用的消息数据，主要用于决策或处理业务流程中的数据。  
  
 消息属性或者是数据（消息本身的内容），或者是元数据（与消息有关的上下文信息，例如时间戳或路由信息）。 您可以使用系统定义的消息上下文属性或传输上下文属性，或者可以通过引用属性架构内的架构字段来定义您自己的属性。 属性用于订阅和相关。  
  
-   可以通过使用作为可分辨的字段或属性字段中指定架构中的字段**升级属性**从编辑器内的对话框。 有关详细信息，请参阅[升级属性](../core/promoting-properties.md)  
  
-   您可以通过使用 DistinguishedField 属性修饰 .NET 类型中的字段来将这一字段指定为可分辨字段，或者通过 Property 属性将该字段指定为属性字段。  
  
## <a name="using-distinguished-fields"></a>使用可分辨字段  
 可分辨字段通过指向消息中的字段的路径进行引用，并且使用句点来分隔消息名称、包含该字段的任何记录的名称以及字段本身的名称：  
  
```  
MyMessage.MyRecord.MySubrecord.MyDistinguishedField  
```  
  
## <a name="using-property-fields"></a>使用属性字段  
 一旦您将某一字段添加到某一属性架构后，就可以在含代码的业务流程和筛选器表达式中访问其值。 有关属性架构的详细信息，请参阅[属性架构](../core/property-schemas.md)。  
  
> [!NOTE]
>  消息内容或数据属性是实质上是对基础数据的快捷方式： 如果你修改属性，将修改的数据，反之亦然。  
  
 消息属性通过消息名称后随括号中的命名空间（架构）和属性名称引用：  
  
```  
MyMessage(Invoice.PropertySchema.InvoiceID)  
```  
  
> [!NOTE]
>  当保留的关键字用作在架构中，字段的名称，并将该字段提升通过选择快速升级时，该字段的属性名称将更改为 __\<保留关键字\>。 （双下划线添加到属性名称之前。）但是，如果您在业务流程表达式中使用此属性名称，则在生成业务流程时将会收到一个编译器错误。  若要更正这一错误，需要在双下划线前手动添加 @。 例如：  
>   
>  `MyMessage(Invoice.PropertySchema.@__Name) = "Product Name";`  
  
## <a name="property-sets"></a>属性集  
 您还可以将一个消息的所有上下文属性（属性集）都分配给其他消息的上下文属性。 若要分配某一属性集，只需将用括号括起来的星号放置于两个消息名称后，其方式与在括号中放置属性相同：  
  
```  
MyMessage2(*)=MyMessage1(*);  
```  
  
 在上例中将该属性集分配给 MyMessage2 后，MyMessage2 中的所有属性都将包含与 MyMessage1 中的属性相同的值。  
  
## <a name="see-also"></a>另请参阅  
 [提升属性](../core/promoting-properties.md)   
 [使用接收消息形状使用筛选器](../core/using-filters-with-the-receive-message-shape.md)   
 [在业务流程中使用消息](../core/using-messages-in-orchestrations.md)   
 [关于 BizTalk 消息上下文属性](../core/about-biztalk-message-context-properties.md)