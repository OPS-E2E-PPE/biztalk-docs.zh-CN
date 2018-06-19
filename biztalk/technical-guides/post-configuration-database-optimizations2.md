---
title: 后配置数据库 Optimizations2 |Microsoft 文档
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
ms.openlocfilehash: 168323f1e7dfdbb796fe29e0025c5d2a6f40c957
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302661"
---
# <a name="post-configuration-database-optimizations"></a>后配置数据库优化
除了按照中的建议之外[预配置数据库 Optimizations2](../technical-guides/pre-configuration-database-optimizations2.md)，应遵循的几个步骤来优化 SQL Server 上的 BizTalk Server 数据库性能*后*BizTalk Server 已安装且已被配置 BizTalk Server 数据库。 本主题提供这些优化的列表。  
  
## <a name="consider-setting-the-text-in-row-table-option-on-specific-messagebox-database-tables"></a>请考虑设置特定的 MessageBox 数据库表上的 text in row 表选项  
 SQL Server 提供了一个名为的表选项**一行中的文本**来声明的类型的字段的内容**文本**， **ntext**，或**映像**其维度的比 (8 Kb) 中的数据页的较小的数据必须存储在数据行。 通过设置此选项在 BizTalkMsgBoxDb 表 （部分表、 假脱机表和 DynamicStateInfo 表），你可以使用具有小上下文和具有小持久性大小的业务流程的小消息时提高消息吞吐量。  
  
-   **部件表**： 当消息大小小于 8 kb 的数据页的尺寸时，应用**一行中的文本**在部件表上的表选项可能会导致 BizTalk Server 性能改善。 部件表包含以下字段：  
  
    -   **ImgPart**： 包含消息部分或消息部分片段。  
  
    -   **ImgPropBag**： 包含消息一部分属性包。  
  
     这样一来，针对 MessageBox，循环内 BizTalk 主机运行的消息代理可以检索一批消息从部件表通过读取少量的页面。 具体取决于特定方案和硬件配置中，此方法可以降低 CPU 使用率在 SQL Server 和 BizTalk Server 中，并提供在延迟和吞吐量方面的重大进步。  
  
-   **假脱机表**： 当消息上下文的平均大小小于 8 kb，启用**一行中的文本**假脱机表上的表选项可帮助你从沿 MessageBox 中读取消息时减少访问次数与其上下文。 若要将此选项应用于假脱机表中，必须消除不必要的上下文属性和可分辨的字段，以减少的大小小于 8 Kb 的消息上下文。  
  
-   **DynamicStateInfo 表**这些表，一个用于每个主机，包含类型为 image 调用 imgData 包含二进制序列化的业务流程状态，在执行过程中遇到持久点时的字段。 当在主机出现内的业务流程的内部状态不太小的一次序列化其大小为不超过 8 kb，**一行中的文本**技术可以成功应用于 DynamicStateInfo_HostA 表。 因此，我们建议你保留的内部状态的业务流程越小越好。 该技术可以显著减少 XLANG 引擎进行序列化、 保留、 反序列化和还原发生持久性点时的业务流程的内部状态所花费的时间。  
  
 我们在我们的检验测试中使用以下设置：  
  
-   EXEC sp_tableoption N'Spool，text in row'，"6000"  
  
-   EXEC sp_tableoption N'Parts'，'text in row，"6000"  
  
## <a name="define-auto-growth-settings-for-biztalk-server-databases-to-a-fixed-value-instead-of-a-percentage-value"></a>定义 BizTalk Server 数据库的自动增长设置为固定值而不是百分比值  
  
-   SQL Server 数据库自动增长是一个阻止操作，这会影响 BizTalk Server 数据库性能。 因此务必分配足够的空间提前要最大程度减少数据库自动增长的匹配项的 BizTalk Server 数据库。  
  
-   数据库自动增长应设置为固定数量的兆字节而不是百分比 (指定文件增长等手段**中兆字节为单位**)。 这应这样做是为了，如果自动增长发生，它会以测得的方式。 这将减少过多的数据库增长的可能性。 BizTalk Server 数据库的增长增量通常应为不低于 100 MB。  
  
