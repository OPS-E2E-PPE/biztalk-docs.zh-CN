---
title: WCF 适配器常见问题解答：消息流和映射 |Microsoft Docs
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
ms.openlocfilehash: 5d80e16fc03ea7ed60f68cbacc9fb4f24b395b9e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393577"
---
# <a name="wcf-adapter-faq-message-flow-and-mapping"></a>WCF 适配器常见问题解答：消息流和映射
## <a name="what-is-the-message-flow-within-the-wcf-and-biztalk-systems"></a>WCF 和 BizTalk 系统中的消息流是什么？  
 下面是向 BizTalk Server 将传入 WCF 消息流的说明：  
  
1. WCF 消息到达接收位置，然后 BizTalk Server 实例化承载的 WCF 服务。  
  
2. WCF 运行时实例化服务的通道堆栈和其通道侦听器。 通道堆栈是一系列处理不同处理任务的阶段。 每个通道堆栈由至少一个传输通道、 最常消息编码器和零个或多个协议通道组成。 传输通道读取到达的传入消息流。 它调用编码器来解释该消息并生成 WCF 消息对象。 现在每个协议通道将有机会对 WCF 消息按顺序进行操作。  
  
3. 通过将其转发通过已配置的 WCF 通道堆栈并将其调度到相应的服务实例的侦听器接收 WCF 消息。 此时在 WCF 消息转换 （映射） 为 BizTalk 消息。 简而言之，WCF 消息标头被写入 BizTalk 消息上下文，WCF 消息正文被写入 BizTalk 消息正文部分。 映射控制 WCF 消息的哪个部分变为 BizTalk 消息正文：信封、 正文或子元素。  
  
4. 配置接收位置中的任何管道组件处理 BizTalk 消息。  
  
5. BizTalk 消息存储在 MessageBox 数据库。  
  
   下面是来自 BizTalk Server 的传出 WCF 消息流的说明：  
  
6. 通过发送端口根据其订阅接收 BizTalk 消息。  
  
7. 任何管道组件在发送端口过程中配置 BizTalk 消息。  
  
8. 实例化 WCF 通道堆栈时，，BizTalk 消息转换 （映射） 到基于服务的外部可见协议的 WCF 消息。  
  
9. WCF 通道堆栈将传输到外部 WCF 服务的 WCF 消息。  
  
## <a name="how-is-a-wcf-message-converted-mapped-into-a-biztalk-message"></a>如何为 WCF 消息转换 （映射） 为 BizTalk 消息？  
 为了了解该映射，我们需要查看 WCF 消息和 BizTalk 消息的结构。  
  
 WCF 消息所依据的 SOAP 消息结构和消息属性、 消息标头和一个消息正文组成。  
  
- **消息属性**是附加到消息对象的公共语言运行时 (CLR) 对象。 属性是 WCF 堆栈和通信的每个最终用户的应用程序的内部。 它们从不直接客户端和服务器之间的传输。  
  
- **消息标头**，但是，客户端和服务器之间进行传输。 上一条消息，可以有许多标头，但只有一个消息正文，并且标头与消息正文进行流处理。 消息标头和消息正文被定义为 XML Infoset。  
  
- **正文**的 WCF 消息是为其属性和标头提供的详细信息的消息的主要内容。  
  
  BizTalk 消息具有不同的结构。  
  
- 没有一组每个消息的上下文属性。 每个上下文属性包含的命名空间名称/值对。 可以升级或写入上下文属性。 如果对它们进行升级，它们可以参与 BizTalk Server 中执行的路由规则。  
  
