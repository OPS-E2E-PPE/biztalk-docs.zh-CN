---
title: WCF 适配器常见问题解答： 消息流和映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 907e5c6a-a095-4b3a-9362-506832b6bc8c
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae55b6447923e9618a3e4776284659d48a2b25a9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968174"
---
# <a name="wcf-adapter-faq-message-flow-and-mapping"></a>WCF 适配器常见问题解答： 消息流和映射
## <a name="what-is-the-message-flow-within-the-wcf-and-biztalk-systems"></a>WCF 和 BizTalk 系统中的消息流是什么？  
 以下是对传入 BizTalk Server 的 WCF 消息流的说明：  
  
1. WCF 消息到达接收位置，然后 BizTalk Server 实例化承载的 WCF 服务。  
  
2. WCF 运行时实例化服务的通道堆栈及其通道侦听器。 通道堆栈是处理不同处理任务的阶段序列。 每个通道堆栈至少由一个传输通道（大多数情况下为消息编码器）和零或多个协议通道组成。 传输通道读取到达的传入消息流。 它调用编码器来解释该消息并生成 WCF 消息对象。 此时，每个协议通道都有机会按顺序操作 WCF 消息。  
  
3. WCF 消息由侦听器接收，该侦听器通过配置的 WCF 通道堆栈转发消息并将其调度到相应的服务实例。 此时，WCF 消息被转换（映射）为 BizTalk 消息。 简而言之，WCF 消息标头被写入 BizTalk 消息上下文，且 WCF 消息正文被写入 BizTalk 消息的正文部分。 映射控制 WCF 消息的哪个部分变为 BizTalk 消息正文： 信封、 正文或子元素。  
  
4. 在接收位置配置的任何管道组件处理 BizTalk 消息。  
  
5. 将 BizTalk 消息存储在 MessageBox 数据库中。  
  
   以下是对自 BizTalk Server 传出的 WCF 消息流的说明：  
  
6. 发送端口根据其订阅接收 BizTalk 消息。  
  
7. 在发送端口配置的任何管道组件处理 BizTalk 消息。  
  
8. 根据服务的外部可见协议，实例化 WCF 通道堆栈，且将 BizTalk 消息转换（映射）为 WCF 消息。  
  
9. WCF 通道堆栈将 WCF 消息传输到外部 WCF 服务。  
  
## <a name="how-is-a-wcf-message-converted-mapped-into-a-biztalk-message"></a>如何将 WCF 消息转换（映射）为 BizTalk 消息？  
 要了解映射，我们需要查看 WCF 消息和 BizTalk 消息的结构。  
  
 WCF 消息以 SOAP 消息结构为模型，由消息属性、消息标头和一个消息正文组成。  
  
- **消息属性**是附加到消息对象的公共语言运行时 (CLR) 对象。 这些属性对于通信每端的 WCF 堆栈和用户应用程序都是内部属性。 它们从不直接在客户端和服务器之间进行传输。  
  
- **消息标头**，但是，客户端和服务器之间进行传输。 一条消息中可能含有许多标头，但只有一个消息正文，与标头不同，以流方式传输消息正文。 消息标头和消息正文都定义为 XML Infoset。  
  
- **正文**的 WCF 消息是为其属性和标头提供的详细信息的消息的主要内容。  
  
  BizTalk 消息具有不同的结构。  
  
- 每条消息有一组上下文属性。 每个上下文属性都由命名空间名称/值对组成。 上下文属性可被升级或写入。 如果是升级，它们可参与到在 BizTalk Server 中执行的路由规则。  
  
