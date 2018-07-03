---
title: 优化数据库文件组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d7fa4c9-e504-4f43-a308-517a4a574c26
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e15f03a0891bff6204c6a8d49cae9dc032caef1f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022699"
---
# <a name="optimizing-filegroups-for-the-databases"></a>优化文件组的数据库
文件输入/输出 (I/O) 争用通常是限制因素或瓶颈，在生产 BizTalk Server 环境中。 BizTalk Server 是一个非常数据库密集型应用程序和 BizTalk Server 使用的 SQL Server 数据库又是大量占用非常文件 I/O。 本主题介绍如何以最佳方式使用的文件和文件组功能的 SQL Server 以最小化的匹配项的文件 I/O 争用和提高 BizTalk Server 解决方案的整体性能。  
  
## <a name="overview"></a>概述  
 每个 BizTalk Server 解决方案将最终会遇到文件 I/O 争用，如增加吞吐量。 I/O 子系统或存储引擎是任意关系数据库的关键组件。 成功的数据库实现通常要求在项目的初期阶段进行仔细的规划。 此规划应考虑下列事项：  
  
- 使用哪种类型的磁盘硬件，如 RAID（独立磁盘冗余阵列）设备。 
  
- 如何使用文件和文件组的磁盘上的数据分配。 有关使用 SQL Server 中的文件和文件组的详细信息，请参阅[数据库文件和文件组](https://docs.microsoft.com/sql/relational-databases/databases/database-files-and-filegroups)。
  
- 实现用于访问数据时提高性能的最佳索引设计。 关于设计索引的详细信息，请参阅[设计索引](https://docs.microsoft.com/sql/relational-databases/sql-server-index-design-guide)。
  
- 如何设置 SQL Server 以获得最佳性能的配置参数。 为 SQL Server 设置最佳的配置参数的详细信息，请参阅[服务器配置选项](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)。
  
  BizTalk Server 的主要设计目标之一是确保消息**永远不会**丢失。 为了缓解问题消息丢失的可能性，消息通常会写入到 MessageBox 数据库，处理消息。 当业务流程处理消息时，会将消息写入到 MessageBox 数据库在业务流程中每个暂留点。 这些持久化点会导致 MessageBox，以将消息和相关的状态写入物理磁盘。 在更高的吞吐量，此持久性相当大的磁盘争用情况，并可能会成为瓶颈。  
  
  进行最佳使用的文件和 SQL Server 中的文件组功能已被证实将有效地解决文件 IO 瓶颈并改进 BizTalk Server 解决方案中的整体性能。  
  
> [!NOTE]  
>  仅应由有经验的 SQL Server 数据库管理员和 BizTalk Server 数据库已正确备份仅后所有完成这种优化。 应在 BizTalk Server 环境中的所有 SQL Server 计算机上执行此优化。  
  
 SQL Server 文件和文件组可用来提高数据库性能，因为此功能允许多个磁盘控制器跨多个磁盘，创建数据库或 RAID （独立磁盘冗余阵列） 系统。 例如，如果计算机上有四个磁盘，那么可以创建一个由三个数据文件和一个日志文件组成的数据库，每个磁盘上放置一个文件。 访问数据时，四个读/写磁头可以同时访问数据并行。 这极大地加快数据库操作。 有关实现为 SQL Server 磁盘硬件解决方案的详细信息，请参阅[数据库的性能](http://go.microsoft.com/fwlink/?LinkID=71419)(http://go.microsoft.com/fwlink/?LinkID=71419) SQL Server 联机丛书中。  
  
 此外，文件和文件组允许数据布局，因为可以在特定的文件组中创建表。 这提高了性能，因为给定表的所有文件 I/O 可以都定向到特定的磁盘。 例如，经常使用的表可以放在位于一个磁盘上的文件组中的文件，并且在数据库中的其他不常访问的表可以位于另一个文件，位于第二个磁盘上的组中的不同文件。  
  
 中相当详细地讨论了文件 I/O 瓶颈[数据库层的瓶颈](../technical-guides/bottlenecks-in-the-database-tier.md)。 文件 I/O （磁盘 I/O） 是一个瓶颈的最常见的指示符"物理磁盘： Average Disk Queue Length"计数器的值。 当"物理磁盘： Average Disk Queue Length"计数器的值大于约 3 任何给定的磁盘上的任何运行 SQL Server 计算机时，然后文件 I/O 可能是瓶颈。  
  
 如果将应用文件组的优化不能解决文件 I/O 瓶颈问题，可能需要通过添加额外的物理或 SAN 驱动器增加磁盘子系统的吞吐量。  
  
 本主题介绍如何手动应用文件和文件组的优化，但这些优化也可编写脚本。 中提供的示例 SQL 脚本[BizTalk Server MessageBox 数据库文件组 SQL 脚本](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)。  
  
> [!NOTE]
>  请务必注意此脚本需要修改以适应文件、 文件组，以及任何给定的 BizTalk Server 解决方案由 SQL Server 数据库的磁盘配置。  
> 
> [!NOTE]
>  本主题还介绍如何创建多个文件和文件组为 BizTalk MessageBox 数据库。 建议的文件和文件组的所有 BizTalk Server 数据库的详尽列表，请参阅"附录 B"的[BizTalk Server 数据库优化](http://go.microsoft.com/fwlink/?LinkID=101578)白皮书 (http://go.microsoft.com/fwlink/?LinkID=101578)。  
> 
> [!NOTE]
>  即使[BizTalk Server 数据库优化](http://go.microsoft.com/fwlink/?LinkID=101578)白皮书 (<http://go.microsoft.com/fwlink/?LinkID=101578>) 编写使用[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]记住，同一原则适用于 BizTalk Server。  
  
## <a name="databases-created-with-a-default-biztalk-server-configuration"></a>使用默认的 BizTalk Server 配置创建的数据库  
 具体取决于该功能启用时可能会在 SQL Server 中创建最多支持 13 不同数据库中配置 BizTalk Server 中，并在默认文件组中创建所有这些数据库。 SQL Server 的默认文件组是主文件组，除非使用 ALTER DATABASE 命令更改默认文件组。 下表列出了配置 BizTalk Server 时，会启用所有功能，如果在 SQL Server 中创建的数据库。  
  
### <a name="biztalk-server-databases"></a>BizTalk Server 数据库  
  
||||  
|-|-|-|  
|**“数据库”**|**默认数据库名称**|**Description**|  
|配置数据库|BizTalkMgmtDb|中央元信息存储在 BizTalk Server 组中的 BizTalk Server 的所有实例。|  
|BizTalk MessageBox 数据库|BizTalkMsgBoxDb|存储订阅谓词。 它是一个主机平台，并使每个 BizTalk Server 主机的队列和状态表。 MessageBox 数据库还存储消息和消息属性。|  
|BizTalk 跟踪数据库|BizTalkDTADb|存储业务和运行状况监视 BizTalk Server 跟踪引擎所跟踪的数据。|  
|BAM 分析数据库|BAMAnalysis|保留业务活动的聚合历史数据的 SQL Server Analysis Services 数据库。|  
|BAM 星型架构数据库|BAMStarSchema|将转换为进行 OLAP 处理从业务活动监视收集的数据。 使用 BAM 分析数据库时，此数据库是必需的。|  
|BAM 主导入数据库|BAMPrimaryImport|活动实例后存储来自业务活动，然后查询的进度和数据的事件。 此数据库还会执行实时聚合。|  
|BAM 存档数据库|BAMArchive|存储订阅谓词。 BAM 存档数据库最大程度减少 BAM 主导入数据库中的业务活动数据的累计。|  
|SSO 数据库|SSODB|安全地存储配置信息的接收位置。 将信息存储为 SSO 关联应用程序，以及所有关联应用程序的加密的用户凭据。|  
|规则引擎数据库|BizTalkRuleEngineDb|存储库：<br /><br /> -策略，这是一组相关的规则。<br />-词汇，即是规则中的数据引用的用户友好的特定于域的名称的集合。|  
|BizTalk 基本 EDI 数据库|BizTalkEDIDb|EDI 文档跟踪和处理数据存储。|  
|工作流服务管理数据库|BizTalkHwsDb|存储由 BizTalk 工作流服务所需的管理信息。|  
|贸易合作伙伴管理数据库|TPM|业务活动服务 (BAS) 贸易合作伙伴数据存储。|  
|跟踪分析服务器管理数据库|BizTalkAnalysisDb|存储业务和运行状况监视 OLAP 多维数据集。|  
  
## <a name="separation-of-data-files-and-log-files"></a>分离的数据文件和日志文件  
 如前文所述，默认的 BizTalk Server 配置 MessageBox 数据库将置于默认文件组中的一个文件中。 默认情况下，MessageBox 数据库的数据和事务日志放置在相同的驱动器和路径。 这样做是为了适应单磁盘系统。 单个文件/文件组/磁盘配置**不是最佳选择**在生产环境中。 为了获得最佳性能，数据文件和日志文件应放置在不同的磁盘上。  
  
> [!NOTE]  
>  日志文件不包括在文件组内。 日志空间与数据空间分开管理。  
  
## <a name="the-8020-rule-of-distributing-biztalk-server-databases"></a>将 BizTalk Server 数据库分发的 80/20 规则  
 在大多数 BizTalk Server 解决方案中，由于磁盘 I/O 争用或数据库争用的主要来源是争用的 BizTalk Server MessageBox 数据库。 这是在单个和多 MessageBox 的情况下，则返回 true。 它有理由假定 80%的值的分布 BizTalk 数据库，将派生自优化的 MessageBox 数据文件和日志文件。 下面详细介绍了在示例方案侧重于优化 MessageBox 数据库的数据文件。 根据需要然后可以为其他数据库遵循这些步骤。 例如，如果解决方案需要广泛的跟踪，跟踪数据库还可以进行优化。  
  
## <a name="manually-adding-files-to-the-messagebox-database-step-by-step"></a>手动将文件添加到 MessageBox 数据库，分步  
 本部分的主题介绍可手动将文件添加到 MessageBox 数据库的步骤。 在此示例中添加三个文件组，然后将文件添加到每个文件组，以跨多个磁盘为 MessageBox 分发文件。
  
### <a name="manually-adding-files-to-the-messagebox-database-on-sql-server"></a>手动将文件添加到 SQL Server 上的 MessageBox 数据库
   
1.  打开**SQL Server Management Studio**以显示**连接到服务器**对话框。  
  
     ![SQL Server 登录名屏幕](../technical-guides/media/sqlserver2008r2-loginscreen.gif "SQLServer2008R2 登录屏幕")  
  
2.  在中**服务器名称**编辑框**连接到服务器**对话框中，输入包含 BizTalk Server MessageBox 数据库的 SQL Server 实例的名称，单击**Connect**以显示 SQL Server Management Studio。 在中**对象资源管理器**窗格中的 SQL Server Management Studio 中，展开**数据库**若要查看数据库的 SQL Server 实例。  
  
     ![SQL Server 2005 Management Studio、 对象资源管理器](../technical-guides/media/81f13912-fedc-48c3-9669-c18863e637b1.gif "81f13912-fedc-48c3-9669-c18863e637b1")  
  
3.  右键单击该数据库向其添加文件，然后依次**属性**以显示**数据库属性**数据库对话框。  
  
     ![SQL Server 2005 数据库属性对话框](../technical-guides/media/82ae7c11-5b3a-4312-876c-70876abdd65c.gif "82ae7c11-5b3a-4312-876c-70876abdd65c")  
  
4.  在中**数据库属性**对话框中，选择**文件组**页。 若要创建的 BizTalkMsgBoxDb 数据库的其他文件组，请单击**添加**。 在以下示例中，添加三个其他文件组。  
  
     ![将文件组添加到数据库的 SQL Server 2005](../technical-guides/media/6be47c0e-06c3-45d9-bce2-a42453da7d19.gif "6be47c0e-06c3-45d9-bce2-a42453da7d19")  
  
5.  在 **“数据库属性”** 对话框中，选择 **“文件”** 页。  
  
     若要创建要添加到的文件组的其他文件，请单击**外**，然后单击**确定**。 MessageBox 数据库现在分布在多个磁盘，它将提供性能优势明显超过单个磁盘配置。  
  
     在以下示例中，为每个前面创建的文件组创建一个文件和每个文件都放置在单独的磁盘。  
  
     ![SQL Server 2005，将文件添加到文件组](../technical-guides/media/d5d5c5df-d483-4f01-8128-f98228de51b9.gif "d5d5c5df-d483-4f01-8128-f98228de51b9")  
  
## <a name="sample-sql-script-for-adding-filegroups-and-files-to-the-biztalk-messagebox-database"></a>用于将文件组和文件添加到 BizTalk MessageBox 数据库的示例 SQL 脚本  
 本指南包含用于将文件组和文件添加到 BizTalk Server MessageBox 数据库的 SQL 脚本。  
  
> [!NOTE]  
>  SQL Server 按顺序写入其日志文件，因为意识到通过创建针对 SQL Server 数据库的多个日志文件没有的性能优势。  
  
 若要运行此脚本，请执行以下步骤：  
  
1. 打开**SQL Server Management Studio**以显示**连接到服务器**对话框。  
  
2. 在中**服务器名称**编辑框**连接到服务器**对话框中，输入包含 BizTalk Server MessageBox 数据库的 SQL Server 实例的名称，单击**Connect**可显示 SQL Server Management Studio 对话框。  
  
3. 在 SQL Server Management Studio 中，单击**文件**菜单，依次指向**新建**，然后单击**使用当前连接查询**SQL 查询编辑器中启动。  
  
4. 复制中的示例脚本[BizTalk Server MessageBox 数据库文件组 SQL 脚本](../technical-guides/biztalk-server-messagebox-database-filegroups-sql-script.md)到查询编辑器中。  
  
5. 编辑脚本以匹配你的 BizTalk 服务器环境中的参数和执行脚本。  
  
   对脚本编写的优点是脚本可以执行多个任务快速、 准确地说，可重现和减少人为错误的可能性。 脚本的缺点是脚本的，编写不正确的执行可能会导致严重的问题，可能需要重新配置从零开始的 BizTalk Server 数据库。  
  
> [!IMPORTANT]  
>  它最重要的是，SQL 脚本如本指南中的示例脚本进行彻底的测试之前正在生产环境中执行。  
  
## <a name="see-also"></a>请参阅  
 [优化数据库性能](../technical-guides/optimizing-database-performance.md)