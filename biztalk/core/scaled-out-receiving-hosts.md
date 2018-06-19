---
title: 向外扩展接收主机 |Microsoft 文档
ms.custom: ''
ms.date: 2016-03-17
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, receive adapters
- high availability
- HTTP adapters, scaling
- receive adapters, scaling
- POP3 adapters, scaling
- MSMQ adapters, scaling
- EDI adapters, scaling
- Web services, scaling
- hosts, multiple
- MQSeries adapters, scaling
- adapters, Windows SharePoint Services
- scaling, hosts
- scaling, adapters
- SAP adapters
- FTP adapters
- scaling, receive adapters
- hosts, receiving
- adapters, Web services
- hosts, scaling
- SOAP adapters, scaling
- adapters, scaling
- SQL adapters, scaling
- Web services, adapters
- File adapters, scaling
- clustering
ms.assetid: 94f35426-37fa-4ad2-8e35-d82fdca02262
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b9bc048de978a6dfd7c28505c54cdaaaef64064
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22272549"
---
# <a name="scaled-out-receiving-hosts"></a>向外扩展接收主机
当主机包含接收项（例如接收位置或管道）时，该主机将充当安全边界，而且消息的解码和解密都将发生在主机内的管道中。 为确保接收主机高度可用，必须有两台或更多 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机运行所有接收主机的实例。 可以通过扩展接收主机来保证可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息传递需要进行大量的部署。 尽管这些部署可能很少处理业务流程，但仍可快速和可靠地路由许多不同类型的消息。  
  
 通过将接收主机与处理业务流程和发送消息的主机分隔开来，您可增强您的环境的安全性和可伸缩性，因为可以独立于其他主机来保护和扩展每个主机。 例如，您可以将两台计算机（主机实例）添加到接收主机，而无需向处理主机或发送主机添加任何计算机。  
  
## <a name="multiple-hosts-for-receiving-messages"></a>使用多个主机接收消息  
 下图显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过在两台计算机正在运行的接收主机实例接收主机提供高可用性的部署。 请注意，此图中的处理主机和发送主机并不高度可用。  
  
 ![用于接收消息的多个主机](../core/media/tdi-ha-scalereceive.gif "TDI_HA_ScaleReceive")  
  
 在进行大型部署、与多个贸易合作伙伴打交道以及使用不同的协议时，您可以采用多个接收主机来分担接收功能。 例如，您可以创建一个主机来接收每个适配器的消息，也可以创建不同主机来接收来自不同合作伙伴的消息。 在创建多个接收主机后，您可以创建安全边界来提高您的环境的可管理性和可伸缩性；但是，这并不能确保环境高度可用。  
  
 为确保环境高度可用，您必须为创建的每个接收主机创建两个或更多主机实例。 例如，您可以创建三个不同的接收主机（A、B 和 C）来接收来自三家不同公司的消息。 为确保所有这些主机高度可用，随后还需要在两台或更多计算机中创建所有这些主机的实例。 请注意，您可以在一台计算机上创建每个主机的实例，而不会影响安全边界、可管理性或可伸缩性。  
  
 下图显示了具有三台计算机的高度可用的 BizTalk Server 环境（其中不同的主机专用于接收来自不同公司的消息）：  
  
 ![接收实例](../core/media/tdi-ha-receiveinstances2.gif "TDI_HA_ReceiveInstances2")  
  
 为确保此配置的高可用性，每台计算机都运行三个主机实例：三家公司中的每一个家都对应一个实例。 每家公司的主机实例都包含用来与该公司进行通信的接收位置和管道。 在常规操作过程中，只要您完成了在接收适配器前扩展所需的工作（例如，为 HTTP 配置网络负载平衡时），则消息传送负载将分布在每个主机的三个主机实例中。 如果一台计算机上的主机实例失败，则在其他两台计算机上运行的主机实例将提供冗余，以保持服务可用。  
  
## <a name="scaling-the-biztalk-server-receive-adapters"></a>扩展 BizTalk Server 接收适配器  
 除了主机实例外，扩展接收主机并提高其可用性的过程还取决于在部署中实施的特定适配器。 每个适配器都具有与协议有关的特性，所以在协议不同的情况下规划和部署也会有所不同。 但是，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使你能够应用所有适配器的支持，主要通过其他计算机和主机实例相同的高可用性解决方案。  
  
 根据所用的具体协议，某些接收适配器需要采用在多台主机计算机中分布传入消息的附加机制，才能确保高可用性。 例如，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 HTTP 或 SOAP 适配器 （也称为 Web 服务适配器） 的解决方案需要负载平衡器如网络负载平衡 (NLB) 分配接收工作负荷。 下表总结了中的最常见适配器的高可用性准则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
