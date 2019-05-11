---
title: 向外扩展接收主机 |Microsoft Docs
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
ms.openlocfilehash: 5f66b1966814be2784b2372135ac0c042a0746a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309324"
---
# <a name="scaled-out-receiving-hosts"></a>向外扩展接收主机
当主机包含接收项时，如接收位置或管道，它充当安全边界，并在主机内的管道中出现消息解码和解密。 若要确保接收主机高度可用，必须具有两个或多个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行的每个接收主机实例的计算机。 可以通过横向扩展接收主机保证可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]消息传递需要进行大量的部署。 尽管这些部署可能很少处理业务流程，它们可以将不同类型的快速和可靠地的许多消息路由。  
  
 通过将接收主机与处理业务流程和发送消息，因为你可以保护并扩展独立于其他主机的每个主机的主机环境中，可以增强安全性和可伸缩性。 例如，可以向接收主机而不将任何计算机添加到处理或发送主机添加两台计算机 （主机实例）。  
  
## <a name="multiple-hosts-for-receiving-messages"></a>多个主机接收消息  
 下图显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过在两台计算机上运行的接收主机实例以确保接收主机提供高可用性的部署。 请注意，在此图中处理和发送主机并不高度可用。  
  
 ![多个主机接收消息](../core/media/tdi-ha-scalereceive.gif "TDI_HA_ScaleReceive")  
  
 对于大型部署，用于处理多个贸易合作伙伴的方案以及方案使用不同的协议时，可以跨多个接收主机来分散接收功能。 例如，您可以用于接收消息的每个适配器或从其他合作伙伴接收消息的不同主机创建主机。 创建多个接收主机时可以创建安全边界并简化可管理性和可伸缩性的您的环境;但是，它会使您的环境高度可用。  
  
 若要使您的环境高度可用，必须为你创建每个接收主机创建两个或多个主机实例。 例如，您可以创建三个不同接收主机 （A、 B 和 C） 以接收来自三家不同公司的消息。 若要使每个这些主机高度可用您然后创建每个这些主机的主机实例在两个或多台计算机中。 请注意，您可以具有的每个主机实例在一台计算机上而不会丢失安全边界、 可管理性或可伸缩性。  
  
 下图显示与专用于接收来自不同公司的消息的主机高度可用的包含三台计算机 BizTalk Server 环境。  
  
 ![接收实例](../core/media/tdi-ha-receiveinstances2.gif "TDI_HA_ReceiveInstances2")  
  
 若要提供此配置中的高可用性，每台计算机都运行三个主机实例： 为每个三家公司的一个实例。 每个公司的主机实例包含接收位置和管道，以便与该公司进行通信。 在典型操作期间，只要您曾经所需的 （例如，如果你配置网络负载平衡 HTTP），接收适配器前扩展工作消息传送负载将分布在三个主机实例为每个主机。 如果一台计算机上的主机实例失败，其他两台计算机上运行的主机实例提供冗余和维护服务可用性。  
  
