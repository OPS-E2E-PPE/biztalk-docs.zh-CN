---
title: 优化数据库文件组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7dbed4d-95d6-4a41-a69e-737a6f2f5a82
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7969280d7fa794820d2e99c164ee00e2ebbecc4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291440"
---
# <a name="optimizing-filegroups-for-the-databases"></a>优化文件组的数据库
文件输入/输出 (I/O) 争用通常是限制因素或瓶颈，在生产 BizTalk Server 环境中。 BizTalk Server 是一个非常数据库密集型应用程序和 BizTalk Server 使用的 SQL Server 数据库又是大量占用非常文件 I/O。  
  
 本主题介绍如何以最佳方式使用的文件和文件组功能的 SQL Server 以最小化的匹配项的文件 I/O 争用和提高 BizTalk Server 解决方案的整体性能。  
  
## <a name="overview"></a>概述  
 每个 BizTalk Server 解决方案将最终会遇到文件 I/O 争用，如增加吞吐量。 I/O 子系统或存储引擎是任意关系数据库的关键组件。 成功的数据库实现通常需要在项目早期阶段进行仔细的规划。 此规划应考虑以下问题：  
  
- 若要使用，例如 RAID （独立磁盘冗余阵列） 设备的磁盘硬件哪种类型。 
  
