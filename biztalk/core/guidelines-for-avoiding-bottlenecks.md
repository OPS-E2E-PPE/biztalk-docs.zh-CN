---
title: 避免瓶颈的准则 |Microsoft Docs
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
ms.openlocfilehash: db480df2d47fdc03b1719ecfb17fdbb8f23eea41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387565"
---
# <a name="guidelines-for-avoiding-bottlenecks"></a>避免瓶颈的准则
尽管中的默认设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供最佳性能的许多硬件和软件配置中，在某些情况下它可能会有所帮助修改这些设置或部署配置。 配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参考以下性能指南：  

-   若要避免资源争用，隔离接收、 业务流程，并将发送到单独的主机上。 可进一步减少争用，隔离从其他主机的跟踪服务。  

-   如果处理 BizTalk Server 上的 CPU 是瓶颈，纵向扩展 BizTalk Server 通过包括更多的 Cpu 或升级到更快的 Cpu。  

## <a name="sql-server-guidelines"></a>SQL Server 的指导原则  
 配置与 Microsoft SQL Server 时，请考虑以下性能指南[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应将数据库配置为只要有可能的专用 SQL Server 实例上运行。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 是数据库密集型应用程序，因此，分离[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和承载的 SQL Server 计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库会提高性能和最佳做法在生产环境中的应考虑[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  

- 只要可能，请使用 SQL Server 使用较快的磁盘子系统。 使用带备份电源的独立磁盘类型 5 (RAID5/10) 的冗余阵列或存储区域网络 (SAN)。  

- 使用 SQL Server 灾难恢复过程以定期备份您的数据库。 从 SQL Server 连接故障自动恢复 BizTalk Server 服务。  

- 隔离到 BizTalk 跟踪数据库 (BizTalkDTADb) 中的单独服务器上的每个消息框。 对于较小的部署在 CPU 资源可用，隔离到 BizTalkDTADb 数据库中的单独物理磁盘上的消息框可能足以。  

- 主 MessageBox 可能是瓶颈，因为 CPU 处理器能力达到饱和或磁盘操作 （平均磁盘队列长度） 的延迟。 如果 CPU 处理瓶颈，为主 messagebox 添加 CPU 处理器。 否则请尝试禁用这种方式，主 MessageBox 可更加高效地将消息路由到其他 MessageBox 数据库的主 MessageBox 上的发布。  

- 如果磁盘操作是瓶颈，BizTalkDTADb 数据库移到专用的 SQL Server 计算机和/或专用的磁盘。 如果主消息框上的 CPU 处理能力和磁盘操作均不是瓶颈，您可以在相同的 SQL Server 计算机，以利用现有硬件上创建新的 MessageBox 数据库。  

- 遵循 SQL Server 最佳做法来隔离到单独的物理磁盘上的 MessageBox 和 BizTalkDTADb 数据库的事务和数据日志文件。  

- 为数据和日志文件; 分配足够的存储空间否则 SQL Server 将自动使用所有这些日志文件保存在磁盘上的可用空间。 日志文件的初始大小将取决于您特殊情况的特定要求。 估计根据测试结果，在部署中的平均文件大小并实施解决方案前扩展存储空间。  

- 对于高磁盘使用情况的数据库，如 MessageBox、 跟踪和业务活动监视 (BAM) 数据库分配足够的存储空间。 如果您的解决方案使用 BizTalk 框架消息传送协议，请为 BizTalk 配置数据库 (BizTalkMgmtDb) 分配足够的存储空间。  

- 根据业务需求 [数据保留期] 和处理特定方案中的数据量，存档/清除作业配置跟踪数据库上，以便 BizTalkDTADb 数据库变得不太大。 （尤其是在一个 BizTalkDTADb 数据库支持多个消息框） 实施数据插入操作的速率限制到达数据库的全部容量，因为此数据库的增长会降低性能。  

- 纵向扩展它们是否瓶颈承载 MessageBox 和 BizTalkDTADb 数据库的服务器。 可以通过添加 Cpu、 添加内存、 升级到更快的 Cpu 和使用高速专用的磁盘来纵向硬件。
