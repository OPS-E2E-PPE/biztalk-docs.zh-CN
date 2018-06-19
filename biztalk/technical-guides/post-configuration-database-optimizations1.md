---
title: 后配置数据库 Optimizations1 |Microsoft 文档
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
ms.openlocfilehash: eeb1c5c8bbb93bce5eb69462585c2da69d587dad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302325"
---
# <a name="post-configuration-database-optimizations"></a>后配置数据库优化
除了按照中的建议之外[预配置数据库优化](../technical-guides/post-configuration-database-optimizations1.md)，应遵循的几个步骤来优化 SQL Server 上的 BizTalk Server 数据库性能*后*BizTalk Server 已安装且已被配置 BizTalk Server 数据库。 本主题提供这些优化的列表。  
  
## <a name="pre-allocate-space-for-biztalk-server-databases-and-define-auto-growth-settings-for-biztalk-server-databases-to-a-fixed-value-instead-of-a-percentage-value"></a>预分配空间的 BizTalk Server 数据库和 BizTalk Server 数据库的自动增长设置定义为固定值而不是百分比值  
  
-   SQL Server 数据库自动增长是会影响 BizTalk Server 数据库性能停滞操作。 因此务必分配足够的空间提前要最大程度减少数据库自动增长的匹配项的 BizTalk Server 数据库。  
  
-   数据库自动增长应设置为固定数量的兆字节而不是百分比 (指定文件增长等手段**中兆字节为单位**)。 这应执行操作，以便如果自动增长发生，它会以以测得的方式，从而减少了过多的数据库增长的可能性。 增长增量通常应是不大于 100 MB （适用于大型文件）、 10 MB （适用于中型文件） 或 （适用于小文件） 的 1 MB。  
  
