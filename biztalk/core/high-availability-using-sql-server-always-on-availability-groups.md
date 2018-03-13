---
title: "使用 SQL Server Alwayson 可用性组的高可用性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4511a578-77d2-49ee-99bd-f0406ad625d0
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d065013cb4975e6d37e2ab50211c5207852ece64
ms.sourcegitcommit: 6fe505d37e81dc2da43f89548e8977b60a6f5dbd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2018
---
# <a name="high-availability-using-sql-server-always-on-availability-groups"></a>使用 SQL Server Alwayson 可用性组的高可用性
配置使用 SQL Server AlwaysOn 可用性组的高可用性。

> [!TIP] 
[设置 BizTalk Server 2016 使用可用性组实验室](https://skastberg.wordpress.com/2017/02/22/setting-up-my-biztalk-server-2016-using-availability-groups-lab/)提供由 Microsoft 字段工程师编写的分步指南。 它基于实验室环境中，并包含几点。 其签出。  

> [!IMPORTANT]
> * Alwayson 可用性组是从 SQL Server 2016 开始提供。 如果你使用的以前的 SQL Server 版本，本主题不适用于你。 
> * BizTalk Server 2016 支持同步提交模式;不支持异步提交模式。 对于灾难恢复，建议配置 BizTalk Server 中备份作业，并使用日志传送。 请参阅[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md)的具体细节。
> 
>    [可用性模式](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/availability-modes-always-on-availability-groups)详细介绍与 Alwayson 可用性组的提交选项。 


## <a name="background-and-history"></a>背景和历史记录

BizTalk Server 非常依赖于 SQL Server 实现数据持久性。 其他组件和 BizTalk Server 中的主机具有特定角色，集成不同的业务应用程序，如接收、 处理，或将消息路由时。 数据库计算机捕获此工作，并将其保存到磁盘。 

BizTalk 使用 SQL Server 故障转移群集和日志传送来为其本地数据库提供高可用性、 备份和还原和灾难恢复。 Azure IaaS （Azure 虚拟机），在以前版本的 SQL Server 不支持故障转移群集实例 （无 MSDTC 支持）。 因此，BizTalk 没有 HA 解决方案时使用 Azure Vm。

从 SQL Server 2016 开始，SQL Server AlwaysOn 可用性组支持本地和使用 Azure Vm MSDTC。 因此，为 BizTalk 数据库本地或 Azure IaaS 方案中支持 SQL Server 2016 AlwaysOn 功能。 

## <a name="sql-server-2016-alwayson-availability-groups"></a>SQL Server 2016 AlwaysOn 可用性组 
部署 AlwaysOn 可用性组需要 Windows Server 故障转移群集 (WSFC) 群集。 给定可用性组的每个可用性副本必须位于相同 WSFC 群集的不同节点上。 为您创建的每个可用性组创建一个 WSFC 资源组。 WSFC 群集将监视此资源组，以便评估主副本的运行状况。  

下图显示的是一个包含一个主要副本和四个次要副本的可用性组。  
 
 ![SQLAG_PrimaryReplica](../core/media/sqlag-primaryreplica.png)

客户端可以连接到使用可用性组侦听器某一给定的可用性组的主副本。 可用性组侦听器提供一组附加到给定的可用性组以便在客户端连接定向到相应的可用性副本的资源。 

>[!IMPORTANT]
> SQL Server 2016 支持 Windows Server 2016 和 Windows Server 2012 R2 上的 MSDTC 与 AlwaysOn 可用性组 (AG)。 **Windows Server 2012 R2**需要[3090973](https://support.microsoft.com/kb/3090973)用于安装的 Windows 修补程序。 
> **Windows Server 2016**要求[RemoteAccessEnabled 注册表项](https://support.microsoft.com/kb/3182294)启用。

SQL Server 不支持与 AlwaysOn 可用性组的 MSDTC 对于 2016年之前的任何版本。  

SQL Server AlwaysOn 可用性组不支持同一个 SQL Server 实例上的数据库之间的 MSDTC。 这意味着，可以在相同的 SQL server 实例上承载的分布式事务中任何两个 BizTalk 数据库。 对于事务一致性，应在不同的 SQL server 实例上承载 BizTalk 数据库参与分布式事务。 请注意它并不重要 SQL 实例是否在同一台计算机或不同计算机上。  


## <a name="providing-high-availability-for-biztalk-databases-using-alwayson-availability-groups"></a>为使用 AlwaysOn 可用性组的 BizTalk 数据库提供高可用性 
在 BizTalk Server 基本配置中，数据库就会将 9 数据库的最小值创建规则和 BAM 包括。 由于 MSDTC 通过可用性组的限制之前提到过，如下面的配置不能确保事务一致性。 

![SQLAG_NoTrans](../core/media/sqlag-notrans.gif)
 
我们建议 BizTalk Server 数据库被分为以下四个 SQL Server 实例︰
 
| 实例 |角色 |该组中的 BizTalk 数据库  |
|--- | --- | ---|
|1 |身份验证 |SSODB|
|2 |管理 |BizTalkMgmtDb| 
|3 |运行时 |BizTalkMsgBoxDb<br/> BizTalkRulesEngineDb<br/> BAMPrimaryImport<br/>BAMStarSchema <br/>BAMAlertsApplication |
|4 |跟踪 |BizTalkDTADb<br/>EsbItineraryDb<br/>EsbExceptionDb | 
 
在向外扩展的 MessageBox 方案 （具有多个 MessageBox 的配置） 中，没有多个 MessageBox 数据库，并且每个 MessageBox 数据库必须位于其自己的 SQL Server 实例上。 

BizTalk Server 还取决于 SQL Server Analysis Services 和 SQL Server Integration Services 针对 BAM 分析和归档。 SQL Server 不为 Integration Services 或 Azure IaaS 中的 Analysis Services 提供高可用性解决方案。 因此建议其他独立 SQL Server 实例用于 BAMArchive 和 BAMAnalysis Analysis Services 数据库。 对于本地安装，可以设置高可用性配置使用 SQL 故障转移群集实例。 

此配置所示，并且建议用于可用性组中的 BizTalk 数据库︰  

![SQLAG_Recommended](../core/media/sqlag-recommended.png)
 
SQL Server 数据库以及 BizTalk Server 配置还会创建 SQL Server 安全登录名和 SQL 代理作业。 AlwaysOn 可用性组仅提供能够管理可用性组内的数据库。 登录名和 BizTalk 的 SQL 代理作业需要创建和更新/管理手动上所有可用性副本。  

下面列出的 SQL Server 安全登录名都与 BizTalk Server 关联。 您可能必须为你的 BizTalk Server 应用程序创建的其他登录名。 如果是这样，你需要将其托管的 BizTalk 数据库副本的 SQL Server 的每个实例上复制。 

1. BizTalk 应用程序用户 （一个或多个对应于每个进程内主机） 
2. BizTalk 独立主机用户 （一个或多个对应于每个独立的主机） 
3. BizTalk Server Administrators 
4. BizTalk Server B2B Operators 
5. BizTalk Server Operators 
6. SSO Administrators 
7. BAM 警报用户 
8. BAM 管理 Web Services 用户 
9. 规则引擎更新服务帐户 

如果你已创建其他主机或者将更高版本创建其他主机，将此过程的一部分创建的新 SQL 登录名。 你必须确保在相应的副本上手动创建这些 SQL 登录名。

以下 SQL Server 代理作业与 BizTalk Server 相关联。 每个服务器上安装的作业有所不同，具体视安装和配置的功能而定。 在 BizTalk Server 配置会创建大部分这些作业。 部分作业是在配置日志传送时创建的。 需要在其相应的 BizTalk 数据库的 SQL Server 托管副本的每个实例上复制这些作业。 这必须手动执行。 

- BizTalkMgmtDb 作业︰ 
    - 备份 BizTalk Server (BizTalkMgmtDb) 
    - CleanupBTFExpiredEntriesJob_BizTalkMgmtDb 
    - 监视 BizTalk Server (BizTalkMgmtDb) 
- BizTalkMsgBoxDb 作业︰ 
    - MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb 
    - MessageBox_Message_Cleanup_BizTalkMsgBoxDb
    - MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb
    - MessageBox_Parts_Cleanup_BizTalkMsgBoxDb 
    - MessageBox_UpdateStats_BizTalkMsgBoxDb 
    - Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 
    - PurgeSubscriptionsJob_BizTalkMsgBoxDb 
    - TrackedMessages_Copy_BizTalkMsgBoxDb 
- 有关其他 msgboxes 的作业
- BizTalkDTADb 作业︰ 
    - DTA 清除和存档 (BizTalkDTADb) 
- BizTalkRulesEngineDb 作业︰ 
    - Rules_Database_Cleanup_BizTalkRuleEngineDb 
- BAMAlertsApplication 作业︰ 
    - 0 个或多个 DelAlertHistJob 

与不同 SQL 故障转移群集实例，在可用性组中所有副本都是活动、 正在运行，且可用。 SQL 代理作业在故障转移的每个副本上复制的它们将运行相应的副本，而不考虑它目前是否在主角色或辅助角色中。 若要确保仅在当前主副本上执行这些作业，每个作业中的每个步骤必须括在 IF 块中，如所示︰ 

    IF (sys.fn_hadr_is_primary_replica(‘dbname’) = 1)  
    BEGIN  
    …  
    END
  
替换 `‘dbname’` 与相应的数据库名称对其作业配置为运行。 下面的示例演示上 BizTalkMsgBoxDb TrackedMessages_Copy_BizTalkMsgBoxDb 此更改︰ 
 
 ![SQLAG_AgentJob](../core/media/sqlag-agentjob.gif)

### <a name="configure-biztalk-server-when-availability-groups-are-already-set-up"></a>配置 BizTalk Server，可用性组已设置时

1. 检查你的操作系统要求： 
* 对所有**Windows Server 2012 R2**计算机，安装[3090973 MSDTC 修补程序](https://support.microsoft.com/kb/3090973)（将打开知识库文章）
* 对所有**Windows Server 2016**计算机，可让[RemoteAccessEnabled 注册表项](https://support.microsoft.com/kb/3182294)（将打开知识库文章）
2. 请确保至少四个不同 SQL 实例，将托管各种 BizTalk 数据库。 此外应在不同 SQL 实例上设置辅助副本。 这会导致的 8 个 SQL 实例 （1 主要和 1 辅助副本的每个 4 的实例），最小值和最少 4 个可用性组。 请参阅上的图中为此可用性组配置。 请确保可用性组创建的 **每数据库 DTC 支持** 选项，因为以后不能更改。 
3. 当配置 BizTalk Server 和指定的 SQL server 名称，则可使用可用性组侦听器名称而不是实际计算机名称。 这在当前主副本上创建 BizTalk 数据库、 登录名和 SQL 代理作业。 
4. 停止 BizTalk 处理 （主机实例，SSO 服务、 IIS，规则引擎更新服务、 BAMAlerts 服务和等等），并停止 SQL 代理作业。 
5. 现在将 BIzTalk 数据库添加到各自的可用性组。 
6. 括起的 SQL 代理作业步骤中的正文 `IF` （如前所述） 以确保它们运行仅当目标是主副本的块。 
7. 编写脚本以将其复制相应的副本上的登录名和 SQL 代理作业。 
8. 复制 SQL DBMail 配置文件和 BAM 警报在相应的 SQL 实例承载辅助副本上的帐户。 
9. 如果正在添加的额外的消息框数据库或部署一个新 BAM 活动/视图更高版本，然后新 SQL 作业创建的新消息框数据库或当前主副本上的 BAM 警报数据库。 请确保在主副本上编辑它，然后在相应的辅助副本上手动创建它们。 

也可以执行此配置使用承载主副本的 SQL 实例。 在这种情况下，BizTalk 完成配置后，运行 `UpdateDatabase.vbs` 和 `UpdateRegistry.vbs` 上述步骤后的 BizTalk 机上的脚本。 这是在下一部分中的更详细地讨论。  
 
### <a name="move-biztalk-server-databases-of-an-existing-biztalk-system-to-availability-groups"></a>将 BizTalk Server 数据库的现有 BizTalk 系统移到可用性组

1. 检查你的操作系统要求： 
* 对所有**Windows Server 2012 R2**计算机，安装[3090973 MSDTC 修补程序](https://support.microsoft.com/kb/3090973)（将打开知识库文章）
* 对所有**Windows Server 2016**计算机，可让[RemoteAccessEnabled 注册表项](https://support.microsoft.com/kb/3182294)（将打开知识库文章）
2. 请确保至少四个不同 SQL 实例，将托管各种 BizTalk 数据库。 此外应在不同 SQL 实例上设置辅助副本。 这会导致的 8 个 SQL 实例 （1 主要和 1 辅助副本的每个 4 的实例），最小值和最少 4 个可用性组。 请参阅上的图中为此可用性组配置。 请确保可用性组创建的 **每数据库 DTC 支持** 选项，因为以后不能更改。  
3. 停止 BizTalk 处理和 SQL 代理作业。 
4. 执行所有 BizTalk 数据库的完整的备份。 
5. 将当前在可用性组中的主角色的 SQL 实例上的 BizTalk 数据库还原。 
6. 脚本登录名和 SQL 代理当前在可用性组中的主角色中的相应 SQL 实例上的作业。  
7. 运行 `UpdateDatabase.vbs` 和 `UpdateRegistry.vbs` 使用以下步骤在 BizTalk 机上的脚本。 输入作为输入的更新信息 xml 中的新服务器名称的可用性组侦听器。  
    1. BizTalk 服务器上停止所有的 BizTalk 服务和企业 SSO 服务。 SQL Server 上停止 SQL 代理服务。 
    2. 在 BizTalk Server 中，编辑 SampleUpdateInfo.xml 以下文件夹中︰ 
 
        32 位计算机︰ `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore`
 
        64 位计算机︰ `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore`
 
            1. Replace "SourceServer" with the source server name (old SQL Server hosting old databases).  
            2. Replace "DestinationServer" with the name of the destination server, which should be the availability group listener name.  
            3. If you have the BAMAnalysis, BAM databases or RuleEngineDB, uncomment the appropriate sections. 

    3. 打开命令提示符，并转到︰ 
 
        32 位计算机︰ `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore` 
 
        64 位计算机︰ `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
        在命令提示符下运行︰  
    `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`  
 
        在 BizTalk 组中只有一台服务器上运行 UpdateDatabase.vbs。 

    4. 将编辑的 SampleUpdateInfo.xml 文件复制到此 BizTalk 组中每个 BizTalk Server 计算机上的以下文件夹︰ 
 
        32 位计算机︰ `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore` 
 
        64 位计算机︰ `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
    5. 在 BizTalk Server 组中每台计算机，打开命令提示符，并转到︰ 
 
        32 位计算机︰ `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore`
 
        64 位计算机︰ `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
        在命令提示符下运行︰  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml` 
 
        在 BizTalk 组中的每个服务器上运行 UpdateRegistry.vbs。 
 
8. 现在，将数据库移到其各自的可用性组。 
9. 复制的 SQL DBMail 配置文件和帐户 BAM 警报上 SQL 实例承载 BAMAlerts 数据库的副本。 
10. 将括在 IF 块中以确保它们运行仅当目标是主 SQL 代理作业步骤的正文。 
11. 编写脚本以将其复制相应的副本上的登录名和 SQL 代理作业。 UpdateDatabase 脚本还会更新 Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 和 TrackedMessages_Copy_BizTalkMsgBoxDb 作业中的服务器名称。 因此在运行 UpdateDatabase 脚本后才脚本 SQL 代理作业。 

## <a name="requirements"></a>要求 
* BizTalk Server 2016 Enterprise
* SQL Server 2016 Enterprise
* Windows Server 2012 R2
* Windows Server 2016 

### <a name="availability-group-listener-configured-with-non-default-port-1433"></a>使用非默认配置的可用性组侦听器端口 (1433) 
使用 SQL 别名在 BizTalk Server 计算机上。 

### <a name="supporting-availability-group-multi-subnet-failovers"></a>支持可用性组多子网故障转移 
BizTalk Server 用于 Microsoft OLE DB 数据库连接，不支持**MultiSubnetFailover**连接选项。 BizTalk Server 不支持 `MultiSubnetFailover (=TRUE)` 连接选项，这可能会导致更高版本在多子网故障转移期间的恢复时间。 

### <a name="read-only-routing"></a>只读路由 
只读路由是指 SQL Server 将为可用性组侦听器的传入连接路由到辅助副本配置为允许只读工作负荷的能力。 

BizTalk 不使用只读路由任何连接到其数据库。 这意味着对可用性副本的可用性组中的"可读辅助副本"选项 BizTalk 数据库连接上没有任何影响。 

### <a name="behavior-of-biztalk-server-host-instances-during-sql-server-failover"></a>BizTalk Server 主机实例在 SQL Server 故障转移过程中的操作 
如果 SQL Server 可用性组进行故障转移，在可用性组上的 BizTalk Server 数据库将暂时不可用。 

#### <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a>SQL Server 故障转移期间进程内主机实例的行为 
如果 BizTalk Server 数据库不可用，BizTalk Server 主机的进程内实例则回收直到还原到 SQL Server 的连接。 一旦恢复到 SQL Server 数据库连接时，文档处理正常恢复。
 
#### <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a>SQL Server 故障转移期间独立主机实例的行为 
如果 BizTalk Server 数据库不可用，则暂停 BizTalk Server 主机的独立的实例，并在 BizTalk Server 应用程序日志中生成类似于以下错误︰ 

    All receive locations are being temporarily disabled because either the MessageBox or Configuration database is not available. When these databases become available, the receive locations will be automatically enabled.
 
后恢复到 SQL Server 数据库连接时，类似于下面一条信息性消息写入到 BizTalk Server 应用程序日志中，并文档处理然后正常恢复︰ 

    All receive locations are being enabled because both the MessageBox and Configuration databases are back online.

#### <a name="biztalk-server-log-shipping-for-disaster-recovery"></a>BizTalk Server 日志传送以实现灾难恢复 
BizTalk Server 实现数据库备用功能通过数据库使用日志传送。 BizTalk Server 日志传送自动化的备份和还原的数据库和事务日志文件，允许备用服务器恢复数据库处理的事件中生产数据库服务器。 将失败。 

**可用性组中的辅助数据库不是备份。** 继续备份 BizTalk 数据库和其事务日志使用 BizTalk Server 日志传送作业。 BizTalk 日志传送实现的方式可确保始终针对每个数据库的当前主副本执行备份。 BizTalk Server 日志传送作业不遵循上可用性组的备份首选项设置。 

如果要向 BizTalk 数据库备份作业来添加其他 BizTalk 数据库，请确保将可用性组侦听器名称用作数据库服务器为其设置备份时。  
 
## <a name="references"></a>References 
 
* [为 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)  
* [对 Microsoft Azure 虚拟机的 Microsoft 服务器软件支持](https://support.microsoft.com/kb/2721672)  
* [SQL Server 数据库镜像、卷影复制服务和 AlwaysOn](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
* [AlwaysOn 可用性组 (SQL Server) 概述](https://msdn.microsoft.com/library/ff877884.aspx)  
* [跨数据库事务支持数据库镜像或 AlwaysOn 可用性组 (SQL Server)](https://msdn.microsoft.com/library/ms366279.aspx)  
* [重新登记时不能调用 SQL Server 接收来自 Windows Server 2012 R2 中的 MSDTC 事务结果](https://support.microsoft.com/kb/3090973)  
* [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)  
* [如何将 BizTalk Server 数据库移](../core/how-to-move-the-biztalk-server-databases.md)  
* [如何还原数据库](../core/how-to-restore-your-databases.md)   
* [多子网可用性组中的连接超时](https://blogs.msdn.microsoft.com/alwaysonpro/2014/06/03/connection-timeouts-in-multi-subnet-availability-group/)  
 
## <a name="known-limitations"></a>已知的限制 

这些限制适用于 BizTalk Server，SQL Server AlwaysOn 可用性组和 Azure 虚拟机。 这些限制可能或不可能在将来获取解决。 

* 可用性组内不管理登录名、 SQL 代理作业，SQL 数据库邮件配置文件和帐户。 这要求手动修改，以确保它们对主副本运行的作业中。 
* SQL Server Analysis Services 和 SQL Server Integration Services 将不参与可用性组。 而不从 SQL Server 此支持，没有这些 Azure 虚拟机中的 HA 解决方案。 BizTalk Server BAM 功能都依赖于这些服务。 
* 可用性组不支持在相同的 SQL 实例上的数据库之间的 MSDTC。 因此，最小的 8 SQL 实例所需配置 BizTalk。 
* 若要解决 MSDTC 可以使用至少两个服务器托管四个 SQL 实例每个配置可用性组，BizTalk 数据库中的限制。 但是，在 Azure 虚拟机中，ILB 不支持多个 IP 地址。 这将强制我们能够在单独服务器上创建每个 SQL 实例。 
* BizTalk Server 不能使用只读路由。 
* BizTalk Server 不会设置 `MultiSubnetFailover` 连接属性。 
* 使用日志传送的 BizTalk 备份作业将始终针对主副本而不考虑对可用性组设置的备份首选项。 
 
