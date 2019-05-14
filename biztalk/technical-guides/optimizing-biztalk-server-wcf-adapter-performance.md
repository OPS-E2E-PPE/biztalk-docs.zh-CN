---
title: 优化 BizTalk Server WCF 适配器性能 |Microsoft Docs
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
ms.openlocfilehash: 500ad07a47285b2a73b3bf6a768b5a722568807f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393498"
---
# <a name="optimizing-biztalk-server-wcf-adapter-performance"></a>优化 BizTalk Server WCF 适配器性能
本主题提供用于选择相应的 WCF 适配器或绑定类型和应用各种 WCF 适配器配置选项的指南的建议。  
  
## <a name="considerations-when-choosing-which-wcf-adapter-to-use-or-which-wcf-customwcf-customisolated-binding-type-to-use"></a>选择要使用哪个 WCF 适配器或要使用的 WCF 自定义 WCF CustomIsolated 绑定类型时的注意事项  
  
-   如果不是严格必需的因为它会增加消息的大小，则不使用消息级安全性。 这又可以尽量减少解决方案的总体吞吐量。  
  
-   在选择要使用哪个 WCF 适配器或哪些 WCF-自定义/Wcf-customisolated**绑定类型**若要使用，请仔细考虑如兼容性、 性能、 托管平台、 安全性、 任何应用程序要求和支持传输协议。 下面列出的准则适用于 WCF 一般情况下，而且不特定于 BizTalk Server:  
  
    -   **BasicHttpBinding**应在 WCF 服务必须支持如 WebSphere Web 服务或期望 ASMX Web 服务的.NET 1.1 应用程序的旧客户端。 因为 BasicHttpBinding 未实现任何安全性默认情况下，如果您需要消息或传输安全，应在此绑定上显式配置。 使用 BasicHttpBinding 公开能够与基于 ASMX 的 Web 服务和客户端以及符合 WS 其他服务进行通信的终结点的基本配置文件 1.1。 配置传输安全性，BasicHttpBinding 默认设置，以便只需使用任何凭据喜欢传统的 ASMX Web 服务。 BasicHttpBinding 可以承载在 IIS 7.5 或 IIS 7.0 中的 WCF 服务。  
  
    -   **WsHttpBinding**如果通过 Internet WCF 客户端将调用 WCF 服务，则应使用。 WsHttpBinding 是适合用于 Internet 方案中不需要支持旧客户端的期望 ASMX Web 服务和 WsHttpBinding，你可以托管在 IIS 7.5 或 IIS 7.0 中的 WCF 服务。 如果需要支持旧客户端，请考虑改为使用 BasicHttpBinding。   
        当您需要公开 WCF 接收位置或采用支持 WS-发送端口时，应使用 WsHttpBinding * 协议，例如 Ws-security 或 Ws-atomictransactions。  
  
    -   **NetTcpBinding**是一个极佳选择，如果您需要以支持在 intranet 中的客户端。 NetTcpBinding 传输性能很重要，并且可接受的 Windows 服务而不是 IIS 中承载服务是适合用于 intranet 方案。 当您想要提供一个安全且可靠的绑定的环境时，请使用此绑定。NET.NET 跨计算机通信。 请注意在 Windows 服务或 IIS 7.5/7.0 中，必须承载 NetTcpBinding。  
  
    -   **NetNamedPipeBinding**应在你需要在你的服务所在的计算机上支持 WCF 客户端。 此绑定提供了一个安全且可靠的绑定环境，以便跨进程的同一台计算机的通信。 使用此绑定时要使用的 NamedPipe 协议。 请注意在 Windows 服务或 IIS 7.5/7.0 中，必须承载 NetNamedPipeBinding。  
  
    -   **NetMsmqBinding**应在你需要支持已断开连接的队列。 队列提供通过使用消息队列 (也称为 MSMQ) 作为传输，从而使支持断开连接的操作、 故障隔离和负荷量。 当客户端和服务不需要在同一时间处于联机状态时，您可以使用 NetMsmqBinding。 此外可以通过使用负载调节管理任意数量的传入消息。 消息队列支持故障隔离、 其中的消息可能会失败而不会影响其他消息的处理。 请注意在 Windows 服务或 IIS 7.5/7.0 中，必须承载 NetMsmqBinding。  
  
    -   **WsDualHttpBinding**如果你需要支持双工服务，应使用。 双工服务是一种服务，使用双工消息模式，从而使回通过回调客户端服务进行通信的功能。 请注意在 Windows 服务或 IIS 7.5/7.0 中，必须承载 WsDualHttpBinding。  
  
