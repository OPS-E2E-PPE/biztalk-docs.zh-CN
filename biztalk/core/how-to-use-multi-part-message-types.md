---
title: 如何使用多部分消息类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6b4a6d6714b7e4f3d31ad25c72277ef725d3592
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383317"
---
# <a name="how-to-use-multi-part-message-types"></a>如何使用多部分消息类型
每个消息具有多部分消息类型，包含零个或多个消息部分的消息结构的说明。 通过 XML 架构定义 (XSD) 语言架构或.NET 类定义部分。 可以定义自己的多部分消息类型，也可以使用现有的.NET 类和架构。  

 您可以访问或将消息部分分配直接在您的业务流程，也可以使用的消息部分公开为可分辨的字段或属性字段的单个元素。 有关详细信息，请参阅[使用可分辨字段和消息属性](../core/using-distinguished-fields-and-property-fields.md)。  

> [!NOTE]
>  多部分消息类型不一定包含多个部分。  

> [!NOTE]
>  可通过.NET 类型定义消息部分**XmlDocument**，这可以用于包含任意 XML 文档、 XML 序列化，任何.NET 类型或任何.NET 类型支持的自定义序列化。  

## <a name="add-a-multi-part-message-type"></a>添加多部分消息类型  

1.  在中**业务流程视图**窗口中，展开**类型**节点。  

2.  右键单击**多部分消息类型**，然后单击**新建多部分消息类型**。  

     **多部分消息类型**文件夹扩展，如果处于折叠状态，并与一个默认消息部分添加一个新的多部分消息类型。  

3.  命名多部分消息类型和提供的消息部分。  

     如果您的多部分消息类型需要多个消息部分，可以通过将分配到的名称添加其他部分\<新建\>消息部分。  

4.  将每个消息部分类型，如.NET 类或架构与相关联。  

## <a name="remove-a-multi-part-message-type"></a>删除多部分消息类型  

-   在中**业务流程视图**窗口中，右键单击多部分消息的类型要删除，然后单击**删除**。  

    > [!NOTE]
    >  从您的业务流程中删除多部分消息类型也将删除的类型信息从使用它的消息。  

    > [!NOTE]
    >  另一个业务流程中定义了项显示为只读的。  

## <a name="remove-a-part-from-a-multi-part-message-type"></a>从多部分消息类型中删除部件  

-   在中**业务流程视图**窗口中，右键单击你想要删除，然后单击的部件**删除**。  

    > [!NOTE]
    >  如果不能删除消息类型的消息部分**消息正文部分**属性设置为 true。 必须先设置**消息正文部分**属性设置为 True 的另一个消息类型的部件。  

## <a name="set-the-type-modifier-for-a-multi-part-message-type"></a>设置多部分消息类型的类型修饰符  

- 在中**属性**窗口中，设置以下属性：  


  |     属性      |                                                                                                                                                                                        Description                                                                                                                                                                                         |
  |-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  | **类型修饰符** | 确定多部分消息类型的作用域：<br /><br /> -   <strong>私有 —</strong>此多部分消息类型的访问权限仅限于包含模块。<br />-   <strong>公共 —</strong>访问此多部分消息类型不受限制。<br />-   <strong>内部 —</strong>此多部分消息类型的访问权限仅限于同一项目中的模块。 |

## <a name="add-parts-to-an-existing-multi-part-message"></a>将部件添加到现有的多部分消息  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供将部件添加到多部分 XLANG 消息，还可以来引用消息部分索引大于最初声明的部分数如果该部分存在的功能。 此功能可能可用于发送或接收 SMTP 消息具有可变数量的附件。 此功能实现，如下所示：  

- 从你的项目，添加对的引用**Microsoft.XLANGs.BaseTypes**。  

- 创建一个变量 (例如*xlangPart*) 的类型**Microsoft.XLANGs.BaseTypes.XLANGMessage**。  

- 调用<em>xlangPart</em>**。AddPart(...)** 使用适当的参数从表达式形状。  

  > [!NOTE]
  >  已增加的部件属于类型**XmlDocument**因此不能添加自定义格式的消息部分使用**addpart （)** 方法。  

> [!NOTE]
>  如果收到包含多于声明部分数量更多部分消息，则业务流程引擎读取有多少个部分是在消息中，然后构造正确的部分类型的部件的匹配部分中声明的消息数类型，然后构造**XmlDocument**部件的剩余部分。  

## <a name="see-also"></a>请参阅  
 **IBaseMessage.AddPart 方法 (COM)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]  
 [在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)   
 [使用可分辨的字段和属性字段](../core/using-distinguished-fields-and-property-fields.md)   
 [在业务流程中使用消息](../core/using-messages-in-orchestrations.md)