-   当 SQL Server 会增加文件的大小时，新的空间必须首先初始化然后才能使用。 这是涉及使用空页填充新的空间的阻止操作。 运行 Windows Server 2003 或更高版本的 SQL Server 2005 支持"即时文件初始化。" 这可以极大地降低文件增长操作的性能影响。 有关详细信息，请参阅"数据库文件初始化"SQL Server 2008 文档在[http://go.microsoft.com/fwlink/?LinkId=132063](http://go.microsoft.com/fwlink/?LinkId=132063)。 本主题提供用于启用即时文件初始化步骤。  
  
## <a name="move-the-backup-biztalk-server-output-directory-to-a-dedicated-lun"></a>将备份 BizTalk Server 输出目录移动到的专用 LUN  
 将备份的 BizTalk Server （完全安装选项和日志备份） 输出目录移动到专用 LUN，编辑步骤 1 和 2 （插入新的输出路径） 的备份的 BizTalk Server [BizTalkMgmtDb] 作业。 从中移动到的专用 LUN 的备份 BizTalk Server 输出目录将减少磁盘 I/O 争用，通过编写到另一个磁盘与作业运行作业时进行读取。  
  
## <a name="verify-the-biztalk-server-sql-agent-jobs-are-running"></a>验证正在运行 BizTalk Server SQL 代理作业  
 BizTalk Server 包括执行重要的功能使你的服务器操作和正常运行的多个 SQL Server 代理作业。 你应监视这些作业的运行状况，并确保它们正在运行且未发生错误。 BizTalk Server 中的性能问题的最常见原因之一是 BizTalk Server SQL 代理作业不运行，这反过来会导致 MessageBox 和跟踪数据库增长未选中状态。 请按照以下步骤来确保 BizTalk 服务器 SQL 代理作业运行正常操作：  
  
 BizTalk Server 中的性能问题的最常见原因之一是 BizTalk Server SQL 代理作业不运行，这反过来会导致 MessageBox 和跟踪数据库增长未选中状态。 请按照以下步骤来确保 BizTalk 服务器 SQL 代理作业运行正常操作：  
  
-   **验证 SQL Server 代理服务是否正在运行**。  
  
-   **验证是否启用了由 BizTalk 服务器安装的 SQL Server 代理作业和成功运行**。  
  
     BizTalk Server SQL Server 代理作业至关重要 — 如果它们未运行，随着时间的推移将降低系统性能。  
  
-   **验证是否及时完成 BizTalk Server SQL Server 代理作业**。  
  
     设置 Microsoft Operations Manager (MOM) 2005年或 Microsoft System Center Operations Manager 2007，以监视作业。  
  
     你应注意的特定于某些作业的计划：  
  
    -   默认情况下，MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业是连续运行。 监视软件应考虑此计划，并且不生成警告。  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb 作业未启用或计划，但它会启动 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业每隔 10 秒。 因此，此作业不应启用、 计划，或手动启动。  
  
-   **验证 SQL Server 代理服务的启动类型已正确配置**。  
  
     验证使用配置的 SQL Server 代理服务**启动类型**的**自动**除非的 SQL Server 代理服务配置为在 Windows Server 群集上的群集资源。 如果 SQL Server 代理服务配置为群集资源，则应配置**启动类型**作为**手动**因为该服务将由群集服务。  
  
## <a name="configure-purging-and-archiving-of-tracking-data"></a>配置清除和存档的跟踪数据  
 请按照下列步骤以确保清除和归档的跟踪数据已正确配置：  
  
-   确保 SQL 代理作业"DTA 清除和存档"正确配置和启用，并且已成功完成。 有关详细信息，请参阅"如何为配置 DTA 清除和存档作业"在 BizTalk Server 文档中[http://go.microsoft.com/fwlink/?LinkId=104908](http://go.microsoft.com/fwlink/?LinkId=104908)。  
  
-   确保作业能够快速生成传入的跟踪数据清除的跟踪数据。 有关详细信息，请参阅"测量最大可持续跟踪吞吐量"BizTalk Server 2006 R2 文档在[http://go.microsoft.com/fwlink/?LinkId=104909](http://go.microsoft.com/fwlink/?LinkId=104909)。  
  
-   查看软清除和硬清除参数，以确保你保存数据的最佳总时间。 有关详细信息，请参阅"存档和清除 BizTalk 跟踪数据库的"在 BizTalk Server 文档中[http://go.microsoft.com/fwlink/?LinkId=101585](http://go.microsoft.com/fwlink/?LinkId=101585)。  
  
-   如果你只需以清除旧数据并不需要对其进行存档第一次，更改 SQL 代理作业调用存储的过程"dtasp_PurgeTrackingDatabase。" 有关详细信息，请参阅"如何为清除数据从 BizTalk 跟踪数据库的"在 BizTalk Server 文档中[http://go.microsoft.com/fwlink/?LinkId=101584](http://go.microsoft.com/fwlink/?LinkId=101584)。  
  
## <a name="monitor-and-reduce-dtc-log-file-disk-io-contention"></a>监视和减少 DTC 日志文件磁盘 I/O 争用  
 Microsoft 分布式事务处理协调器 (MS DTC) 日志文件可以成为大型事务环境中的磁盘 I/O 瓶颈。 这在使用支持事务，如 SQL Server、 MSMQ 或 MQSeries，或在多 MessageBox 环境中的适配器时尤其如此。 事务的适配器使用 DTC 事务，以及多 MessageBox 环境广泛利用 DTC 事务。 若要确保 DTC 日志文件不会成为磁盘 I/O 瓶颈，则应该监视磁盘 DTC 日志文件驻留在 SQL Server 数据库服务器上的磁盘 I/O 使用情况。 如果磁盘 DTC 日志文件所在的磁盘 I/O 使用情况变得过多请考虑将 DTC 日志文件移到更快的磁盘。 在环境中在群集 SQL Server，这是不尽可能考虑因为日志文件已将共享的驱动器，可能会具有多个轴的快速 SAN 驱动器上。 不过仍应监视磁盘 I/O 使用情况，因为它可能成为非群集环境中的瓶颈或 DTC 日志文件时，与其他占用大量磁盘的文件的共享磁盘上。  
  
 若要确保 DTC 日志文件不会成为磁盘 I/O 瓶颈，则应该监视磁盘 DTC 日志文件驻留在 SQL Server 数据库服务器上的磁盘 I/O 使用情况。 如果磁盘 DTC 日志文件所在的磁盘 I/O 使用情况变得过多，请考虑将 DTC 日志文件移到更快的磁盘。  
  
 在环境中在群集 SQL Server，这是不尽可能考虑因为日志文件已将共享的驱动器，可能会具有多个轴的快速 SAN 驱动器上。 不过仍应监视磁盘 I/O 使用情况，因为它可能成为非群集环境中的瓶颈或 DTC 日志文件时，与其他占用大量磁盘的文件的共享磁盘上。  
  
## <a name="separate-the-messagebox-and-tracking-databases"></a>单独的 MessageBox 和跟踪数据库  
 由于 BizTalk MessageBox 和 BizTalk 跟踪数据库中最活跃的我们建议将数据文件和事务日志文件放置于其中每种上专用的驱动器，以减少磁盘 I/O 争用问题的可能性。 例如，您将需要为 MessageBox 和 BizTalk 跟踪数据库文件的四个驱动器，一个驱动器的以下各项：  
  
-   MessageBox 数据文件  
  
-   MessageBox 事务日志文件  
  
-   BizTalk 跟踪 (DTA) 数据文件  
  
-   BizTalk 跟踪 (DTA) 事务日志文件  
  
 分隔 BizTalk MessageBox 和 BizTalk 跟踪数据库和分离数据库文件和事务日志文件在不同的物理磁盘上被视为减少磁盘 I/O 争用的最佳做法。 请尝试以尽可能跨多个物理磁盘轴磁盘 I/O。 此外可以通过在专用的 SQL Server 上放置 BizTalk 跟踪数据库降低磁盘 I/O 争用，但是，你仍应遵循上面方面分隔数据文件和事务日志文件的做法。  
  
## <a name="optimize-filegroups-for-the-biztalk-server-databases"></a>优化文件组的 BizTalk Server 数据库  
 按照中的步骤[Databases1 优化文件组](../technical-guides/optimizing-filegroups-for-the-databases1.md)和"BizTalk Server 数据库优化"白皮书，网址[http://go.microsoft.com/fwlink/?LinkId = 101578](http://go.microsoft.com/fwlink/?LinkId=101578)创建其他文件组和 BizTalk Server 数据库文件。 这会大大增加从单个磁盘配置的 BizTalk Server 数据库的性能。