## <a name="wcf-binding-comparison"></a>WCF 绑定比较  
 绑定提供用于配置通道堆栈的机制。 绑定创建一个进程来生成通道堆栈使用传输通道、 消息编码器和一组协议通道。 Windows Communication Foundation 附带了许多经过预配置来解决最常见通信方案的内置绑定。  
  
|绑定类名称|Transport|消息编码|安全模式|可靠消息传送|事务流 （默认情况下禁用）|  
|------------------------|---------------|----------------------|-------------------|------------------------|----------------------------------------------|  
|BasicHttpBinding|HTTP|Text|None|不支持|不支持|  
|WSHttpBinding|HTTP|Text|消息|禁用|WS-AtomicTransactions|  
|NetTcpBinding|TCP|Binary|Transport|禁用|OleTransactions|  
|NetNamedPipesBinding|命名管道|Binary|Transport|不支持|OleTransactions|  
|NetMsmqBinding|MSMQ|Binary|消息|不支持|不支持|  
|CustomBinding|您决定|您决定|您决定|您决定|您决定|  
  
 你可以选择根据自己的通信需要的特定绑定。 例如：  
  
-   **BasicHttpBinding**专为与简单的 Web 服务互操作性。 BasicHttpBinding 使用 HTTP 来传输和消息编码的文本。  
  
-   **WSHttpBinding**设计互操作性与更高级的 Web 服务，可能会充分利用不同的 WS-* 协议。  WSHttpBinding 也使用 HTTP 传输和消息编码的文本。  
  
-   **NetTcpBinding**并**NetNamedPipeBinding**专为高效，并执行 ant 通信与其他 WCF 应用程序分别在计算机之间或同一台计算机上。  
  
-   如果你需要在运行时使用一个或多个自定义协议通道的最大的灵活性，可以使用**CustomBinding**从而让你能够确定哪些绑定元素编写您的绑定。  
  
> [!NOTE]  
>  绑定具有不同响应时间和吞吐量方面的特征。 因此，若要提高性能的常规建议使用 NetTcpBindind 和 NetNamesPipeBinding 在可能的情况。  
  
## <a name="use-the-tcp-transport-and-binary-message-encoding-to-maximize-wcf-adapter-throughput-and-minimize-wcf-adapter-latency"></a>使用 TCP 传输和二进制消息编码以最大化 WCF 适配器吞吐量并降低 WCF 适配器延迟  
 使用 Wcf-nettcp 适配器在可能的情况来最大化吞吐量。 Wcf-nettcp 适配器使用 TCP/IP 传输协议和二进制消息编码一起提供改进的性能相比其他 WCF-* 适配器。  
  
 或者，可以使用配置 WCF 自定义 （或 Wcf-customisolated 适配器的接收位置） **customBinding**绑定类型。 然后，添加**binaryMessageEncoding**绑定扩展来实现二进制消息编码并**tcpTransport**绑定扩展来实现消息传输协议为 TCP/IP。 这种方法是非常灵活，因为它允许您选择和配置所需的绑定元素，并创建自定义通道来扩展 BizTalk 消息引擎的默认行为。 如果实现的 WCF 自定义适配器**customBinding**绑定类型，指定这些值的绑定扩展配置参数，以最大化吞吐量并降低延迟。  
  
 **发送端口配置值：**  
  
