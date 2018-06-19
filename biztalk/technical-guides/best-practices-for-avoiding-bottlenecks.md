---
title: 最佳做法，避免瓶颈 |Microsoft 文档
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
ms.openlocfilehash: 08f2291d6aa4d16c251a110bc6f94c6288dc5064
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299661"
---
# <a name="best-practices-for-avoiding-bottlenecks"></a>为避免瓶颈的最佳做法
虽然 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的默认设置可为许多硬件和软件配置提供最佳性能，但在某些情况下修改这些设置或部署配置可能更为有利。 配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，请参考下列性能指南：  
  
-   若要防止资源争用，接收，业务流程，并在单独的主机上发送的隔离。 为了进一步将资源争用降到最低，请隔离来自其他主机的跟踪服务。  
  
-   如果运行 BizTalk Server 的计算机上的 CPU 处理是瓶颈，扩展运行 BizTalk Server 包括更多的 Cpu 或升级到更快的 Cpu 的计算机。  
  
## <a name="sql-server-guidelines"></a>SQL Server 指导原则  
 在使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置 Microsoft SQL Server 时，请参考以下性能指南：  
  
-   只要可能，请为 SQL Server 配置快速的磁盘子系统。 使用独立磁盘类型 10 的冗余阵列 (RAID10 0 + 1) 或存储区域网络 (SAN) 与备份的电源。  
  
-   隔离从 BizTalk 跟踪数据库 (BizTalkDTADb) 的独立服务器上每个 MessageBox 数据库。 对于较小的部署如果 CPU 资源可用，它可能不足以隔离 BizTalk 跟踪数据库中的单独物理磁盘上的 MessageBox 数据库。  
  
-   主 MessageBox 数据库可能是由于处理器产生的 CPU 饱和度或从磁盘操作 （平均磁盘队列长度） 的延迟的瓶颈。 如果 CPU 处理瓶颈，添加到主 MessageBox CPU 处理器。 如果没有，请尝试禁用 master MessageBox 数据库上的发布。 这种方式 master MessageBox 数据库可以更多有效地处理路由到其他 MessageBox 数据库的消息。 当使用多个 MessageBox 数据库时，该选项以禁用发布才有效。  
  
-   如果磁盘操作是瓶颈，移动到专用的 SQL Server 计算机和/或专用的磁盘 BizTalk 跟踪数据库。 如果主 MessageBox 数据库上的 CPU 处理和磁盘操作不是瓶颈，你可以在相同的 SQL Server 计算机，以便利用你现有的硬件上创建新的 MessageBox 数据库。  
  
-   请遵循中的建议[优化文件组 Databases2](../technical-guides/optimizing-filegroups-for-the-databases2.md)若要隔离的事务和数据的日志文件到单独的物理磁盘的 MessageBox 和 BizTalk 跟踪数据库。  
  
-   为数据和日志文件分配足够的存储空间。 否则 SQL Server 将自动使用所有可用空间的磁盘上保存的日志文件。 日志文件的初始大小取决于你的方案中的特定要求。 根据测试结果估计要部署的文件的平均大小，并在实施解决方案前扩展存储空间。  
  
-   为密集磁盘使用数据库，例如 MessageBox、 运行状况和活动跟踪 (HAT)，以及业务活动监视 (BAM) 分配足够的存储空间。 如果您的解决方案使用 BizTalk 框架消息协议，请为 BizTalk 配置数据库 (BizTalkMgmtDb) 分配足够的存储空间。  
  
-   根据业务需要如数据保持期，并在你的方案，处理的数据量配置的"DTA 存档和清除"SQL Server 代理作业上 HAT 跟踪数据库，BizTalk 跟踪数据库变得不太大。 此数据库的增长会降低性能，因为达到数据库的完整容量施加了限制上的数据插入操作的速率。 当一个 BizTalk 跟踪数据库支持多个 MessageBox 数据库时，也是如此。  
  
-   如果它们是瓶颈托管 MessageBox 和 BizTalk 跟踪数据库的服务器向上扩展。 你可以通过添加 Cpu、 添加内存，升级到更快的 Cpu，并使用高速的专用的磁盘扩展的硬件。  
  
-   跨多个文件拆分 TempDB 文件可能会解决与 I/O 操作相关的性能问题。 作为一般原则是，每个处理器的一个文件数据文件为创建和使用相同的大小创建的所有文件。  
  
-   更改数据库自动增长设置为固定值如 100 150 MB。 默认情况下，数据库增长配置为 10%，这可能导致延迟在增大更大的数据库。  
  
-   SQL Server 内存应通过将最小服务器内存和最大服务器内存设置为相同的值设置为固定值。 一般情况下，将 75%的物理内存分配给 SQL Server，并将操作系统和任何应用程序的其余部分的 25%。 如果这是专用的 SQL Server，你可以减少量为最小操作系统保留 1 GB。  
  
## <a name="see-also"></a>另请参阅  
 [查找并消除瓶颈](../technical-guides/finding-and-eliminating-bottlenecks.md)