---
title: 配置后数据库 Optimizations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 609eda22-8399-4b7c-b860-21b495d2f68d
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8489d69489a23d6c81efb8443cccbb40c7a357ea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993790"
---
# <a name="post-configuration-database-optimizations"></a>配置后数据库优化
除了遵循中的建议，还[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)，应遵循的几个步骤以优化 SQL Server 上的 BizTalk Server 数据库性能*后*安装 BizTalk Server 和 BizTalk Server 数据库已配置。 本主题提供了一系列这些优化。  
  
## <a name="consider-setting-the-text-in-row-table-option-on-specific-messagebox-database-tables"></a>请考虑设置上特定 MessageBox 数据库表的 'text in row 表选项  
 SQL Server 提供了一个名为的表选项**行中的文本**声明的类型的字段的内容**文本**， **ntext**，或者**映像**必须在数据行中存储的数据的维度较小的数据页 (8 Kb)。 通过设置此选项在 BizTalkMsgBoxDb 表 （Parts 表中，后台处理表和 DynamicStateInfo 表），可以使用具有小的上下文和业务流程具有小型持久性大小的小消息时增加消息吞吐量。  
  
- **部件表**： 如果消息大小小于 8 kb 的数据页的尺寸，应用**行中的文本**在部件表上的表选项可能会导致 BizTalk Server 性能改进。 在部件表包含以下字段：  
  
  - **ImgPart**： 包含消息部分或消息部分片段。  
  
  - **ImgPropBag**： 包含消息部分属性包。  
  
    这样一来，当遍历对 MessageBox，BizTalk 主机中运行的消息代理可以检索一批消息部件表中通过读取少量页面。 具体取决于特定方案和硬件配置中，此方法可以降低 CPU 使用率在 SQL Server 和 BizTalk Server 中，并提供在延迟和吞吐量方面的重大进步。  
  
- **假脱机表**： 当消息上下文的平均大小小于 8 kb 时，启用**行中的文本**上后台处理表的表选项可帮助您从沿 MessageBox 中读取消息时减少访问次数连同其上下文。 若要将此选项应用于后台处理表，必须消除不必要的上下文属性和可分辨的字段，以减小大小小于 8 Kb 的消息上下文。  
  
- **DynamicStateInfo 表**这些表，一个用于每个主机包含名为包含二进制序列化业务流程的状态，在其执行期间遇到持久点时的 imgData 映像类型的字段。 当业务流程主机 HostA 内的内部状态是非常小的一次序列化其大小为不超过 8 kb，**行中的文本**方法可以成功应用于 DynamicStateInfo_HostA 表。 因此我们建议您使业务流程的内部状态尽可能小。 此技术可以显著减少 XLANG 引擎进行序列化、 保留、 反序列化和还原业务流程持久化点时的内部状态所用的时间。  
  
  我们在我们的检验测试中使用以下设置：  
  
- EXEC sp_tableoption N'Spool'，'text in row'，"6000"  
  
- EXEC sp_tableoption N'Parts'，'text in row'，"6000"  
  
## <a name="define-auto-growth-settings-for-biztalk-server-databases-to-a-fixed-value-instead-of-a-percentage-value"></a>定义 BizTalk Server 数据库的自动增长设置为固定值而不是百分比值  
  
-   SQL Server 数据库自动增长是阻塞操作，这会影响 BizTalk Server 数据库性能。 因此务必要分配足够的空间用于 BizTalk Server 数据库预先以最大程度减少数据库自动增长的匹配项。  
  
-   应将数据库自动增长设置为固定数量的兆字节而不是百分比 (指定文件的增长**兆字节中**)。 这应进行以便发生自动增长时，它会以标准方式。 这将减少过多的数据库增长的可能性。 BizTalk Server 数据库的增长增量通常应为不低于 100 MB。  
  
