---
title: 配置后步骤用于优化环境 |Microsoft Docs
description: 要在安装和配置 BizTalk Server 后完成的任务包括配置的 SQL 代理作业、 安装 EDI 架构、 创建主机和主机实例以及 BizTalk Server 中的详细信息
ms.custom: ''
ms.prod: biztalk-server
ms.date: 09/27/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0fef6ea-e7cc-4ea9-936d-5d638bc43feb
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3562487e70557ec57a686d8b0109f61eccaa8dce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394018"
---
# <a name="post-configuration-steps-to-optimize-your-environment"></a>用于优化环境的配置后步骤
配置后步骤，以帮助提高性能，维护 BizTalk 环境，并安装 EDI 架构。

## <a name="disable-shared-memory-protocol-in-sql-server"></a>禁用 SQL Server 中的 Shared Memory 协议

1. 打开 **SQL Server 配置管理器**。
2. 展开**SQL Server 网络配置**，然后选择**MSSQLSERVER 的协议**。
3. 右键单击**Shared Memory**，然后选择**禁用**。
4. 选择**SQL Server Services**，右键单击**SQL Server (MSSQLServer)**，然后选择**重启**。
5. 关闭**SQL Server 配置管理器**。

## <a name="configure-the-sql-agent-jobs"></a>配置 SQL 代理作业

1. **SQL Server Management Studio**，并连接到**数据库引擎**。
2. 展开 **“SQL Server 代理”**，然后展开 **“作业”**。 配置以下作业：  

    作业名称  |Description  |为什么需要它  
    ---------|---------|---------
    备份 BizTalk Server | 备份 BizTalk Server 数据库和日志文件。 在配置该作业，确定频率和文件位置等参数。<br/><br/>以下链接介绍了 SQL 代理作业和其参数：<br/><br/>[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)<br/>[如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)|此 SQL 代理作业会截断事务日志，从而可帮助提高性能。<br/><br/>此作业不会移除或删除备份文件，包括较早的文件。 若要删除备份文件，请参阅"备份 BizTalk Server"作业失败时的备份文件累积一段时间中的 Microsoft BizTalk Server 数据库服务器。
    DTA 清除和存档 |截断并存档 BizTalk Server 跟踪数据库 (BizTalkDTADb)。 在配置该作业，确定参数喜欢多长时间内将保存已完成的实例以及还有多少天，以保留所有数据。<br/><br/>以下链接介绍了 SQL 代理作业和其参数： <br/><br/>[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)<br/>[如何配置 DTA 清除和存档作业](../core/how-to-configure-the-dta-purge-and-archive-job.md)|此 SQL 代理作业通过维护跟踪主机和清除跟踪事件会直接影响性能。

## <a name="maintain-your-backup-files"></a>维护备份文件

BizTalk Server 不包括任何作业要删除备份文件。 因此，如何维护备份文件是由您决定。 许多用户创建 sp_DeleteBackupHistoryAndFiles 存储过程，然后直接在备份 BizTalk Server 作业中调用此存储的过程。 某些用户创建维护计划。 由您的选择。 本主题列出了这两个选项。

#### <a name="option-1-create-the-spdeletebackuphistoryandfiles-stored-procedure"></a>选项 1：创建 sp_DeleteBackupHistoryAndFiles 存储过程

1. 在 SQL Server Management Studio 中，选择 BizTalk 管理数据库 (BizTalkMgmtDb)。 
2. 选择**新查询**，并运行以下 T-SQL 脚本创建 sp_DeleteBackupHistoryAndFiles 存储过程： 

    ```
    CREATE PROCEDURE [dbo].[sp_DeleteBackupHistoryAndFiles] @DaysToKeep smallint = null
    AS

    BEGIN
    set nocount on
    IF @DaysToKeep IS NULL OR @DaysToKeep <= 1
    RETURN
    /*
    Only delete full sets
    If a set spans a day in such a way that some items fall into the deleted group and the other does not, do not delete the set
    */

    DECLARE DeleteBackupFiles CURSOR
    FOR SELECT 'del "' + [BackupFileLocation] + '\' + [BackupFileName] + '"' FROM [adm_BackupHistory]
    WHERE  datediff( dd, [BackupDateTime], getdate() ) >= @DaysToKeep
    AND [BackupSetId] NOT IN ( SELECT [BackupSetId] FROM [dbo].[adm_BackupHistory] [h2] WHERE [h2].[BackupSetId] = [BackupSetId] AND datediff( dd, [h2].[BackupDateTime], getdate() ) < @DaysToKeep )

    DECLARE @cmd varchar(400)
    OPEN DeleteBackupFiles
    FETCH NEXT FROM DeleteBackupFiles INTO @cmd
    WHILE (@@fetch_status <> -1)
    BEGIN
        IF (@@fetch_status <> -2)
        BEGIN
            EXEC master.dbo.xp_cmdshell @cmd, NO_OUTPUT
            delete from [adm_BackupHistory] WHERE CURRENT OF DeleteBackupFiles
            print @cmd
        END
        FETCH NEXT FROM DeleteBackupFiles INTO @cmd
    END

    CLOSE DeleteBackupFiles
    DEALLOCATE DeleteBackupFiles
    END
    GO
    ```

