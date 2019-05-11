---
title: WCF 适配器常见问题解答：一般概念 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbeac135-3ba8-4b0b-a8ca-4eb5eb3d3ca3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d3611a5e12cbbe52946630404c3ed6eb36f886c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393595"
---
# <a name="wcf-adapter-faq-general-conceptual"></a>WCF 适配器常见问题解答：一般概念
下面是一些常见一般和概念性问题有关 Windows® Communication Foundation (WCF) 适配器的信息。  
  
## <a name="what-is-a-wcf-adapter"></a>WCF 适配器是什么？  
 BizTalk 适配器是 Microsoft® BizTalk® Server 与外界通信的方式的关键部分。 WCF 适配器是管理 BizTalk 应用程序需要将消息发送到，和从 WCF 终结点接收消息之间的通信过程的组件。 使用 BizTalk Server 中，WCF 适配器公开为 WCF 绑定。 这意味着，可以使用 WCF 绑定任何 WCF 应用程序可以直接与进行通信的 WCF 适配器，而无需 BizTalk Server 进行干预。 但是，使用 WCF 适配器通过 BizTalk Server 可以提供许多应用程序基础结构的 BizTalk Server 提供的优势。 这些常见问题解答的焦点主要使用来自 BizTalk Server 环境中的 WCF 适配器。  
  
 WCF 适配器允许 BizTalk Server 使用 WCF 绑定来发送和接收 WCF 消息。 WCF 客户端应用程序可以的发送到 BizTalk WCF 消息接收的位置，WCF 接收此消息接收适配器。 适配器接收 WCF 消息，并将其转换为 BizTalk 消息。 如何发生转换将取决于特定适配器的配置设置的配置为使用 BizTalk Server 管理控制台。 适配器将提交到内部 BizTalk MessageBox 数据库的 BizTalk 消息。 相应地，BizTalk 发送端口使用 WCF 适配器可以订阅此消息类型、 获取 BizTalk 消息、 将其转换为 WCF 消息，并使用其中一个受支持的 WCF 协议的 WCF 服务终结点将 WCF 消息传输。  
  
 使用来自 BizTalk Server 中的 WCF 适配器提取 BizTalk WCF 应用程序解决方案，如选择和实现通信协议、 安全问题和事务性操作的隐藏的复杂性。  
  
## <a name="what-are-the-wcf-adapter-bindings"></a>WCF 适配器绑定有哪些？  
 WCF 绑定分为两个类别之一：  
  
- **自定义绑定：** 为提高绑定灵活性，存在特殊的自定义绑定。 这包括通信情况下，需要与标准绑定存在偏差。 Wcf-custom 和 Wcf-customisolated 适配器允许开发大量的绑定自定义项。 这是通过允许现有绑定元素 （BindingElement 类） 的组成和行为 （Behavior 类） 的应用程序。  
  
- **标准绑定：** Microsoft 的目标是开发专注于最常见通信方案的适配器。 使用标准绑定，通过隐藏通信协议的许多细节，简化了开发人员的体验。 BizTalk Server 中的 WCF 适配器集反映了.NET Framework 4.0 WCF 库中可用的绑定集。 标准绑定引入到.NET WCF 库以使典型绑定模式更易于使用。 它们涵盖了最常使用的通信方案，包括：  
  
  -   WCF-WsHttp  
  
  -   WCF-BasicHttp  
  
  -   WCF-NetTcp  
  
  -   WCF-NetMsmg  
  
  -   WCF-NetNamedPipe  
  
  BizTalk Server R2 附带以下 WCF 适配器：  
  
1.  **Wcf-wshttp 适配器：** 提供对于 WS-* 标准的支持通过 HTTP 传输。 Wcf-wshttp 适配器实现了下列规范：WS 事务之间外部应用程序和 MessageBox 数据库和 Ws-security 的消息安全性和身份验证的事务交互。 传输协议是 HTTP 或 HTTPS，并且消息编码是文本或消息传输优化机制 (MTOM) 编码。  
  
2.  **Wcf-basichttp 适配器：** 与基于 ASMX 的 Web 服务和客户端以及符合 WS 其他服务进行通信的基本配置文件 1.1。 传输协议是 HTTP 或 HTTPS，并且消息编码是文本编码。  
  
3.  **Wcf-nettcp 适配器：** 提供对于 WS-* 标准的支持通过 TCP 传输。 Wcf-nettcp 适配器提供有效的通信，并实现了下列规范：WS 事务之间外部应用程序和 MessageBox 数据库和 Ws-security 的消息安全性和身份验证的事务交互。 传输协议是 TCP，和消息编码是二进制编码。  
  
