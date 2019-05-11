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
ms.openlocfilehash: d7bbbde2d18aa2c51b3e5331b9028abb0b0332ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399481"
---
# <a name="tips-for-designing-your-adapter"></a>设计您的适配器的提示
本部分包含提示和适配器开发人员已经学会设计适配器时的提示。  
  
## <a name="handler-properties-should-be-strings-if-used-as-default-configurations"></a>处理程序属性应为字符串，如果用作默认配置  
 它看起来很有吸引力的默认值为使用 XSD 生成的处理程序属性表的属性及其**位置**属性因为未设置值**位置**运行时自动使用处理程序中设置的值。 但有几个问题使这个想法很有用。  
  
 问题在于不知道提供给运行时的值是否重写。 执行此操作的典型方法是为值定义 NULL 概念，然后针对该值运行测试。 问题时使用基于 XSD 的属性表中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是仅针对字符串支持 NULL。 即使您希望适配器具有默认设置通过使用此 NULL 测试并且愿意将适配器限制为字符串类型，它仍暴露于非常别扭的用户界面。  
  
 XSD 生成的属性表仅支持回 NULL 属性的设置，请右键单击该属性，此时**置空？** 出现上下文菜单和属性可以设置为 NULL。 一个属性是 NULL 没有可视反馈。  
  
## <a name="considerations-for-implementing-schema-generation-wizards"></a>有关实现架构生成向导的注意事项  
 程序员喜欢针对强类型化的对象模型编写代码。 在代码中操作 XML 乍看起来比较笨拙，而且容易出错。 但一些技巧并巧妙使用.NET Framework 提供的支持可以极大地简化问题。  
  
#### <a name="do-not-create-xml-documents-with-string-concatenation"></a>不要使用字符串串联创建 XML 文档  
 其中一个最严重的错误，以使与 XML 是尝试并生成从字符串串联和打印内存中的语句。 这会消耗大量的 CPU 时间和内存。 即使对于最简单的 XML 代码段，它是更轻松地将 XmlWriter 或文档对象模型 (DOM) 之类的工具。 如果使用 XmlWriter，不使用原始的写功能，因为编写器会丢失文档的状态。  
  
 在运行时，XmlWriter 比 XML DOM 由于与 DOM 相关联的高内存消耗问题 但是，在配置或设计时这很可能不会出现问题。 使用 DOM 便于使用 XPATH 查询，可以是有用的附加工具。  
  
#### <a name="consider-defining-the-skeleton-of-your-xml-document-as-a-resource"></a>请考虑将 XML 文档的主干定义为资源  
 如果从设计工具生成大型 XML 文档并生成的文档始终遵循相同的基本结构，请考虑为要允许进行更改，当您需要对其进行编辑时的项目中的资源将整个主干 XML 文件。  
  
 将代码加载到 DOM 中，然后到为文档的主干添加枝叶，通过使用 XPATH 挑选出你想要将其添加到的节点。 在这种情况下，创建 Web 服务描述语言 (WSDL) 文件。 该向导在资源中存储主干 WSDL 文件，并添加生成的 XML 架构定义 (XSD) 子级部分。 它使用具有 xpath 的 selectNode 来查找正确的父级。 这是用户界面代码，因此性能不是问题，并且生成的实现是干净、 可靠且易于维护。  
  
## <a name="consider-placing-processing-steps-in-the-biztalk-pipeline"></a>考虑将处理步骤置于 BizTalk 管道  
 一般情况下生成的 Microsoft 适配器移动消息格式基于处理与适配器和 BizTalk 管道。 一个典型示例是结构化，但非 XML 数据源的适配器。  
  
 在这种情况下，适配器仅获取数据并使用 BizTalk 管道对其进行分析并将其转换为等效的 XML。 优点是管道组件本身变得可重复使用一种体系结构。  
  
## <a name="make-adapter-behavior-configurable"></a>使适配器行为可配置  
 从 MQSeries 适配器测试版程序中学到的经验之一是不是所有的客户很乐意使用相同的行为。 当涉及处理错误和排序时更是如此。 解决方法是使行为成为可配置。 您可以指定适配器是否支持排序，失败是否被移至挂起队列中，或它们是否会导致适配器停止处理并禁用其自身。 此类行为可配置可以显著减少客户的工作量时将需要编写复杂的业务流程或脚本外部的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来实现相同的结果。  
  
## <a name="support-correlation-with-message-queues"></a>支持与消息队列相关联  
 许多消息传送平台支持消息标头，以支持应用程序级别请求-响应方案中的相关 ID 的概念。 示例包括 MQSeries、 MSMQ 和 SQL Service Broker。 这看起来很有吸引力的外部消息传送系统的请求-响应模式映射到中的发送-响应适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 但这不会由于所在事务不会有用。 具体而言，发送到外部消息传送系统需要事务性提交之前的另一端的队列看到的数据。 接收也必须在单独的事务。  
  
 中的解决方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是：  
  
- 在业务流程中使用相关集  
  
- 配置两个单独的端口： 一个用于发送和接收  
  
  在简单的示例业务流程指定适配器与消息关联的相关 ID。 这是作为传递到适配器上下文属性对消息。 在更复杂的情况下，该方案调用外部消息传送系统分配 id。 在这种情况下它可以传递从发送端口业务流程并带有响应消息。 此响应消息只是传回 ID，并不是真正的消息响应。  
  
> [!NOTE]
>  争用条件中没有业务流程引擎，以便该消息的真正响应有可能赢取显示发送的 ID 响应。 必须在业务流程本身中处理此争用条件。