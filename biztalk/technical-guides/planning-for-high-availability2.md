---
title: 规划高 Availability2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65271fd5-5294-406f-87f8-3aa394c235a2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9b5ff05391eed424e7b910296cc5aa801f8cab1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008326"
---
# <a name="planning-for-high-availability"></a>规划高可用性
BizTalk Server 的高可用性侧重于恢复可能会中断 BizTalk Server 部署中的可用性的功能组件。  
  
 若要演示 BizTalk Server 中的高可用性，你必须导致失败，并度量恢复中的产品的有效性。 高度可用的 BizTalk Server 部署使错误和失败对外部应用程序和系统，透明，并确保所有服务都继续正常工作中断降至最低。  
  
 设计为提供高可用性的 BizTalk Server 部署需要在应用程序集成或业务过程集成方案中实现涉及每个功能组件的冗余。 BizTalk Server 通过从概念上讲分隔中的数据，简化了这些方案的实现*主机*处理数据。 A*主机*是 BizTalk 的逻辑容器项，如业务流程、 发送处理程序，以及接收处理程序。 你创建*托管实例*并将它们分配到主机。 主机实例是特定服务器上的主机的物理表示。 它是调用 BTSNTSvc.exe BizTalk Server 服务进程或另一个进程，例如，IIS 进程。 因此提供高可用性，BizTalk Server 涉及运行多个*托管实例*和群集 BizTalk Server 数据库，如下所示：  
  
-   **BizTalk 主机的体系结构**。 BizTalk Server，可单独的主机和运行多个主机实例以提供高可用性的关键功能，如接收消息，处理业务流程，并将发送消息。 这些主机不需要任何其他群集或负载平衡机制，因为 BizTalk Server 会自动在通过主机实例的多台计算机之间分发工作负荷。 但是，承载的 HTTP 和 SOAP 适配器需要负载平衡机制如网络负载平衡 (NLB) 来提供高可用性，并运行 ftp 接收处理程序主机，MSMQ、 POP3、 SQL、 和 SAP 需要运行接收处理程序机制聚类分析，以提供高可用性。  
  
    > [!NOTE]  
    >  你必须始终群集 SAP 接收适配器以适应两阶段提交方案。  
  
-   **BizTalk Server 数据库的体系结构**。 BizTalk Server 数据库的高可用性配置通常由在主动/被动服务器群集配置中配置两个或多个 SQL Server 数据库计算机组成。 这些计算机共享公共的磁盘资源 (如 RAID 1 + 0 SCSI 磁盘阵列或存储区域网络)，使用 Windows 故障转移群集来提供备份的冗余和容错能力。  
  
 对于高可用性至关重要的另一个 BizTalk 功能组件是主密钥服务器。 BizTalk Server 依赖于此服务，以获取加密密钥。  
  
 本部分提供有关如何解决每个类别中的高可用性的信息。 由于 BizTalk Server 高可用性解决方案基于 Windows 和 SQL Server，请确保在配置 BizTalk Server 的主机之前，具有高可用性部署这些产品。 以下链接包括有关确保这些基础产品的高可用性的信息：  
  
-   **高可用性解决方案 (SQL Server)] (https://docs.microsoft.com/sql/sql-server/failover-clusters/high-availability-solutions-sql-server)**  
  
-   **[故障转移群集 Windows Server 中](https://docs.microsoft.com/windows-server/failover-clustering/failover-clustering-overview)**
  
## <a name="understanding-the-impact-of-a-component-failure"></a>了解组件故障的影响  
 下表列出了组件和 BizTalk Server 环境和对 BizTalk Server 环境的影响的依赖关系，如果组件或依赖项失败。 确定是否群集组件或依赖项时，应考虑可能失败的作用域。  
  
|组件或依赖项|故障的范围|  
|-----------------------------|----------------------|  
|SQL Server|系统级。 如果 SQL Server 失败 BizTalk Server 将不能处理的文档。|  
|主密钥服务器|系统级。 如果主密钥服务器失败 BizTalk Server 将不能处理的文档。 <br/>**注意：** 如果主密钥服务器失败，BizTalk 组中的每个 BizTalk 服务器将继续使用缓存的内存中副本的主密钥，直到重新启动该 BizTalk 服务器上的企业 SSO 服务。 如果企业 SSO 服务 BizTalk 服务器上重新启动，然后从内存中释放主密钥的缓存的副本，并 BizTalk 服务器必须能够联系以获取主密钥的另一个副本的主密钥服务器。 不重新启动 BizTalk 服务器上的企业 SSO 服务在组中如果主密钥服务器失败并且你希望 BizTalk 服务器继续处理文档。|  
|MSDTC|服务器。 如果 MSDTC 失败，则将失败，对于需要事务支持服务器上的任何组件。 <br/>**注意：** 因为 SQL Server 和主密钥服务器依赖于 MSDTC 事务支持，如果 SQL server 或主密钥服务器上的 MSDTC 失败，故障的范围将成为系统范围。 在运行时操作期间与 SQL Server 和主密钥服务器通信时，BizTalk Server 需要事务的支持。|  
|BizTalk 主机实例|服务器。 存放在一个 BizTalk 主机实例的任何组件将不能参与文档处理，如果主机实例失败。|  
|Microsoft 消息队列 (MSMQ)|服务器。 如果 MSMQ 失败然后依赖于 MSMQ 服务，诸如 MSMQ 适配器的任何文档处理将暂停服务器上。|  
|文件系统|服务器。 如果文件系统失败然后依赖于文件系统中，诸如文件适配器的任何文档处理将暂停服务器上。|  
  
 若要能够更好地管理高可用的 BizTalk Server 系统，你必须 BizTalk 堆栈更好地理解： Windows Server、 DC （DNS、 DHCP）、 BizTalk Server、 SQL Server、 IIS 服务器、 文件服务器、 MSMQ 服务器、 外部应用程序。 本部分重点介绍 BizTalk Server 和依赖的 SQL Server 计算机的高可用性。  
  
## <a name="biztalk-server-high-availability-examples"></a>BizTalk Server 高可用性示例  
 提供通过向外扩展的层的主机的高可用性的示例方案 Microsoft BizTalk Server 中，请参阅[示例 BizTalk Server 高可用性方案](../core/sample-biztalk-server-high-availability-scenarios.md)。
  
## <a name="see-also"></a>另请参阅  
 [BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [数据库的高可用性](../technical-guides/high-availability-for-databases.md)   
 [主密钥服务器的高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [清单：提供高可用性灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)