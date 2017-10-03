---
title: "管理员的 BAM 任务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2d9ae9a6-50fa-4f82-8e48-8dffa55c127f
caps.latest.revision: "33"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b529a0510ee56a92d3957a84a91d635666016f1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bam-tasks-for-administrators"></a>管理员的 BAM 任务
本主题描述 BAM 管理员在管理 BAM 基础结构时需要执行的典型任务。  
  
## <a name="configuring-bam"></a>配置 BAM  
 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置向导进行 BAM 的初始配置。 使用该配置向导，管理员可以执行以下操作：  
  
-   启用业务活动监视工具  
  
-   为 BAM 聚合启用 SQL Server Analysis Services  
  
-   指定 BAM 工具使用的服务器名和数据库  
  
-   为 BAM 警报启用 SQL Server Notification Services  
  
-   指定用于运行 BAM 通知服务的帐户  
  
-   指定用于发送 BAM 警报的 SMTP 服务器  
  
-   指定用于存储 BAM 警报的文件位置  
  
-   指定 BAM 警报数据库所在的 SQL 服务器的名称  
  
-   指定警报数据库名称的前缀  
  
-   在计算机上启用 BAM 门户  
  
-   指定用于运行 BAM 门户的 Web Services 帐户  
  
-   指定可以访问 BAM 门户的 Windows 组  
  
-   指定 BAM 门户网站的位置  
  
 有关使用该配置向导的详细信息，请参阅以下主题：  
  
