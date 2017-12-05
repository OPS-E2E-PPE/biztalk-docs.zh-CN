---
title: "如何使用多个部分消息类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multi-part message types, parts
- multi-part message types, creating
- multi-part message types, type modifiers
- messages
- multi-part message types, deleting
- orchestrations, messages
- deleting, multi-part messages
- multi-part message types, about multi-part message types
- orchestrations, type modifier
- messages, multi-parts
- creating, multi-part messages
- messages, about messages
ms.assetid: 009a39bd-cfc4-42d9-918c-88ac24bfc370
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4e4a07b88e832d99f586d10cdf8af4dbea3af3e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-use-multi-part-message-types"></a>如何使用多个部分消息类型
每条消息都具有多部分消息类型，该消息类型描述由零个或多个消息部分构成的消息结构。 这些部分由 XML 架构定义 (XSD) 语言架构或 .NET 类定义。 您可以定义自己的多部分消息类型，或使用现有的 .NET 类和架构。  
  
 您可以在业务流程中直接访问或分配消息部分，或使用消息部分中已公开为可分辨字段或属性字段的单个元素。 有关详细信息，请参阅[使用可分辨字段和消息属性](../core/using-distinguished-fields-and-property-fields.md)。  
  
> [!NOTE]
>  多部分消息类型不一定包含多个部分。  
  
> [!NOTE]
>  可以由.NET 类型定义的消息部分**XmlDocument**，这可以用于包含任意 XML 文档由 XML 序列化，任何.NET 类型或任何.NET 类型支持的自定义序列化。  
  
## <a name="add-a-multi-part-message-type"></a>添加多个部分消息类型  
  
1.  在**业务流程视图**窗口中，展开**类型**节点。  
  
2.  右键单击**多部分消息类型**，然后单击**新多部分消息类型**。  
  
     **多部分消息类型**文件夹扩展，如果折叠状态，并与一个默认的消息部分添加一个新的多个部分消息类型。  
  
3.  命名多部分消息类型和所提供的消息部分。  
  
     如果多个部分消息类型需要多个消息部分，你可以通过分配到名称添加其他部分\<新建\>消息部件。  
  
4.  将每个消息部分与一个类型相关联，如 .NET 类或架构。  
  
## <a name="remove-a-multi-part-message-type"></a>删除多个部分消息类型  
  
-   在**业务流程视图**窗口中，右键单击多部分消息你想要删除，然后单击的类型**删除**。  
  
    > [!NOTE]
    >  从业务流程中删除多部分消息类型还会从使用它的消息中删除类型信息。  
  
    > [!NOTE]
    >  显示为只读的项目将在其他业务流程中定义。  
  
## <a name="remove-a-part-from-a-multi-part-message-type"></a>从多个部分消息类型删除部件  
  
-   在**业务流程视图**窗口中，右键单击你想要删除，然后单击的部分**删除**。  
  
    > [!NOTE]
    >  如果不能删除消息类型的消息部分**消息正文部分**属性设置为 true。 首先必须设置**消息正文部分**属性设置为 True 的另一个消息类型的部件。  
  
## <a name="set-the-type-modifier-for-a-multi-part-message-type"></a>为多个部分消息类型设置的类型修饰符  
  
-   在**属性**窗口中，设置以下属性：  
  
    |属性|Description|  
    |--------------|-----------------|  
    |**类型修饰符**|确定多部分消息类型的作用域：<br /><br /> -   **私有-**到这种多个部分的消息类型的访问仅限于包含模块。<br />-   **公共 —**访问此多个部分消息类型不受限制。<br />-   **内部 —**到这种多个部分的消息类型的访问仅限于同一项目中的模块。|  
  
## <a name="add-parts-to-an-existing-multi-part-message"></a>将部件添加到现有的多个部分消息  
  
-   使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以向多部分 XLANG 消息中添加部分，还可以使用大于最初声明的部分号的索引来引用消息部分（如果该部分存在）。 在发送或接收附件数量不确定的 SMTP 邮件时，此功能可能十分有用。 按照以下所述进行操作，即可实现此功能：  
  
-   从你的项目，添加对的引用**Microsoft.XLANGs.BaseTypes**。  
  
-   创建一个变量 (例如*xlangPart*) 类型的**Microsoft.XLANGs.BaseTypes.XLANGMessage**。  
  
-   调用*xlangPart***。AddPart(...)**使用表达式形状从相应的参数。  
  
    > [!NOTE]
    >  添加的部件属于类型**XmlDocument**无法添加自定义格式的消息部分使用**AddPart()**方法。  
  
> [!NOTE]
>  如果收到包含大于的声明部分数多部分消息时，有多少个部分是在消息中，业务流程引擎读取然后构造中声明的消息的部件的数量匹配的部件的正确部件类型类型，然后构造**XmlDocument**部件的其余部分。  
  
## <a name="see-also"></a>另请参阅  
 **IBaseMessage.AddPart 方法 (COM)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
 [在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)   
 [使用可分辨的字段和属性字段](../core/using-distinguished-fields-and-property-fields.md)   
 [在业务流程中使用消息](../core/using-messages-in-orchestrations.md)