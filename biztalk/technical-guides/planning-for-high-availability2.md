---
title: 规划高 Availability2 |Microsoft Docs
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
ms.openlocfilehash: 4e804960e71990d5e179a8720a827f1081546c14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242573"
---
# <a name="planning-for-high-availability"></a>规划高可用性
BizTalk Server 的高可用性着重于恢复可能会中断 BizTalk Server 部署中的可用性的功能组件。  
  
 若要演示 BizTalk Server 中的高可用性，必须可以导致失败，并衡量在恢复时的产品的效率。 高度可用的 BizTalk Server 部署创建错误和失败对外部应用程序和系统透明，并确保所有服务都继续正常工作中断降至最低。  
  
 设计提供高可用性的 BizTalk Server 部署需要在应用程序集成或业务流程集成方案中实现每个功能组件所涉及的冗余。 BizTalk Server 从概念上讲分隔中的数据来简化这些方案的实现*主机*处理的数据。 一个*主机*是 BizTalk 的逻辑容器项，如业务流程、 发送处理程序，以及接收处理程序。 您创建*托管实例*并将其分配到主机。 主机实例是主机的特定服务器上的物理表示形式。 它是名为 BTSNTSvc.exe BizTalk Server 服务进程或另一个进程，例如，IIS 进程。 因此在 BizTalk Server 涉及运行多个提供高可用性*托管实例*和群集 BizTalk Server 数据库中，按如下所示：  
  
- **为 BizTalk 主机的体系结构**。 BizTalk Server 允许您分隔不同的主机和运行多个主机实例以提供高可用性，如接收消息、 处理业务流程和发送消息的关键功能。 这些主机不需要任何其他群集或负载平衡机制，因为 BizTalk Server 会自动将工作负荷分散到主机实例的多台计算机。 但是，承载为 HTTP 和 SOAP 适配器需要负载平衡机制如网络负载平衡 (NLB) 以提供高可用性，而运行 ftp 接收处理程序主机，MSMQ、 POP3、 SQL 和 SAP 需要运行的接收处理程序聚类分析机制，用于提供高可用性。  
  
  > [!NOTE]  
  >  必须始终群集 SAP 接收适配器以容纳两阶段提交方案。  
  
- **BizTalk Server 数据库的体系结构**。 在主动/被动服务器群集配置中配置两个或多个 SQL Server 数据库计算机通常包含 BizTalk Server 数据库的高可用性配置。 这些计算机共享公共的磁盘资源 (例如 RAID 1 + 0 SCSI 磁盘阵列或存储区域网络) 并使用 Windows 故障转移群集提供备份冗余和容错功能。  
  
  至关重要的高可用性的另一个 BizTalk 功能组件是主密钥服务器。 BizTalk Server 依赖于此服务，以获取加密密钥。  
  
  本部分提供有关如何解决每个类别中的高可用性的信息。 由于 BizTalk Server 高可用性解决方案基于 Windows 和 SQL Server，因此请确保配置的 BizTalk Server 的主机前，具有高可用性部署这些产品。 以下链接包括有关为这些基础产品提供高可用性的信息：  
  
- **高可用性解决方案 (SQL Server)] (https://docs.microsoft.com/sql/sql-server/failover-clusters/high-availability-solutions-sql-server)**  
  
- **[故障转移群集 Windows Server 中](https://docs.microsoft.com/windows-server/failover-clustering/failover-clustering-overview)**
  
## <a name="understanding-the-impact-of-a-component-failure"></a>了解在组件发生故障的影响  
 下表列出的组件和 BizTalk Server 环境与对 BizTalk Server 环境的影响的依赖项，如果组件或依存关系失败。 决定是否群集组件或依存关系时，应考虑潜在故障的范围。  
  
|组件或依存关系|故障范围|  
|-----------------------------|----------------------|  
|SQL Server|系统范围。 如果 SQL Server 失败，然后 BizTalk Server 将不能处理的文档。|  
|主密钥服务器|系统范围。 如果主密钥服务器发生故障，然后 BizTalk Server 将不能处理的文档。 <br/>**注意：** 如果主密钥服务器失败，BizTalk 组中的每个 BizTalk server 将继续使用主密钥的缓存的内存中副本，直到重新启动 BizTalk server 上的企业 SSO 服务。 如果 BizTalk server 上重新启动企业 SSO 服务，然后从内存中释放主密钥的缓存的副本和 BizTalk 服务器必须能够联系主密钥服务器以获取主密钥的另一个副本。 不重新启动 BizTalk 服务器上的企业 SSO 服务在组中如果主密钥服务器失败，并且你希望 BizTalk server 以继续处理文档。|  
|MSDTC|服务器。 如果 MSDTC 失败需要事务的支持的服务器上的任何组件将失败。 <br/>**注意：** 因为 SQL Server 和主密钥服务器依赖于 MSDTC 事务支持，故障的范围将成为系统范围内，如果 SQL server 或主密钥服务器上的 MSDTC 失败。 在运行时操作期间，与 SQL Server 和主密钥服务器进行通信时，BizTalk Server 需要事务支持。|  
|BizTalk 主机实例|服务器。 驻留在 BizTalk 主机实例中的任何组件将无法参与文档处理，如果主机实例失败。|  
|Microsoft 消息队列 (MSMQ)|服务器。 如果 MSMQ 失败然后是依赖于 MSMQ 服务，如 MSMQ 适配器的任何文档处理将停止在服务器上。|  
|文件系统|服务器。 如果文件系统出现故障则取决于文件系统，如文件适配器中，任何文档处理将停止在服务器上。|  
  
 若要能够更好地管理高度可用的 BizTalk Server 系统，必须具有 BizTalk 堆栈更好地理解：Windows Server、 DC （DNS、 DHCP）、 BizTalk Server、 SQL Server、 IIS 服务器、 文件服务器、 MSMQ 服务器、 外部应用程序。 本部分重点介绍 BizTalk Server 和相关的 SQL Server 计算机的高可用性。  
  
## <a name="biztalk-server-high-availability-examples"></a>BizTalk Server 高可用性示例  
 通过主机的各层进行扩展提供高可用性的示例方案在 Microsoft BizTalk Server 中，请参阅[BizTalk Server 高可用性示例方案](../core/sample-biztalk-server-high-availability-scenarios.md)。
  
## <a name="see-also"></a>请参阅  
 [BizTalk 主机的的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)   
 [数据库的高可用性](../technical-guides/high-availability-for-databases.md)   
 [主密钥服务器的高可用性](../technical-guides/high-availability-for-the-master-secret-server.md)   
 [清单：提供高可用性灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)