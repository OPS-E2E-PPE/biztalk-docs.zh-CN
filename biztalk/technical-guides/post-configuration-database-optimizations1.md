---
title: 配置后数据库 Optimizations1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 763b5358-97ed-4ada-8318-0ad07388ba89
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e89da931e7f7a007734d69dfec8921556982ec24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975078"
---
# <a name="post-configuration-database-optimizations"></a>配置后数据库优化
除了遵循中的建议，还[预配置数据库优化](../technical-guides/post-configuration-database-optimizations1.md)，应遵循的几个步骤以优化 SQL Server 上的 BizTalk Server 数据库性能*后*安装 BizTalk Server 和 BizTalk Server 数据库已配置。 本主题提供了一系列这些优化。  
  
## <a name="pre-allocate-space-for-biztalk-server-databases-and-define-auto-growth-settings-for-biztalk-server-databases-to-a-fixed-value-instead-of-a-percentage-value"></a>预分配空间的 BizTalk Server 数据库和为固定值而不是百分比值定义 BizTalk Server 数据库的自动增长设置  
  
-   SQL Server 数据库自动增长是阻塞操作，会影响 BizTalk Server 数据库性能。 因此务必要分配足够的空间用于 BizTalk Server 数据库预先以最大程度减少数据库自动增长的匹配项。  
  
-   应将数据库自动增长设置为固定数量的兆字节而不是百分比 (指定文件的增长**兆字节中**)。 这应完成因此发生自动增长时，它会以测量方式，从而减少了过多的数据库增长的可能性。 增长增量应通常不能大于 100 MB （对于大型文件）、 （适用于中型文件），10 MB 或 1 MB （对于小文件）。  
  
