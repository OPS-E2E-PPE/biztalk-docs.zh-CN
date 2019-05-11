---
title: 如何配置日志传送目标系统 |Microsoft Docs
ms.custom: ''
ms.date: 2015-12-03
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, log shipping
- system failures, preventing
- log shipping
- databases, backing up
- backing up, databases
- system failures, backing up
- backing up, system failures
ms.assetid: 7b4425f5-b105-4fb2-a503-94ca1e75ad55
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58951da7a59b041ef97b2b93e5153cc27d517b0e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340862"
---
# <a name="how-to-configure-the-destination-system-for-log-shipping"></a>如何配置日志传送目标系统
日志传送具有备用服务器功能，用以缩短出现系统故障时的停机时间。 日志传送，您可以自动将源系统内的事务日志发送到目标系统。 在目标系统中，事务日志还原到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库; 它们与源数据库紧密同步。  
  
 日志传送在单个服务器和分布式的服务器环境中的工作原理。 服务器或包含实时数据的服务器组称作源 （或主要） 系统。 服务器或使用备份还原数据库备份的源生成 （或主要） 系统的服务器组称作目标 （或辅助） 系统。  
  
 [有关日志传送](https://docs.microsoft.com/sql/database-engine/log-shipping/about-log-shipping-sql-server)中的 SQL 文档提供了特定的详细信息。  
  
 可以使用以下步骤以创建为单个源系统的一个服务器组成的目标系统。 如果目标系统包含多个服务器，重复每个目标服务器上的步骤。  
  
> [!IMPORTANT]
>  请总是在某个安全位置保留备份文件的一个副本。 即使你进行了日志备份，在没有备份文件的情况下也无法还原数据库。  
  
## <a name="prerequisites"></a>先决条件  
* 以的成员身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
* 在源和目标系统上使用相同版本的 SQL Server。 SQL Server 必须安装在源和目标系统上的同一相对位置。  
  
* SQL 事务日志的目录 (。LDF 文件） 在源系统必须也存在于目标系统。 如果此目录不在目标系统上，创建具有相同名称和源系统上的权限的目录。  
  
### <a name="configure-the-destination-system-for-log-shipping"></a>配置日志传送的目标系统  
  
1. 在目标系统上，打开**SQL Server Management Studio**，并连接到 SQL Server。 选择**主**从可用数据库。  
  
2. 上**文件**菜单中，**打开**以下 SQL 脚本：  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Schema.sql  
   ```  
  
3. 上**查询**菜单中，选择**Execute**。  
  
    *Logshipping_destination_schema 将*删除并重新创建用于还原目标系统上的源数据库的表。 这包括表以存储数据库正在恢复的源系统的 BizTalkMgmtDb 数据库导入的备份历史记录副本的列表和有关 SQL Server 代理作业的信息配置为对源数据库运行。  
  
4. 上**文件**菜单中，**打开**以下 SQL 脚本：  
  
   ```    
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\LogShipping_Destination_Logic.sql  
   ```  
  
5. 上**查询**菜单中，选择**Execute**。  
  
6. 在计算机或计算机已标识为目标系统中，打开**SQL Server Management Studio**并连接到 SQL Server。  
  
7. 选择**新查询**。 在查询窗口中，粘贴以下命令：  
  
   ```  
   exec bts_ConfigureBizTalkLogShipping @nvcDescription = '<MyLogShippingSolution>',  
   @nvcMgmtDatabaseName = '<BizTalkServerManagementDatabaseName>',  
   @nvcMgmtServerName = '<BizTalkServerManagementDatabaseServer>',  
   @SourceServerName = null, -- null indicates that this destination server restores all databases  
   @fLinkServers = 1 -- 1 automatically links the server to the management database  
   ```  
  
    然后：  
  
   1.  在目标系统上启用 **[Ad Hoc Distributed Queries](https://docs.microsoft.com/sql/database-engine/configure-windows/server-configuration-options-sql-server)**。  
  
   2.  在查询窗口中，替换*\<MyLogShippingSolution\>* 的有意义的说明，用单引号引起。  
  
   3.  在查询窗口中，替换*\<BizTalkServerManagementDatabaseName\>* 并*\<BizTalkServerManagementDatabaseServer\>* 与名称和源 BizTalk 管理数据库，用单引号引起的位置。  
  
   > [!NOTE]
   >  如果你有多个源服务器，则可以每个源服务器还原到其自己的目标服务器。 每个目标服务器上，在 **@SourceServerName = null**参数，替换*null*具有适当的源服务器的名称，用单引号引起 (例如，  **@SourceServerName = 'MySourceServer'**)。  
  
8. 上**查询**菜单中，选择**Execute**。  
  
   > [!IMPORTANT]
   >  如果查询失败，则解决该问题与查询后，您必须重新开始此过程来重新配置目标系统的步骤 1 中。  
  
   > [!NOTE]
   >  在目标系统上的还原作业尝试重新创建每个还原的数据库在同一位置中的日志和数据文件，因为它们存在于源数据库服务器上。  
  
9. 在目标系统上**SQL Server Management Studio**，展开**SQL Server 代理**，然后展开**作业**。  
  
     在详细信息窗格中，有三个新作业：  
  
   - **BTS 日志传送获取备份历史记录**  
  
      此 BizTalk 作业将备份历史记录从源移到目标。 它是默认计划每分钟运行。 若要将历史记录从源分片移动到目标尽可能频繁地运行此作业。 出现系统故障到源系统时，标识为目标系统的服务器继续处理已导入的历史记录。  
  
   - **BTS 服务器日志传送还原数据库**  
  
      此 BizTalk 作业可将指定数据库的源的备份文件还原到目标服务器。 它是默认计划每分钟运行。 此作业会连续运行而无法完成，只要有要还原的备份文件。 作为额外的预防措施，你可以运行此作业一次以确保其完成。  
  
   - **BTS 日志传送还原到标记**  
  
      此 BizTalk 作业将所有数据库还原到上次日志备份中的一个标记。 这可确保所有数据库处于事务一致的状态。 此外，此作业将重新创建所有源系统必须已在目标系统上的 SQL Server 代理作业。  
  
     > [!IMPORTANT]
     >  你应监视这些作业，以确保它们不失败。  
  
10. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请转到以下文件夹：  
  
     32 位计算机： %SystemDrive%\Program Files\Microsoft BizTalk Server\<版本\>\Schema\Restore  
  
     64 位计算机： %SystemDrive%\Program 文件 (x86) \Microsoft BizTalk Server\<版本\>\Bins32\Schema\Restore  
  
11. 右键单击**SampleUpdateInfo.xml**，然后选择**编辑**。 请执行以下操作：  
  
    -   所有实例替换都为**SourceServer**与源系统的名称。  
  
    -   所有实例替换都为**DestinationServer**与目标系统的名称。  
  
    > [!IMPORTANT]
    >  包括源和目标系统的名称周围的引号。  
    > 
    > [!NOTE]
    >  如果您重命名的任何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，则还必须更新 XML 文件中的数据库名称。  
    > 
    > [!NOTE]
    >  如果已配置 BAM，则必须添加以下行中的**OtherDatabases**一部分**SampleUpdateInfo.xml** BAMAlertsApplication 和 BAMAlertsNSMain 数据库的文件：   
    > `<Database Name="BAM Alerts Application DB" oldDBName="BAMAlertsApplication" oldDBServer="SourceServer" newDBName=" BAMAlertsApplication" newDBServer="DestinationServer"/>`  
    > `<Database Name="BAM Alerts Instance DB" oldDBName="BAMAlertsNSMain" oldDBServer="SourceServer" newDBName="BAMAlertsNSMain" newDBServer="DestinationServer"/>`  
    > 
    >  如果更改这两个数据库的默认名称，请使用实际的数据库名称。  
  
12. 如果您有多个 MessageBox 数据库您[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统中，到列表中，添加其他 MessageBoxDB 行，然后设置**IsMaster ="0"** 为非主数据库。  
  
13. 如果使用 BAM 或规则引擎，取消注释根据这些行。  
  
14. 如果有任何自定义数据库，将其下添加**\<OtherDatabases\>** 部分。 请参阅[如何备份自定义数据库](../core/how-to-back-up-custom-databases.md)。  
  
15. 在完成编辑文件，请保存该文件，并退出。  
  
## <a name="next-steps"></a>后续步骤  
 [如何还原数据库](../core/how-to-restore-your-databases.md)  
  
## <a name="see-also"></a>请参阅  
 [如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md)   
 [如何安排备份 BizTalk Server 作业](../core/how-to-schedule-the-backup-biztalk-server-job.md)   
 [如何备份自定义数据库](../core/how-to-back-up-custom-databases.md)