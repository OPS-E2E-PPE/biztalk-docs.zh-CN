---
title: 处理消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- processing
- messages, pipelines
- routing, about routing
- adapters, about adapters
- routing, message types
- processing, messages
- messages, processing
- routing
- messages, routing
- pipelines, about pipelines
- message types
- messages, message types
- messages, adapters
ms.assetid: e6d1f969-20c9-41f6-85cb-46cf92656348
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 829fffc773bfc19100ad03448baf68b5846996f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266485"
---
# <a name="processing-the-message"></a>处理消息
当消息在 BizTalk Server 中传输时，到目前为止我们所介绍的所有组件在消息的处理过程中均发挥了一定的作用。 本部分将提供有关这些组件如何在功能上交互的更详细信息（从接收消息开始）。 下图显示了接收端口的组成部分以及消息流将如何通过接收进程。  
  
 *接收端口* 由一个或多个接收位置以及零个或多个映射组成。 映射为用于将 XML 消息从一种结构或格式转换为另一种结构或格式的可扩展样式表语言转换 (XSLT) 样式表，并通常用于接收进程以将消息规范化为内部格式。 接收位置控制接收消息的终结点。 接收位置由接收适配器的终结点配置以及接收管道组成。  
  
 ![接收端口结构和处理](../core/media/arch-message-processing.gif "arch_message_processing")  
  
## <a name="the-role-of-the-adapter"></a>适配器的作用  
 接收适配器通过读取数据流和创建消息来启动接收消息的过程。 例如，文件适配器发现某文件已置于其配置的位置中，然后在流中读取该文件。 适配器将创建消息（Microsoft.BizTalk.Message.Interop.IBaseMessage 接口实现）、向该消息添加部分（Microsoft.BizTalk.Message.Interop.IBasePart 接口实现）、然后将数据流作为该部分内容进行提供。  
  
 此外，适配器还将写入和升级到与位置、适配器类型以及其他内容（与适配器相关）相关的消息上下文属性。 在创建消息及其上下文后，适配器将消息传递到终结点管理器。 然后，通过为接收位置配置的接收管道处理该消息。 在消息由管道处理后，终结点管理器使用消息代理发布该消息前，使用映射将消息转换为所需格式。  
  
## <a name="the-role-of-the-pipeline"></a>管道的作用  
 尽管初始消息是由适配器创建的，但对收到消息的处理过程大部分发生在接收管道中。 管道处理针对消息内容以及消息上下文。 消息内容通常在解码、拆装和验证阶段进行处理，而对消息上下文的处理则可发生在所有阶段。 但是，管道无需作用于内容或上下文。 例如，默认的直通管道并未配置任何组件并且不会对消息内容或上下文进行处理。 为简单起见，此文档将重点介绍拆装组件，因为这些组件通常对消息路由的影响最大。  
  
 *拆装器* 的工作是处理来自适配器的传入消息并将其拆装成多个消息，以及对消息数据进行解析。 在传入消息具有多个较小的消息时，称为 *交换*。 通过使开发人员能够配置与包装内容（即，平面文件拆装器的头部架构和尾部架构以及 XML 拆装器的信封架构）以及（可能重复）正文内容有关的信息，平面文件拆装器和 XML 拆装器可以处理交换。 此外，这两种拆装器都可将原始消息解析为 XML 内容。 如果在 BizTalk Server 中不需要做进一步的 XML 处理，则自定义拆装器无需将内容解析为 XML。 示例方案包括简单的路由方案，在此方案中，在特定接收位置进入系统的消息将发送到不具有映射或其他基于 XML 的处理的特定发送端口。  
  
## <a name="routing-with-the-message-type"></a>具有消息类型的路由  
 在路由中使用的最常见消息属性之一为消息类型。 在开发人员创建架构以定义消息的结构后，此架构将定义该消息的类型。 类型由架构定义中的根节点和命名空间确定。 例如，如下 XML 文档可能具有消息类型 http://tempuri.org/samples/MessageType#Message  
  
```  
<Message xmlns=http://tempuri.org/samples/MessageType>  
<SomeOtherElement type="sample"/>  
</Message>  
```  
  
 若要在路由中使用消息类型，则必须将其升级到上下文中。 拆装器用于将此值升级到消息上下文以及带有最具体的消息结构信息的管道组件中。 XML 和平面文件拆装器将在处理消息时升级消息类型，并且任何自定义拆装器也应升级此属性以确保正确地进行路由。  
  
 需要特别注意的是，消息不必一定具有某一类型。 如前所述，消息各部分可以是任何二进制数据，并且无需具有定义其结构的架构。 尽管自定义管道组件、适配器或从业务流程调用的代码均可与此类型的消息部分交互，但这些部分通常不必由 BizTalk Server 本身对其进行大量处理（如果有）即可在整个 BizTalk Server 中传递。  
  
 管道组件（例如适配器）还可将属性写入和升级到消息上下文。 实际上，管道组件是大多数开发人员用于将属性放入消息上下文的最常见的机制。 开发人员可创建架构并在架构中升级属性。 此信息将作为批注存储于架构中，以供随后管道组件使用。 所有内置拆装器和组装器组件（平面文件、XML 和 BizTalk 框架）均使用文档架构检索与要升级的属性有关的信息。 使用来自批注的 XML Path 语言 (XPath) 语句，拆装器可以知道要升级的元素在文档中的位置。 在通过文档传输过程中，拆装器将查找与 XPath 语句之一相匹配的元素，并根据需要，将值升级或写入上下文中。  
  
 还可以编写自定义管道组件，以便将接收或发送的消息中任意数据的属性放入上下文。 若要将属性升级到上下文并可用于路由（这可能是升级值的原因），则应创建具有属性定义的属性架构并将其部署到 BizTalk Server。 在定义由自定义组件使用的属性架构前，应首先了解升级属性的各种类型。 在属性架构中定义的升级属性具有以下两种基本类型之一：  
  
