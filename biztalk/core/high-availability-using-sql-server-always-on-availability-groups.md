---
title: 使用 SQL Server Always On 可用性组实现高可用性 |Microsoft Docs
description: 若要获取使用 SQL Server Always On 可用组 (AG)，包括系统要求和限制的高可用性 (HA) 解决方案的不同节点上的 BizTalk Server 数据库进行分组。 Always On AG 需要 Windows Server 故障转移群集 (WSFC)。
ms.custom: ''
ms.date: 07/8/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4511a578-77d2-49ee-99bd-f0406ad625d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d163c035cdf45ede600509783040114a0eaa0a2b
ms.sourcegitcommit: 1f0306e812c95dc32c4496345c19f141612cb2c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2018
ms.locfileid: "37913854"
---
# <a name="high-availability-using-sql-server-always-on-availability-groups---biztalk-server"></a>使用 SQL Server Always On 可用性组的 BizTalk Server 的高可用性
配置使用 SQL Server AlwaysOn 可用性组实现高可用性。

> [!TIP]
> [设置 BizTalk Server 2016 使用可用性组实验室](https://skastberg.wordpress.com/2017/02/22/setting-up-my-biztalk-server-2016-using-availability-groups-lab/)提供由 Microsoft 现场工程师编写的分步指南。 它基于在实验室环境中，并包含一些意见。 其签出。  
> 
> [!IMPORTANT]
> * 可从 SQL Server 2016 always On 可用性组。 如果使用以前的 SQL Server 版本，本主题不适用于您。 
> * BizTalk Server 2016 支持同步提交模式;不支持异步提交模式。 对于灾难恢复，建议配置备份 BizTalk Server 作业，并使用日志传送。 请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)的具体详细信息。
> 
>    [可用性模式](https://docs.microsoft.com/sql/database-engine/availability-groups/windows/availability-modes-always-on-availability-groups)详细介绍与 Alwayson 可用性组的提交选项。 


## <a name="background-and-history"></a>背景和历史记录

BizTalk Server 严重依赖 SQL Server 实现数据持久性。 集成完全不同的业务应用程序，如接收、 处理或路由消息时，其他组件和 BizTalk Server 中的主机具有特定的角色。 数据库计算机捕获此工作，并将其保存到磁盘。 

BizTalk 使用 SQL Server 故障转移群集和日志传送来为其在本地数据库提供高可用性、 备份和还原和灾难恢复。 在 Azure IaaS （Azure 虚拟机），以前版本的 SQL Server 不支持故障转移群集实例 （没有 MSDTC 支持）。 因此，BizTalk 不具有高可用性解决方案时使用 Azure Vm。

从 SQL Server 2016 开始，SQL Server AlwaysOn 可用性组支持在本地和使用 Azure Vm 的 MSDTC。 因此，BizTalk 数据库的本地或在 Azure IaaS 方案中支持的 SQL Server 2016 AlwaysOn 功能。 

## <a name="sql-server-2016-alwayson-availability-groups"></a>SQL Server 2016 AlwaysOn 可用性组 
部署 AlwaysOn 可用性组需要 Windows Server 故障转移群集 (WSFC) 群集。 给定可用性组的每个可用性副本必须位于相同 WSFC 群集的不同节点上。 为您创建的每个可用性组创建一个 WSFC 资源组。 WSFC 群集将监视此资源组，以便评估主副本的运行状况。  

下图显示的是一个包含一个主要副本和四个次要副本的可用性组。  
 
 ![SQLAG_PrimaryReplica](../core/media/sqlag-primaryreplica.png)

客户端可以连接到使用可用性组侦听器为给定的可用性组的主副本。 可用性组侦听器提供了一组附加到给定的可用性组以便在客户端连接定向到相应的可用性副本的资源。 

>[!IMPORTANT]
> SQL Server 2016 支持 Windows Server 2016 和 Windows Server 2012 R2 上的 MSDTC 与 AlwaysOn 可用性组 (AG)。 **Windows Server 2012 R2**需要[3090973](https://support.microsoft.com/kb/3090973) Windows 修补程序安装。 
> **Windows Server 2016**要求[RemoteAccessEnabled 注册表项](https://support.microsoft.com/kb/3182294)启用。

对于 2016年之前的任何版本，SQL Server 不支持与 AlwaysOn 可用性组的 MSDTC。  

SQL Server AlwaysOn 可用性组不支持同一个 SQL Server 实例上的数据库之间的 MSDTC。 这意味着，可以在同一个 SQL server 实例上承载分布式事务中的任何两个 BizTalk 数据库。 对于事务一致性，应在不同的 SQL server 实例上托管参与分布式事务中的 BizTalk 数据库。 请注意它并不重要的 SQL 实例是否在同一台计算机或不同的计算机上。 


## <a name="provide-high-availability-for-biztalk-databases-using-alwayson-availability-groups"></a>为使用 AlwaysOn 可用性组的 BizTalk 数据库提供高可用性 
在 BizTalk Server 基本配置中，数据库就会将一个最少为 9 的数据库创建包括规则和 BAM。 由于 MSDTC 可用性组限制前文所述，如下面的配置不能确保事务一致性。 

![SQLAG_NoTrans](../core/media/sqlag-notrans.gif)
 
我们建议使用 BizTalk Server 数据库可分为以下四个 SQL Server 实例：
 
| 实例 |角色 |该组中的 BizTalk 数据库  |
|--- | --- | ---|
|@shouldalert |身份验证 |SSODB|
|2 |管理 |BizTalkMgmtDb| 
|3 |运行时 |BizTalkMsgBoxDb<br/> BizTalkRulesEngineDb<br/> BAMPrimaryImport<br/>BAMStarSchema <br/>BAMAlertsApplication |
|4 |跟踪 |BizTalkDTADb<br/>EsbItineraryDb<br/>EsbExceptionDb | 
 
在向外扩展 MessageBox 方案 （使用多个 MessageBox 的配置） 中，没有多个 MessageBox 数据库，并且每个 MessageBox 数据库必须位于其自己的 SQL Server 实例上。 

BizTalk Server 还依赖于 SQL Server Analysis Services 和 BAM 分析和存档的 SQL Server Integration Services。 Integration Services 或 Azure IaaS 中的 Analysis Services，SQL Server 不提供高可用性解决方案。 因此建议为 BAMArchive 和 BAMAnalysis Analysis Services 数据库使用其他独立 SQL Server 实例。 对于在本地安装，可以设置高可用性配置使用 SQL 故障转移群集实例。 

此配置是，如下图所示，建议在可用性组中的 BizTalk 数据库：  

![SQLAG_Recommended](../core/media/sqlag-recommended.png)
 
SQL Server 数据库，以及 BizTalk Server 配置还会创建 SQL Server 安全登录名和 SQL 代理作业。 AlwaysOn 可用性组仅提供的功能来管理在可用性组的数据库。 登录名和 BizTalk 的 SQL 代理作业需要创建并更新/手动管理所有可用性副本。  

> [!NOTE]
> SQL Server 2016 Service Pack 2 和同一可用性组中的多个数据库之间的更高版本支持 DTC 事务。 BizTalk Server 支持与 CU5 启动此功能。
> 在配置 BizTalk Server 2016 的 SQL Server 2016 Service Pack 2 和更高版本时，所有 BizTalk Server 数据库可以都部署到单个可用性组。

下面列出的 SQL Server 安全登录名是与 BizTalk Server 相关联。 您可能必须为 BizTalk Server 应用程序创建其他登录名。 如果是这样，您需要复制它们承载 BizTalk 数据库的副本的 SQL Server 的每个实例上。 

1. BizTalk Application Users （一个或多个对应于每个进程内主机） 
2. BizTalk Isolated Host Users （一个或多个对应于每个独立的主机） 
3. BizTalk Server Administrators 
4. BizTalk Server B2B Operators 
5. BizTalk Server Operators 
6. SSO Administrators 
7. BAM 警报用户 
8. BAM 管理 Web Services 用户 
9. 规则引擎更新服务帐户 

如果已创建其他主机或者将在以后创建其他主机，将作为此过程的一部分创建的新 SQL 登录名。 您必须确保在相应的副本上手动创建这些 SQL 登录名。

以下 SQL Server 代理作业与 BizTalk Server 相关联。 每个服务器上安装的作业有所不同，具体视安装和配置的功能而定。 BizTalk Server 配置期间创建这些作业大部分。 部分作业是在配置日志传送时创建的。 需要在其相应的 BizTalk 数据库的 SQL Server 托管副本的每个实例上复制这些作业。 这必须手动执行。 

- BizTalkMgmtDb 的作业： 
    - 备份 BizTalk Server (BizTalkMgmtDb) 
    - CleanupBTFExpiredEntriesJob_BizTalkMgmtDb 
    - 监视 BizTalk Server (BizTalkMgmtDb) 
- BizTalkMsgBoxDb 作业： 
    - MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb 
    - MessageBox_Message_Cleanup_BizTalkMsgBoxDb
    - MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb
    - MessageBox_Parts_Cleanup_BizTalkMsgBoxDb 
    - MessageBox_UpdateStats_BizTalkMsgBoxDb 
    - Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 
    - PurgeSubscriptionsJob_BizTalkMsgBoxDb 
    - TrackedMessages_Copy_BizTalkMsgBoxDb 
- 有关其他 msgboxes 的作业
- BizTalkDTADb 作业： 
    - DTA 清除和存档 (BizTalkDTADb) 
- BizTalkRulesEngineDb 作业： 
    - Rules_Database_Cleanup_BizTalkRuleEngineDb 
- BAMAlertsApplication 作业： 
    - 0 或更多 DelAlertHistJob 

与 SQL 故障转移群集实例，不同可用性组中所有副本都是活动、 正在运行，且可用。 时在每个副本的故障转移会有重复的 SQL 代理作业，它们将对相应的副本，而不考虑它目前是否在主角色或辅助角色中运行。 若要确保仅在当前主副本上执行这些作业，每个作业的每一步必须括在 IF 块中，如所示： 

    ```
    IF (sys.fn_hadr_is_primary_replica(‘dbname’) = 1)  
    BEGIN  
    …  
    END
    ```
  
替换为`‘dbname’`与对其作业配置为运行相应的数据库名称。 下面的示例演示在 BizTalkMsgBoxDb TrackedMessages_Copy_BizTalkMsgBoxDb 此更改： 
 
 ![SQLAG_AgentJob](../core/media/sqlag-agentjob.gif)

### <a name="configure-biztalk-when-availability-groups-are-already-set-up"></a>如果可用性组已设置了，配置 BizTalk

1. 检查操作系统要求： 
2. 对所有**Windows Server 2012 R2**的计算机，安装[3090973 MSDTC 修补程序](https://support.microsoft.com/kb/3090973)（打开知识库文章）
3. 对所有**Windows Server 2016**的计算机，启用[RemoteAccessEnabled 注册表项](https://support.microsoft.com/kb/3182294)（打开知识库文章）
4. 请确保具有至少四个不同的 SQL 实例将托管多个 BizTalk 数据库。 此外应在不同的 SQL 实例上设置辅助副本。 这会导致最少 8 个 SQL 实例 （1 主副本和 1 辅助副本的每个 4 个实例），且最少 4 个可用性组。 请参阅上的图中为此可用性组配置。 请确保可用性组创建与**每数据库 DTC 支持**选项，因为这是无法更改更高版本。 
5. 当配置 BizTalk Server 并指定 SQL 服务器名称，而不是实际的计算机名称使用可用性组侦听器名称。 这在当前主副本上创建 BizTalk 数据库、 登录名和 SQL 代理作业。 
6. 停止 BizTalk 处理 （主机实例、 SSO 服务、 IIS、 规则引擎更新服务、 BAMAlerts 服务等），并停止 SQL 代理作业。 
7. 现在将 BIzTalk 数据库添加到相应的可用性组。 
8. 将正文中的 SQL 代理作业步骤`IF`块 （如前所述） 以确保它们运行仅当目标是主副本。 
9. 脚本才能将它们复制相应的副本上的登录名和 SQL 代理作业。 
10. 复制 SQL DBMail 配置文件和 BAM 警报的相应 SQL 实例承载辅助副本上的帐户。 
11. 如果要添加其他 messagebox 数据库或部署一个新 BAM 活动/视图更高版本，然后新 SQL 作业创建新的消息框数据库或当前主副本上的 BAM 警报数据库。 请确保主副本上对其进行编辑，然后在相应的辅助副本上手动创建它们。 

也可以完成此配置使用承载主副本的 SQL 实例。 在这种情况下，BizTalk 配置之后，运行`UpdateDatabase.vbs`和`UpdateRegistry.vbs`上述步骤后的 BizTalk 计算机上的脚本。 下一节中更详细地对此进行了讨论。  
 
### <a name="move-existing-biztalk-databases-to-availability-groups"></a>将现有 BizTalk 数据库移到可用性组

1. 检查操作系统要求： 
2. 对所有**Windows Server 2012 R2**的计算机，安装[3090973 MSDTC 修补程序](https://support.microsoft.com/kb/3090973)（打开知识库文章）
3. 对所有**Windows Server 2016**的计算机，启用[RemoteAccessEnabled 注册表项](https://support.microsoft.com/kb/3182294)（打开知识库文章）
4. 请确保具有至少四个不同的 SQL 实例将托管多个 BizTalk 数据库。 此外应在不同的 SQL 实例上设置辅助副本。 这会导致最少 8 个 SQL 实例 （1 主副本和 1 辅助副本的每个 4 个实例），且最少 4 个可用性组。 请参阅上的图中为此可用性组配置。 请确保可用性组创建与**每数据库 DTC 支持**选项，因为这是无法更改更高版本。  
5. 停止 BizTalk 处理和 SQL 代理作业。 
6. 执行完整备份所有 BizTalk 数据库。 
7. 还原当前在主角色中可用性组中的 SQL 实例上的 BizTalk 数据库。 
8. 编写脚本的登录名和 SQL 代理作业当前在主角色中可用性组中的相应 SQL 实例上。  
9. 运行`UpdateDatabase.vbs`和`UpdateRegistry.vbs`脚本使用以下步骤在 BizTalk 机上的。 输入作为输入的更新信息 xml 中的新服务器名称的可用性组侦听器。  
    1. 在 BizTalk Server 上停止所有 BizTalk 服务和企业 SSO 服务。 SQL Server 上停止 SQL 代理服务。 
    2. 在 BizTalk Server 上编辑 SampleUpdateInfo.xml 以下文件夹中： 
 
        32 位计算机： `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore`
 
        64 位计算机： `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore`
 
            1. Replace "SourceServer" with the source server name (old SQL Server hosting old databases).  
            2. Replace "DestinationServer" with the name of the destination server, which should be the availability group listener name.  
            3. If you have the BAMAnalysis, BAM databases or RuleEngineDB, uncomment the appropriate sections. 

    3. 打开命令提示符，并转到： 
 
        32 位计算机： `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore` 
 
        64 位计算机： `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
        在命令提示符下运行：  
    `cscript UpdateDatabase.vbs SampleUpdateInfo.xml`  
 
        在 BizTalk 组中只有一台服务器上运行 UpdateDatabase.vbs。 

    4. 将已编辑的 SampleUpdateInfo.xml 文件复制到此 BizTalk 组中每个 BizTalk Server 计算机上的以下文件夹： 
 
        32 位计算机： `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore` 
 
        64 位计算机： `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
    5. BizTalk Server 组中每台计算机，打开命令提示符，并转到： 
 
        32 位计算机： `%SystemRoot%\Program Files\Microsoft BizTalk Server 20xx\Schema\Restore`
 
        64 位计算机： `%SystemRoot%\Program Files (x86)\Microsoft BizTalk Server 20xx\Bins32\Schema\Restore` 
 
        在命令提示符下运行：  
    `cscript UpdateRegistry.vbs SampleUpdateInfo.xml` 
 
        在 BizTalk 组中的每个服务器上运行 UpdateRegistry.vbs。 
 
10. 现在，将数据库移到其各自的可用性组。 
11. 复制 SQL DBMail 配置文件和帐户为 BAM 警报上 SQL 实例承载 BAMAlerts 数据库的副本。 
12. 将 IF 块来确保仅当目标是主它们运行中的 SQL 代理作业步骤的正文。 
13. 脚本才能将它们复制相应的副本上的登录名和 SQL 代理作业。 UpdateDatabase 脚本还会更新 Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 和 TrackedMessages_Copy_BizTalkMsgBoxDb 作业中的服务器名称。 仅在运行 UpdateDatabase 脚本后，因此脚本 SQL 代理作业。 

## <a name="requirements"></a>要求 
* BizTalk Server 2016 企业版
* SQL Server 2016 Enterprise 或 SQL Server 2016 Standard (请参阅**已知限制**本主题中)
* Windows Server 2012 R2 或 Windows Server 2016 

### <a name="availability-group-listener-configured-with-non-default-port-1433"></a>使用非默认配置的可用性组侦听器端口 (1433) 
使用 SQL 别名在 BizTalk Server 的计算机上。 

### <a name="support-availability-group-multi-subnet-failovers"></a>支持可用性组多子网故障转移 
BizTalk Server 使用 Microsoft OLE DB 的数据库连接不支持**MultiSubnetFailover**连接选项。 BizTalk Server 不支持`MultiSubnetFailover (=TRUE)`连接选项，这可能会导致在多子网故障转移期间更高版本的恢复时间。 

### <a name="read-only-routing"></a>只读路由 
只读路由是指 SQL Server 能够将可用性组侦听器的传入连接路由到配置为允许只读工作负荷的辅助副本。 

BizTalk 不使用只读路由的任何其数据库的连接。 这意味着可用性副本上可用性组中的"可读辅助副本"选项 BizTalk 数据库连接不产生任何影响。 

### <a name="behavior-of-biztalk-host-instances-during-sql-server-failover"></a>SQL Server 故障转移期间 BizTalk 主机实例的行为 
如果 SQL Server 可用性组发生故障转移，可用性组上的 BizTalk Server 数据库将暂时不可用。 

#### <a name="behavior-of-in-process-host-instances-during-sql-server-failover"></a>SQL Server 故障转移期间进程内主机实例的行为 
如果 BizTalk Server 数据库不可用，然后 BizTalk Server 主机的进程内实例被回收直到还原到 SQL Server 的连接。 一旦还原到 SQL Server 数据库的连接，文档处理正常恢复。
 
#### <a name="behavior-of-isolated-host-instances-during-sql-server-failover"></a>SQL Server 故障转移期间独立主机实例的行为 
如果 BizTalk Server 数据库不可用，则 BizTalk Server 主机的独立的实例暂停，并在 BizTalk Server 应用程序日志中生成如下错误： 

    All receive locations are being temporarily disabled because either the MessageBox or Configuration database is not available. When these databases become available, the receive locations will be automatically enabled.
 
一旦还原到 SQL Server 数据库的连接，类似于以下的信息性消息写入到 BizTalk Server 应用程序日志和文档处理然后正常恢复： 

    All receive locations are being enabled because both the MessageBox and Configuration databases are back online.

#### <a name="log-shipping-for-disaster-recovery"></a>日志传送灾难恢复 
BizTalk Server 实现数据库备用功能通过数据库使用日志传送。 BizTalk Server 日志传送可以自动备份和还原的数据库和事务日志文件，从而允许在备用服务器恢复数据库处理在的生产数据库服务器无法正常工作。 

**可用性组中的辅助数据库不是备份。** 继续备份 BizTalk 数据库和其事务日志使用 BizTalk Server 日志传送作业。 实现 BizTalk 日志传送的方式可确保始终针对每个数据库的当前主副本执行备份。 BizTalk Server 日志传送作业不遵循上可用性组的备份首选项设置。 

如果要添加到 BizTalk 数据库备份作业的其他 BizTalk 数据库，请务必的可用性组侦听器名称用作数据库服务器为其设置备份时。  
 
## <a name="references"></a>References 
 
* [为 BizTalk Server 数据库提供高可用性](../core/providing-high-availability-for-biztalk-server-databases.md)  
* [对 Microsoft Azure 虚拟机的 Microsoft 服务器软件支持](https://support.microsoft.com/kb/2721672)  
* [SQL Server 数据库镜像、卷影复制服务和 AlwaysOn](../core/sql-server-database-mirroring-volume-shadow-copy-service-and-alwayson.md)  
* [AlwaysOn 可用性组 (SQL Server) 概述](https://msdn.microsoft.com/library/ff877884.aspx)  
* [跨数据库事务支持数据库镜像或 AlwaysOn 可用性组 (SQL Server)](https://msdn.microsoft.com/library/ms366279.aspx)  
* [当 SQL Server 收到来自 Windows Server 2012 R2 中的 MSDTC 事务结果时，不能调用重新登记](https://support.microsoft.com/kb/3090973)  
* [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)  
* [如何移动 BizTalk Server 数据库](../core/how-to-move-the-biztalk-server-databases.md)  
* [如何还原数据库](../core/how-to-restore-your-databases.md)   
* [多子网可用性组中的连接超时](https://blogs.msdn.microsoft.com/alwaysonpro/2014/06/03/connection-timeouts-in-multi-subnet-availability-group/)  
 
## <a name="known-limitations"></a>已知的限制 

这些限制适用于 BizTalk Server，SQL Server AlwaysOn 可用性组和 Azure 虚拟机。 这些限制可能或不可能在将来获得解决。 

* 可用性组中不会管理登录名、 SQL 代理作业、 SQL DB 邮件配置文件和帐户。 这需要手动进行修改以确保它们对主副本运行的作业中。 
* SQL Server Analysis Services 和 SQL Server Integration Services 将不参与可用性组。 如果没有此支持从 SQL Server，没有这些 Azure 虚拟机中的 HA 解决方案。 BizTalk Server BAM 功能都依赖于这些服务。 
* 在 SQL Server 2016 SP2 之前, 可用性组不支持在同一 SQL 实例的数据库之间 MSDTC。 因此，需要最少 8 个 SQL 实例来配置 BizTalk。 

  从 SQL Server 2016 SP2 开始*并*BizTalk Server 2016 [CU5](https://support.microsoft.com/help/2555976/service-pack-and-cumulative-update-list-for-biztalk-server)，BizTalk 数据库可以使用相同的 SQL Server 实例。 

* 若要解决 MSDTC 可以使用最少两台服务器托管四个 SQL 实例每个配置可用性组，BizTalk 数据库的限制。 此外可以使用[与 Azure 负载均衡器的多个 IP 地址](https://docs.microsoft.com/azure/load-balancer/load-balancer-multivip-overview)。 因此，如果你想要在一台服务器上的端口 1433年上使用四个默认 SQL 实例，您需要四个 IP 地址。 如果仅限于一个 IP 地址，并且你想要托管在同一服务器上的多个 SQL 实例，则在确保针对每个 SQL 实例使用自定义端口。 

  从 SQL Server 2016 SP2 开始*并*BizTalk Server 2016 [CU5](https://support.microsoft.com/help/2555976/service-pack-and-cumulative-update-list-for-biztalk-server)，BizTalk Server 数据库可以使用相同的 SQL Server 实例。 

* BizTalk Server 不能使用只读路由。 
* BizTalk Server 不会设置`MultiSubnetFailover`连接属性。 
* 使用日志传送的 BizTalk 备份作业将始终针对主副本而不考虑对可用性组设置的备份首选项。 
* SQL Server 2016 Standard 仅支持一个单一数据库中每个 SQL AlwaysOn 可用性组。 由于 BizTalk 使用多个数据库，通常建议为 SQL Server Enterprise edition。
* 如果使用 Azure Vm，建议使用专用 MSDTC 对于固定的 TCP/IP 端口。 当使用固定的 TCP/IP 端口时，不会限制您通常与较早的操作系统; 一起使用的 RPC 端口范围它可帮助简化你的防火墙和负载均衡器规则。 若要避免与已知的较低端口冲突，请考虑使用更高版本的固定的端口 (如 > 20000)。 [配置 DTC 单个端口支持](https://msdn.microsoft.com/library/windows/desktop/dd573191(v=vs.85).aspx)描述`ServerTcpPort`注册表项。 除了 MSDTC 的固定端口，还使用主要的 RPC 端口 135。 
