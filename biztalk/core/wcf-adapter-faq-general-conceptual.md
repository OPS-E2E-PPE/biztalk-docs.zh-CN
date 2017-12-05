---
title: "WCF 适配器常见问题： 常规概念 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbeac135-3ba8-4b0b-a8ca-4eb5eb3d3ca3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a33e6ba26f0ba97cb10aa2f9ee728683719dd66
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="wcf-adapter-faq-general-conceptual"></a>WCF 适配器常见问题解答：一般概念
下面是一些常见的有关 Windows® Communication Foundation (WCF) 适配器的一般和概念性问题。  
  
## <a name="what-is-a-wcf-adapter"></a>WCF 适配器是什么？  
 BizTalk 适配器是 Microsoft® BizTalk® Server 与外界通信方式的关键部分。 WCF 适配器是一个组件，它管理 BizTalk 应用程序与其需求之间的通信过程，以便将消息发送到 WCF 终结点和从 WCF 终结点接收消息。 与 BizTalk Server 中，WCF 适配器显示为 WCF 绑定。 这意味着任何可使用 WCF 绑定的 WCF 应用程序都可以直接与 WCF 适配器通信，无需 BizTalk Server 进行干预。 但是，通过 BizTalk Server 使用 WCF 适配器可让您享受 BizTalk Server 提供的许多应用程序基础结构优势。 这些常见问题解答的焦点主要是在 BizTalk Server 环境中使用 WCF 适配器。  
  
 WCF 适配器允许 BizTalk Server 使用 WCF 绑定来发送和接收 WCF 消息。 WCF 客户端应用程序可以将 WCF 消息发送到 BizTalk 接收位置，WCF 接收适配器在此处接收消息。 该适配器接收 WCF 消息并将其转换为 BizTalk 消息。 如何发生转换将取决于某些适配器配置设置（使用 BizTalk Server管理控制台配置这些设置）。 适配器将 BizTalk 消息提交到内部 BizTalk MessageBox 数据库。 相应地，使用 WCF 适配器的 BizTalk 发送端口可以订阅此消息类型，获取 BizTalk 消息，将其转换为 WCF 消息，以及使用支持的一种 WCF 协议将 WCF 消息传输到 WCF 服务终结点。  
  
 如果在 BizTalk Server 中使用 WCF 适配器，将抽象化 BizTalk-WCF 应用程序解决方案隐藏的复杂性，如通信协议、安全问题和事务性操作的选择和实现。  
  
## <a name="what-are-the-wcf-adapter-bindings"></a>WCF 适配器绑定是什么？  
 WCF 绑定分为以下两个类别之一：  
  
-   **自定义绑定：**实现更高绑定灵活性，存在特殊的自定义绑定。 这包括需要与标准绑定存在偏差的通信情况。 WCF-Custom 和 WCF CustomIsolated 适配器允许开发大量的绑定自定义。 通过允许将现有绑定元素（BindingElement 类）和行为应用程序（Behavior 类）组合来实现此操作。  
  
-   **标准绑定：** Microsoft 的目标是开发适配器侧重于最常见的通信方案。 使用标准绑定，将通过隐藏通信协议的许多细节来简化开发人员的体验。 BizTalk Server 中的 WCF 适配器集反映的一套.NET Framework 4.0 WCF 库中可用的绑定。 将标准绑定引入到 .NET WCF 库，是为了使典型绑定模式更易于使用。 它们涉及最常用的通信方案，包括：  
  
    -   WCF-WsHttp  
  
    -   WCF-BasicHttp  
  
    -   WCF-NetTcp  
  
    -   WCF-NetMsmg  
  
    -   WCF-NetNamedPipe  
  
 BizTalk Server R2 附带以下 WCF 适配器：  
  
1.  **WCF WSHttp 适配器：**提供的 WS-* 标准支持通过 HTTP 传输。 WCF-WSHttp 适配器实现了下列规范：WS-Transaction（用来在外部应用程序和 MessageBox 数据库之间进行事务性交互）和 WS-Security（用来实现消息安全和身份验证）。 传输协议是 HTTP 或 HTTPS，和消息编码是一个文本或消息传输优化机制 (MTOM) 编码。  
  
2.  **WCF BasicHttp 适配器：**通信与基于 ASMX 的 Web 服务和客户端以及符合 WS 其他服务的基本配置文件 1.1。 传输协议是 HTTP 或 HTTPS，消息编码是文本编码。  
  
3.  **WCF NetTcp 适配器：**提供的 WS-* 标准支持通过 TCP 传输。 WCF-NetTcp 适配器提供有效的通信并实现下列规范：WS-Transaction（用来在外部应用程序和 MessageBox 数据库之间进行事务性交互）和 WS-Security（用来实现消息安全和身份验证）。 传输为 TCP，和消息编码则是二进制编码。  
  