## <a name="pre-size-biztalk-server-databases-to-appropriate-size-with-multiple-data-files"></a>预先大小 BizTalk Server 数据库迁移到具有多个数据文件的适当大小  
 当 SQL Server 会增加文件的大小时，它必须首先初始化的新空间，然后才能使用。 这是涉及使用空页填充新的空间的阻止操作。 SQL Server 2005 或更高版本运行 Windows Server 2003 或更高版本支持"即时文件初始化。" 这可以极大地降低文件增长操作的性能影响。 有关详细信息，请参阅[数据库文件初始化](http://go.microsoft.com/fwlink/?LinkId=132063)(http://go.microsoft.com/fwlink/?LinkId=132063) SQL Server 联机丛书中。 本主题提供用于启用即时文件初始化步骤。  
  
 以下列表描述了在我们的检验测试中使用的 BizTalk Server 数据库配置：  
  
-   **BizTalk DTADB （BizTalk 跟踪数据库文件）：** 具有的文件大小为 100 MB 增长的 2048 MB 和 1024 MB 的日志文件，100 MB 增长数据文件。  
  
-   **BizTalkMgmtdb （BizTalk 管理数据库文件）：** 具有 100 MB 增长 512 MB 的文件大小和 100 MB 增长 512 MB 的日志文件的数据文件。  
  
-   **SSODB:** 具有 100 MB 增长 512 MB 的文件大小和 100 MB 增长 512 MB 的日志文件的数据文件。  
  
-   **BizTalkMsgBoxDb （BizTalk MessageBox 数据库）：** 8 个数据文件，每个都有 100 MB 增长的 2 GB 的文件大小和 100 MB 增长 20 GB 的日志文件。 由于 BizTalk MessageBox 数据库都是最活跃的我们建议你将放置数据文件和事务日志文件上专用的驱动器，以减少磁盘 I/O 争用问题的可能性。 在我们实验室环境中，我们使用一个驱动器的以下各项：  
  
    -   MessageBox 数据文件  
  
    -   MessageBox 事务日志文件  
  
 以下 SQL 脚本可以用于预大小 BizTalkMsgBoxDb 它最初具有驱动器 J (J:\BizTalkMsgBoxDb.mdf) 上数据文件和 K (K:\BizTalkMsgBoxDb_log 盘上日志文件。LDF):  
  
> [!IMPORTANT]  
>  此脚本是提供的"按原样，"旨在演示或教学目的，，要使用您自己承担。 使用此脚本不支持由 Microsoft 和 Microsoft 则没有此脚本的适用性的保证。  
  
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
 将备份 BizTalk （完全安装选项和日志备份） 输出目录移动到的专用 LUN，然后编辑要指向的专用 LUN 的备份的 BizTalk Server 作业。 从中移动到的专用 LUN 的备份 BizTalk Server 输出目录将减少磁盘 I/O 争用，通过编写到另一个磁盘与作业运行作业时进行读取。 有关配置 BizTalk Server 中备份作业的详细信息请参阅[如何配置备份 BizTalk Server 作业](http://go.microsoft.com/fwlink/?LinkID=153813)(http://go.microsoft.com/fwlink/?LinkID=153813) BizTalk Server 2010 帮助中。  
  
## <a name="verify-that-the-biztalk-server-sql-agent-jobs-are-running"></a>请验证正在运行 BizTalk Server SQL 代理作业  
 BizTalk Server 包括执行重要的功能使你的服务器操作和正常运行的多个 SQL Server 代理作业。 你应监视这些作业的运行状况，并确保它们正在运行且未发生错误。 BizTalk Server 中的性能问题的最常见原因之一是 BizTalk Server SQL 代理作业不运行，这反过来会导致 MessageBox 和跟踪数据库增长未选中状态。 请按照以下步骤来确保 BizTalk 服务器 SQL 代理作业运行正常操作：  
  
1.  **验证 SQL Server 代理服务是否正在运行**。  
  
2.  **验证是否已启用由 BizTalk 服务器安装的 SQL Server 代理作业和成功运行**。  
    BizTalk Server SQL Server 代理作业至关重要： 如果它们未运行，随着时间的推移将降低系统性能。  
  
3.  **验证 BizTalk Server SQL Server 代理作业是否完成及时**。   
    设置 Microsoft System Center Operations Manager 的最新版本，以监视作业。  
    你应注意的特定于某些作业的计划：  
  
    -   默认情况下，MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业是连续运行。 监视软件应考虑此计划，并且不生成警告。  
  
    -   MessageBox_Message_Cleanup_BizTalkMsgBoxDb 作业未启用或计划，但它会启动 MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb 作业每隔 10 秒。 因此，此作业不应启用、 计划，或手动启动。  
  
4.  **验证是否已正确配置 SQL Server 代理服务的启动类型**。  
    验证使用配置的 SQL Server 代理服务**启动类型**的**自动**除非的 SQL Server 代理服务配置为在 Windows Server 群集上的群集资源。 如果 SQL Server 代理服务配置为群集资源，则应配置**启动类型**作为**手动**因为该服务将由群集服务。  
  
## <a name="configure-purging-and-archiving-of-tracking-data"></a>配置清除和存档的跟踪数据  
 请按照下列步骤以确保清除和归档的跟踪数据已正确配置：  
  
1.  确保 SQL 代理作业"DTA 清除和存档"正确配置和启用，并且已成功完成。 有关详细信息，请参阅[如何配置 DTA 清除和存档作业](http://go.microsoft.com/fwlink/?LinkID=153814)(http://go.microsoft.com/fwlink/?LinkID=153814) BizTalk Server 文档中。  
  
2.  确保作业能够快速生成传入的跟踪数据清除的跟踪数据。 有关详细信息，请参阅[测量最大的可持续跟踪吞吐量](http://go.microsoft.com/fwlink/?LinkID=153815)(http://go.microsoft.com/fwlink/?LinkID=153815) BizTalk Server 文档中。  
  
3.  查看软清除和硬清除参数，以确保你保存数据的最佳总时间。 有关详细信息，请参阅[存档和清除 BizTalk 跟踪数据库](http://go.microsoft.com/fwlink/?LinkID=153816)(http://go.microsoft.com/fwlink/?LinkID=153816) BizTalk Server 文档中。  
  
4.  如果你只需以清除旧数据并不需要对其进行存档第一次，更改 SQL 代理作业调用存储的过程"dtasp_PurgeTrackingDatabase。" 有关详细信息，请参阅[如何清除数据从 BizTalk 跟踪数据库](http://go.microsoft.com/fwlink/?LinkID=153817)(http://go.microsoft.com/fwlink/?LinkID=153817) BizTalk Server 文档中。  
  
## <a name="monitor-and-reduce-dtc-log-file-disk-io-contention"></a>监视和减少 DTC 日志文件磁盘 I/O 争用  
 分布式事务处理协调器 (DTC) 日志文件可以成为大型事务环境中的磁盘 I/O 瓶颈。 这在使用支持事务，如 SQL Server、 MSMQ 或 MQSeries，或在多 MessageBox 环境中的适配器时尤其如此。 事务的适配器使用 DTC 事务，以及多 MessageBox 环境广泛利用 DTC 事务。 若要确保 DTC 日志文件不会成为磁盘 I/O 瓶颈，则应该监视磁盘 DTC 日志文件驻留在 SQL Server 数据库服务器上的磁盘 I/O 使用情况。 如果磁盘 DTC 日志文件所在的磁盘 I/O 使用情况变得过多，请考虑将 DTC 日志文件移到更快的磁盘。 在环境中在群集 SQL Server，这是不尽可能考虑因为日志文件已将共享的驱动器，可能会具有多个轴的快速 SAN 驱动器上。 不过仍应监视磁盘 I/O 使用情况。 这是因为它可能成为瓶颈在非群集环境或 DTC 日志文件时与其他占用大量磁盘的文件的共享磁盘上。  
  
## <a name="separate-the-messagebox-and-tracking-databases"></a>单独的 MessageBox 和跟踪数据库  
 由于 BizTalk MessageBox 和 BizTalk 跟踪数据库中最活跃的我们建议将数据文件和事务日志文件放置于其中每种上专用的驱动器，以减少磁盘 I/O 争用问题的可能性。 例如，您将需要为 MessageBox 和 BizTalk 跟踪数据库文件的四个驱动器，一个驱动器的以下各项：  
  
-   MessageBox 数据文件  
  
-   MessageBox 事务日志文件  
  
-   BizTalk 跟踪 (DTA) 数据文件  
  
-   BizTalk 跟踪 (DTA) 事务日志文件  
  
 分隔 BizTalk MessageBox 和 BizTalk 跟踪数据库和分离数据库文件和事务日志文件在不同的物理磁盘上被视为减少磁盘 I/O 争用的最佳做法。 请尝试以尽可能跨多个物理磁盘轴磁盘 I/O。 此外可以减少磁盘 I/O 争用，通过将 BizTalk 跟踪数据库放置在专用的 SQL 服务器;但是，你仍应遵循上面方面分隔数据文件和事务日志文件的做法。  
  
## <a name="optimize-filegroups-for-the-biztalk-server-databases"></a>优化文件组的 BizTalk Server 数据库  
 按照中的步骤[Databases2 优化文件组](../technical-guides/optimizing-filegroups-for-the-databases2.md)和[BizTalk Server 数据库优化](http://go.microsoft.com/fwlink/?LinkId=101578)白皮书 ([http://go.microsoft.com/fwlink/?LinkId = 101578](http://go.microsoft.com/fwlink/?LinkId=101578)) 来创建其他文件组和 BizTalk Server 数据库文件。 这会大大增加从单个磁盘配置的 BizTalk Server 数据库的性能。  
  
## <a name="see-also"></a>另请参阅  
 [优化数据库性能](../technical-guides/optimizing-database-performance.md)