---
title: 优化 BizTalk Server WCF 适配器性能 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2900c845-15be-4466-8fa0-b51b2486842f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d5ce620e7d9da984081b0f0874985bfe762eeae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299669"
---
# <a name="optimizing-biztalk-server-wcf-adapter-performance"></a>优化 BizTalk Server WCF 适配器性能
本主题提供用于选择相应的 WCF 适配器或绑定类型和应用各种 WCF 适配器配置选项的指南的建议。  
  
## <a name="considerations-when-choosing-which-wcf-adapter-to-use-or-which-wcf-customwcf-customisolated-binding-type-to-use"></a>选择要使用哪个 WCF 适配器或要使用的 WCF 自定义 WCF CustomIsolated 绑定类型时的注意事项  
  
-   如果不是严格需要，因为它会增加消息的大小，则不使用消息级安全性。 这反过来可以尽量减少解决方案的总体吞吐量。  
  
-   选择要使用哪个 WCF 适配器或哪些 WCF 的自定义/WCF-CustomIsolated 时**绑定类型**若要使用，仔细考虑任何应用程序要求，如兼容性、 性能、 托管平台、 安全性和支持传输。 下面列出的准则适用于 WCF 一般情况下，而且不特定于 BizTalk Server:  
  
    -   **BasicHttpBinding**如果 WCF 服务需要支持如 WebSphere Web 服务或预期的 ASMX Web 服务的.NET 1.1 应用程序的旧客户端应使用。 由于 BasicHttpBinding 不实施任何安全，默认情况下，如果需要消息或传输的安全性，应在此绑定上显式配置。 使用 BasicHttpBinding 来公开能够与基于 ASMX 的 Web 服务和客户端以及符合 WS 其他服务进行通信的终结点的基本配置文件 1.1。 当配置传输安全性，BasicHttpBinding 默认设置，以便只需使用任何凭据如经典的 ASMX Web 服务。 BasicHttpBinding 可用于承载 IIS 7.5 或 IIS 7.0 中的 WCF 服务。  
  
    -   **WsHttpBinding**如果通过 Internet WCF 客户端将调用 WCF 服务应使用。 WsHttpBinding 是一个不错的选择在其中你无需支持预期的 ASMX Web 服务的旧客户端，并且 WsHttpBinding 可用于承载 IIS 7.5 或 IIS 7.0 中的 WCF 服务的 Internet 方案。 如果你确实需要支持旧客户端，请考虑改为使用 BasicHttpBinding。   
        应使用 WsHttpBinding，当你需要公开 WCF 接收位置或采用发送端口支持 WS-* 协议，例如 Ws-security 或 WS AtomicTransactions。  
  
    -   **NetTcpBinding**是一个理想的选择，如果你需要支持在 intranet 中的客户端。 NetTcpBinding 是一个不错的选择对 intranet 方案，如果传输性能对你很重要，并且它是可接受的 Windows 服务而不是 IIS 中承载服务。 当你想要提供一个安全且可靠的绑定的环境时，请使用此绑定。NET.NET 跨计算机通信。 请注意在 Windows 服务或在 IIS 7.5/7.0 中，必须承载 NetTcpBinding。  
  
    -   **NetNamedPipeBinding**如果你需要在你的服务所在的计算机上支持 WCF 客户端应使用。 此绑定提供用于跨进程，同一台计算机的通信的安全且可靠的绑定环境。 使用此绑定，如果你想要利用 NamedPipe 协议。 请注意在 Windows 服务或在 IIS 7.5/7.0 中，必须承载 NetNamedPipeBinding。  
  
    -   **NetMsmqBinding**如果你需要支持断开连接队列应使用。 队列提供通过使用消息队列 (也称为 MSMQ) 作为传输协议，支持的断开连接的操作、 故障隔离、 和负荷量。 当客户端和服务不需要在同一时间处于联机状态时，你可以使用 NetMsmqBinding。 你还可以通过使用负载分级管理任意数量的传入消息。 消息队列支持故障隔离、 其中的消息可能会失败而不会影响其他消息的处理。 请注意在 Windows 服务或在 IIS 7.5/7.0 中，必须承载 NetMsmqBinding。  
  
    -   **WsDualHttpBinding**如果你需要以支持双工服务应使用。 双工服务是使用双工消息模式，从而使通过回调与客户端的服务进行通信的功能的服务。 请注意在 Windows 服务或在 IIS 7.5/7.0 中，必须承载 WsDualHttpBinding。  
  
