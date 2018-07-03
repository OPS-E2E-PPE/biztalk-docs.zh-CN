---
title: 设计您的适配器的提示 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0bb60988-4e48-4654-9cf4-512dd7c97239
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 306cb2ae9aeca57804a57f0dfa8c1de1bfd0025d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982678"
---
# <a name="tips-for-designing-your-adapter"></a>设计适配器的提示
本部分包含适配器开发人员在设计适配器时所发现的技巧。  
  
## <a name="handler-properties-should-be-strings-if-used-as-default-configurations"></a>处理程序属性用作默认配置时应为字符串  
 它看起来很有吸引力的默认值为使用 XSD 生成的处理程序属性表的属性及其**位置**属性因为未设置值**位置**运行时自动使用处理程序中设置的值。 但是有几个问题使这个想法没有多大意义。  
  
 问题在于不知道提供给运行时的值是否会被重写。 为此，通常为值定义 NULL 概念，然后针对该值运行测试。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中使用基于 XSD 的属性表的问题是仅针对字符串支持 NULL。 即使您希望适配器通过使用此 NULL 测试来得到默认设置并且愿意将适配器限制为字符串类型，它所显示的用户界面也非常别扭。  
  
 XSD 生成的属性表仅支持回 NULL 属性的设置，请右键单击该属性，此时**置空？** 出现上下文菜单和属性可以设置为 NULL。 屏幕上不会显示任何信息以指示属性是否为 NULL。  
  
## <a name="considerations-for-implementing-schema-generation-wizards"></a>实现架构生成向导的注意事项  
 程序员喜欢针对强类型对象模型编写代码。 在代码中操作 XML 乍看起来比较笨拙，而且容易出错。 不过，通过一些技巧并巧妙使用 .NET Framework 提供的支持可以在很大程度上简化问题。  
  
#### <a name="do-not-create-xml-documents-with-string-concatenation"></a>请勿使用字符串串联来创建 XML 文档  
 使用 XML 时最严重的错误之一就是试图通过字符串串联和打印内存中的语句来生成 XML。 这会消耗大量 CPU 时间和内存。 即使对于最基本的 XML 代码段，使用诸如 XmlWriter 或文档对象模型 (DOM) 等工具都会简化操作。 如果您使用 XmlWriter，请勿使用“写入后读取”写功能，因为编写器会丢失文档的状态。  
  
 在运行时，由于与 DOM 相关的大量内存消耗问题，XmlWriter 比 XML DOM 优先级高。 但是在配置或设计时，这很可能就不是个问题了。 使用 DOM 可以更好地使用 XPATH 查询，这是个有用的附加工具。  
  
#### <a name="consider-defining-the-skeleton-of-your-xml-document-as-a-resource"></a>考虑将 XML 文档的主干定义为资源  
 如果要通过设计工具生成很大的 XML 文档并且生成的文档始终具有相同的基本结构，则可以考虑将整个主干 XML 文件作为项目中的资源，以便在需要编辑时对其进行更改。  
  
 将代码加载到 DOM 中，然后为文档的主干添加枝叶，方法是使用 XPATH 挑选要添加内容的节点。 在本示例中，您将创建 Web Services 描述语言 (WSDL) 文件。 该向导在资源中存储主干 WSDL 文件，并添加生成的 XML 架构定义 (XSD) 子级部分。 它使用具有 xpath 的 selectNode 来查找正确的父级。 这是用户界面代码，所以性能不是问题并且生成的实现方法清楚、功能强大并且可维护。  
  
## <a name="consider-placing-processing-steps-in-the-biztalk-pipeline"></a>考虑将处理步骤置于 BizTalk 管道中  
 通常情况下，Microsoft 生成的适配器会将基于消息格式的处理过程从适配器中移出，然后移入 BizTalk 管道中。 结构化非 XML 数据源的适配器就是一个很好的示例。  
  
 在这种情况下，适配器仅获取数据，而 BizTalk 管道则用于分析该数据并将其转换为 XML 中的等效数据。 优点是管道组件自身成为结构中可重复使用的部分。  
  
## <a name="make-adapter-behavior-configurable"></a>使适配器行为可配置  
 从 MQSeries 适配器测试版程序中学到的经验之一是：不是所有的客户都会满意同一个行为。 当涉及处理错误和排序时，更是如此。 解决方法是使行为成为可配置的。 您可以指定适配器是否支持排序，失败是否被移到挂起队列，或它们是否会导致适配器停止处理并禁用其自身。 当客户需要在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 外部编写复杂的业务流程或脚本来达到同一结果时，编写可配置的行为可以在很大程度上减少客户的工作量。  
  
## <a name="support-correlation-with-message-queues"></a>支持与消息队列相关联  
 很多消息传送平台支持消息标头的相关 ID 的概念，以支持应用程序级别的请求-响应方案。 示例包括 MQSeries、MSMQ 和 SQL Service Broker。 将外部消息传送系统的请求-响应模式映射到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的发送-响应适配器，这看起来很有吸引力。 但是，由于存在事务，此操作没有任何意义。 具体而言，向外部消息传送系统发送数据时需要事务性提交，然后队列的另一端才可以看到数据。 接收也必须是单独的事务。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的解决方案将执行以下操作：  
  
- 在业务流程中使用相关集  
  
- 配置两个单独的端口： 一个用于发送和接收  
  
  在简单的情形中，业务流程按适配器指定与消息有关的相关 ID。 它作为消息的上下文属性传递给适配器。 在更复杂的情况下，该方案调用外部消息传送系统分配 id。 在这种情况下它可以传递从发送端口业务流程并带有响应消息。 此响应消息只是传回 ID，并不是真正的消息响应。  
  
> [!NOTE]
>  在业务流程引擎中有一个争用条件，可能会显示消息的真正响应而不显示发送端口的 ID 响应。 此争用条件必须在业务流程自身中处理。