## <a name="pre-size-biztalk-server-databases-to-appropriate-size-with-multiple-data-files"></a>预调整到适当大小的 BizTalk Server 数据库与多个数据文件的大小  
 SQL Server 会增加文件的大小，它必须先初始化新的空间，然后才能使用。 这是涉及使用空页填充新的空间的阻塞操作。 SQL Server 2005 或更高版本运行 Windows Server 2003 或更高版本支持"即时文件初始化"。 这可以大大减少文件增长操作的性能影响。 有关详细信息，请参阅[数据库文件初始化](http://go.microsoft.com/fwlink/?LinkId=132063)(http://go.microsoft.com/fwlink/?LinkId=132063) SQL Server 联机丛书中。 本主题提供用于启用即时文件初始化步骤。  
  
 以下列表介绍了在我们的检验测试中使用的 BizTalk Server 数据库配置：  
  
- **BizTalk DTADB （BizTalk 跟踪数据库文件）：** 数据文件的文件大小为 2048 MB，增长 100 MB 具有和 1024 MB 的日志文件，增长 100 MB。  
  
- **BizTalkMgmtdb （BizTalk 管理数据库文件）：** 具有 512 MB 和增长 100 MB 的文件大小和 512 MB 的日志文件，增长 100 MB 的数据文件。  
  
- **SSODB:** 具有 512 MB 和增长 100 MB 的文件大小和 512 MB 的日志文件，增长 100 MB 的数据文件。  
  
- **BizTalkMsgBoxDb （BizTalk MessageBox 数据库）：** 8 个数据文件，每个都有 2 GB，带有增长 100 MB 的文件大小和 20 gb 具有增长 100 MB 的日志文件。 由于 BizTalk MessageBox 数据库都是最活跃的我们建议将数据文件和事务日志文件上专用的驱动器，以减少磁盘 I/O 争用问题的可能性。 在我们的实验室环境，我们使用一个驱动器的以下各项：  
  
  -   MessageBox 数据文件  
  
  -   MessageBox 事务日志文件  
  
  可以使用以下 SQL 脚本预调整 BizTalkMsgBoxDb 最初具有驱动器 J (J:\BizTalkMsgBoxDb.mdf) 上数据文件和驱动器 K (K:\BizTalkMsgBoxDb_log 上的一个日志文件大小。LDF):  
  
> [!IMPORTANT]  
>  提供"按原样，"用于演示或培训目的，并且将使用您自己承担，此脚本。 使用此脚本不受 Microsoft，因此 Microsoft 不保证此脚本的适用性。  
  
```  
EXEC dbo.sp_helpdb BizTalkMsgBoxDb  
ALTER DATABASE BizTalkMsgBoxDb MODIFY FILE (NAME = BizTalkMsgBoxDb , FILENAME = 'J:\BizTalkMsgBoxDb.mdf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_2 , FILENAME = 'J:\BizTalkMsgBoxDb_2.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_3 , FILENAME = 'J:\BizTalkMsgBoxDb_3.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_4 , FILENAME = 'J:\BizTalkMsgBoxDb_4.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_5 , FILENAME = 'J:\BizTalkMsgBoxDb_5.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_6 , FILENAME = 'J:\BizTalkMsgBoxDb_6.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_7 , FILENAME = 'J:\BizTalkMsgBoxDb_7.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
ALTER DATABASE BizTalkMsgBoxDb ADD FILE    (NAME = BizTalkMsgBoxDb_8 , FILENAME = 'J:\BizTalkMsgBoxDb_8.ndf' , SIZE = 2GB , FILEGROWTH = 100MB)  
GO  
ALTER DATABASE BizTalkMsgBoxDb MODIFY FILE (NAME = BizTalkMsgBoxDb_log , FILENAME = 'K:\BizTalkMsgBoxDb_log.LDF', SIZE =  20GB , FILEGROWTH = 100MB)  
GO  
```  
  
## <a name="move-the-backup-biztalk-server-output-directory-to-a-dedicated-lun"></a>将备份 BizTalk Server 输出目录移动到的专用 LUN  
 将备份 BizTalk （完全安装选项和日志备份） 输出目录移动到的专用 LUN，然后编辑备份 BizTalk Server 作业，以指向专用 LUN。 正在读取移动到的专用 LUN 的备份 BizTalk Server 输出目录将减少磁盘 I/O 争用，运行时，该作业是通过写入到非作业所在的磁盘。 有关配置备份 BizTalk Server 作业的详细信息请参阅[如何配置备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/?LinkID=153813)(http://go.microsoft.com/fwlink/?LinkID=153813) BizTalk Server 2010 帮助中。  
  
## <a name="verify-that-the-biztalk-server-sql-agent-jobs-are-running"></a>验证 BizTalk Server SQL 代理作业正在运行  
 BizTalk Server 包含多个执行重要功能，以使服务器正常操作和运行的 SQL Server 代理作业。 应监视这些作业的运行状况，并确保它们无错运行。 BizTalk Server 中的性能问题的最常见原因之一是 BizTalk Server SQL 代理作业不运行，这又可能导致 MessageBox 和跟踪数据库增长未选中状态。 请按照以下步骤来确保 BizTalk Server SQL 代理作业运行正常操作：  
  
1.  **验证 SQL Server 代理服务是否正在运行**。  
  
2.  **验证 BizTalk server 安装的 SQL Server 代理作业是否已启用并成功运行**。  
    BizTalk Server SQL Server 代理作业至关重要： 如果未运行，随着时间的推移会降低系统性能。  
  
3.  **验证 BizTalk Server SQL Server 代理作业是否及时完成**。   
    设置 Microsoft System Center Operations Manager 的最新版本监视作业。  
    应注意的特定于某些作业的计划：  
  
    -   默认情况下，MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业会连续运行。 监视软件，应考虑此计划，并生成警告。  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb 作业未启用或未计划，但它由 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业启动每隔 10 秒。 因此，此作业不应启用、 计划，或手动启动。  
  
4.  **验证是否已正确配置 SQL Server 代理服务的启动类型**。  
    验证 SQL Server 代理服务配置与**启动类型**的**自动**除非 SQL Server 代理服务配置为在 Windows Server 群集上群集资源。 如果 SQL Server 代理服务配置为群集资源，则应配置**启动类型**作为**手动**因为该服务将由群集服务。  
  
## <a name="configure-purging-and-archiving-of-tracking-data"></a>配置清除和存档的跟踪数据  
 请按照下列步骤以确保清除和存档的跟踪数据已正确配置：  
  
1.  请确保 SQL 代理作业"DTA 清除和存档"是正确配置和启用，并且已成功完成。 有关详细信息，请参阅[如何配置 DTA 清除和存档作业](http://go.microsoft.com/fwlink/?LinkID=153814)(http://go.microsoft.com/fwlink/?LinkID=153814) BizTalk Server 文档中。  
  
2.  确保作业可以快速生成传入跟踪数据清除跟踪数据。 有关详细信息，请参阅[测量的最大可承受跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815) BizTalk Server 文档中。  
  
3.  查看软清除和硬清除参数，以确保保持最佳的时间长度的数据。 有关详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](http://go.microsoft.com/fwlink/?LinkID=153816)(http://go.microsoft.com/fwlink/?LinkID=153816) BizTalk Server 文档中。  
  
4.  如果您只需清除旧数据，则不需要将其存档第一次，更改 SQL 代理作业来调用存储的过程"dtasp_PurgeTrackingDatabase。" 有关详细信息，请参阅[如何从 BizTalk 跟踪数据库中清除数据](http://go.microsoft.com/fwlink/?LinkID=153817)(http://go.microsoft.com/fwlink/?LinkID=153817) BizTalk Server 文档中。  
  
## <a name="monitor-and-reduce-dtc-log-file-disk-io-contention"></a>监视和降低 DTC 日志文件磁盘 I/O 争用  
 大型事务环境中的磁盘 I/O 瓶颈可能会导致分布式事务处理协调器 (DTC) 日志文件。 使用支持事务，例如 SQL Server、 MSMQ 或 MQSeries，或在多 MessageBox 环境中的适配器时，也是如此。 事务性适配器使用 DTC 事务，多 MessageBox 环境进行广泛使用 DTC 事务。 若要确保 DTC 日志文件不会成为磁盘 I/O 瓶颈，则应该监视磁盘用于 DTC 日志文件驻留在 SQL Server 数据库服务器的磁盘 I/O 使用情况。 如果磁盘用于 DTC 日志文件所在的位置的磁盘 I/O 使用情况变得过多，请考虑将 DTC 日志文件移到更快的磁盘。 在 SQL Server 已群集的环境中，这是不需考虑尽可能因为日志文件将可能会具有多个心轴的快速 SAN 驱动器的共享驱动器。 不过仍应监视磁盘 I/O 使用情况。 这是因为它可以成为 DTC 日志文件时与其他占用大量磁盘的文件的共享磁盘上或非群集环境中的瓶颈。  
  
## <a name="separate-the-messagebox-and-tracking-databases"></a>单独的 MessageBox 和跟踪数据库  
 由于 BizTalk MessageBox 和 BizTalk 跟踪数据库是最活跃，因此我们建议将数据文件和事务日志文件放置在专用的驱动器，以减少磁盘 I/O 争用问题的可能性上的每个。 例如，您将需要四个驱动器的 MessageBox 和 BizTalk 跟踪数据库文件、 一个驱动器的以下各项：  
  
- MessageBox 数据文件  
  
- MessageBox 事务日志文件  
  
- BizTalk 跟踪 (DTA) 数据文件  
  
- BizTalk 跟踪 (DTA) 事务日志文件  
  
  将 BizTalk MessageBox 和 BizTalk 跟踪数据库和分离数据库文件和事务日志文件在不同的物理磁盘上被视为减少磁盘 I/O 争用的最佳实践。 请尝试以尽可能跨任意数量的物理心轴磁盘 I/O。 你还可以通过将 BizTalk 跟踪数据库放置在专用的 SQL Server; 上减少磁盘 I/O 争用但是，仍应遵循上面的实践方面并将数据文件和事务日志文件。  
  
## <a name="optimize-filegroups-for-the-biztalk-server-databases"></a>优化 BizTalk Server 数据库的文件组  
 按照中的步骤[优化文件组的数据库 2](../technical-guides/optimizing-filegroups-for-the-databases2.md)并[BizTalk Server 数据库优化](http://go.microsoft.com/fwlink/?LinkId=101578)白皮书 ([http://go.microsoft.com/fwlink/?LinkId=101578](http://go.microsoft.com/fwlink/?LinkId=101578)) 来创建更多文件组和 BizTalk Server 数据库文件。 这会极大地增加从单个磁盘配置 BizTalk Server 数据库的性能。  
  
## <a name="see-also"></a>请参阅  
 [优化数据库性能](../technical-guides/optimizing-database-performance.md)