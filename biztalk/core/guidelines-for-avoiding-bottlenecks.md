---
title: 避免瓶颈的准则 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 640ab399-b22d-4f71-b41d-ea8d778e064a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e78f637c2fd6919b4182f2a58b5f16fbd23f0170
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246509"
---
# <a name="guidelines-for-avoiding-bottlenecks"></a>避免瓶颈的准则
虽然 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的默认设置可为许多硬件和软件配置提供最佳性能，但在某些情况下修改这些设置或部署配置可能更为有利。 配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，请参考下列性能指南：  
  
-   为阻止资源争用，应将接收、业务流程和发送隔离到不同的主机上。 为了进一步将资源争用降到最低，请隔离来自其他主机的跟踪服务。  
  
-   如果瓶颈为 BizTalk Server 的 CPU 处理能力，请通过增加 CPU 数量或升级到更快的 CPU 来提升 BizTalk Server 的性能。  
  
## <a name="sql-server-guidelines"></a>SQL Server 指导原则  
 在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置 Microsoft SQL Server 时，请参考以下性能指南：  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库应配置为在尽可能的专用 SQL Server 实例上运行。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库密集型应用程序，因此分离[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和承载 SQL Server 计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库将提高性能，应予以考虑在生产中的最佳实践[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
-   只要可能，请为 SQL Server 配置快速的磁盘子系统。 使用带备份电源的独立磁盘冗余阵列类型 5 (RAID5/10) 或存储区域网络 (SAN)。  
  
-   定期使用 SQL Server 灾难恢复进程备份您的数据库。 BizTalk Server 服务将自动从 SQL Server 连接故障中恢复。  
  
-   将所有 MessageBox 隔离到与 BizTalk 跟踪数据库 (BizTalkDTADb) 所在的服务器之外的其他服务器上。 对于更小型的部署，在 CPU 资源可用的情况下，可能可以将 MessageBox 隔离到 BizTalkDTADb 数据库所在物理磁盘之外的其他磁盘上。  
  
-   主 MessageBox 可能会因 CPU 处理器的处理能力达到饱和或磁盘操作的延迟（平均磁盘队列长度）而成为瓶颈。 如果瓶颈为 CPU 处理能力，请为主 MessageBox 添加 CPU 处理器。 如果不尝试禁用发布上 Master 消息框，的这样 Master MessageBox 可以更有效地处理路由到其他 MessageBox 数据库的消息。  
  
-   如果瓶颈为磁盘操作，请将 BizTalkDTADb 数据库移至专用的 SQL Server 计算机和/或专用磁盘。 如果主 MessageBox 中的 CPU 处理能力和磁盘操作均不是瓶颈，则您可在同一 SQL Server 计算机上创建新的 MessageBox 数据库，以充分利用您现有的硬件。  
  
-   按照 SQL Server 最佳实践将 MessageBox 和 BizTalkDTADb 数据库的事务和数据日志文件隔离到不同的物理磁盘上。  
  
-   为数据和日志文件分配足够的存储空间，否则 SQL Server 会自动将保存日志文件的磁盘中的所有可用空间全部用完。 日志文件的初始大小取决于您特殊情况的特定要求。 根据测试结果估计要部署的文件的平均大小，并在实施解决方案前扩展存储空间。  
  
-   为磁盘空间需求量大的数据库分配足够的存储空间，这些数据库有 MessageBox 数据库、跟踪数据库、业务活动监视 (BAM) 数据库。 如果您的解决方案使用 BizTalk 框架消息协议，请为 BizTalk 配置数据库 (BizTalkMgmtDb) 分配足够的存储空间。  
  
-   根据业务需求 [数据保留期] 和特定情况下要处理的数据量，配置跟踪数据库的存档/清除作业，以便 BizTalkDTADb 数据库不会增长得过于庞大。 此数据库的增长会降低性能（尤其一个 BizTalkDTADb 数据库支持多个 MessageBox 的情况），这是因为数据库中存满数据后，插入数据的速率会受到限制。  
  
-   如果 MessageBox 和 BizTalkDTADb 数据库所在的服务器为瓶颈，请提升这些服务器的性能。 您可通过增加 CPU 和内存、升级到更快的 CPU 和使用高速专用磁盘来提升硬件性能。