3. 打开备份 BizTalk Server 作业，并选择**步骤**。
4. 编辑**清除备份历史记录**步骤，以便调用新*sp_DeleteBackupHistoryAndFiles*存储过程而不是上一*sp_DeleteBackupHistory*存储的过程。
5. 选择**确定**以保存所做的更改。

#### <a name="option-2-create-a-maintenance-plan"></a>选项 2：创建维护计划

1. 在 SQL Server Management Studio 中，展开**管理**，右键单击**维护计划**，然后选择**维护计划向导**。
2. 命名计划 (例如，将其命名*清除备份文件*)，然后选择**更改**按钮旁边**计划**。
3. 选择你想要清除备份文件的频率。 这些设置是完全取决于您。 选择“确定”，然后选择“下一步”。
4. 选择**清除维护任务**，然后选择**下一步**。
5. 在中**清除任务**窗口中，转到**搜索文件夹并删除文件...**，选择备份文件夹 (也许 f:\BizTalkBackUps)，然后输入 **.bak**文件扩展名。 您还可以选择根据保留时间删除文件。 如果你想要删除早于 3 周的文件，例如，输入 3。 选择“**下一步**”。
6. 完成向导并输入所需的任何其他信息。 选择“完成”。


## <a name="install-edi-schemas-and-more-edi-as2-configuration"></a>安装 EDI 架构和更多 EDI AS2 配置
 EANCOM、 EDIFACT、 HIPAA 和 X12 架构文件都包括在名为 MicrosoftEdiXSDTemplates.exe 的自解压缩可执行文件。 若要创建 EDI 解决方案，请解压缩这些文件，并随项目部署。 若要安装并解压缩这些文件：  