|**适配器**|**高可用性准则**|  
|-----------------|---------------------------------------|  
|HTTP|将多台计算机添加到接收主机并配置 NLB 以将传入消息分配给多个主机计算机。|  
|SOAP|将多台计算机添加到接收主机并配置 NLB 以将传入消息分配给多个主机计算机。|  
|文件|向接收主机添加多台计算机，其中每台主机计算机上的接收位置都引用同一文件夹或通用命名约定 (UNC) 路径。 对于完整的高可用性解决方案，必须确保 UNC 路径指向的文件位置是高度可用的（或者至少是可靠的）。|  
|FTP|将 FTP 接收适配器配置为在群集 BizTalk 主机中运行。 有关详细信息，请参阅[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。|  
|POP3|将 POP3 接收适配器配置为在群集 BizTalk 主机中运行。 有关详细信息，请参阅[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。|  
|MSMQ|配置 MSMQ 接收适配器在 Windows 群集 BizTalk 主机中运行。 有关详细信息，请参阅[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。 如果 MSMQ 接收位置要在远程 MSMQ 服务器上使用队列，你不需要群集 BizTalk 主机。  在此方案中，运行 MSMQ 接收主机组中的多个 BizTalk 计算机上。|  
|MQSeries|向此适配器的接收主机添加多台计算机，在 MQSeries for Windows 中使用群集队列管理器，并群集 MQSeries Server for Windows。|  
|Windows Sharepoint Services|将多台计算机添加到接收主机并配置 NLB 以将传入消息分配给多个主机计算机。|  
|-WCF NetTcp<br />基于 WCF 的自定义项|向接收主机添加多台计算机，并配置 NLB 以在这些主机计算机间分发传入消息。<br /><br /> -或者-<br /><br /> 群集适配器接收处理程序使用的主机。|  
|-WCF NetNamedPipe<br />-WCF BasicHttp<br />-WCF WSHttp<br />-WCF CustomIsolated|向接收主机添加多台计算机，并配置 NLB 以在这些主机计算机间分发传入消息。|  
|WCF-NetMsmq|群集适配器接收处理程序使用的主机。|  
  
### <a name="http-adapter"></a>HTTP 适配器  
 HTTP 接收中的适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是在每个接收主机计算机作为主机实例运行的 Internet 服务器 API (ISAPI) 扩展 (BTSHTTPReceive.dll)。 当合作伙伴通过 HTTP 协议将消息发送到 BizTalk Server 时，该消息通常会送达安装有 Internet 信息服务 (IIS) 的 BizTalk Server 计算机上的特定 URL。 您可在 BizTalk Server 中创建接收位置订阅此 URL 的主机实例。 在消息送达此 URL 后，BizTalk Server 将对这些消息进行检索，然后将其保存在 MessageBox 数据库中。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为 HTTP 提供高可用性通过让你创建多个相同的接收主机的主机实例接收适配器。 如果您使用 NLB 在多个接收主机中分发传入消息，则这些主机实例订阅的具体 URL 可以是共享的群集 IP 地址。 这些主机都可为群集的虚拟 IP 地址提供服务，这样，在一个群集成员发生故障时，其他成员仍可以为此 IP 地址提供服务。  
  
### <a name="soap-adapter-web-services-adapter"></a>SOAP 适配器 （Web 服务适配器）  
 与 HTTP 接收适配器不同，Web Services 的接收适配器不包括 ISAPI 扩展功能。 该适配器通过使用 BizTalk Web Services 发布向导指定的 URL 接收传入消息。 此向导可导出 Web Services 并创建充当接收位置的虚拟目录。  
  
 为确保 Web Services 适配器的高可用性，请向接收主机添加多台计算机，并使用 NLB 分发传入消息。 在客户端通过 Web Services 适配器将消息发送到 BizTalk Server 时，NLB 将利用这些接收主机之一来平衡消息负载，然后该主机上运行的相应主机实例将消息存储到 MessageBox 数据库中。  
  
### <a name="file-adapter"></a>文件适配器  
 文件接收适配器可从文件夹或 UNC 路径检索消息。 此适配器通常在公司内使用，而不是在企业对企业方案中使用，因为双方均需要访问该路径的权限，而不同公司通常不能共享文件系统。 您可将文件接收处理程序配置为订阅路径，以便在消息到达接收位置时 BizTalk Server 可检索这些消息。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为 file 接收适配器通过让你在多个订阅的相同的 UNC 路径的主机计算机上创建主机实例提供高可用性。 如果在一台主机计算机上运行的主机实例遇到错误或失败，则在其他主机计算机上运行的同一主机实例仍可检索消息，并将其存储到 MessageBox 数据库中。  
  
### <a name="ftp-adapter"></a>FTP 适配器  
 不应将 FTP 接收适配器配置为在多个主机中运行，因为 FTP 接收适配器使用 FTP 协议从目标系统检索文件，而 FTP 协议没有任何文件锁定概念，不能确保在运行 FTP 接收适配器的多个实例时不会同时检索同一文件的多个副本。 FTP 接收适配器应配置为在群集的 BizTalk 主机中运行。 有关详细信息，请参阅[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
### <a name="pop3-adapter"></a>POP3 适配器  
 除非 POP3 适配器从中进行读取的 POP3 服务器允许对同一邮箱进行多个并行连接，否则 POP3 接收适配器可配置为在多个主机中运行。 如果 POP3 适配器连接到的 POP3 服务器允许对其邮箱进行多个并行连接，则必须通过将 POP3 适配器接收处理程序配置为在已经群集的 BizTalk 主机实例中运行，来确保 POP3 适配器的高可用性。 有关详细信息，请参阅[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
### <a name="msmq-adapter"></a>MSMQ 适配器  
 若要实现高可用性，运行 MSMQ，请在为群集的 MSMQ 资源相同的群集组中的 Windows 群集 BizTalk 主机中接收适配器。 有关详细信息，请参阅[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
 如果 MSMQ 接收位置是**仅**接收来自 MSMQ 队列在远程 MSMQ 服务器上，则可以通过运行 MSMQ 实现高可用性接收 BizTalk 组中的多个 BizTalk 计算机上的主机。  若要为了使 MSMQ 提供高可用性，你必须确保远程 MSMQ 服务器使用故障转移群集在 Windows 中。  如果使用事务性队列时，必须运行远程 MSMQ 服务器 MSMQ 4.0 (Windows Server 2008) 或更高版本。  
  
### <a name="mqseries-adapter"></a>MQSeries 适配器  
 Microsoft BizTalk Adapter for MQSeries 用作之间的桥梁[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 IBM MQSeries 服务器。 为确保在使用此适配器时实现高度可用的解决方案，必须有多个运行 MQSeries 适配器的主机的实例，在 MQSeries for Windows 中使用群集队列管理器，并群集 MQSeries Server for Windows。 有关群集队列管理器和群集 MQSeries 服务器的详细信息，请参阅 IBM WebSphere MQ 文档。 有关确保 MQSeries 适配器高度可用的详细信息，请参阅用于 MQSeries 的 Microsoft BizTalk 适配器的帮助中的“高可用性”。  
  
### <a name="windows-sharepoint-services-adapter"></a>Windows SharePoint Services 适配器  
 Windows SharePoint Services 适配器通过调入 BizTalk 安装在 SharePoint 计算机上的 Windows SharePoint Services Web Services 从 SharePoint 中检索消息。 该适配器使用签出机制，以便确保不同的主机实例不会处理同一消息。 这允许接收适配器，可以通过添加更多的主机实例扩展。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于 SharePoint 接收适配器通过让你提供高可用性运行相同接收相同的 HTTP URL 指向 SharePoint NLB 安装订阅的多个主机实例上的位置。  
  
### <a name="wcf-nettcp-adapter"></a>WCF NetTcp 适配器  
 可以使用 IP 层负载平衡技术平衡 NetTcpBinding 的负载。 但是，默认情况下，NetTcpBinding 合并 TCP 连接会降低连接延迟。 这是影响负载平衡基本机制的优化设置。 优化 NetTcpBinding 的主要配置值是租约超时时间，该值为连接池设置的一部分。 连接池使得客户端连接与场内特定服务器相关联。 由于这些连接的生存期增长（租约超时设置控制的因素），场中各个服务器的负载分布变得不平衡。 进而平均调用时间增加。 从而当在负载平衡方案中使用 NetTcpBinding 时，请考虑缩短绑定使用的默认租约超时。 对于负载平衡方案，30 秒租约超时是比较合理的起点，尽管优化值依赖于应用程序。 有关通道租约超时和其他传输配额的详细信息，请参阅“传输配额”。  
  
## <a name="see-also"></a>另请参阅  
 [为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)