4.  **Wcf-netmsmq 适配器：** 通过利用消息队列 (也称为 MSMQ) 作为传输机制来提供支持并启用对松散耦合应用程序、 故障隔离、 负载调配和已断开连接操作的支持。  
  
5.  **Wcf-netnamedpipe 适配器：** 提供了计算机上的跨进程通信的安全优化。 Wcf-netnamedpipe 适配器使用传输安全性保证传输安全，命名管道进行消息传递，并且包含二进制消息编码。  
  
     每个刚刚提到的五个适配器对应于 1 对 1 关系中的一个 WCF 绑定。 我们正准备略有讨论与 WCF 模型，因为实际上两个非重复自定义适配器对应一个 WCF CustomBinding 的两个自定义适配器的结构。  
  
6.  **Wcf-custom 适配器：** 启用 WCF 扩展功能的使用。 该适配器，可以选择和配置 WCF 绑定和行为信息的接收位置或发送端口在 BizTalk Server 进程中承载。  
  
7.  **Wcf-customisolated 适配器：** 允许通过 HTTP 传输使用 WCF 扩展功能。 该适配器，可以选择和配置 WCF 绑定和行为信息在独立的主机的 Internet 信息服务 (IIS) 中运行的接收位置。  
  
## <a name="what-is-the-difference-between-the-wcf-xxx-adapter-and-the-wcf-xxx-binding"></a>Wcf-xxx 适配器和 wcf-xxx 绑定之间的区别是什么？  
 每个 WCF 适配器对应于一个内置 WCF 绑定。 在较高级别，这些术语可以互换几乎说 wcf-xxx 适配器使用 wcf-xxx 绑定时。 例如，Wcf-basichttp 适配器使用 WCF BasicHttpBinding 类。 WCF 绑定是 WCF 终结点定义的一部分。 这是在称为"ABC"的 WCF 终结点，其中这些字母代表地址、 绑定和协定。  
  
 绑定由绑定元素的集合组成。 每个元素描述终结点与客户端的通信方式的一些方面。 绑定必须包括：  
  
- 至少一个传输绑定元素。  
  
- 至少一个消息编码绑定元素 （默认情况下可以提供传输绑定元素）。  
  
- 任意数量的其他协议绑定元素。  
  
  生成按此描述的运行时环境的进程允许每个绑定元素提供到该环境的代码。 它是通常要求客户端以匹配的相同绑定类型和调用的 WCF 服务支持的适配器。 在 WCF 级别配置文件中或通过代码明确，则可以以声明方式定义一个绑定。 WCF 适配器的功能包括通信使用特定 WCF 绑定，并因此术语"适配器"和"绑定"往往在用法上近乎相同。  
  
## <a name="when-using-the-wcf-adapters-how-do-you-decide-which-wcf-binding-to-use"></a>使用 WCF 适配器时，如何决定使用哪个 WCF 绑定？  
 您可以做出这一决定基于消息传送模式、 外部约束和性能，按该顺序。  
  
1.  **消息传送模式：** 通信模式是根据消息流的通信方式。 例如，消息可能是单向 （请求） 或双向 （请求-响应），它可能事务性，它可能需要排队，依次类推。  
  
    -   如果已排队，您需要使用 Wcf-netmsmq 适配器，它支持单向队列事务性的通信。  
  
    -   如果模式是双向请求-响应和两台计算机之间的流，你将 HTTP （如果您担心尽可能的灵活） 或 Wcf-nettcp （如果您担心性能）。  
  
    -   如果消息保留在一台计算机上，并且只需两个进程之间流动，您可以使用 Wcf-netnamedpipe 绑定。  
  
2.  **外部约束：** 可能存在指示您使用特定绑定的问题。 例如，假设外部系统要求 SOAP Web Services 版本 1.2 和 Addressing 1.0。 在这种情况下，最好的绑定选择是使用 Wcf-wshttp 适配器的 WSHttpBinding。 很可能，外部系统还必须要求配置特定的安全模式。 如果外部系统要求 Soap Web Services 1.1 您将为 HTTP 绑定使用 Wcf-basichttp 适配器。  
  