- 如何使用文件和文件组的磁盘上的数据分配。 有关使用 SQL Server 中的文件和文件组的详细信息，请参阅[数据库文件和文件组](https://docs.microsoft.com/sql/relational-databases/databases/database-files-and-filegroups)。
  
- 实现用于访问数据时提高性能的最佳索引设计。 关于设计索引的详细信息，请参阅[设计索引](https://docs.microsoft.com/sql/relational-databases/sql-server-index-design-guide)。
  
- 如何设置 SQL Server 以获得最佳性能的配置参数。 为 SQL Server 设置最佳的配置参数的详细信息，请参阅[服务器配置选项](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)。 
  
  BizTalk Server 的主要设计目标之一是确保消息**永远不会**丢失。 为了缓解问题消息丢失的可能性，消息通常会写入到 MessageBox 数据库，处理消息。 当业务流程处理消息时，会将消息写入到 MessageBox 数据库在业务流程中每个暂留点。 这些持久化点会导致 MessageBox，以将消息和相关的状态写入物理磁盘。 在更高的吞吐量，此持久性相当大的磁盘争用情况，并可能会成为瓶颈。  
  
  进行最佳使用的文件和 SQL Server 中的文件组功能已被证实将有效地解决文件 IO 瓶颈并改进 BizTalk Server 解决方案中的整体性能。 仅应由有经验的 SQL Server 数据库管理员和 BizTalk Server 数据库已正确备份仅后所有完成这种优化。 应在 BizTalk Server 环境中的所有 SQL Server 计算机上执行此优化。  
  
  若要提高数据库性能，因为此功能可让数据库将创建跨多个磁盘的多个磁盘控制器或 RAID （独立磁盘冗余阵列） 系统，可以利用 SQL Server 文件和文件组。 例如，如果您的计算机有四个磁盘，你可以创建三个数据文件和一个日志文件，每个磁盘上放置一个文件组成的数据库。 访问数据时，四个读/写磁头可以同时访问数据并行。 这极大地加快数据库操作。 有关实现为 SQL Server 磁盘硬件解决方案的详细信息，请参阅"数据库的性能"SQL Server 联机丛书中位于[ http://go.microsoft.com/fwlink/?LinkID=71419 ](http://go.microsoft.com/fwlink/?LinkID=71419)。  
  
  此外，文件和文件组允许数据布局，因为可以在特定的文件组中创建表。 这提高了性能，因为给定表的所有文件 I/O 可以都定向到特定的磁盘。 例如，经常使用的表可以放在位于一个磁盘上的文件组中的文件，并且在数据库中的其他不常访问的表可以位于另一个文件，位于第二个磁盘上的组中的不同文件。  
  
  中相当详细地讨论了文件 IO 瓶颈[数据库层的瓶颈](../technical-guides/bottlenecks-in-the-database-tier.md)。 文件 I/O (磁盘 I/O) 是一个瓶颈的最常见的指示符"物理磁盘： Average Disk Queue Length"计数器的值。 当"物理磁盘： Average Disk Queue Length"计数器的值大于约 3 在任何 SQL 服务器上任何给定的磁盘时，然后文件 I/O 可能是瓶颈。  
  
  如果将应用文件组的优化不能解决文件 I/O 瓶颈问题，然后它可能需要通过添加额外的物理或 SAN 驱动器增加磁盘子系统的吞吐量。  
  
  本主题介绍了如何手动应用文件和文件组的优化，但这些优化也可编写脚本。 在本主题末尾提供了一个示例 SQL 脚本。 请务必注意此脚本需要修改以适应文件、 文件组，以及任何给定的 BizTalk Server 解决方案所使用的 SQL Server 数据库的磁盘配置。  
  
 
## <a name="databases-created-with-a-default-biztalk-server-configuration"></a>使用默认的 BizTalk Server 配置创建的数据库  
 具体取决于可能在 SQL Server 中创建多达 13 不同数据库中配置 BizTalk Server 和所有这些数据库的默认文件组中创建时启用功能。 SQL Server 的默认文件组是主文件组，除非使用 ALTER DATABASE 命令更改默认文件组。 下表列出了配置 BizTalk Server 时，会启用所有功能，如果在 SQL Server 中创建的数据库。  
  
### <a name="biztalk-server-databases"></a>BizTalk Server 数据库  
  
||||  
|-|-|-|  
|**“数据库”**|**默认数据库名称**|**说明**|  
|配置数据库|BizTalkMgmtDb|中央元信息存储在 BizTalk Server 组中的 BizTalk Server 的所有实例。|  
|BizTalk MessageBox 数据库|BizTalkMsgBoxDb|存储订阅谓词。 它是一个主机平台，并使每个 BizTalk Server 主机的队列和状态表。 MessageBox 数据库还存储消息和消息属性。|  
|BizTalk 跟踪数据库|BizTalkDTADb|存储业务和运行状况监视 BizTalk Server 跟踪引擎所跟踪的数据。|  
|BAM 分析数据库|BAMAnalysis|保留业务活动的聚合历史数据的 SQL Server Analysis Services 数据库。|  
|BAM 星型架构数据库|BAMStarSchema|将转换为进行 OLAP 处理从业务活动监视收集的数据。 使用 BAM 分析数据库时，此数据库是必需的。|  
|BAM 主导入数据库|BAMPrimaryImport|活动实例后存储来自业务活动，然后查询的进度和数据的事件。 此数据库还会执行实时聚合。|  
|BAM 存档数据库|BAMArchive|存储订阅谓词。 BAM 存档数据库最大程度减少 BAM 主导入数据库中的业务活动数据的累计。|  
|SSO 数据库|SSODB|安全地存储配置信息的接收位置。 将信息存储为 SSO 关联应用程序，以及所有关联应用程序的加密的用户凭据。|  
|规则引擎数据库|BizTalkRuleEngineDb|存储库：<br /><br /> -策略，这是一组相关的规则。<br />-词汇，即是规则中的数据引用的用户友好的特定于域的名称的集合。|  
|跟踪分析服务器管理数据库|BizTalkAnalysisDb|存储业务和运行状况监视 OLAP 多维数据集。|  
  
## <a name="separation-of-data-files-and-log-files"></a>分离的数据文件和日志文件  
 如上文所述，默认的 BizTalk Server 配置 MessageBox 数据库将置于默认文件组中的一个文件中。 默认情况下，MessageBox 数据库的数据和事务日志放置在相同的驱动器和路径。 这样做是为了适应单磁盘系统。 单个文件/文件组/磁盘配置**不是最佳选择**在生产环境中。 为了获得最佳性能，数据文件和日志文件应放置在不同的磁盘上。  
  
> [!NOTE]  
>  日志文件永远不会是一个文件组的一部分。 从数据空间分开管理日志空间。  
  
## <a name="the-8020-rule-of-distributing-biztalk-server-databases"></a>将 BizTalk Server 数据库分发的 80/20 规则  
 在大多数 BizTalk Server 解决方案中，由于磁盘 I/O 争用或数据库争用的主要来源是争用的 BizTalk Server MessageBox 数据库。 这是在单个和多 MessageBox 的情况下，则返回 true。 它有理由假定 80%的值的分布 BizTalk 数据库，将派生自优化的 MessageBox 数据文件和日志文件。 下面详细介绍了在示例方案侧重于优化 MessageBox 数据库的数据文件。 这些然后可以执行步骤的其他数据库根据需要例如，如果解决方案需要大量跟踪，则还可以优化跟踪数据库。  
  
## <a name="manually-adding-files-to-the-messagebox-database-step-by-step"></a>手动将文件添加到 MessageBox 数据库，分步  
 本部分介绍可手动将文件添加到 MessageBox 数据库的步骤。 在此示例中添加三个文件组，然后将文件添加到每个文件组，以跨多个磁盘为 MessageBox 分发文件。   
  
> [!NOTE]  
>  为了完成本指南中的性能测试，通过使用将作为 BizTalk Server 性能优化指南的一部分发布的脚本优化了文件组。 出于参考目的提供了下面的步骤。  
  
### <a name="manually-adding-files-to-the-messagebox-database-on-sql-server"></a>手动将文件添加到 SQL Server 上的 MessageBox 数据库
  
1. 打开**SQL Server Management Studio**以显示**连接到服务器**对话框。  
  
     ![SQL Server 管理登录屏幕](../technical-guides/media/641a03f4-362c-4dde-8c9d-ac313d8881e3.gif "641a03f4-362c-4dde-8c9d-ac313d8881e3")  
  
2.  在中**服务器名称**字段**连接到服务器**对话框中，输入包含 BizTalk Server MessageBox 数据库的 SQL Server 实例的名称，然后单击**连接**按钮以显示**Microsoft SQL Server Management Studio**对话框。  
  
     在中**对象资源管理器**窗格中的 SQL Server Management Studio 中，展开**数据库**若要查看数据库的 SQL Server 实例。  
  
     ![SQL Server Management Studio、 对象资源管理器](../technical-guides/media/81f13912-fedc-48c3-9669-c18863e637b1.gif "81f13912-fedc-48c3-9669-c18863e637b1")  
  
3.  右键单击要为其添加文件，然后单击数据库**属性**以显示**数据库属性**数据库对话框。  
  
     ![SQL Server 数据库属性对话框](../technical-guides/media/82ae7c11-5b3a-4312-876c-70876abdd65c.gif "82ae7c11-5b3a-4312-876c-70876abdd65c")  
  
4.  在中**数据库属性**对话框中，选择**文件组**页。 单击**添加**按钮以创建 BizTalkMsgBoxDb 数据库的其他文件组。 在以下示例中，添加三个其他文件组。  
  
     ![SQL Server，向数据库添加文件组](../technical-guides/media/6be47c0e-06c3-45d9-bce2-a42453da7d19.gif "6be47c0e-06c3-45d9-bce2-a42453da7d19")  
  
5.  在 **“数据库属性”** 对话框中，选择 **“文件”** 页。  
  
     单击**外**按钮以创建要添加到的文件组的其他文件，然后单击**确定**。 MessageBox 数据库现在分布在多个磁盘，它将提供性能优势明显超过单个磁盘配置。  
  
     在下面的示例中，为每个前面创建的文件组创建一个文件和每个文件都放置在单独的磁盘。  
  
     ![SQL Server，将文件添加到文件组](../technical-guides/media/d5d5c5df-d483-4f01-8128-f98228de51b9.gif "d5d5c5df-d483-4f01-8128-f98228de51b9")  
  
## <a name="sample-sql-script-for-adding-filegroups-and-files-to-the-biztalk-messagebox-database"></a>用于将文件组和文件添加到 BizTalk MessageBox 数据库的示例 SQL 脚本  
 下面的示例 SQL 脚本执行手动完成上一节中的相同任务。  
此示例脚本假定存在通过 J.的非重复逻辑驱动器 G该脚本创建文件组和每个文件组的文件，并将 J 驱动器上的日志文件。  
  
> [!NOTE]  
>  SQL Server 按顺序写入其日志文件，因为意识到通过创建针对 SQL Server 数据库的多个日志文件没有的性能优势。  
  
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
  
 下面的示例 SQL 脚本可用来将特定的文件组设置为默认文件组：  
  
```  
USE [BizTalkMsgBoxDb]  
GO  
declare @isdefault bit  
SELECT @isdefault=convert(bit, (status & 0x10)) FROM sysfilegroups WHERE groupname=N'BTS_MsgBox_FG1'  
if(@isdefault=0)  
ALTER DATABASE [BizTalkMsgBoxDb] MODIFY FILEGROUP [BTS_MsgBox_FG1] DEFAULT  
GO  
```  
  
 对脚本编写的优点是脚本可以执行多个任务快速、 准确地说，可重现和减少人为错误的可能性。 脚本的缺点是脚本的，编写不正确的执行可能会导致严重的问题，可能需要重新配置从零开始的 BizTalk Server 数据库。 因此，它是最重要的 SQL 脚本，如本主题中列出的示例脚本进行全面测试才能在生产环境中正在执行。