---
title: WCF 适配器常见问题： 使用 WCF 服务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: befa2268-8a65-465f-8086-70a66808845e
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41d02fe0b7be1f53edaac4c18cfd7717a25c3a71
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="wcf-adapter-faq-using-wcf-services"></a>WCF 适配器常见问题解答：使用 WCF 服务
## <a name="how-does-biztalk-server-use-its-wcf-adapters-to-access-wcf-services"></a>BizTalk Server 如何使用其 WCF 适配器访问 WCF 服务？  
 BizTalk WCF 适配器在 BizTalk Server 中通过 WCF 接收位置或发送端口进行配置。 当启用使用 WCF 适配器的接收位置时，将为每个接收位置实例化并初始化一个 ServiceHost 实例。 ServiceHost 运行一个接受传入 WCF 消息的通用服务，然后在将这些消息发布到 BizTalk MessageBox 数据库之前将其转换为 BizTalk 消息。 通用 ServiceHost 服务处于 WCF BizTalk 接收适配器实现内部，并公开一个无类型的协定。 在 WCF 中，一个无类型协定由操作签名组成，它们采用类型为 WCF System.ServiceModel.Channel.Message 的一个参数。  
  
 如果 WCF 服务将由 BizTalk 发送端口访问，即便无数据返回，也应将 WCF 服务的操作标记为 IsOneWay=false。 客户端协定上的操作应使用 IsOneWay=false 和 ReplyAction=”*” 进行批注。  此外，来自客户端的所有调用都应标记为 IsOneWay=”false”。 双向服务操作可以返回的消息类型的值。 此规则的例外使用 WCF NetMsmq 适配器，因为它会执行将消息发送到 MSMQ 队列的单向操作。 在这种情况下，发送端口可以是单向的，并且任何服务操作可标记为 IsOneWay=true。  
  
 还可以在 WCF 中的实际返回空值的方法上定义 isOneWay=false OperationContract，这可能有点令人困惑。 在这种情况下，实际上会在网络上返回一个由 WCF 运行时为您创建的消息。  
  
 BizTalk WCF 适配器将使用此功能。 当您指定单向 BizTalk 端口时，实际上会获得一个在 WCF 适配器实现中 isOneWay=false 的空方法。 关键是，在使用直接通道（如 HTTP 或 net.tcp）时，BizTalk 单向端口实际将对应 isOneWay=false OperationContract。 列队通道（如 net.msmq）的不同之处在于，单向 BizTalk 端口确实会设置为 isOneWay=true OperationContract。 情况不同是因为，WCF 调度程序针对该通道使用一个事务。  
  
## <a name="how-do-you-create-and-use-a-custom-binding-with-a-wcf-custom-adapter"></a>你如何创建和自定义绑定中使用 WCF 自定义适配器？  
 WCF CustomBinding 包含的绑定元素集合。 CustomBinding 可通过汇集已存在的 BindingElement 来创建（例如，将已存在的“传输”和另一个源中已存在的“编码器”合并）。 或者，可以通过结合使用新编写的自定义 BindingElement 预先存在 BindingElement 创建它。 在代码中 CustomBinding 可以从这些组件绑定元素生成通过以编程方式添加它们。 WCF 还允许这种结构通过.NET 配置 （配置文件）。 使用 BizTalk Server 可以通过 BizTalk WCF 自定义适配器创建此 CustomBinding。  
  
 BizTalk WCF 自定义适配器不仅允许你从绑定元素生成一个新的绑定，而且还可以在配置新的绑定直接。 它还允许你配置标准绑定上的行为。 这是特别有用，因为编写自定义行为是比写入新的绑定元素对象容易得多。  
  
 生成 BindingElement 是一项涉及的开发任务和它的引用的最佳来源是 WCF 示例在超链接"http://go.microsoft.com/fwlink/?LinkId=142449"\t"_blank" http://go.microsoft.com/fwlink/?LinkId=142449。 若要创建自定义 BindingElement 你创建自 BindingElement 派生的类。 新 BindingElement 将一定要处于新的程序集。 此程序集必须安装到全局程序集缓存 (GAC) 的管理计算机 BizTalk 主机中，发送端口，并且接收位置的配置。 若要将自定义绑定与特定发送端口相关联或接收位置时，首先需要将其添加到\<bindingElementExtensions\>的同一台计算机上的 machine.config 文件的部分。  
  
 建立你然后可以显示所做的更改后 **传输属性配置** 对话框中，将绑定配置。  
  
1.  上 **绑定** 选项卡上，对于绑定类型，选择 **customBinding**。  
  
2.  在 **绑定** 窗格中，右键单击 **CustomBindingElement**, ，然后选择 **添加扩展**。  
  
3.  选择你在 machine.config 文件中指定的绑定元素，并根据需要配置绑定。 现在已准备好用于消息传输或接收。  
  
 在这种方式添加后，BizTalk 会进行自定义绑定的非常有限的验证。 因此，务必确保按正确的顺序列出的绑定元素。 在运行时第一次调用所需的绑定元素必须 CustomBindingElement 绑定树在对话框中底部。 绑定元素的列表必须包含一个传输协议和该传输协议必须为列表的底部。 BindingElement 集还可能包含“编码器”。 详细信息，请参阅 WCF 文档上绑定元素在[ http://go.microsoft.com/fwlink/?LinkId=142449 ](http://go.microsoft.com/fwlink/?LinkId=142449)。  
  
## <a name="what-is-a-wcf-custom-behavior-and-how-do-i-use-one-with-biztalk-server"></a>如何使用一个与 BizTalk Server 和 WCF 自定义行为是什么？  
 使用 WCF 消息通信机制的优势之一是通过使用自定义代码来扩展其服务的功能的机会。 自定义行为扩展是一个将 WCF 与其他市场中的 Web 服务技术区分开来的功能。  
  
 没有在 WCF 消息截获和执行自定义处理一条消息到达其最终目标之前的流中的不同点。 WCF 自定义行为扩展都是一个此类类型的截获机制，可用于扩展在不同的粒度级别的 WCF 服务或客户端功能。 在 WCF 服务和客户端级别可以存在自定义行为扩展。 配置到 WCF 服务调用堆栈上的行为没有任何影响用于发起呼叫的通信绑定。 事实上，行为是对客户端通常不可见，因为它们不会显示在服务发布的元数据。 客户端通常具有不知道在对 WCF 操作的调用期间执行行为。  
  
 相比其他在 Web 应用程序之间通信的方式，在调用 WCF 服务中轻松实现自定义处理的能力是 WCF 为何是一个如此丰富的编程范例的主要原因之一。 此自定义处理几乎可以采取 Web 应用程序内扩展性要求规定的任何格式。 开发人员可以创建检查和验证服务配置的自定义扩展，或修改在 WCF 客户端和服务应用程序中的运行时行为。 行为可以补充正常消息处理、 在处理过程中修改消息、 仔细检查特定配置条件和采取适当的措施，验证调用方的标识和可以将消息传递是否成功等。因为真正是一个自定义处理机制实现任何扩展性需要你的应用程序。  
  
 若要在 BizTalk Server 中使用 WCF 自定义行为将配置使用它 **行为** 接收位置或发送端口的 WCF 自定义或 WCF CustomIsolated 适配器的选项卡。