|设置|默认值|推荐值|  
|-------------|-------------------|-----------------------|  
|**TcpTransportBindingElement.ConnectionPoolSettings.maxOutboundConnectionsPerEndpoint** -获取或设置连接池中缓存的每个终结点的出站连接的最大数目。 这将限制为每个唯一的远程终结点缓存的连接数。 如果具有更多活动客户端连接而超出此值，则服务可能不响应向客户端，并应调整此值以容纳的最大为每个唯一远程终结点缓存的预期连接数。 有关此属性的详细信息，请参阅[TcpConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint 属性](http://go.microsoft.com/fwlink/?LinkId=157737)(http://go.microsoft.com/fwlink/?LinkId=157737) MSDN 上。|10|请尝试 > = 20|  
  
 **接收端口配置值：**  
  
|设置|默认值为.NET Framework 4|针对.NET Framework 4 的推荐的值|默认值为.NET Framework 3.5|.NET Framework 3.5 的建议的值|  
|-------------|----------------------------------------|--------------------------------------------|------------------------------------------|----------------------------------------------|  
|**TcpTransportBindingElement.MaxPendingAccepts** -获取或设置的最大挂起异步接受数可用于处理传入连接到服务的操作。 对于高水平的同时连接含有的情况，此值可能会不足，应调整连同**MaxPendingConnections**属性以处理更多的并发客户端连接尝试次数。 应该不需要将此属性设置为值大于目前在托管服务的计算机的处理器数目。 有关此属性的详细信息，请参阅[ConnectionOrientedTransportBindingElement.MaxPendingAccepts 属性](http://go.microsoft.com/fwlink/?LinkId=157738)(http://go.microsoft.com/fwlink/?LinkId=157738) MSDN 上。|1|2*ProcessorCount|1|请尝试 > = 20|  
|**TcpTransportBindingElement.MaxPendingConnections** -获取或设置最大服务上等待调度的连接数。 这将限制等待调度的同时进行的客户端连接数。 如果此值太低，客户端连接尝试可能会被服务拒绝。 如果过高，则服务可能在重负载期间缓慢或无响应向客户端。 此属性应设置为一个值，使服务能够运行在大容量时，而不要太高。 当堆栈调用中的高层**AcceptDispatch**，该连接从等待调度的连接队列中移除。 有关此属性的详细信息，请参阅[ConnectionOrientedTransportBindingElement.MaxPendingConnections 属性](http://go.microsoft.com/fwlink/?LinkId=157735)(http://go.microsoft.com/fwlink/?LinkId=157735) MSDN 上。|10|16*ProcessorCount|10|请尝试 > = 20|  
|**TcpTransportBindingElement.ListenBacklog** -获取或设置的最大排队的连接请求可为挂起状态数。 **ListenBacklog**是套接字级别属性的个数"挂起接受"的请求进行排队。 请确保最大并发连接数不超过基础套接字队列。 有关此属性的详细信息请参阅[TcpTransportBindingElement.ListenBacklog 属性](http://go.microsoft.com/fwlink/?LinkId=157734)(http://go.microsoft.com/fwlink/?LinkId=157734) MSDN 上。|10|16*ProcessorCount|10|请尝试 > = 20|  
  
 **将 ServiceThrottlingBehavior 服务行为添加到 Wcf-custom 或 Wcf-customisolated 接收位置，并使用以下设置：**  
  
> [!NOTE]  
>  可以修改 ServiceThrottlingBehavior 服务行为的任何元素之前，必须首先添加**serviceThrottling**到行为扩展**行为**选项卡**WCF 自定义\*传输属性**对话框。 若要将 serviceThrottling 添加到行为的列表，请选择**行为**选项卡**WCF 自定义\*传输属性**对话框中，右键单击**ServiceBehavior**下**行为**，单击**将扩展添加**，选择**serviceThrottling**，然后单击**确定**。 然后单击以选择下可用的属性**ServiceThrottlingElement**并根据需要更改的属性的值。  
  
|设置|默认值为.NET Framework 4|针对.NET Framework 4 的推荐的值|默认值为.NET Framework 3.5|建议值为.Net Framework 3.5|  
|-------------|----------------------------------------|--------------------------------------------|------------------------------------------|----------------------------------------------|  
|**ServiceThrottlingBehavior.MaxConcurrentCalls** -获取或设置一个值，指定的最大活动处理跨消息数**ServiceHost**。 **MaxConcurrentCalls**属性指定的最大活动处理跨消息数**ServiceHost**对象。 每个通道都可以有一个挂起的消息不会影响的值**MaxConcurrentCalls**直到 WCF 开始对其进行处理。 有关此属性的详细信息，请参阅[ServiceThrottlingBehavior.MaxConcurrentCalls](http://go.microsoft.com/fwlink/?LinkId=157838) (http://go.microsoft.com/fwlink/?LinkId=157838) MSDN 上。 默认值为 BizTalk Wcf-custom 和 Wcf-customisolated 接收适配器**MaxConcurrentCalls**属性是**16**每个 CPU。 **注意：** BizTalk Server WCF 接收适配器 Wcf-custom 和 Wcf-customisolated 适配器公开以外**最大并发调用**上的属性**绑定**选项卡**WCF\*传输属性**对话框可以配置此行为。 默认值**最大并发调用**行为**200**。|16*ProcessorCount|16*ProcessorCount|-16 BizTalk Wcf-custom 和 Wcf-customisolated 接收适配器。<br />-200 的其他 WCF 接收适配器。|-尝试 > = 200，为 Wcf-custom 和 Wcf-customisolated 接收适配器。<br />-尝试 > 200**最大并发调用**上的属性**绑定**选项卡**WCF-\*传输属性**BizTalk Server WCF 的对话框接收 Wcf-custom 和 Wcf-customisolated 适配器之外的适配器。|  
|**ServiceThrottlingBehavior.maxConcurrentInstances** -获取或设置一个值，指定的最大数目**InstanceContext**可以立即执行该服务中的对象。 **MaxConcurrentInstances**属性指定的最大数目**InstanceContext**服务中的对象。 务必要记住之间的关系**MaxConcurrentInstances**属性和**InstanceContextMode**属性。 如果**InstanceContextMode**为 PerSession，生成的值为总会话数。 如果**InstanceContextMode**是 PerCall，生成的值是并发调用数。 如果消息到达时的最大数目**InstanceContext**对象已存在，则消息将保存直到**InstanceContext**对象关闭。 有关此属性的详细信息，请参阅[ServiceThrottlingBehavior.MaxConcurrentInstances 属性](http://go.microsoft.com/fwlink/?LinkId=157897)(http://go.microsoft.com/fwlink/?LinkId=157897) MSDN 上。 默认值为 Wcf-custom 和 Wcf-customisolated 接收适配器 MaxConcurrentInstances 属性是**116**每个 CPU。 **注意：** 由于 WCF 接收位置将作为包含在 Microsoft.BizTalk.Adapter.Wcf.Runtime.dll 程序集中，因为此类标记为 ServiceBehavior(InstanceContextMode= BizTalkServiceInstance 类的实例InstanceContextMode.Single，ConcurrencyMode=ConcurrencyMode.Multiple)。 所有传入请求由相同的单一实例对象，则忽略此参数。 因此 maxConcurrentInstances 属性设置上某些 WCF 自定义接收位置不起作用，因为活动实例的数目始终等于 1。|116*ProcessorCount|116*ProcessorCount|26|Try >= 200|  
|**ServiceThrottlingBehavior.MaxConcurrentSessions** - **MaxConcurrentSessions**属性获取或设置会话的最大数目**ServiceHost**对象可接受一次。 务必了解，在这种情况下进行会话并不局限于仅支持可靠会话的通道。 每个侦听器对象都可以有一个挂起通道会话不会影响的值**MaxConcurrentSessions**直到 WCF 接受该通道会话并开始处理通道会话消息。 此属性是最有用方案使用的会话。 当此属性设置为小于客户端线程数的值时，从多个客户端请求可能会获取排入队列中相同的套接字连接。 从客户端与服务创建一个会话的请求将被阻止。 它们将保持阻止状态直到服务关闭其会话与其他客户端，如果服务上打开的会话数已达到指定的值**MaxConcurrentSessions**。 然后将未处理的客户端请求超时时，并在服务关闭会话。 若要避免这种情况下，请考虑运行客户端线程从不同的应用程序域，以便通过不同的套接字连接接受请求消息。 有关此属性的详细信息，请参阅[ServiceThrottlingBehavior.MaxConcurrentSessions 属性](http://go.microsoft.com/fwlink/?LinkID=157864)(http://go.microsoft.com/fwlink/?LinkId=157864) MSDN 上。|100*ProcessorCount|100*ProcessorCount|10|Try >= 200|  
  
 当修改端口的配置设置应用更改系统地;单独修改每个参数，并测试对性能和总体稳定性的更改的影响。 如往常一样，要应用的正确值取决于特定方案： 如果值设置过低，可以降低可伸缩性;而如果值设置过高，应用程序要求可能会超过物理计算机上的资源容量。 此外，由于这些属性相关的它们应统一且一致的方式设置。 有关使用 ServiceThrottlingBehavior 控制 WCF 服务性能的详细信息，请参阅[使用 ServiceThrottlingBehavior 控制 WCF 服务性能](http://go.microsoft.com/fwlink/?LinkId=157908)(http://go.microsoft.com/fwlink/?LinkId=157908) MSDN 上。  
  
## <a name="see-also"></a>请参阅  
 [优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)