- 在 BizTalk Server 中消息的数据可以包含多个流。 因为可以单独读取每个流，是多部分 BizTalk 消息。 一个消息部分比较特殊，它被称为正文部分。  
  
  因为通信有时是双向的 WCF 适配器允许为特定的转换或映射，以配置有关的消息交换的入站和出站方向。 这可以为接收位置和 BizTalk Server 中的发送端口。  
  
  BizTalk WCF 适配器支持在运行时这些两个消息结构之间转换的排列数。 通过控制映射**消息**选项卡**传输属性**个 WCF 适配器的对话框。 例如，最明显转换和默认情况下，为入站 WCF 消息的正文变为 BizTalk 消息的正文时。 有关映射模式的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkID=119792 ](http://go.microsoft.com/fwlink/?LinkID=119792)。  
  
## <a name="how-can-you-preserve-the-complete-incoming-wcf-message-inside-the-biztalk-message"></a>可以保留的 BizTalk 消息内完成的传入 WCF 消息的方式？  
 入站 BizTalk 消息正文选项之一是**信封**选项。 选择此选项将整个 soap: Envelope 元素中包含到传入 BizTalk 消息正文的 SOAP 消息。 生成的 BizTalk 消息包含信封标记、 所有标头和正文。  
  
## <a name="how-can-you-extract-specific-elements-of-the-incoming-wcf-message-into-a-biztalk-message-or-map-elements-of-an-outgoing-biztalk-message-to-an-outgoing-wcf-message"></a>您如何将传入 WCF 消息的特定元素提取到 BizTalk 消息，或将传出 BizTalk 消息的元素映射到传出 WCF 消息？  
 若要映射 WCF 或 BizTalk 消息正文部分，使用路径或模板选项。 这允许您输入的 XPath 表达式提取消息正文的特定部分。 在此情况下不支持完整的 XPath 语法，因为提取流式传输和读取器必须因此始终向前读取。 这就是在为什么**消息**它称为"路径-按正文路径定位内容"而不是"XPath – 按正文路径定位内容。"选项卡  
  
 在接收端，使用路径表达式，用于指示从 WCF 消息中读取数据的方式。 对于入站消息，Path 语句提取的特定元素将替换 BizTalk 消息的内容。 适配器使用此路径表达式来查找和提取 BizTalk 消息的所需的数据。  
  
 在发送端，使用模板从 BizTalk 消息创建 WCF 消息。 出站消息的模板选项旨在允许 XPath 选项反向。 在 WCF 适配器配置中，XML 代码段用作的出站消息的结构的基础。 BizTalk 消息的内容将在运行时插入到此结构。  
  
 为传出消息，还必须选择使用 XML、 Base64、 字符串或十六进制中的节点编码设置编写的元素的类型。 您希望提取 WCF 消息中包含的二进制数据流时，此选项会非常有用。 使用此功能可指示 WCF 适配器使用 WCF 消息的正文读取器调用 ReadContextAsBase64。 此调用允许直接通过 XmlReader API 读取，因此使用此功能，二进制数据可以直接从移动 WCF 传输到 BizTalk MessageBox 数据库中二进制数据。 通过写入含有二进制数据的节点路径可以拉出，并将其放入 BizTalk 消息。  
  
## <a name="how-do-you-access-wcf-message-properties-within-an-incoming-wcf-message"></a>如何访问传入 WCF 消息中的 WCF 消息属性？  
 若要转换为 BizTalk 消息之前，请访问传入 WCF 消息中的属性，可以使用自定义的 WCF 通道组件或服务模型结合使用 WCF 行为扩展点。 例如， **IDispatchMessageInspector**对象。 BizTalk Wcf-custom 和 Wcf-customisolated 适配器提供了使你的应用程序可插入到使用 WCF 行为的强大功能轻松地**行为**选项卡**传输属性**对话框这些适配器。  
  
 若要允许 WCF 消息是可用于 WCF 适配器的属性，这些属性首先需要向其中写入消息正文或标头，因为内容。 标头复制到 BizTalk 消息上下文自动为您。 如果你想升级属性值，可用于自定义 BizTalk 管道组件中将 WCF 消息属性升级到 BizTalk 消息上下文**IComponent： 执行**方法。 WCF 自定义适配器中使用自定义 WCF 行为，可充分利用 WCF 和 BizTalk 的扩展性让您的解决方案，更为强大和灵活。 WCF 适配器可以合并现有的 BizTalk 和 WCF 扩展性来解决你的问题。  
  
 好消息是这种情况下公共属性，WCF 适配器中是一种快捷方式。 而不是写入到这两个扩展内容，您可以只需使用 WCF 扩展创建一个新的"已知"属性，理解的 WCF 适配器。  
  
 为了编写或将 SOAP 标头值升级到 BizTalk 消息上下文，WCF 消息必须包含属性名称和命名空间组成的值对的集合。 这样，WCF 适配器，以便识别的标头值是以写入或升级。  
  
 WCF 适配器需要下面的消息属性中的 WCF 消息的写入或升级到 BizTalk 消息上下文的 SOAP 标头值：  
  
-   若要升级到 BizTalk 消息上下文的 SOAP 标头值，WCF 适配器会寻找的密钥对**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote**和值**列表 < KeyValuePair\<XmlQualifiedName，对象\>>**. 使用此对 WCF 适配器采用命名空间、 名称和值从**XmlQualifiedName**对象，并将其用于升级标头值。  
  
-   若要编写，而不是升级到 BizTalk 消息上下文中，SOAP 标头值 WCF 适配器会寻找的密钥对**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext**和值**列表 < KeyValuePair\<XmlQualifiedName，对象\>>。** WCF 适配器使用此对写入到消息上下文的值。  
  
> [!NOTE]
>  升级的属性还必须在 BizTalk 属性架构中以接受由 BizTalk 运行时指定。  
  
## <a name="you-have-an-existing-orchestration-or-send-port-etc-that-expects-a-biztalk-multipart-message-how-can-you-get-a-multipart-message-in-the-wcf-scenario"></a>具有一个现有的业务流程 （或发送端口，等等） 的期望 BizTalk 多部分消息。 如何在 WCF 方案中获取多部分消息？  
 BizTalk 多部分消息组成一个或多个消息部分。 但是，WCF 具有多部分消息的概念。 因为 WCF 不使用多部分消息，BizTalk WCF 适配器也不会使用它们。 问题在于，您可能具有的现有 BizTalk 业务流程或写入到生成或使用多部分消息的管道。  
  
 如果你需要通过传入 WCF 消息和 WCF 适配器到 BizTalk Server 中获取多部分消息，在 WCF 消息中以 XML 形式呈现多部分数据。 开发用于处理传入 XML 流 （WCF 消息） 并创建应用程序相应的 BizTalk 多部分消息的自定义 BizTalk 管道组件。 如果需要，可以在发送端反向完成这些步骤。