- BizTalk Server 中消息的数据可由多个数据流组成。 BizTalk 消息分为多部分，因为可以分别读取各个流。 其中一个消息部分比较特殊，称为正文部分。  
  
  因为通信有时是双向的，所以 WCF 适配器允许为消息交换的入站和出站方向配置特定的转换或映射。 可为 BizTalk Server 中的接收位置和发送端口执行此操作。  
  
  BizTalk WCF 适配器在运行时支持在这两种消息结构之间进行多种排列的转换。 通过控制映射**消息**选项卡**传输属性**个 WCF 适配器的对话框。 例如，最明显转换也即默认转换是在入站 WCF 消息的正文变为 BizTalk 消息的正文时。 有关映射模式的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkID=119792 ](http://go.microsoft.com/fwlink/?LinkID=119792)。  
  
## <a name="how-can-you-preserve-the-complete-incoming-wcf-message-inside-the-biztalk-message"></a>如何在 BizTalk 消息内保留完整的 WCF 传入消息？  
 入站 BizTalk 消息正文选项之一是**信封**选项。 选择此选项可将 soap:Envelope 元素中包含的整个 SOAP 消息带到传入 BizTalk 消息正文。 所生成的 BizTalk 消息将包含信封标记、所有标头和正文。  
  
## <a name="how-can-you-extract-specific-elements-of-the-incoming-wcf-message-into-a-biztalk-message-or-map-elements-of-an-outgoing-biztalk-message-to-an-outgoing-wcf-message"></a>如何将传入 WCF 消息的特定元素提取到 BizTalk 消息，或如何将传出 BizTalk 消息的元素映射到传出 WCF 消息？  
 若要映射 WCF 或 BizTalk 消息正文的一部分，请使用“路径或模板”选项。 这使您可以输入 XPath 表达式来提取消息正文的特定部分。 在这种情况下不支持完整的 XPath 语法，因为提取是流式传输的，因此读取器必须始终向前读取内容。 这就是在为什么**消息**它称为"路径-按正文路径定位内容"而不是"XPath – 按正文路径定位内容。"选项卡  
  
 在接收端，使用指示如何从 WCF 消息读取数据的 Path 表达式。 对于入站消息，Path 语句提取的特定元素将替换 BizTalk 消息的正文。 适配器使用此 Path 表达式来查找和提取 BizTalk 消息的所需数据。  
  
 在发送端，使用模板从 BizTalk 消息创建 WCF 消息。 为出站消息指定模板选项可允许 XPath 选项反向。 在 WCF 适配器配置中，XML 代码段用作出站消息结构的基础。 BizTalk 消息的内容在运行时插入到此结构中。  
  
 对于传出消息，还必须选择使用“节点编码”设置（XML、Base64、String 或 Hexadecimal）所编写元素的类型。 在希望提取 WCF 消息中包含的二进制数据流时，此选项非常有用。 使用此功能可指示 WCF 适配器对 WCF 消息的正文读取器调用 ReadContextAsBase64。 此调用允许直接通过 XmlReader API 读取二进制数据，因此使用此功能，二进制数据可以直接从 WCF Transport 移动到 BizTalk MessageBox 数据库。 通过写入含有二进制数据的节点的路径，您可以提取它并将其放入 BizTalk 消息。  
  
## <a name="how-do-you-access-wcf-message-properties-within-an-incoming-wcf-message"></a>如何访问传入 WCF 消息中的 WCF 消息属性？  
 若要在传入 WCF 消息转换为 BizTalk 消息之前访问其中的属性，可以结合使用 WCF 行为和自定义 WCF 通道组件或服务模型扩展点。 例如， **IDispatchMessageInspector**对象。 BizTalk Wcf-custom 和 Wcf-customisolated 适配器提供了使你的应用程序可插入到使用 WCF 行为的强大功能轻松地**行为**选项卡**传输属性**对话框这些适配器。  
  
 若要使 WCF 消息的属性可用于 WCF 适配器，必须首先将这些属性作为内容写入消息正文或标头。 自动为您将标头复制到 BizTalk 消息上下文。 如果你想升级属性值，可用于自定义 BizTalk 管道组件中将 WCF 消息属性升级到 BizTalk 消息上下文**IComponent： 执行**方法。 WCF 自定义适配器中使用自定义 WCF 行为，可充分利用 WCF 和 BizTalk 的扩展性让您的解决方案，更为强大和灵活。 WCF 适配器使您可以结合使用现有 BizTalk 和 WCF 扩展性来解决问题。  
  
 好消息是在这种常见属性情况下，WCF 适配器中有一个快捷方式。 您只需使用 WCF 扩展创建 WCF 适配器了解的新“已知”属性，而无需同时写入这两个扩展内容。  
  
 为了将 SOAP 标头值写入或升级到 BizTalk 消息上下文，WCF 消息必须包含由属性名称和命名空间组成的值对集合。 这使 WCF 适配器可以识别标头值是被写入还是被升级的。  
  
 在将 SOAP 标头值写入或升级到 BizTalk 消息上下文时，WCF 适配器需要获取 WCF 消息中的以下消息属性：  
  
-   若要升级到 BizTalk 消息上下文的 SOAP 标头值，WCF 适配器会寻找的密钥对**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote**和值**列表 < KeyValuePair\<XmlQualifiedName，对象\>>**. 使用此对 WCF 适配器采用命名空间、 名称和值从**XmlQualifiedName**对象，并将其用于升级标头值。  
  
-   若要编写，而不是升级到 BizTalk 消息上下文中，SOAP 标头值 WCF 适配器会寻找的密钥对**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext**和值**列表 < KeyValuePair\<XmlQualifiedName，对象\>>。** WCF 适配器使用此对将这些值写入消息上下文。  
  
> [!NOTE]
>  还必须在 BizTalk 属性架构中指定升级的属性，以便被 BizTalk 运行时接受。  
  
## <a name="you-have-an-existing-orchestration-or-send-port-etc-that-expects-a-biztalk-multipart-message-how-can-you-get-a-multipart-message-in-the-wcf-scenario"></a>您有一个期望 BizTalk 多部分消息的现有业务流程（或发送端口等）。 如何在 WCF 方案中获取多部分消息？  
 BizTalk 多部分消息由一个或多个消息部分组成。 但是，WCF 没有多部分消息的概念。 因为 WCF 不使用多部分消息，所以 BizTalk WCF 适配器也不使用它们。 问题在于，您可以让写入的现有 BizTalk 业务流程或管道生成或使用多部分消息。  
  
 如果需要通过传入 WCF 消息和 WCF 适配器将多部分消息写入 BizTalk Server，请在 WCF 消息中以 XML 形式显示多部分数据。 开发自定义 BizTalk 管道组件可处理传入 XML 流（WCF 消息）并为应用程序创建相应的 BizTalk 多部分消息。 如果需要，可以在发送端反向完成这些步骤。