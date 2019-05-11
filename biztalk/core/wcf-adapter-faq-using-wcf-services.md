---
title: WCF 适配器常见问题解答：使用 WCF 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: befa2268-8a65-465f-8086-70a66808845e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65dc8427321d148430bcf3eb888c645ab4117937
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393580"
---
# <a name="wcf-adapter-faq-using-wcf-services"></a>WCF 适配器常见问题解答：使用 WCF 服务
## <a name="how-does-biztalk-server-use-its-wcf-adapters-to-access-wcf-services"></a>BizTalk Server 如何使用其 WCF 适配器访问 WCF 服务？  
 BizTalk WCF 适配器配置在 BizTalk Server 中通过 WCF 接收位置或发送端口。 启用使用 WCF 适配器的接收位置后，实例化并为每个接收位置初始化一个 ServiceHost 实例。 ServiceHost 运行通用服务，用于接受传入 WCF 消息，并将其发布到 BizTalk MessageBox 数据库之前将其转换为 BizTalk 消息。 通用 ServiceHost 服务处于 WCF BizTalk 的内部接收适配器实现，并公开一个无类型协定。 在 WCF 中，一个无类型协定由采用一个参数的类型为 WCF System.ServiceModel.Channel.Message 的操作签名组成。  
  
 WCF 服务的操作应标记为 IsOneWay = false，如果它们是由 BizTalk 发送端口访问，即使没有要返回的数据。 上的客户端协定对操作应批注使用 IsOneWay = false 和 ReplyAction ="*"。  此外来自客户端的所有调用都应都标记为 IsOneWay ="false"。 双向服务操作可能会返回消息类型的值。 此规则的例外使用 Wcf-netmsmq 适配器，因为它执行的将消息发送到 MSMQ 队列是单向操作。 在这种情况下，发送端口可以是单向和任何服务操作标记为 IsOneWay = true。  
  
 可能会有点令人困惑，还有可能在 WCF 中定义 isOneWay = false OperationContract 上实际返回空值的方法。 在这种情况下是实际上为你创建由 WCF 运行时在网络上返回一条消息。  
  
 BizTalk WCF 适配器将使用此功能。 指定单向 BizTalk 端口时实际上获得一个 void 方法使用 isOneWay = false 的 WCF 适配器实现中。 关键是 BizTalk 单向端口，使用 HTTP 或 net.tcp，如直接通道时实际将对应 isOneWay = false OperationContract。 例如 net.msmq 排队的信道是不同在于，单向 BizTalk 端口确实会设置为 isOneWay = true OperationContract。 这种情况是不同的因为 WCF 调度程序使用针对通道的事务。  
  
## <a name="how-do-you-create-and-use-a-custom-binding-with-a-wcf-custom-adapter"></a>您如何创建和自定义绑定中使用 WCF 自定义适配器？  
 WCF CustomBinding 的 Bindingelement 的集合组成。 可以通过将放在一起 （例如，组合使用另一来源的预先存在的编码器的预先存在传输） 的 Bindingelement 创建 CustomBinding。 或者，可以通过结合使用的新写入的自定义 BindingElement 预先存在的 BindingElement 创建它。 在代码中 CustomBinding 可从生成 Bindingelement 这些组件通过以编程方式添加它们。 WCF 还允许这种结构通过.NET 配置 （配置文件）。 通过使用 BizTalk Server 可以通过 BizTalk WCF 自定义适配器创建此 CustomBinding。  
  
 BizTalk WCF 自定义适配器不仅可用于从 Bindingelement 构建新的绑定还允许你配置一个新的绑定直接。 它还允许您配置标准绑定上的行为。 这是特别有用，因为编写自定义行为是比编写新的 Bindingelement 对象容易得多。  
  
 构建 BindingElement 是一项涉及的开发任务和为其引用的最佳来源是 WCF 示例在超链接"<http://go.microsoft.com/fwlink/?LinkId=142449>"\t"_blank" http://go.microsoft.com/fwlink/?LinkId=142449。 若要创建的自定义 BindingElement 您创建派生自 BindingElement 类。 新的 BindingElement 将一定要在新的程序集。 此程序集必须安装到全局程序集缓存 (GAC) 的 BizTalk 主机中，发送端口和接收位置的管理计算机配置。 若要将自定义绑定关联与特定的发送端口或接收位置，首先需要将其添加到\<bindingElementExtensions\>的同一台计算机上的 machine.config 文件的部分。  
  
 做出此更改，则可以将启动后**传输属性配置**对话框以配置绑定。  
  
1. 上**绑定**选项卡上，为绑定类型选择**customBinding**。  
  
2. 在中**绑定**窗格中，右键单击**CustomBindingElement**，然后选择**添加扩展**。  
  
3. 选择在 machine.config 文件中指定的绑定元素和所需配置的绑定。 现在已准备好用于消息传输或接收。  
  
   以这种方式添加后，BizTalk 会进行非常有限的验证自定义绑定。 因此，务必确保按正确顺序列出的绑定元素。 在运行时首次调用所需的绑定元素必须位于底部的对话框中的 CustomBindingElement 绑定树上。 Bindingelement 的列表必须包含一个传输，该传输必须位于列表的底部。 Bindingelement 集还可能包含编码器。 详细信息，请参阅 WCF 文档上绑定元素在[ http://go.microsoft.com/fwlink/?LinkId=142449 ](http://go.microsoft.com/fwlink/?LinkId=142449)。  
  
## <a name="what-is-a-wcf-custom-behavior-and-how-do-i-use-one-with-biztalk-server"></a>什么是 WCF 自定义行为以及如何使用另一个使用 BizTalk Server？  
 将 WCF 用作消息的通信机制的优势之一是通过使用自定义代码来扩展其服务的功能的机会。 自定义行为扩展是一种将 WCF 与其他 Web 服务技术市场中区分开来的功能。  
  
 没有要截获并执行自定义处理一条消息到达其最终目标之前的 WCF 消息流中的不同点。 WCF 自定义行为扩展是一种此类类型的拦截机制，并且可以用于扩展在不同级别的粒度的 WCF 服务或客户端功能。 可以在 WCF 服务和客户端级别存在自定义行为扩展。 调用堆栈的 WCF 服务上配置一个行为具有用于发起呼叫的通信绑定没有影响。 事实上，行为是对客户端通常不可见，因为它们不会显示在服务发布的元数据。 客户端通常具有行为在 WCF 操作的调用过程中执行不知道。  
  
 轻松地实现自定义对 WCF 服务的调用中处理的能力是通信的 WCF 为何是通信的此类丰富的编程范例相比 Web 应用程序之间的其他方式的主要原因之一。 此自定义处理可能需要几乎任何窗体的 Web 应用程序内扩展性要求规定。 开发人员可以创建自定义扩展插件的检查和验证服务配置或修改在 WCF 客户端和服务应用程序的运行时行为。 行为可以补充正常消息处理、 在处理期间修改消息，细察某个配置条件和采取相应的措施、 验证调用方的标识和可以传递该消息是否成功，等等。因为它真正是一个自定义处理机制实现任何扩展需要你的应用程序。  
  
 若要在 BizTalk Server 中使用 WCF 自定义行为将配置使用它**行为**接收位置或发送端口的 Wcf-custom 或 Wcf-customisolated 适配器的选项卡。