-   [配置使用 BizTalk Server 配置的 BAM 警报](http://msdn.microsoft.com/library/04d79f8c-9e7f-4ba8-83ce-f79c33fb8e60)  
  
-   [配置使用 BizTalk Server 配置的 BAM 工具](http://msdn.microsoft.com/library/075a1627-5bc2-488c-a88c-42c86cc8c3bb)  
  
-   [配置 BAM 门户使用 BizTalk Server 配置](http://msdn.microsoft.com/library/8af7cccb-823e-48bd-9743-dfbba4bafa11)  
  
### <a name="distributed-notification-services"></a>分布式 Notification Services  
 如果将 BAM 配置为在分布式环境中运行，则在处理警报和通知时将具有性能优势。 如果要这样配置，则 Notification Services 的提供者、生成者和分发者角色将位于不同的计算机上，因此您必须在多计算机环境中安装 Notification Services。  
  
##### <a name="to-configure-distributed-notification-services"></a>配置分布式 Notification Services  
  
1.  安装 [!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)] Notification Services。 有关分布式通知服务的详细信息，请参阅[!INCLUDE[btsSQLServer2005](../includes/btssqlserver2005-md.md)]Notification Services 文档[http://go.microsoft.com/fwlink/?LinkId=68095](http://go.microsoft.com/fwlink/?LinkId=68095)。  
  
    > [!NOTE]
    >  Notification Services 未包含在[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]。 如果你使用[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]，安装[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]通知服务安装时[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]通过选择**BAM 警报提供程序 SQL Notification Services**选项下**其他软件**上**组件安装**安装向导页。  
  
2.  若要创建 BAM 通知运行 C:\Program Files\Microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol 分布式环境中的每台计算机上的服务注册-name bamalerts-服务器\<服务器名称 >-服务-serviceusername \<alertsuseraccount >-servicepassword \<passwd > 从命令提示符。  
  
3.  编辑每台计算机上为分布式 Notification Services 配置的 BAM 基础结构配置文件。 若要获取配置文件，请使用**bm.exe get-config FileName:\<输出文件 >**命令。  
  
4.  编辑配置文件以引用分布式 Notification Services 环境中的服务器：  
  
    ```  
    <Property Name="GeneratorServerName">PFIDWYUK</Property>  
    <Property Name="ProviderServerName">PFIDWYUK</Property>  
    <Property Name="DistributorServerName">PFIDWYUK</Property>  
    ```  
  
5.  使用 bm.exe 更新-config FileName:\<配置文件 > 更新 BAM 配置。  
  
6.  重新启动分布式环境中所有计算机上的 Notification Services。  
  
 在多计算机环境中安装 BAM 的详细信息，请参阅[相关到 BizTalk Server 2013 的指南安装](http://go.microsoft.com/fwlink/p/?LinkID=269582)和[安装和配置 BAM （业务活动监视） 在多台计算机环境](http://go.microsoft.com/fwlink/p/?LinkID=208597)。  
  
### <a name="moving-the-bam-primary-import-database"></a>移动 BAM 主导入数据库  
 有时，可能必须移动 BAM 主导入数据库，例如，在升级硬件或扩展操作时。 若要移动该数据库，需要执行备份和还原操作。 有关此过程的详细信息，请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。  
  
### <a name="working-with-bam-definitions"></a>处理 BAM 定义  
 管理员需要经常处理 BAM 定义。 用于处理 BAM 定义的主要工具是 BAM 管理实用程序。 使用此实用程序可以执行以下任务：  
  
-   更改活动。 你可以使用**部署所有**，**更新所有**，**删除活动**，**和集 actvitywindow** BAM 管理实用程序的命令若要更改你已部署的活动。  
  
-   将索引应用于活动表以提高性能。 你使用**创建索引**和**删除索引**命令来修改活动的索引。  
  
-   设置视图的安全性。 你可以使用**添加帐户**和**删除帐户**命令向用户授予访问权限视图。  
  
-   配置分布式活动导航。 你使用**启用引用**和**禁用引用**命令来配置的活动的分布式的导航。 有关活动的分布式导航的详细信息，请参阅[管理分布式导航的远程活动](../core/managing-distributed-navigation-of-remote-activities.md)。  
  
-   审核更改。 你可以列出对 BAM 动态基础结构使用的更改**获取变更**命令。  
  
 可通过 BAM 管理实用程序的所有命令的说明，请参阅[BAM 管理实用工具](../core/bam-management-utility.md)。 有关使用 BAM 管理实用程序来处理 BAM 定义的示例，请参阅[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)。  
  
## <a name="configuring-multiple-biztalk-groups-to-reference-a-single-bam-database"></a>将多个 BizTalk 组配置为引用单个 BAM 数据库  
 配置为使用新的或现有的 BAM 时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组中，你可以配置要使用相同的 BAM 数据库已正在由另一个使用的组[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  若要以这种方式配置 BAM，必须执行以下任务：  
  
-   从现有的 BAM 主导入数据库使用获取配置信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置向导。 这包括服务器和数据库的名称。 请注意复选框的状态。 确保获取 BAM 工具和 BAM 警报页的配置信息。  
  
-   为新组配置 BAM，然后输入与已为目标 PIT 配置的信息完全相同的信息。 为新组输入配置信息时，将使用从现有组收集的所有信息来配置该新组，唯一的不同是必须将 BAM 警报用户保留为空。  
  
## <a name="backing-up-and-restoring-bam"></a>Backing Up and Restoring BAM  
 管理员应当为灾难恢复情况做好准备。 您应当备份 BAM 分析数据库、跟踪分析数据库、BAM 星型架构数据库、BAM 存档数据库和 BAM 主导入数据库，以便在必须还原它们时提供所需文件。  有关备份和还原的 BAM 数据库的信息，请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。  
  
## <a name="working-with-renamed-servers"></a>处理重命名服务器  
 在重命名服务器或在服务器之间移动 BAM 基础结构后，必须通过更新 Excel 工作簿中的 BAM 定义来更新该工作簿。  
  
 您需要更新该工作簿的情况包括：  
  
-   将 BAM 基础结构移动到新数据库的过渡情况。 若要确保 Excel 工作簿仍然能够正常使用，必须重新部署或进行迁移，然后重新更新工作簿。  
  
-   重命名正运行 BizTalk Server 的计算机的情况。 这需要更新的 DTS 包和除了更新工作簿的 OLAP 数据源。  
  
 更新 Excel 工作簿可以采用两种方法：  
  
-   从新服务器运行以下 BAM 管理器命令：  
  
     **bm.exe 更新 livedataworkbook-名称：\<livedata 工作簿变为 update.xls >**  
  
    > [!NOTE]
    >  你还可以指定新的服务器名称和/或 BAM 主导入数据库名称： **bm.exe 更新 livedataworkbook-名称：\<livedata 工作簿变为 update.xls > [-Server:\<服务器 >] [-数据库：\<数据库 >]**  
  
-   也可以在 Excel 中更新 Excel 工作簿：  
  
    1.  打开要更新的工作簿。  
  
    2.  从 BAM 菜单上，单击**BAM 数据库连接**。  
  
    3.  输入新的服务器名和 BAM 主导入数据库名。  
  
## <a name="managing-alerts"></a>管理警报  
 管理员可以以几种方式管理警报：  
  
 您可以使用 BAM 管理实用程序来部署和删除警报。 还可以使用该实用程序来添加和删除订阅，以及启用和禁用警报。 有关使用 BAM 管理实用程序的详细信息，请参阅[BAM 管理实用工具](../core/bam-management-utility.md)，[管理 BAM 安全](../core/managing-bam-security.md)，和[管理 BAM 定义](../core/managing-bam-definitions.md)。  
  
 您还可以通过 BAM 门户来创建和删除警报。  有关创建使用 BAM 门户警报的信息，请参阅[BAM 门户中的活动搜索](../core/activity-searches-in-the-bam-portal.md)。  
  
### <a name="cleaning-up-the-alerts-chronicle-table"></a>清理 Alerts Chronicle 表  
 如果配置 BAM 警报，则为创建的每个活动视图都创建一个 SQL 作业。 将使用以下模板命名该作业：  
  
 bam_\<视图名称 > _\<活动视图 > _DelAlertHistJob  
  
 此作业负责清除审核数据的指定实例警报\<活动视图 > Bam_Metadata_AlertChronicle 表中。 如果您对特定的活动视图定义了实例警报，则每次触发警报时，就会向该表添加一个新行。  
  
 您可以手动运行此作业以便清理该表，或者可以根据您的应用程序或环境的需要计划此作业的运行时间。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM](../core/managing-bam.md)