## <a name="scaling-the-biztalk-server-receive-adapters"></a>扩展 BizTalk Server 接收适配器  
 除了主机实例外缩放并确保接收主机高度可用的过程还取决于在部署中实施的特定适配器。 每个适配器都具有特定于协议的特性可以使规划和部署在每种情况不同。 但是， [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ，你可将所有适配器的支持，主要通过其他计算机和主机实例相同的高可用性解决方案。  
  
 具体取决于所使用的特定协议，某些接收适配器需要额外的机制分布在多台主机计算机之间的传入消息，以提供高可用性。 例如，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用 HTTP 或 SOAP 适配器 （也称为 Web services 适配器） 的解决方案需要如网络负载平衡 (NLB) 来分布接收工作负荷的负载均衡器。 下表总结了中的最常见的适配器的高可用性指南[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
|**适配器**|**高可用性指南**|  
|-----------------|---------------------------------------|  
|HTTP|向接收主机添加多台计算机并配置 NLB 以在多台主机计算机间分发传入消息。|  
|SOAP|向接收主机添加多台计算机并配置 NLB 以在多台主机计算机间分发传入消息。|  
|文件|向引用相同文件的文件夹或通用命名约定 (UNC) 路径每台主机计算机上的接收位置的接收主机添加多台计算机。 对于完整的高可用性解决方案，必须确保 UNC 路径指向的文件位置是高度可用 （或至少是可靠）。|  
|FTP|配置 FTP 接收适配器在群集 BizTalk 主机中运行。 有关详细信息，请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。|  
|POP3|配置 POP3 接收适配器在群集 BizTalk 主机中运行。 有关详细信息，请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。|  
|MSMQ|配置 MSMQ 接收适配器运行在 Windows 群集 BizTalk 主机中。 有关详细信息，请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。 如果与 MSMQ 接收位置远程 MSMQ 服务器上使用队列，不需要群集 BizTalk 主机。  在此方案中，运行 MSMQ 的接收主机组中的多个 BizTalk 计算机上。|  
|MQSeries|添加多个计算机连接到此适配器的接收主机在 MQSeries 的 Windows 中使用群集的队列管理器和群集 MQSeries Server for Windows。|  
|Windows Sharepoint Services|向接收主机添加多台计算机并配置 NLB 以在多台主机计算机间分发传入消息。|  
|-   WCF-NetTcp<br />-自定义 WCF|向接收主机添加多台计算机并配置 NLB 以在这些主机计算机间分发传入消息。<br /><br /> -或者-<br /><br /> 群集主机适配器所用的接收处理程序。|  
|-   WCF-NetNamedPipe<br />-   WCF-BasicHttp<br />-   WCF-WSHttp<br />-WCF CustomIsolated|向接收主机添加多台计算机并配置 NLB 以在这些主机计算机间分发传入消息。|  
|WCF-NetMsmq|群集主机适配器所用的接收处理程序。|  
  
### <a name="http-adapter"></a>HTTP 适配器  
 HTTP 接收适配器中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是作为主机实例在每个接收主机计算机运行的 Internet 服务器 API (ISAPI) 扩展 (BTSHTTPReceive.dll)。 当合作伙伴通过 HTTP 协议向 BizTalk Server 发送一条消息时，消息通常会送达的特定 url 的 BizTalk Server 计算机上使用 Internet 信息服务 (IIS) 安装。 使用订阅此 URL 的接收位置在 BizTalk Server 中创建主机实例。 当消息到达的 URL 上时，BizTalk Server 对其进行检索，并将其保留在 MessageBox 数据库中。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供高可用性的 HTTP 接收适配器通过让你创建同一接收主机的多个主机实例。 这些主机实例订阅可以是共享的特定 URL、 群集 IP 地址，如果您使用 NLB 分发传入消息跨多个接收主机。 这些主机都可提供在群集的虚拟 IP 地址，以便如果在一个群集成员出现故障，其他人仍可提供此 IP 地址。  
  
### <a name="soap-adapter-web-services-adapter"></a>SOAP 适配器 （Web Services 适配器）  
 与 HTTP 接收适配器，不同的 Web 服务接收适配器不涉及的 ISAPI 扩展。 它接收通过使用 BizTalk Web Services 发布向导指定 URL 的传入消息。 此向导导出 Web 服务，并为接收位置创建虚拟目录的函数。  
  
 若要为 Web services 适配器提供高可用性，向接收主机添加多台计算机，并使用 NLB 分发传入消息。 当客户端通过 Web 服务适配器将消息发送到 BizTalk Server 时，NLB 负载平衡到接收主机之一的消息和在主机上运行的合适的主机实例将消息保存在 MessageBox 数据库。  
  
### <a name="file-adapter"></a>文件适配器  
 文件接收适配器检索消息文件文件夹或 UNC 路径。 因为这两个参与方需要对该路径的权限，并且公司通常不能共享文件系统中而不是企业到企业方案中的公司通常使用此适配器。 配置文件接收处理程序来订阅路径，以便 BizTalk Server 可检索消息到达接收位置时。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文件接收适配器通过让你在订阅同一 UNC 路径的多台主机计算机上创建主机实例提供高可用性。 如果在一台主机计算机上运行的主机实例遇到错误或失败，另一台主机计算机上运行的同一主机实例可以检索消息并将其保存到 MessageBox 数据库。  
  
### <a name="ftp-adapter"></a>FTP 适配器  
 FTP 接收适配器不应配置为在多个主机中运行，因为 FTP 接收适配器使用 FTP 协议从目标系统检索文件和 FTP 协议没有任何文件锁定以确保多个概念的相同副本文件不会同时检索正在运行的多个实例的 FTP 接收适配器时。 FTP 接收适配器应配置为群集的 BizTalk 主机中运行。 有关详细信息，请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
### <a name="pop3-adapter"></a>POP3 适配器  
 POP3 接收适配器可以配置为在多个主机中运行，除非适配器从中进行读取的 POP3 服务器允许对同一邮箱进行多个并发连接。 如果 POP3 适配器连接到的 POP3 服务器允许对其邮箱进行多个并发连接然后 POP3 适配器的高可用性而必须实现通过配置的 POP3 适配器接收处理程序已被 BizTalk 主机实例中运行群集。 有关详细信息，请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
### <a name="msmq-adapter"></a>MSMQ 适配器  
 若要实现高可用性，运行 MSMQ 接收适配器中为群集 MSMQ 资源同一个群集组的 Windows 群集 BizTalk 主机。 有关详细信息，请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
 MSMQ 接收位置是否**仅**接收来自远程 MSMQ 服务器上的 MSMQ 队列，则可以通过运行 MSMQ 实现高可用性 BizTalk 组中接收多个 BizTalk 计算机上的主机。  若要为 MSMQ 提供高可用性，必须确保远程 MSMQ 服务器正在使用中 Windows 故障转移群集。  如果使用的事务性队列，必须运行远程 MSMQ 服务器 MSMQ 4.0 (Windows Server 2008) 或更高版本。  
  
### <a name="mqseries-adapter"></a>MQSeries 适配器  
 用于 MQSeries 的 Microsoft BizTalk 适配器用作之间的桥梁[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 IBM MQSeries 服务器。 若要使用此适配器时，提供高度可用的解决方案，必须运行 MQSeries 适配器的主机的多个实例、 在 MQSeries 的 Windows 中使用群集的队列管理器和群集 MQSeries Server for Windows。 有关群集队列管理器和群集 MQSeries 服务器的详细信息，请参阅 IBM WebSphere MQ 文档。 有关确保 MQSeries 适配器高度可用的详细信息，请参阅有关 MQSeries 的帮助的 Microsoft BizTalk 适配器中的"高可用性"。  
  
### <a name="windows-sharepoint-services-adapter"></a>Windows SharePoint Services 适配器  
 Windows SharePoint Services 适配器通过调入 SharePoint 计算机上安装 BizTalk 的 Windows SharePoint Services web 服务从 SharePoint 中检索消息。 适配器使用签出机制，以确保不同的主机实例不会处理同一消息。 这样，接收适配器若要横向扩展添加更多主机实例。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供高可用性，SharePoint 通过让你接收适配器的相同接收位置在订阅同一 HTTP URL 指向 SharePoint NLB 安装的多个主机实例上运行。  
  
### <a name="wcf-nettcp-adapter"></a>Wcf-nettcp 适配器  
 NetTcpBinding 可使用 IP 层负载平衡技术平衡负载。 但是，nettcpbinding 合并 TCP 连接默认情况下以减少连接延迟。 这是一种优化方式会干扰的负载平衡的基本机制。 优化 NetTcpBinding 的主要配置值是租约超时，它是连接池设置的一部分。 连接池使得客户端连接成为场中的特定服务器相关联。 这些连接的生存期的增加 （由租约超时设置控制的因素），场中的不同服务器上的负载分布变得不平衡。 因此平均调用时间增加。 因此，当在负载平衡方案中，使用 NetTcpBinding，请考虑减少由绑定使用的默认租约超时。 30 秒租约超时是比较合理的起点的负载平衡方案，尽管最佳值与应用程序相关。 有关通道租约超时和其他传输配额的详细信息，请参阅传输配额。  
  
## <a name="see-also"></a>请参阅  
 [为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)