4.  **WCF NetMsmq 适配器：**提供支持队列利用消息队列 (也称为 MSMQ) 作为传输协议和启用支持松散耦合应用程序、 故障隔离、 负载分级，并断开连接操作。  
  
5.  **WCF NetNamedPipe 适配器：**提供针对计算机上跨进程通信的安全优化。 WCF-NetNamedPipe 适配器使用传输安全性保证传输安全，使用命名管道进行消息传送，并且使用二进制消息编码方式。  
  
     每个五个适配器刚刚提到对应于 1:1 的关系中的一个 WCF 绑定。 我们即将讨论的两个自定义适配器的结构与 WCF 模型稍有不同，在该结构中实际上有两个不同的自定义适配器对应于一个 WCF CustomBinding。  
  
6.  **WCF 自定义适配器：**启用 WCF 扩展性功能的使用。 使用此适配器可以为在 BizTalk Server 进程中托管的接收位置或发送端口选择并配置 WCF 绑定和行为信息。  
  
7.  **WCF CustomIsolated 适配器：**启用通过 HTTP 传输的 WCF 扩展性功能。 使用该适配器，可以为运行于 Internet 信息服务 (IIS) 独立主机上的接收位置选择并配置 WCF 绑定和行为信息。  
  
## <a name="what-is-the-difference-between-the-wcf-xxx-adapter-and-the-wcf-xxx-binding"></a>WCF-xxx 适配器和 WCF-xxx 绑定之间的区别是什么？  
 每个 WCF 适配器对应于一个内置的 WCF 绑定。 在更高层面上，当提到 WCF-xxx 适配器使用 WCF-xxx 绑定时，几乎可交换使用这些术语。 例如，WCF-BasicHttp 适配器使用 WCF BasicHttpBinding 类。 WCF 绑定是 WCF 终结点定义的一部分。 这在 WCF 终结点的“ABC”中提到，其中这些字母代表地址、绑定和协定。  
  
 绑定由绑定元素的集合组成。 每个元素都描述终结点如何与客户端通信的一些方面。 绑定必须包括：  
  
-   至少一个传输绑定元素。  
  
-   至少一个消息编码绑定元素（默认情况下，传输绑定元素可提供该元素）。  
  
-   任意数量的其他协议绑定元素。  
  
 按此描述生成运行时环境的过程将允许每个绑定元素向该环境提供代码。 通常要求客户端与调用的 WCF 服务支持的相同绑定类型和适配器相匹配。 在 WCF 级别，可在配置文件中以声明方式定义或通过代码明确定义绑定。 WCF 适配器使用特定的 WCF 绑定来帮助通信，因此，术语“适配器”和“绑定”在用法上近乎相同。  
  
## <a name="when-using-the-wcf-adapters-how-do-you-decide-which-wcf-binding-to-use"></a>在使用 WCF 适配器时，如何决定使用哪个 WCF 绑定？  
 您可以根据消息传送模式、外部约束和性能，按这种顺序做出此决定。  
  
1.  **消息传递模式：**通信的模式是通信发生基于消息的流的方式。 例如，消息可能是单向（请求）或双向（请求-响应），可能是事务性，也可能是队列形式等。  
  
    -   如果是队列形式，则需要使用 WCF-NetMsmq 适配器，它支持单向队列事务性通信。  
  
    -   如果模式是双向的请求-响应并且在两台计算机之间流动，则可以使用 HTTP（如果考虑尽可能的灵活）或 WCF-NetTcp（如果考虑性能）。  
  
    -   如果消息保留在一台计算机上，并且仅在两个进程之间流动，则可以使用 WCF-NetNamedPipe 绑定。  
  
2.  **外部的约束：**可能有规定所使用的特定绑定的问题。 例如，假定外部系统要求 SOAP Web Services 版本 1.2 和 Addressing 1.0。 在这种情况下，最好的绑定选择是使用 WCF-WsHttp 适配器的 WSHttpBinding。 很可能，外部系统还将要求配置特定的安全模式。 如果外部系统要求 Soap Web Services 1.1，可以为 HTTP 绑定使用 WCF-BasicHttp 适配器。  
  
