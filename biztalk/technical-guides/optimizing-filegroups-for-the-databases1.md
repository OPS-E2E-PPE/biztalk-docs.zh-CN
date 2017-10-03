---
title: "针对 Databases1 优化文件组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7dbed4d-95d6-4a41-a69e-737a6f2f5a82
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d7a9feb1f455a24b397c2dbd0084d08f1cf332
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-filegroups-for-the-databases"></a>数据库优化文件组
文件输入/输出 (I/O) 争用经常是限制因素或在生产 BizTalk Server 环境中的形成瓶颈。 BizTalk Server 是一个非常数据库密集型应用程序和 BizTalk Server 使用的 SQL Server 数据库又是非常文件 I/O 密集型。  
  
 本主题介绍如何更好地利用的文件和文件组功能的 SQL Server，以最少的匹配项的文件 I/O 争用并提高 BizTalk Server 解决方案的整体性能。  
  
## <a name="overview"></a>概述  
 每个 BizTalk Server 解决方案将最终会遇到文件 I/O 争用，随着提高吞吐量。 I/O 子系统或存储引擎是任何关系数据库的一个关键组件。 成功的数据库实现通常要求在项目的初期阶段进行仔细的规划。 此规划应考虑下列事项：  
  
-   使用哪种类型的磁盘硬件，如 RAID（独立磁盘冗余阵列）设备。 有关使用 RAID 硬件解决方案的详细信息，请参阅"关于基于硬件的解决方案"SQL Server 联机丛书中在[http://go.microsoft.com/fwlink/?LinkID=113944](http://go.microsoft.com/fwlink/?LinkID=113944)。  
  
-   如何在使用文件和文件组的磁盘上的数据分配。 有关在 SQL Server 2008 中使用文件和文件组的详细信息，请参阅"使用文件和文件组"SQL Server 联机丛书中在[http://go.microsoft.com/fwlink/?LinkID = 69369](http://go.microsoft.com/fwlink/?LinkID=69369)和"了解文件和文件组"SQL Server 联机丛书中在[http://go.microsoft.com/fwlink/?LinkID = 96447](http://go.microsoft.com/fwlink/?LinkID=96447)。  
  
-   实现在访问数据时提高性能的最佳索引设计。 有关设计索引的详细信息，请参阅"设计中的索引"SQL Server 联机丛书在[http://go.microsoft.com/fwlink/?LinkID=96457](http://go.microsoft.com/fwlink/?LinkID=96457)。  
  
-   如何设置 SQL Server 配置参数，以获得最佳性能。 为 SQL Server 设置最佳的配置参数的详细信息，请参阅"优化服务器性能"SQL Server 联机丛书中在[http://go.microsoft.com/fwlink/?LinkID=71418](http://go.microsoft.com/fwlink/?LinkID=71418)。  
  
 BizTalk Server 的主要设计目标之一是确保消息的**永远不会**丢失。 为了缓解消息丢失的可能性，消息频繁写入到 MessageBox 数据库中，处理消息。 时由业务流程处理消息，则会将消息写入到 MessageBox 数据库在业务流程中每个持久性点。 这些持久性点导致 MessageBox 写入物理磁盘的消息和相关的状态。 在更高的吞吐量，此持久性可能导致大量的磁盘争用，且可能成为瓶颈。  
  
 进行最佳使用的文件和 SQL Server 中的文件组功能已被证实将有效地满足文件 IO 瓶颈，并改进在 BizTalk Server 解决方案中的整体性能。 此优化仅应由有经验的 SQL Server 数据库管理员和 BizTalk Server 数据库已正确备份仅后的全部完成。 应该在 BizTalk Server 环境中的所有 SQL Server 计算机上执行此优化。  
  
 可以利用 SQL Server 文件和文件组，来提高数据库性能，因为此功能允许数据库创建跨多个磁盘、 多个磁盘控制器或 RAID （独立磁盘冗余阵列） 系统。 例如，如果计算机上有四个磁盘，那么可以创建一个由三个数据文件和一个日志文件组成的数据库，每个磁盘上放置一个文件。 根据访问数据时，四个读/写磁头可以同时访问并行中的数据。 这极大地加快数据库操作。 有关实现 SQL Server 磁盘的硬件解决方案的详细信息，请参阅"中的数据库性能"SQL Server 联机丛书在[http://go.microsoft.com/fwlink/?LinkID=71419](http://go.microsoft.com/fwlink/?LinkID=71419)。  
  
 此外，文件和文件组中启用数据放置，因为可以在特定的文件组中创建表。 这提高了性能，因为对于给定的表的所有文件 i/o 操作可以都定向到特定的磁盘。 例如，常用的表可以放置中的文件组，位于一个磁盘上的文件和其他不太常访问的表，在数据库可以位于另一个文件，位于第二个磁盘上的组中的不同文件。  
  
 在主题"中的数据库层识别瓶颈"中的大量详细讨论文件 IO 瓶颈[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]文档[http://go.microsoft.com/fwlink/?LinkId=147626](http://go.microsoft.com/fwlink/?LinkId=147626)。 文件 I/O (磁盘 I/O) 是瓶颈的最常见指示器是"物理磁盘： 平均磁盘队列长度"计数器的值。 如果"物理磁盘： 平均磁盘队列长度"计数器的值大于大约 3 上的任何 SQL 服务器的任何给定磁盘，则文件 I/O 可能将一个瓶颈。  
  
 如果应用文件组优化不能解决文件 I/O 瓶颈问题，然后它可能需要通过添加其他物理计算机或 SAN 驱动器增加磁盘子系统的吞吐量。  
  
 本主题介绍如何手动应用文件和文件组的优化，但这些优化也可以编写脚本。 在本主题末尾提供了一个示例 SQL 脚本。 请务必注意，此脚本将需要进行修改以便适应文件、 文件组，以及任何给定的 BizTalk Server 解决方案所使用的 SQL Server 数据库的磁盘配置。  
  
> [!NOTE]  
>  本主题介绍如何创建多个文件和 BizTalk MessageBox 数据库文件组。 建议的文件和 BizTalk Server 数据库的所有文件组的穷举列表，请参阅**附录 B**的绝佳的"BizTalk Server 数据库优化"白皮书在[http://go.microsoft.com/fwlink/？LinkID = 101578](http://go.microsoft.com/fwlink/?LinkID=101578)。  
  
## <a name="databases-created-with-a-default-biztalk-server-configuration"></a>使用 BizTalk Server 配置的默认创建的数据库  
 具体取决于该功能启用时可能在 SQL Server 中创建多达 13 不同数据库中配置 BizTalk Server 中，以及所有这些数据库创建的默认文件组。 SQL Server 的默认文件组是主文件组，除非使用 ALTER DATABASE 命令更改默认文件组。 下表列出了如果配置 BizTalk Server 时启用所有功能在 SQL Server 中创建的数据库。  
  
### <a name="biztalk-server-databases"></a>BizTalk Server 数据库  
  
||||  
|-|-|-|  
|**数据库**|**默认数据库名称**|**Description**|  
|配置数据库|BizTalkMgmtDb|中央元数据信息存储在 BizTalk Server 组中的 BizTalk Server 的所有实例。|  
|BizTalk MessageBox 数据库|BizTalkMsgBoxDb|存储订阅谓词。 它是一个主机平台，并为每个 BizTalk Server 主机中保留队列和状态表。 MessageBox 数据库还存储消息和消息属性。|  
|BizTalk 跟踪数据库|BizTalkDTADb|存储业务和运行状况监视由 BizTalk Server 跟踪引擎跟踪数据。|  
|BAM 分析数据库|BAMAnalysis|有关业务活动以保持聚合的历史数据的 SQL Server Analysis Services 数据库。|  
|BAM 星型架构数据库|BAMStarSchema|转换为进行 OLAP 处理业务活动监视中收集的数据。 使用 BAM 分析数据库时，此数据库是必需的。|  
|BAM 主导入数据库|BAMPrimaryImport|存储在活动实例后发生的事件的业务活动，然后查询进度和数据。 此数据库还执行实时聚合。|  
|BAM 存档数据库|BAMArchive|存储订阅谓词。 BAM 存档数据库最小化 BAM 主导入数据库中的业务活动数据的累计。|  
|SSO 数据库|SSODB|安全地存储配置的信息接收位置。 存储有关 SSO affiliate 应用程序，以及所有关联应用程序的加密的用户凭据。|  
|规则引擎数据库|BizTalkRuleEngineDb|存储库：<br /><br /> -策略，它是相关的规则集。<br />-词汇，它们是在规则中的数据引用的用户友好的特定于域的名称的集合。|  
|跟踪 Analysis Server 管理数据库|BizTalkAnalysisDb|存储业务和运行状况监视 OLAP 多维数据集。|  
  
## <a name="separation-of-data-files-and-log-files"></a>数据文件和日志文件的分离  
 如上所述，默认 BizTalk Server 配置 MessageBox 数据库会置于单个文件中的默认文件组中。 默认情况下，MessageBox 数据库的数据和事务日志放置在相同的驱动器和路径。 这样做是为了适应单磁盘系统。 单个文件/文件组/磁盘配置是**不是最佳选择**在生产环境中。 为了获得最佳性能，数据文件和日志文件应置于单独磁盘上。  
  
> [!NOTE]  
>  日志文件不包括在文件组内。 日志空间与数据空间分开管理。  
  
## <a name="the-8020-rule-of-distributing-biztalk-server-databases"></a>80/20 规则分发 BizTalk Server 数据库  
 在大多数 BizTalk Server 解决方案中，由于磁盘 I/O 争用或数据库争用的主要来源是争用的 BizTalk Server MessageBox 数据库。 这是在单个和多 MessageBox 方案 true。 它是合理的假定，80%的值的分发 BizTalk 数据库将派生自优化的 MessageBox 数据文件和日志文件。 详细描述下面的示例方案侧重于优化 MessageBox 数据库的数据文件。 这些步骤，可以然后遵循其他数据库的根据需要例如，如果解决方案需要大量跟踪，则也可以优化跟踪数据库。  
  
## <a name="manually-adding-files-to-the-messagebox-database-step-by-step"></a>手动将文件添加到 MessageBox 数据库，分步  
 本部分介绍可后接手动将文件添加到 MessageBox 数据库的步骤。 在此示例中添加三个文件组，并随后将文件添加到每个文件组，以针对 MessageBox 中将文件分发在多个磁盘。 在此示例中，在 SQL Server 2005 和 SQL Server 2008 上执行这些步骤。  
  
> [!NOTE]  
>  为了完成本指南中的性能测试，文件组进行了优化通过将作为的一部分发布的脚本使用[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]性能优化指南。 出于参考目的提供了下面的步骤。  
  
### <a name="manually-adding-files-to-the-messagebox-database-on-sql-server-2005-or-sql-server-2008"></a>手动将文件添加到 SQL Server 2005 或 SQL Server 2008 上的 MessageBox 数据库  
 **请按照下列步骤手动将文件添加到 MessageBox 数据库上[!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)]或[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]:**  
  
> [!NOTE]  
>  尽管有细微的差异，在用户界面之间[!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)]和[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]，下面列出的步骤适用于这两个版本[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft SQL Server 2005**或**Microsoft SQL Server 2008**，然后单击**SQL Server Management Studio**以显示**连接到服务器**对话框。  
  
     ![SQL Server 2005 管理登录屏幕](../technical-guides/media/641a03f4-362c-4dde-8c9d-ac313d8881e3.gif "641a03f4-362c-4dde-8c9d-ac313d8881e3")  
  
2.  在**服务器名称**字段**连接到服务器**对话框中，输入保存 BizTalk Server MessageBox 数据库中，SQL Server 实例的名称，然后单击**连接**按钮以显示**Microsoft SQL Server Management Studio**对话框。  
  
     在**对象资源管理器**窗格中的 SQL Server Management Studio，展开**数据库**若要查看的此实例的数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。  
  
     ![SQL Server 2005 Management Studio、 对象资源管理器](../technical-guides/media/81f13912-fedc-48c3-9669-c18863e637b1.gif "81f13912-fedc-48c3-9669-c18863e637b1")  
  
3.  右键单击要添加文件，并依次为其数据库**属性**以显示**数据库属性**对话框中的数据库。  
  
     ![SQL Server 2005 数据库属性对话框中](../technical-guides/media/82ae7c11-5b3a-4312-876c-70876abdd65c.gif "82ae7c11-5b3a-4312-876c-70876abdd65c")  
  
4.  在**数据库属性**对话框中，选择**文件组**页。 单击**添加**按钮创建的 BizTalkMsgBoxDb 数据库的其他文件组。 在下面的示例中，添加三个其他文件组。  
  
     ![SQL Server 2005 中，向数据库添加文件组](../technical-guides/media/6be47c0e-06c3-45d9-bce2-a42453da7d19.gif "6be47c0e-06c3-45d9-bce2-a42453da7d19")  
  
5.  在 **“数据库属性”** 对话框中，选择 **“文件”** 页。  
  
     单击**添加**按钮以创建要添加到文件组的其他文件，然后单击**确定**。 MessageBox 数据库现在分布在多个磁盘，将提供的单个磁盘配置有显著的性能优势。  
  
     在下面的示例中，为每个以前创建的文件组创建一个文件和每个文件放置在单独的磁盘上。  
  
     ![SQL Server 2005 中，将文件添加到文件组](../technical-guides/media/d5d5c5df-d483-4f01-8128-f98228de51b9.gif "d5d5c5df-d483-4f01-8128-f98228de51b9")  
  
## <a name="sample-sql-script-for-adding-filegroups-and-files-to-the-biztalk-messagebox-database"></a>用于将文件组和文件添加到 BizTalk MessageBox 数据库示例 SQL 脚本  
 下面的示例 SQL 脚本执行手动完成上一节中的相同任务。  
此示例脚本假定存在不同逻辑驱动器 G 通过 j 编写。该脚本创建文件组和每个文件组的文件，并使 J 驱动器上的日志文件。  
  
> [!NOTE]  
>  SQL Server 按顺序将写入其日志文件，因为没有任何性能优势，实现通过创建针对 SQL Server 数据库的多个日志文件。  
  
```  
-- Filegroup changes are made using the master database  
USE [master]  
GO  
  
-- Script-wide declarations  
DECLARE @CommandBuffer nvarchar(2048)  
DECLARE @FG1_Path nvarchar(1024)  
DECLARE @FG2_Path nvarchar(1024)  
DECLARE @FG3_Path nvarchar(1024)  
DECLARE @Log_Path nvarchar(1024)  
  
-- Set the default path for all filegroups  
SET @FG1_Path = N'G:\BizTalkMsgBoxDATA\'  
SET @FG2_Path = N'H:\BizTalkMsgBoxDATA\'  
SET @FG3_Path = N'I:\BizTalkMsgBoxDATA\'  
SET @Log_Path = N'J:\BizTalkMsgBoxLog\'  
  
ALTER DATABASE [BizTalkMsgBoxDb] ADD FILEGROUP [BTS_MsgBox_FG1]  
SET @CommandBuffer = N'ALTER DATABASE [BizTalkMsgBoxDb] ADD FILE ( NAME = N''BizTalkMsgBoxDb_FG1'', FILENAME = N''' + @FG1_Path +   
N'BizTalkMsgBoxDb_FG1.ndf'' , SIZE = 102400KB , MAXSIZE = UNLIMITED, FILEGROWTH = 10240KB ) TO FILEGROUP [BTS_MsgBox_FG1]'  
EXECUTE (@CommandBuffer)  
  
ALTER DATABASE [BizTalkMsgBoxDb] ADD FILEGROUP [BTS_MsgBox_FG2]  
SET @CommandBuffer = N'ALTER DATABASE [BizTalkMsgBoxDb] ADD FILE ( NAME = N''BizTalkMsgBoxDb_FG1'', FILENAME = N''' + @FG2_Path +   
N'BizTalkMsgBoxDb_FG2.ndf'' , SIZE = 102400KB , MAXSIZE = UNLIMITED, FILEGROWTH = 10240KB ) TO FILEGROUP [BTS_MsgBox_FG2]'  
EXECUTE (@CommandBuffer)  
  
ALTER DATABASE [BizTalkMsgBoxDb] ADD FILEGROUP [BTS_MsgBox_FG3]  
SET @CommandBuffer = N'ALTER DATABASE [BizTalkMsgBoxDb] ADD FILE ( NAME = N''BizTalkMsgBoxDb_FG1'', FILENAME = N''' + @FG3_Path +   
N'BizTalkMsgBoxDb_FG3.ndf'' , SIZE = 102400KB , MAXSIZE = UNLIMITED, FILEGROWTH = 10240KB ) TO FILEGROUP [BTS_MsgBox_FG3]'  
EXECUTE (@CommandBuffer)  
  
ALTER DATABASE [BizTalkMsgBoxDb] MODIFY FILE ( NAME = N'BizTalkMsgBoxDb_log', SIZE = 10240KB , MAXSIZE = UNLIMITED, FILEGROWTH = 10240KB )  
  
GO -- Completes the previous batch, as necessary  
```  
  
 下面的示例 SQL 脚本无法用于将特定的文件组设置为默认文件组：  
  
```  
USE [BizTalkMsgBoxDb]  
GO  
declare @isdefault bit  
SELECT @isdefault=convert(bit, (status & 0x10)) FROM sysfilegroups WHERE groupname=N'BTS_MsgBox_FG1'  
if(@isdefault=0)  
ALTER DATABASE [BizTalkMsgBoxDb] MODIFY FILEGROUP [BTS_MsgBox_FG1] DEFAULT  
GO  
```  
  
 脚本的优点是，脚本可以快速执行多个任务，并确切地说，可重现而减少人为错误的可能性。 脚本的缺点是脚本的执行编写不正确可能会导致严重的问题，可能需要的 BizTalk Server 数据库，以便从从头开始重新配置。 因此，它是极其重要的 SQL 脚本，如本主题中列出的示例脚本全面的测试才能在生产环境中正在执行。