-   [Microsoft.XLANGs.BaseTypes.MessageContextPropertyBase](http://msdn.microsoft.com/library/microsoft.xlangs.basetypes.messagecontextpropertybase.aspx) 或  
  
-   [Microsoft.XLANGs.BaseTypes.MessageDataPropertyBase](http://msdn.microsoft.com/library/microsoft.xlangs.basetypes.messagedatapropertybase.messagedatapropertybase.aspx)  
  
 具有基本类型 MessageDataPropertyBase 的属性表示此属性的值来自消息的内容。 这是在属性架构中定义的属性的默认值，并且最常用。 而 MessageContextPropertyBase 则表示属性属于消息上下文，但不必直接来自消息数据。 以 MessageContextPropertyBase 作为其基本类型的属性通常由适配器和拆装器升级，并包含通用属性（例如，消息类型和适配器类型）。  
  
 了解属性的各种类型并在定义属性时适当使用这些类型十分重要。 而对于在业务流程中访问消息的上下文属性时，了解这一点尤为重要。 如果属性标识为 MessageDataPropertyBase，则业务流程设计器将检查要接收消息的架构，并确保该架构定义了匹配的升级属性。 如果在与要访问的升级属性相关联的架构中没有找到任何属性，则设计器将不允许对其进行访问。 相反，如果该属性定义为 MessageContextPropertyBase，则该消息类型将不起作用并可访问该属性。  
  
 在自定义管道中，将属性升级或写入到上下文的机制非常相似。 对于写入属性，可通过调用 IBaseMessageContext.Write 方法将值放置在上下文中。 而对于已升级属性，只需使用 IBaseMessageContext.Promote 方法。 上述每种方法均采用属性名称、命名空间和值。 对于升级属性，名称和命名空间为属性架构中定义的属性的名称和命名空间，并可通过引用属性架构程序集和使用为属性创建的类上的属性，更轻松地对其进行访问。 而可分辨字段则使用公共命名空间 http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields，并且用于检索值的 XPath 表达式通常用作名称。  
  
 下面的代码显示了将属性升级和写入到上下文的示例。 请注意，在此示例中，可分辨字段将写入到上下文中。 这只适用于以下类型的业务流程：在该业务流程中，消息架构将标识可分辨字段以便业务流程设计器了解该字段。 将属性写入到上下文中有助于接收或发送端上的其他管道组件使用这些属性。  
  
```  
//create an instance of the property to be promoted  
SOAP.MethodName methodName = new SOAP.MethodName();  
  
//call the promote method on the context using the property class for name   
//and namespace  
pInMsg.Context.Promote(methodName.Name.Name, methodName.Name.Namespace,   
"theSOAPMethodName");  
  
//write a distinguished field to the context  
pInMsg.Context.Write("theDistinguishedProperty",   
"http://schemas.microsoft.com/BizTalk/2003/btsDistinguishedFields",   
"theDistinguishedValue");  
```  
  
 在将值写入或升级到上下文中时请注意以下事实：  
  
-   如果使用先前曾用于升级属性的同一名称和命名空间将值写入到上下文中，将导致无法再升级该属性。 写入的内容将从根本上覆盖升级的内容。  
  
-   将空值写入到上下文中将删除该值，因为不允许使用空值属性。  
  
-   升级属性的长度限制在 256 个字符之内，而写入属性则没有长度上的限制。  
  
 升级属性用于消息路由，并由于有关比较和存储效率的原因，对升级属性的大小有所限制。 尽管对写入属性的大小没有硬性限制，但如果在上下文中使用过大的值，也会对性能造成影响，因为这些值仍必须与消息一起进行处理和传递。  
  
 在消息准备从 BizTalk Server 发送时，它将在发送端口中经历一个互补的过程。 映射将在发送管道执行前应用于消息，从而，消息在由管道处理并通过适配器发送前转换为特定于客户或应用程序的格式。 在发送管道中，属性将从上下文降级到消息中，而非升级到消息上下文中。  
  
 ![发送端口，并发送管道过程](../core/media/arch-message-processing-2.gif "arch_message_processing 2")  
  
## <a name="see-also"></a>另请参阅  
 [运行时体系结构](../core/runtime-architecture.md)   
 [BizTalk Server 如何处理大消息](../core/how-biztalk-server-processes-large-messages.md)