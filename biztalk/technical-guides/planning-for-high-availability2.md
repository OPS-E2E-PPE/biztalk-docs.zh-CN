---
title: "规划高 Availability2 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65271fd5-5294-406f-87f8-3aa394c235a2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 310414b094b7175c6b07fc92697b460e6dd2a830
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-high-availability"></a>规划高可用性
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 的高可用性着重于恢复在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署中可能出现可用性问题的功能组件。  
  
 为了演示中的高可用性[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，你需要会导致失败，并度量恢复中的产品的有效性。 高度可用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署创建错误和失败透明外部应用程序和系统，并确保所有服务都继续正常工作中断降至最低。  
  
 设计[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]提供高可用性的部署涉及到实现冗余，以便在应用程序集成或业务过程集成方案涉及每个功能组件。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]通过从概念上讲分隔中的数据，简化了这些方案的实现*主机*处理数据。 A*主机*是 BizTalk 的逻辑容器项，如业务流程、 发送处理程序，以及接收处理程序。 你创建*托管实例*并将它们分配到主机。 主机实例是特定服务器上的主机的物理表示。 它是[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]BTSNTSvc.exe 或另一个进程调用服务过程中，例如，IIS 进程。 因此提供的高可用性[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]涉及运行多个*托管实例*和群集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，，如下所示：  
  
-   **BizTalk 主机的体系结构**。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]可以单独的主机和运行多个主机实例以提供高可用性的关键功能，如接收消息，处理业务流程，并将发送消息。 这些主机不需要任何其他群集或负载平衡机制因为[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]自动通过主机实例的多台计算机间分配工作负荷。 但是，承载的 HTTP 和 SOAP 适配器需要负载平衡机制如网络负载平衡 (NLB) 来提供高可用性，并运行 ftp 接收处理程序主机，MSMQ、 POP3、 SQL、 和 SAP 需要运行接收处理程序机制聚类分析，以提供高可用性。  
  
    > [!NOTE]  
    >  你必须始终群集 SAP 接收适配器以适应两阶段提交方案。  
  
-   **BizTalk Server 数据库的体系结构**。 高可用性配置[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]数据库通常包括两个或多个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库在不主动/被动服务器群集配置中配置的计算机。 这些计算机共享公共的磁盘资源 (如 RAID 1 + 0 SCSI 磁盘阵列或存储区域网络)，使用 Windows 故障转移群集来提供备份的冗余和容错能力。  
  
 对于高可用性至关重要的另一个 BizTalk 功能组件是主密钥服务器。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依赖于此服务，以获取加密密钥。  
  
 本部分提供有关如何解决每个类别中的高可用性的信息。 因为[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]高可用性解决方案基于[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]和[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]，请确保在配置主机之前，具有高可用性部署这些产品[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。 以下链接包括有关确保这些基础产品的高可用性的信息：  
  
-   **白皮书： 高可用性 — 始终上技术**在[http://go.microsoft.com/fwlink/?LinkId=156812](http://go.microsoft.com/fwlink/?LinkId=156812)。  
  
-   获取有关在 Windows Server 2008 的问题疑难解答的详细信息[Windows Server 2008 部署、 管理和故障排除页](http://go.microsoft.com/fwlink/?LinkId=156813)(http://go.microsoft.com/fwlink/?LinkId=156813)。  
  
-   在 Windows Server 2008 中获取有关可用性和可伸缩性的详细信息[可用性和可伸缩性](http://go.microsoft.com/fwlink/?LinkId=156814)(http://go.microsoft.com/fwlink/?LinkId=156814)。  
  
-   请参阅**高可用性**部分[Windows Server 2008 R2 文章和白皮书页](http://go.microsoft.com/fwlink/?LinkId=157760)(http://go.microsoft.com/fwlink/?LinkId=157760)。  
  
## <a name="understanding-the-impact-of-a-component-failure"></a>了解组件故障的影响  
 下表列出了组件和依赖关系[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境和对影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境如果的组件或依赖项失败。 确定是否群集组件或依赖项时，应考虑可能失败的作用域。  
  
|组件或依赖项|故障的范围|  
|-----------------------------|----------------------|  
|[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]|系统级。 如果[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]然后失败[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将无法处理的文档。|  
|主密钥服务器|系统级。 如果主密钥服务器然后失败[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将无法处理的文档。 **注意：**如果主密钥服务器失败，BizTalk 组中的每个 BizTalk 服务器将继续使用缓存的内存中副本的主密钥，直到重新启动该 BizTalk 服务器上的企业 SSO 服务。 如果企业 SSO 服务 BizTalk 服务器上重新启动，然后从内存中释放主密钥的缓存的副本，并 BizTalk 服务器必须能够联系以获取主密钥的另一个副本的主密钥服务器。 不重新启动 BizTalk 服务器上的企业 SSO 服务在组中如果主密钥服务器失败并且你希望 BizTalk 服务器继续处理文档。|  
|MSDTC|服务器。 如果 MSDTC 失败，则将失败，对于需要事务支持服务器上的任何组件。 **注意：**因为[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和主密钥服务器依赖于 MSDTC 事务支持，如果 SQL server 或主密钥服务器上的 MSDTC 失败，故障的范围将成为系统范围。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与通信时需要事务支持[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和在运行时操作期间的主密钥服务器。|  
|BizTalk 主机实例|服务器。 存放在一个 BizTalk 主机实例的任何组件将不能参与文档处理，如果主机实例失败。|  
|Microsoft 消息队列 (MSMQ)|服务器。 如果 MSMQ 失败然后依赖于 MSMQ 服务，诸如 MSMQ 适配器的任何文档处理将暂停服务器上。|  
|文件系统|服务器。 如果文件系统失败然后依赖于文件系统中，诸如文件适配器的任何文档处理将暂停服务器上。|  
  
 若要能够更好地管理高可用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统，你必须具有 BizTalk 堆栈更好地理解： [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]，DC （DNS、 DHCP） [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]， [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，IIS 服务器、 文件服务器、 MSMQ 服务器、 外部应用程序。 本部分重点的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和依赖[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。  
  
## <a name="biztalk-server-high-availability-examples"></a>BizTalk Server 高可用性示例  
 有关在 Microsoft 中的示例方案[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，提供通过向外扩展的层的主机的高可用性，请参阅[示例 BizTalk Server 高可用性方案](http://go.microsoft.com/fwlink/?LinkId=156815)(http://go.microsoft.com/fwlink/?LinkId=156815)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [数据库的高可用性](../technical-guides/high-availability-for-databases.md)   
 [主密钥服务器的高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [清单： 提高可用性与灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)