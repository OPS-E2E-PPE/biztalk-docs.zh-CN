---
title: 避免瓶颈的最佳做法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81da2e31-dce0-43fb-841f-e65ff99e80a7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07145b9b46f1527f970ec27511827d385468fcaa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401266"
---
# <a name="best-practices-for-avoiding-bottlenecks"></a>避免瓶颈的最佳实践
尽管中的默认设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供最佳性能的许多硬件和软件配置中，在某些情况下它可能会有所帮助修改这些设置或部署配置。 配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参考以下性能指南：  
  
-   若要避免资源争用，隔离接收业务流程和发送在单独主机上。 可进一步减少争用，隔离从其他主机的跟踪服务。  
  
-   如果运行 BizTalk Server 的计算机上处理的 CPU 是瓶颈，增加运行 BizTalk Server 包括更多的 Cpu 或升级到更快的 Cpu 的计算机。  
  
## <a name="sql-server-guidelines"></a>SQL Server 的指导原则  
 配置与 Microsoft SQL Server 时，请考虑以下性能指南[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
-   只要可能，请使用 SQL Server 使用较快的磁盘子系统。 使用独立磁盘类型 10 的冗余阵列 (RAID10 0 + 1) 或带备份电源的存储区域网络 (SAN)。  
  
-   隔离从 BizTalk 跟踪数据库 (BizTalkDTADb) 的独立服务器上每个 MessageBox 数据库。 对于较小的部署在 CPU 资源可用，它可能足以隔离从 BizTalk 跟踪数据库的单独物理磁盘上的 MessageBox 数据库。  
  
-   主 MessageBox 数据库可能是瓶颈，因为 CPU 处理器能力达到饱和或磁盘操作 （平均磁盘队列长度） 的延迟。 如果 CPU 处理瓶颈，请到主 MessageBox 添加 CPU 处理器。 否则，尝试在主 MessageBox 数据库上禁用发布。 这种方式主 MessageBox 数据库可以更多有效地处理消息路由到其他 MessageBox 数据库。 使用多个 MessageBox 数据库时，若要禁用的发布选项才有效。  
  
-   如果磁盘操作是瓶颈，将 BizTalk 跟踪数据库移到专用的 SQL Server 计算机和/或专用的磁盘。 如果主 MessageBox 数据库上的 CPU 处理能力和磁盘操作均不是瓶颈，您可以在相同的 SQL Server 计算机，以利用现有硬件上创建新的 MessageBox 数据库。  
  
-   请遵循中的建议[优化文件组的数据库 2](../technical-guides/optimizing-filegroups-for-the-databases2.md)隔离事务和数据日志文件的 MessageBox 数据库和 BizTalk 跟踪数据库到单独的物理磁盘上。  
  
-   为数据和日志文件分配足够的存储空间。 否则 SQL Server 将自动使用所有保存的日志文件在磁盘上的可用空间。 日志文件的初始大小取决于你的方案中的特定要求。 估计根据测试结果，在部署中的平均文件大小并实施解决方案前扩展存储空间。  
  
-   对于高磁盘使用数据库，如 MessageBox、 运行状况和活动跟踪 (HAT) 和业务活动监视 (BAM) 分配足够的存储空间。 如果您的解决方案使用 BizTalk 框架消息传送协议，请为 BizTalk 配置数据库 (BizTalkMgmtDb) 分配足够的存储空间。  
  
-   具体取决于业务需求，如数据保留期，并在你的方案中处理的数据量"DTA 存档和清除"SQL Server 代理作业 HAT 跟踪在数据库上配置，以便 BizTalk 跟踪数据库变得不太大。 此数据库的增长会降低性能，因为达到数据库的全部容量限制数据插入操作的速率。 当一个 BizTalk 跟踪数据库支持多个 MessageBox 数据库时，也是如此。  
  
-   纵向扩展它们是否瓶颈承载 MessageBox 和 BizTalk 跟踪数据库的服务器。 可以通过添加 Cpu、 添加内存、 升级到更快的 Cpu 和使用高速专用的磁盘来纵向硬件。  
  
-   将 TempDB 文件拆分到多个文件可能会解决与 I/O 操作相关的性能问题。 一般原则是，创建一个文件数据文件，每个处理器和创建的所有文件都使用相同的大小。  
  
-   更改数据库自动增长设置为固定值如 100-150 MB。 默认情况下，数据库的增长速度配置为 10%，这可能会导致延迟增大更大的数据库时。  
  
-   SQL Server 内存应通过将最小服务器内存和最大服务器内存设置为相同的值设置为固定值。 一般情况下，分配到 SQL Server 的 75%的物理内存和保留操作系统和任何应用程序的其余部分的 25%。 如果这是专用的 SQL Server，可以减少量为最小操作系统保留 1 GB。  
  
## <a name="see-also"></a>请参阅  
 [查找并消除瓶颈](../technical-guides/finding-and-eliminating-bottlenecks.md)