## <a name="wcf-binding-comparison"></a>WCF 绑定比较  
 绑定提供了用于配置通道堆栈的机制。 绑定创建一个过程来生成通道堆栈使用传输通道、 消息编码器选项和协议通道的一组。 Windows Communication Foundation 附带有许多都被预配置为满足最常见通信方案的内置绑定。  
  
|绑定类名称|Transport|消息编码|安全模式|可靠消息传递|事务流 （默认情况下禁用）|  
|------------------------|---------------|----------------------|-------------------|------------------------|----------------------------------------------|  
|BasicHttpBinding|HTTP|Text|无|不支持|不支持|  
|WSHttpBinding|HTTP|Text|消息|禁用|WS AtomicTransactions|  
|NetTcpBinding|TCP|二进制|Transport|禁用|OleTransactions|  
|NetNamedPipesBinding|命名管道|二进制|Transport|不支持|OleTransactions|  
|NetMsmqBinding|MSMQ|二进制|消息|不支持|不支持|  
|CustomBinding|你决定|你决定|你决定|你决定|你决定|  
  
 你可以选择基于通信需求的特定绑定。 例如：  
  
-   **BasicHttpBinding**旨在与简单 Web 服务互操作性。 BasicHttpBinding 使用 HTTP 传输和消息编码的文本。  
  
-   **WSHttpBinding**专为互操作性与更高级的 Web 服务，它们可能利用不同 WS-* 协议。  WSHttpBinding 还使用 HTTP 传输和消息编码的文本。  
  
-   **NetTcpBinding**和**NetNamedPipeBinding**旨在高效，并执行与其他 WCF 应用程序的 ant 通信分别跨计算机或同一台计算机上。  
  
-   如果你需要通过使用运行时的一个或多个自定义协议通道的最大的灵活性，你可以使用**CustomBinding** ，它将授予你决定哪些绑定元素构成你绑定的可能性。  
  
> [!NOTE]  
>  绑定具有一些在响应时间和吞吐量方面不同的特征。 因此，以提高性能的常规建议使用 NetTcpBindind 和 NetNamesPipeBinding 在可能的情况。  
  
## <a name="use-the-tcp-transport-and-binary-message-encoding-to-maximize-wcf-adapter-throughput-and-minimize-wcf-adapter-latency"></a>使用 TCP 传输和二进制消息编码以最大化 WCF 适配器吞吐量并减少 WCF 适配器延迟  
 使用 WCF NetTcp 适配器时可以最大化吞吐量。 WCF NetTcp 适配器使用 TCP/IP 传输协议和二进制消息编码一起提供改进的性能，与其他 WCF-相比 * 适配器。  
  
 或者，可以使用配置的 WCF 自定义 （或用于接收位置的 WCF CustomIsolated 适配器） **customBinding**绑定类型。 然后，将添加**binaryMessageEncoding**绑定扩展来实现二进制消息编码和**tcpTransport**绑定扩展来实现 TCP/IP 作为消息传输协议。 这种方法是非常灵活，因为它允许你以选择并配置所需的绑定元素，并创建自定义通道，以扩展 BizTalk 消息引擎的默认行为。 如果实现的 WCF 自定义适配器**customBinding**绑定类型，指定以下值作为要最大化吞吐量并减少延迟的绑定扩展配置参数。  
  
 **发送端口的配置值：**  
  