3.  **性能：** 做出调用的速度可能是哪个绑定在中选择要使用你的应用程序的决定性因素：  
  
    -   如果 WCF 服务和 BizTalk Server 在同一计算机上，使用 Wcf-netnamedpipe 适配器是最佳的性能选择。  
  
    -   如果在本地网络上的 WCF 服务，WCF NetTcp 实现最佳性能。  
  
    -   如果性能不是主要考虑因素，调用会通过 Internet，或者基于 HTTP 的适配器 （Wcf-wshttp 或 Wcf-basichttp） 是合适的适配器。  
  
         使用任何高级的 HTTP 功能 (Wcf-wshttp) 还是只使用基本功能 (Wcf-basichttp) 将决定哪个基于 HTTP 的适配器是要使用的最佳选择。  
  
## <a name="when-do-you-use-one-of-the-two-custom-wcf-adapters"></a>何时使用两个自定义 WCF 适配器之一？  
 有两个自定义 WCF 适配器随 BizTalk Server。 有两个自定义适配器，是因为 BizTalk Server 要求托管某个特定适配器类型必须是其注册到系统的一部分，原因。 尽管 WCF Framework 中只有一种 CustomBinding 类型，但 BizTalk Server 以容纳此限制在预先存在的 BizTalk 适配器模型中有两个自定义适配器。 实际上，这些适配器将真正是您曾经需要因为它们允许完全控制对 WCF 通道堆栈配置的唯一适配器。  
  
 自定义适配器的唯一缺点是，它们还需要您为 WCF 配置和各种扩展性技术非常熟悉。  简化配置是 Microsoft 为标准 WCF 绑定提供适配器的原因。 标准绑定是预定义，以涵盖了大多数的常见用例并使发送和接收消息通过 BizTalk Server 一样简单。 标准绑定无法完整或精确地满足您的发送端口的要求或接收位置时，会发生通常使用这些自定义适配器之一的需求。 例如，可能有为其消息使用专有压缩方案的应用程序。 若要支持此功能，必须编写自定义绑定元素。 使用两个标准自定义适配器之一，以解决传送要求此自定义绑定的配置。 因此，自定义适配器允许更高级别的控制通过通道堆栈的通信进程的绑定配置。  
  
 自定义和自定义独立适配器之间的主要区别是托管，并托管仅影响 BizTalk Server 在接收端。 唯一的接收位置而不是发送端口使用 Wcf-customisolated 适配器。 术语"独立"是一个 BizTalk 用语，指的是 BizTalk Server BtsNtSvc.exe 进程外托管。 因此，传输被托管在外部标准 BtsNtSvc.exe 进程在 Internet 信息服务 (IIS) 使用 HTTP 传输时使用 Wcf-customisolated 适配器。 WCF 自定义适配器可以用于接收位置或发送端口。 传输被托管在标准 BtsNtSvc.exe 进程时使用它。  
  
## <a name="how-does-a-wcf-endpoint-relate-to-biztalk-server"></a>WCF 终结点与 BizTalk Server 如何相关？  
 WCF 终结点由地址、 绑定和协定 (ABC) 组成。 BizTalk Server 中用户指定的地址在接收位置或发送端口。 由用户选择的 WCF 适配器指定绑定。 该协定由程序员驱动，其中指定终结点公开的接口。  
  
 作为消息发送到的 WCF 接收位置存在实际的终结点。  有多种方法可以公开 BizTalk Server 应用程序中的 WCF 终结点：  
  
- 可以使用 BizTalk WCF 服务发布向导发布 BizTalk 业务流程作为 WCF 终结点。  
  
- 可以使用 BizTalk WCF 服务发布向导在现有的 BizTalk 应用程序中创建接收位置。  
  
- 通过在代码中配置接收位置的绑定和地址，可以手动创建一个 WCF 终结点。  在这种情况下接收位置实际上是无类型。  它具有完全以 WCF 消息类，使其能够接收任何消息格式到 MessageBox 数据库中指定的协定。  
  
  每个 BizTalk 接收位置使用 WCF 适配器公开为 WCF 客户端可以在其中进行调用的 WCF 终结点。  接收位置在内部使用其自己的 WCF ServiceHost，以允许不同的接收位置，若要启用或禁用互相独立地。 服务终结点的生存期且与接收位置启用。 它因为此生存期问题是，所以 WCF ServiceHosts 对应接收位置而不是接收端口。 WCF 的设计确保各个 ServiceHosts 不消耗大量的运行时资源和很多可以运行在同一可执行文件，无任何问题。  
  
  每个 BizTalk 发送端口使用 WCF 适配器对应于对 WCF 服务所做的调用。 要发送的消息时，BizTalk Server 为适配器对应的那些消息中 BizTalk WCF 适配器的 WCF 客户端代理的创建。 发送消息之后发布的 WCF 客户端代理。 发送端口上的 WCF 生存期不断传入，并且就可以创建、 使用和销毁代理。