3.  **性能：**调用速度可能的绑定中你选择使用应用程序中的决定性因素：  
  
    -   如果 WCF 服务和 BizTalk Server 在同一台计算机上，则使用 WCF-NetNamedPipe 适配器是最佳的性能选择。  
  
    -   如果 WCF 服务位于本地网络上，WCF-NetTcp 则会产生最佳性能。  
  
    -   如果性能不是主要考虑对象，并且通过 Internet 进行调用，则任何一个基于 HTTP 的适配器（WCF-WsHttp 或 WCF-BasicHttp）都是合适的适配器。  
  
         不管是使用任何高级 HTTP 功能 (WCF-WsHttp) 还是只使用基本功能 (WCF-BasicHttp)，都将指示哪个基于 HTTP 的适配器是最佳的使用选择。  
  
## <a name="when-do-you-use-one-of-the-two-custom-wcf-adapters"></a>何时使用两个自定义 WCF 适配器之一？  
 有两个自定义 WCF 适配器附带 BizTalk Server。 存在两个自定义适配器的原因是因为，BizTalk Server 要求托管某个特定适配器类型需要是其系统注册的一部分。 虽然在 WCF Framework 中仅有一种 CustomBinding 类型，但是在 BizTalk Server 中有两个自定义适配器，以在已存在的 BizTalk 适配器模型中适应这种限制。 在现实中，这些适配器将真正是您一直需要的仅有的适配器，因为它们允许对 WCF 通道堆栈配置实现完全控制。  
  
 自定义适配器的唯一缺点是，它们还需要您对 WCF 配置和各种扩展性技术非常地了解。  简化配置是 Microsoft 为标准 WCF 绑定提供适配器的原因。 预定义标准绑定是为了覆盖大多数常用的案例，并使通过 BizTalk Server 发送和接收消息尽可能地简单。 使用这些自定义适配器的需求通常仅发生在标准绑定无法完整或精确地满足您的发送端口或接收位置要求。 例如，可能存在一个为其消息使用专有压缩方案的应用程序。 为了对此进行支持，必须编写一个自定义绑定元素。 使用两个标准自定义适配器之一，可配置此自定义绑定，以解决传送要求。 因此，自定义适配器允许对通过通道堆栈的通信进程的绑定配置进行更高级别的控制。  
  
 自定义适配器和自定义独立适配器之间的主要区别是托管，托管仅影响 BizTalk Server 的接收端。 WCF-CustomIsolated 适配器仅与接收位置一起使用，不与发送端口一起使用。 术语“独立”是一个 BizTalk 用语，指在 BizTalk Server BtsNtSvc.exe 进程外托管。 因此，当传输被托管在使用 HTTP 传输的 Internet 信息服务 (IIS) 中的标准 BtsNtSvc.exe 进程之外时，将使用 WCF-CustomIsolated 适配器。 WCF-Custom 适配器可以与接收位置或发送端口一起使用。 它在传输被托管在标准 BtsNtSvc.exe 进程中时使用。  
  
## <a name="how-does-a-wcf-endpoint-relate-to-biztalk-server"></a>WCF 终结点如何与 BizTalk Server 相关？  
 WCF 终结点由地址、绑定和协定 (ABC) 组成。 在 BizTalk Server 中，用户指定接收位置或发送端口的地址。 绑定由用户选择的 WCF 适配器指定。 协定由程序员驱动，其中指定终结点公开的接口。  
  
 实际终结点以 WCF 消息发送到的接收位置形式存在。  有多种方法可以公开 BizTalk Server 应用程序中的 WCF 终结点：  
  
-   可以使用 BizTalk WCF 服务发布向导将 BizTalk 业务流程发布为 WCF 终结点。  
  
-   可以使用 BizTalk WCF 服务发布向导在现有 BizTalk 应用程序中创建一个接收位置。  
  
-   可以通过使用代码配置接收位置的绑定和地址手动创建一个 WCF 终结点。  在这种情况下，接收位置实际上是无类型的。  它有一个完全按照 WCF 消息类指定的协定，从而允许其接收任何消息格式到 MessageBox 数据库。  
  
 使用 WCF 适配器的每个 BizTalk 接收位置都公开为一个 WCF 终结点，WCF 客户端可以在其中进行调用。  接收位置内部使用其自己的 WCF ServiceHost，以允许独立启用或禁用不同的接收位置。 只要启用接收位置，便存在服务终结点的生存期。 因为此生存期问题，所以 WCF ServiceHosts对应接收位置，而非接收端口。 WCF 的设计确保各个 ServiceHosts 从运行时资源而言并不昂贵，许多可以在相同的可执行文件中运行，无任何问题。  
  
 使用 WCF 适配器的每个 BizTalk 发送端口都对应一个对 WCF 服务的调用。 当有消息发送时，BizTalk Server 将向适配器发送这些在 BizTalk WCF 适配器中创建 WCF 客户端代理的消息。 发送消息之后，WCF 客户端代理即被释放。 发送端口上的 WCF 生存期随代理的创建、使用和释放而不断地开始和结束。