|设置|默认值|推荐值|  
|-------------|-------------------|-----------------------|  
|**TcpTransportBindingElement.ConnectionPoolSettings.maxOutboundConnectionsPerEndpoint** -获取或设置最大连接池中缓存的每个终结点的出站连接数。 这将限制为每个唯一的远程终结点缓存的连接数。 如果具有更多活动客户端连接而超出此值，该服务可能表现为客户端，并应将此值调整以适应最大为每个唯一远程终结点缓存的预期连接数。 有关此属性的详细信息，请参阅[TcpConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint 属性](http://go.microsoft.com/fwlink/?LinkId=157737)(http://go.microsoft.com/fwlink/?LinkId=157737) MSDN 上。|10|请尝试 > = 20|  
  
 **接收端口配置值：**  
  
|设置|.NET Framework 4 的默认值|针对.NET Framework 4 的建议的值|.NET Framework 3.5 的默认值|.NET Framework 3.5 的建议的值|  
|-------------|----------------------------------------|--------------------------------------------|------------------------------------------|----------------------------------------------|  
|**TcpTransportBindingElement.MaxPendingAccepts** -获取或设置最大挂起异步接受数可用于处理传入连接到服务的操作。 对于具有高级别的同时连接导致的方案，此值还不够，而应将调整连同**MaxPendingConnections**属性以处理更多的并发客户端连接尝试次数。 应该不需要将此属性设置为一个值大于存在于承载该服务的计算机的处理器数。 有关此属性的详细信息，请参阅[ConnectionOrientedTransportBindingElement.MaxPendingAccepts 属性](http://go.microsoft.com/fwlink/?LinkId=157738)(http://go.microsoft.com/fwlink/?LinkId=157738) MSDN 上。|1|2 * ProcessorCount|1|请尝试 > = 20|  
|**TcpTransportBindingElement.MaxPendingConnections** -获取或设置连接在服务上等待调度的最大数目。 这将限制等待调度的同时进行的客户端连接数。 如果此值太低，则客户端连接尝试可能拒绝服务。 如果太高，则服务可能无迟缓或没有响应向客户端负荷期间。 此属性应设置为一个值，允许服务运行在大容量时，和不更高版本。 当堆栈调用中的高层**AcceptDispatch**，连接从等待调度的连接队列中删除。 有关此属性的详细信息，请参阅[ConnectionOrientedTransportBindingElement.MaxPendingConnections 属性](http://go.microsoft.com/fwlink/?LinkId=157735)(http://go.microsoft.com/fwlink/?LinkId=157735) MSDN 上。|10|16 * ProcessorCount|10|请尝试 > = 20|  
|**TcpTransportBindingElement.ListenBacklog** -获取或设置的最大可为挂起状态的排队的连接请求数。 **ListenBacklog**是套接字级别的属性，描述的"挂起接受"号进行排队的请求。 确保最大并发连接数不超过基础套接字队列。 有关此属性的详细信息请参阅[TcpTransportBindingElement.ListenBacklog 属性](http://go.microsoft.com/fwlink/?LinkId=157734)(http://go.microsoft.com/fwlink/?LinkId=157734) MSDN 上。|10|16 * ProcessorCount|10|请尝试 > = 20|  
  
 **将 ServiceThrottlingBehavior 服务行为添加到 WCF 自定义或 WCF CustomIsolated 接收位置并使用以下设置：**  
  
> [!NOTE]  
>  可以修改 ServiceThrottlingBehavior 服务行为的任何元素之前，必须首先添加**serviceThrottling**到行为扩展**行为**选项卡**WCF 自定义\*传输属性**对话框。 若要将 serviceThrottling 添加到行为的列表中，选择**行为**选项卡**WCF 自定义\*传输属性**对话框中，右键单击**ServiceBehavior**下**行为**，单击**将扩展添加**，选择**serviceThrottling**，然后单击**确定**。 然后单击以选择下可用的属性**ServiceThrottlingElement**并根据需要更改属性的值。  
  
|设置|.NET Framework 4 的默认值|针对.NET Framework 4 的建议的值|.NET Framework 3.5 的默认值|建议值为.Net Framework 3.5|  
|-------------|----------------------------------------|--------------------------------------------|------------------------------------------|----------------------------------------------|  
|**ServiceThrottlingBehavior.MaxConcurrentCalls** -获取或设置一个值，指定的最大活动处理跨消息数**ServiceHost**。 **MaxConcurrentCalls**属性指定的最大活动处理跨消息数**ServiceHost**对象。 每个通道都可以有一个挂起消息不会影响的值**MaxConcurrentCalls**直到 WCF 开始对其进行处理。 有关此属性的详细信息，请参阅[ServiceThrottlingBehavior.MaxConcurrentCalls](http://go.microsoft.com/fwlink/?LinkId=157838) (http://go.microsoft.com/fwlink/?LinkId=157838) MSDN 上。 默认值为 BizTalk WCF 自定义和 WCF CustomIsolated 接收适配器**MaxConcurrentCalls**属性是**16**每个 CPU。 **注意：** BizTalk Server WCF 接收 WCF 自定义和 WCF CustomIsolated 适配器公开以外的适配器**最大并发调用**属性**绑定**选项卡**WCF-\*传输属性**对话框中，以配置此行为。 默认值**最大并发调用**行为是**200**。|16 * ProcessorCount|16 * ProcessorCount|-16 个的 BizTalk WCF 自定义和 WCF CustomIsolated 接收适配器。<br />-200 其他 wcf 接收适配器。|-尝试 > = 200，用于 WCF 自定义和 WCF CustomIsolated 接收适配器。<br />-尝试为 200 >**最大并发调用**属性**绑定**选项卡**WCF-\*传输属性**BizTalk Server WCF 的对话框中接收而不是 WCF 自定义和 WCF CustomIsolated 适配器的适配器。|  
|**ServiceThrottlingBehavior.maxConcurrentInstances** -获取或设置一个值，指定的最大数目**InstanceContext**可以同时执行的服务中的对象。 **MaxConcurrentInstances**属性指定的最大数**InstanceContext**服务中的对象。 务必要记住之间的关系**MaxConcurrentInstances**属性和**InstanceContextMode**属性。 如果**InstanceContextMode**为 PerSession，生成的值为总会话数。 如果**InstanceContextMode**是 PerCall，生成的值是并发调用数。 如果消息到达时的最大数**InstanceContext**对象已经存在，直到保存该消息**InstanceContext**对象关闭。 有关此属性的详细信息，请参阅[ServiceThrottlingBehavior.MaxConcurrentInstances 属性](http://go.microsoft.com/fwlink/?LinkId=157897)(http://go.microsoft.com/fwlink/?LinkId=157897) MSDN 上。 默认值用于 WCF 自定义和 WCF CustomIsolated 接收适配器 MaxConcurrentInstances 属性是**116**每个 CPU。 **注意：** 由于 WCF 接收位置实现为包含在 Microsoft.BizTalk.Adapter.Wcf.Runtime.dll 程序集，因为此类标记为 ServiceBehavior (InstanceContextMode BizTalkServiceInstance 类的实例= InstanceContextMode.Single，ConcurrencyMode=ConcurrencyMode.Multiple）。 所有传入请求由相同的单一实例对象，并将忽略此参数。 因此，将 maxConcurrentInstances 属性设置上某些 WCF 自定义接收位置具有不起作用，，因为活动的实例数也始终等于 1。|116 * ProcessorCount|116 * ProcessorCount|26|请尝试 > = 200|  
|**ServiceThrottlingBehavior.MaxConcurrentSessions** - **MaxConcurrentSessions**属性获取或设置最大会话数**ServiceHost**对象可一次接受. 务必了解，在这种情况下进行会话并不局限于仅支持可靠会话的通道。 每个侦听器对象都可以有一个挂起通道会话不会影响的值**MaxConcurrentSessions**直到 WCF 接受通道会话并开始处理通道会话消息。 此属性是最有用中进行的方案使用的会话。 当此属性设置为小于客户端线程数的值时，从多个客户端请求可能会在同一套接字连接中进行排队。 将阻止来自尚未与服务建立会话的客户端的请求。 它们将保持阻止状态，直到该服务将关闭它的会话与其他客户端，如果服务上打开的会话数已达到指定的值**MaxConcurrentSessions**。 然后将未被提供服务的客户端请求超时时，和服务关闭会话。 若要避免这种情况下，请考虑运行客户端线程从不同的应用程序域，以便其他套接字连接接受请求消息。 有关此属性的详细信息，请参阅[ServiceThrottlingBehavior.MaxConcurrentSessions 属性](http://go.microsoft.com/fwlink/?LinkID=157864)(http://go.microsoft.com/fwlink/?LinkId=157864) MSDN 上。|100 * ProcessorCount|100 * ProcessorCount|10|请尝试 > = 200|  
  
 当修改端口配置设置应用更改系统地;单独修改每个参数，并测试对性能和整体稳定性更改的效果。 如往常一样，要应用的正确值取决于特定的方案： 如果值设置得太低，则可以减少可伸缩性;而如果值设置过高，则应用程序要求可能超出的计算机上的物理资源容量。 此外，由于这些属性在相关，它们应在一致和一致的方式设置。 有关使用 ServiceThrottlingBehavior 控制 WCF 服务性能的详细信息，请参阅[使用 ServiceThrottlingBehavior 控制 WCF 服务性能](http://go.microsoft.com/fwlink/?LinkId=157908)(http://go.microsoft.com/fwlink/?LinkId=157908) MSDN 上。  
  
## <a name="see-also"></a>另请参阅  
 [优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)