1. 运行[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]安装，然后安装**开发人员工具和 SDK**组件。 此组件将 MicrosoftEdiXSDTemplates.exe EDI 架构文件下载到 \XSD_Schema\EDI 文件夹中。  

   > [!NOTE]
   > 如果升级[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，在安装中的 MicrosoftEdiXSDTemplates.exe 文件将替换为与升级关联的新的 MicrosoftEdiXSDTemplates.exe 文件。 如果你需要上一个架构，则备份上一个 MicrosoftEdiXSDTemplates.exe 文件。  
   > 
   > [!NOTE]
   > 如果在升级时升级消息架构[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]到更高版本中，您可能会遇到的问题，使用更新后的架构，或者您可能必须执行其他升级步骤。 "更新架构的注意事项"一节中，请参阅[更新应用程序的重要注意事项](../core/important-considerations-for-updating-applications.md)

2. 转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\XSD_Schema\EDI，然后双击 MicrosoftEdiXSDTemplates.exe。  

3. 架构解压缩到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\XSD_Schema\EDI。 在解压缩架构时，它们都存储在 EANCOM、 EDIFACT、 HIPAA 和 X12 文件夹。  

#### <a name="add-a-reference-to-the-biztalk-server-edi-application"></a>添加对 BizTalk Server EDI 应用程序的引用  
 在部署的 EDI 架构、 管道和业务流程**BizTalk EDI 应用程序**。 若要将用作 EDI 应用程序的任何其他应用程序，添加到引用**BizTalk EDI 应用程序**。 步骤：  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**应用程序**。 右键单击你想要为 EDI 使用的应用程序 (如*BizTalk Application 1*)，选择**添加**，然后选择**引用**。  

2. 选择**BizTalk EDI 应用程序**，然后选择**确定**以保存所做的更改。  

> [!TIP]
>  若要查看对其他应用程序的引用，请右键单击任何应用程序，然后选择**属性**。 选择**引用**。 您还可以添加新的引用，并删除现有的引用。  

> [!NOTE]
>  不要对 BizTalk EDI 应用程序中添加自定义项目。 最好是将保留该应用程序作为-是。  

#### <a name="start-batch-orchestrations"></a>启动批处理业务流程  
 如果启用了用于接收和/或发送 EDI 批的参与方，然后启动批处理业务流程。 这些业务流程不会启动安装向导或配置向导。 步骤：  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**BizTalk EDI 应用程序**，然后选择**业务流程**。  

2. 右键单击每个以下的业务流程，然后选择**启动**:  

   -   Microsoft.BizTalk.Edi.BatchSuspendOrchestration.BatchElementSuspendService (程序集：Microsoft.BizTalk.Edi.BatchingOrchestration.dll)  

   -   Microsoft.BizTalk.Edi.BatchingOrchestration.BatchingService (程序集：Microsoft.BizTalk.Edi.BatchingOrchestration.dll)  

   -   Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService (程序集：Microsoft.BizTalk.Edi.RoutingOrchestration.dll)  

> [!NOTE]
>  如果接收和/或发送 EDI 批，则只应启动 EDI 批处理业务流程。 在系统不接收或发送 EDI 批时启动它们可能会影响系统性能。  

#### <a name="migrate-edi-artifacts-from-a-previous-biztalk-version"></a>从早期版本的 BizTalk 迁移 EDI 项目  
 在中管理贸易合作伙伴的方式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]已更新中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2010年及更新版本。 在前面[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本中，创建参与方是仅为贸易合作伙伴，而不是针对托管的合作伙伴[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2010年及更高版本，必须为所有贸易合作伙伴，包括托管的合作伙伴创建参与方[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在以前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本，编码 （X12 和 EDIFACT） 和传输 (AS2) 协议属性在参与方级别定义。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2010年及更新版本，这些属性通过协议定义。  

 若要从早期版本迁移参与方数据[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含参与方迁移工具。 请考虑以下迁移路径：  


| [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 版本  |                                                                                                                                                                                                                                                                                                                                     迁移路径                                                                                                                                                                                                                                                                                                                                      |
|---------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]**       | 升级到 BizTalk Server 2009。 然后，使用附带的参与方迁移工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2013/2013 R2 迁移到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2013/2013 R2。<br /><br /> **或者**，使用附带的参与方迁移工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2013/2013 R2 迁移到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2010年。 然后，升级到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2013/2013 R2。 |
| **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009** |                                                                                                                                                                                                           使用附带的参与方迁移工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2013/2013 R2 直接迁移到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2013/2013 R2。                                                                                                                                                                                                            |
| **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2010** |                                                                                                                                                                                                                                                                                       升级到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2013/2013 R2。                                                                                                                                                                                                                                                                                       |

 参与方迁移工具位于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]介质的 \PartyMigrationTool 文件夹下。  


## <a name="install-biztalk-health-monitor-bhm"></a>安装 BizTalk 运行状况监视器 (BHM)

BizTalk 运行状况监视器提供了一个仪表板来创建和查看 MessageBox 查看器的报表、 创建自定义查询、 运行终止符任务、 监视多个 BizTalk 环境，和的详细信息。 如果你负责 BizTalk 环境，我们建议安装和使用此工具检查 BizTalk 环境的运行状况并对其进行维护。

关键链接：

[下载 BHM](https://www.microsoft.com/download/details.aspx?id=43716)  
[安装 BHM](http://social.technet.microsoft.com/wiki/contents/articles/26466.biztalk-server-how-to-install-the-new-biztalk-health-monitor-snap-in.aspx)  
[BHM 官方博客](https://blogs.msdn.microsoft.com/biztalkhealthmonitor/)

## <a name="create-your-hosts-and-host-instances"></a>创建主机和主机实例
建议将某些关键任务分到单独的主机。 例如，始终创建单独的主机专用于仅跟踪。 创建另一个主机/主机实例，它侧重于接收消息、 用于发送消息，另一个主机/主机实例和业务流程的另一个主机/主机实例。 

提供了此区域中的许多建议。 下面是一些可帮助你开始： 

[管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)  
[为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md)  
[最佳做法：创建和配置 BizTalk Server 主机和主机](http://social.technet.microsoft.com/wiki/contents/articles/19701.biztalk-server-best-practices-create-and-configure-biztalk-server-host-and-host-instances.aspx)  
[在同一计算机上运行多个主机中的业务流程](http://social.technet.microsoft.com/wiki/contents/articles/31183.biztalk-server-running-orchestrations-in-multiple-hosts-on-the-same-computer.aspx)  
[PowerShell 创建和配置 BizTalk Server 主机、 主机实例和处理程序](https://gallery.technet.microsoft.com/PowerShell-to-Configure-43d77916)  
[TechNet Wiki 上的 BizTalk Server 资源](http://social.technet.microsoft.com/wiki/contents/articles/2240.biztalk-server-resources-on-the-technet-wiki.aspx)