-   SQL Server 会增加文件的大小，新的空间必须首先初始化之前可以使用它。 这是涉及使用空页填充新的空间的阻塞操作。 运行 Windows Server 2003 或更高版本的 SQL Server 2005 支持"即时文件初始化"。 这可以大大减少文件增长操作的性能影响。 详细信息，请参阅"数据库文件初始化"上的 SQL Server 2008 文档中[ http://go.microsoft.com/fwlink/?LinkId=132063 ](http://go.microsoft.com/fwlink/?LinkId=132063)。 本主题提供用于启用即时文件初始化步骤。  
  
## <a name="move-the-backup-biztalk-server-output-directory-to-a-dedicated-lun"></a>将备份 BizTalk Server 输出目录移动到的专用 LUN  
 将备份 BizTalk Server （完全安装选项和日志备份） 输出目录移至专用 LUN，编辑步骤 1 和 2 （插入新的输出路径） 的备份 BizTalk Server [BizTalkMgmtDb] 作业。 正在读取移动到的专用 LUN 的备份 BizTalk Server 输出目录将减少磁盘 I/O 争用，运行时，该作业是通过写入到非作业所在的磁盘。  
  
## <a name="verify-the-biztalk-server-sql-agent-jobs-are-running"></a>验证 BizTalk Server SQL 代理作业正在运行  
 BizTalk Server 包含多个执行重要功能，以使服务器正常操作和运行的 SQL Server 代理作业。 应监视这些作业的运行状况，并确保它们无错运行。 BizTalk Server 中的性能问题的最常见原因之一是 BizTalk Server SQL 代理作业不运行，这又可能导致 MessageBox 和跟踪数据库增长未选中状态。 请按照以下步骤来确保 BizTalk Server SQL 代理作业运行正常操作：  
  
 BizTalk Server 中的性能问题的最常见原因之一是 BizTalk Server SQL 代理作业不运行，这又可能导致 MessageBox 和跟踪数据库增长未选中状态。 请按照以下步骤来确保 BizTalk Server SQL 代理作业运行正常操作：  
  
-   **验证 SQL Server 代理服务是否正在运行**。  
  
-   **验证 BizTalk server 安装的 SQL Server 代理作业是否已启用并成功运行**。  
  
     BizTalk Server SQL Server 代理作业至关重要 — 如果它们未运行，随着时间的推移会降低系统性能。  
  
-   **验证 BizTalk Server SQL Server 代理作业完成及时**。  
  
     设置 Microsoft Operations Manager (MOM) 2005年或 Microsoft System Center Operations Manager 2007，监视作业。  
  
     应注意的特定于某些作业的计划：  
  
    -   默认情况下，MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业会连续运行。 监视软件，应考虑此计划，并生成警告。  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb 作业未启用或未计划，但它由 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业启动每隔 10 秒。 因此，此作业不应启用、 计划，或手动启动。  
  
-   **验证 SQL Server 代理服务的启动类型是否正确配置**。  
  
     验证 SQL Server 代理服务配置与**启动类型**的**自动**除非 SQL Server 代理服务配置为在 Windows Server 群集上群集资源。 如果 SQL Server 代理服务配置为群集资源，则应配置**启动类型**作为**手动**因为该服务将由群集服务。  
  
## <a name="configure-purging-and-archiving-of-tracking-data"></a>配置清除和存档的跟踪数据  
 请按照下列步骤以确保清除和存档的跟踪数据已正确配置：  
  
-   请确保 SQL 代理作业"DTA 清除和存档"是正确配置和启用，并且已成功完成。 详细信息，请参阅"如何向配置 DTA 清除和存档作业"中的 BizTalk Server 文档[ http://go.microsoft.com/fwlink/?LinkId=104908 ](http://go.microsoft.com/fwlink/?LinkId=104908)。  
  
-   确保作业可以快速生成传入跟踪数据清除跟踪数据。 有关详细信息，请参阅"测量最大可承受跟踪吞吐量"BizTalk Server 2006 R2 文档在[ http://go.microsoft.com/fwlink/?LinkId=104909 ](http://go.microsoft.com/fwlink/?LinkId=104909)。  
  
-   查看软清除和硬清除参数，以确保保持最佳的时间长度的数据。 有关详细信息，请参阅"存档和清除 BizTalk 跟踪数据库的"BizTalk Server 文档在[ http://go.microsoft.com/fwlink/?LinkId=101585 ](http://go.microsoft.com/fwlink/?LinkId=101585)。  
  
-   如果您只需清除旧数据，则不需要将其存档第一次，更改 SQL 代理作业来调用存储的过程"dtasp_PurgeTrackingDatabase。" 有关详细信息，请参阅"如何清除数据从 BizTalk 跟踪数据库的"BizTalk Server 文档在[ http://go.microsoft.com/fwlink/?LinkId=101584 ](http://go.microsoft.com/fwlink/?LinkId=101584)。  
  
## <a name="monitor-and-reduce-dtc-log-file-disk-io-contention"></a>监视和降低 DTC 日志文件磁盘 I/O 争用  
 大型事务环境中的磁盘 I/O 瓶颈可能会导致 Microsoft 分布式事务处理协调器 (MS DTC) 日志文件。 使用支持事务，例如 SQL Server、 MSMQ 或 MQSeries，或在多 MessageBox 环境中的适配器时，也是如此。 事务性适配器使用 DTC 事务，多 MessageBox 环境进行广泛使用 DTC 事务。 若要确保 DTC 日志文件不会成为磁盘 I/O 瓶颈，则应该监视磁盘用于 DTC 日志文件所在的 SQL Server 数据库服务器的磁盘 I/O 使用情况。 如果磁盘用于 DTC 日志文件所在的位置的磁盘 I/O 使用情况变得多余请考虑将 DTC 日志文件移到更快的磁盘。 在 SQL Server 已群集的环境中，这是不需考虑尽可能因为日志文件将可能会具有多个心轴的快速 SAN 驱动器的共享驱动器。 不过仍应监视磁盘 I/O 使用情况，因为它可以成为非群集环境中的瓶颈或 DTC 日志文件时，与其他占用大量磁盘的文件的共享磁盘上。  
  
 若要确保 DTC 日志文件不会成为磁盘 I/O 瓶颈，则应该监视磁盘用于 DTC 日志文件所在的 SQL Server 数据库服务器的磁盘 I/O 使用情况。 如果磁盘用于 DTC 日志文件所在的位置的磁盘 I/O 使用情况变得过多，请考虑将 DTC 日志文件移到更快的磁盘。  
  
 在 SQL Server 已群集的环境中，这是不需考虑尽可能因为日志文件将可能会具有多个心轴的快速 SAN 驱动器的共享驱动器。 不过仍应监视磁盘 I/O 使用情况，因为它可以成为非群集环境中的瓶颈或 DTC 日志文件时，与其他占用大量磁盘的文件的共享磁盘上。  
  
## <a name="separate-the-messagebox-and-tracking-databases"></a>单独的 MessageBox 和跟踪数据库  
 由于 BizTalk MessageBox 和 BizTalk 跟踪数据库是最活跃，因此我们建议将数据文件和事务日志文件放置在专用的驱动器，以减少磁盘 I/O 争用问题的可能性上的每个。 例如，您将需要四个驱动器的 MessageBox 和 BizTalk 跟踪数据库文件、 一个驱动器的以下各项：  
  
- MessageBox 数据文件  
  
- MessageBox 事务日志文件  
  
- BizTalk 跟踪 (DTA) 数据文件  
  
- BizTalk 跟踪 (DTA) 事务日志文件  
  
  将 BizTalk MessageBox 和 BizTalk 跟踪数据库和分离数据库文件和事务日志文件在不同的物理磁盘上被视为减少磁盘 I/O 争用的最佳实践。 请尝试以尽可能跨任意数量的物理心轴磁盘 I/O。 你还可以通过将 BizTalk 跟踪数据库放置在专用的 SQL Server 上减少磁盘 I/O 争用，但是，仍应遵循上面的实践方面并将数据文件和事务日志文件。  
  
## <a name="optimize-filegroups-for-the-biztalk-server-databases"></a>优化 BizTalk Server 数据库的文件组  
 按照中的步骤[优化文件组 Databases1](../technical-guides/optimizing-filegroups-for-the-databases1.md)和"BizTalk Server 数据库优化"白皮书，网址[ http://go.microsoft.com/fwlink/?LinkId=101578 ](http://go.microsoft.com/fwlink/?LinkId=101578)为 BizTalk 创建其他文件组和文件服务器数据库。 这会极大地增加从单个磁盘配置 BizTalk Server 数据库的性能。