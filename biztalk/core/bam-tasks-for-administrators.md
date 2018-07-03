---
title: 管理员的 BAM 任务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d9ae9a6-50fa-4f82-8e48-8dffa55c127f
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 742eeffd496eaf43fbdd809f2610f2af64d04251
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996358"
---
# <a name="bam-tasks-for-administrators"></a>管理员的 BAM 任务
本主题描述 BAM 管理员在管理 BAM 基础结构时需要执行的典型任务。  
  
## <a name="configuring-bam"></a>配置 BAM  
 进行 BAM 的初始配置使用 BizTalk Server 配置向导。 使用该配置向导，管理员可以执行以下操作：  
  
- 启用业务活动监视工具  
  
- 为 BAM 聚合启用 SQL Server Analysis Services  
  
- 指定 BAM 工具使用的服务器名和数据库  
  
- 为 BAM 警报启用 SQL Server Notification Services  
  
- 指定用于运行 BAM 通知服务的帐户  
  
- 指定用于发送 BAM 警报的 SMTP 服务器  
  
- 指定用于存储 BAM 警报的文件位置  
  
- 指定 BAM 警报数据库所在的 SQL 服务器的名称  
  
- 指定警报数据库名称的前缀  
  
- 在计算机上启用 BAM 门户  
  
- 指定用于运行 BAM 门户的 Web Services 帐户  
  
- 指定可以访问 BAM 门户的 Windows 组  
  
- 指定 BAM 门户网站的位置  
  
  有关使用该配置向导的详细信息，请参阅以下主题：  
  
- [配置 BAM 警报](../install-and-config-guides/configure-biztalk-server.md)  
  
- [配置 BAM 工具](../install-and-config-guides/configure-biztalk-server.md)  
  
- [配置 BAM 门户](../install-and-config-guides/configure-biztalk-server.md)  
  
### <a name="distributed-notification-services---sql-server-2008-r2-only"></a>分布式的 Notification Services-仅限 SQL Server 2008 R2
如果将 BAM 配置为在分布式环境中运行，则在处理警报和通知时将具有性能优势。 如果要这样配置，则 Notification Services 的提供者、生成者和分发者角色将位于不同的计算机上，因此您必须在多计算机环境中安装 Notification Services。  

> [!NOTE]
> 从 SQL Server 2012 开始，BizTalk Server 使用 SQL Database Mail。 因此，如果要使用 SQL Server 2012 或更高版本，这不适用于您。 请参阅[BAM 警报](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts)有关的指南。
  
##### <a name="to-configure-distributed-notification-services"></a>配置分布式 Notification Services  
  
1. 安装 SQL Server Notification Services。 
  
   > [!NOTE]
   >  SQL Server 中不包括通知服务。 通过选择安装 BizTalk Server 时安装 SQL Server Notification Services**用于 SQL Notification Services 的 BAM 警报提供程序**下**其他软件**上**组件安装**安装向导页。  
  
2. 若要创建 BAM 通知服务运行 C:\Program Files\Microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol 在分布式环境中的每台计算机上注册的名称 bamalerts-server\<服务器名称\>-服务-serviceusername\<警报用户帐户\>-servicepassword \<passwd\>从命令提示符。  
  
3. 编辑每台计算机上为分布式 Notification Services 配置的 BAM 基础结构配置文件。 若要获取配置文件，请使用**bm.exe 获取配置-FileName:\<输出文件\>** 命令。  
  
4. 编辑配置文件以引用分布式 Notification Services 环境中的服务器：  
  
   ```  
   <Property Name="GeneratorServerName">PFIDWYUK</Property>  
   <Property Name="ProviderServerName">PFIDWYUK</Property>  
   <Property Name="DistributorServerName">PFIDWYUK</Property>  
   ```  
  
5. 使用 bm.exe 更新-config-FileName:\<配置文件\>更新 BAM 配置。  
  
6. 重新启动分布式环境中所有计算机上的 Notification Services。  
  
   在多计算机环境中安装 BAM 的详细信息，请参阅[安装并配置 BAM （业务活动监视） 在多计算机环境中](http://go.microsoft.com/fwlink/p/?LinkID=208597)。  
  
### <a name="moving-the-bam-primary-import-database"></a>移动 BAM 主导入数据库  
 有时，可能必须移动 BAM 主导入数据库，例如，在升级硬件或扩展操作时。 若要移动该数据库，需要执行备份和还原操作。 有关此过程的详细信息，请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。  
  
### <a name="working-with-bam-definitions"></a>处理 BAM 定义  
 管理员需要经常处理 BAM 定义。 用于处理 BAM 定义的主要工具是 BAM 管理实用程序。 使用此实用程序可以执行以下任务：  
  
- 更改活动。 可以使用**部署全部**，**更新全部**，**删除活动**，**和集 actvitywindow** BAM 管理实用程序的命令若要更改已部署的活动。  
  
- 将索引应用于活动表以提高性能。 您使用**创建索引**并**删除索引**命令来修改活动上的索引。  
  
- 设置视图的安全性。 可以使用**添加帐户**并**删除帐户**命令，授予用户访问视图的权限。  
  
- 配置分布式活动导航。 您使用**启用引用**并**禁用引用**命令以配置分布式的活动导航。 有关分布式活动导航的详细信息，请参阅[管理分布式导航的远程活动](../core/managing-distributed-navigation-of-remote-activities.md)。  
  
- 审核更改。 可以列出对 BAM 动态基础结构使用的更改**get 更改**命令。  
  
  可通过 BAM 管理实用程序的所有命令的说明，请参阅[BAM 管理实用程序](../core/bam-management-utility.md)。 有关使用 BAM 管理实用程序来处理 BAM 定义的示例，请参阅[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)。  
  
## <a name="configuring-multiple-biztalk-groups-to-reference-a-single-bam-database"></a>将多个 BizTalk 组配置为引用单个 BAM 数据库  
 在配置 BAM 以使用新的或现有的 BizTalk Server 组，可以配置要使用已在由另一个 BizTalk Server 组使用的 BAM 数据库的组。  若要以这种方式配置 BAM，必须执行以下任务：  
  
-   从使用 BizTalk Server 配置向导在现有 BAM 主导入数据库中获取的配置信息。 这包括服务器和数据库的名称。 请注意复选框的状态。 确保获取 BAM 工具和 BAM 警报页的配置信息。  
  
-   为新组配置 BAM，然后输入与已为目标 PIT 配置的信息完全相同的信息。 为新组输入配置信息时，将使用从现有组收集的所有信息来配置该新组，唯一的不同是必须将 BAM 警报用户保留为空。  
  
## <a name="backing-up-and-restoring-bam"></a>Backing Up and Restoring BAM  
 管理员应当为灾难恢复情况做好准备。 您应当备份 BAM 分析数据库、跟踪分析数据库、BAM 星型架构数据库、BAM 存档数据库和 BAM 主导入数据库，以便在必须还原它们时提供所需文件。  有关备份和还原 BAM 数据库的信息，请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。  
  
## <a name="working-with-renamed-servers"></a>处理重命名服务器  
 在重命名服务器或在服务器之间移动 BAM 基础结构后，必须通过更新 Excel 工作簿中的 BAM 定义来更新该工作簿。  
  
 您需要更新该工作簿的情况包括：  
  
- 将 BAM 基础结构移动到新数据库的过渡情况。 若要确保 Excel 工作簿仍然能够正常使用，必须重新部署或进行迁移，然后重新更新工作簿。  
  
- 重命名正运行 BizTalk Server 的计算机的情况。 这需要更新 DTS 包和 OLAP 数据源，除了更新工作簿。  
  
  更新 Excel 工作簿可以采用两种方法：  
  
- 从新服务器运行以下 BAM 管理器命令：  
  
   **bm.exe 更新 livedataworkbook-名称：\<update.xls 到实时数据工作簿\>**  
  
  > [!NOTE]
  >  您还可以指定新的服务器名称和/或 BAM 主导入数据库名称： **bm.exe 更新 livedataworkbook-名称：\<update.xls 到实时数据工作簿\>[-Server:\<server\>] [-数据库：\<数据库\>]**  
  
- 也可以在 Excel 中更新 Excel 工作簿：  
  
  1.  打开要更新的工作簿。  
  
  2.  从 BAM 菜单中，单击**BAM 数据库连接**。  
  
  3.  输入新的服务器名和 BAM 主导入数据库名。  
  
## <a name="managing-alerts"></a>管理警报  
 管理员可以以几种方式管理警报：  
  
 您可以使用 BAM 管理实用程序来部署和删除警报。 还可以使用该实用程序来添加和删除订阅，以及启用和禁用警报。 有关使用 BAM 管理实用程序的详细信息，请参阅[BAM 管理实用程序](../core/bam-management-utility.md)，[管理 BAM 安全性](../core/managing-bam-security.md)，并[管理 BAM 定义](../core/managing-bam-definitions.md)。  
  
 您还可以通过 BAM 门户来创建和删除警报。  有关创建使用 BAM 门户的警报的信息，请参阅[BAM 门户中的活动搜索](../core/activity-searches-in-the-bam-portal.md)。  
  
### <a name="cleaning-up-the-alerts-chronicle-table"></a>清理 Alerts Chronicle 表  
 如果配置 BAM 警报，则为创建的每个活动视图都创建一个 SQL 作业。 将使用以下模板命名该作业：  
  
 bam_\<视图名称\>_\<活动视图\>_DelAlertHistJob  
  
 此作业清理审核数据为指定的实例警报\<活动视图\>为 Bam_Metadata_AlertChronicle 表中。 如果您对特定的活动视图定义了实例警报，则每次触发警报时，就会向该表添加一个新行。  
  
 您可以手动运行此作业以便清理该表，或者可以根据您的应用程序或环境的需要计划此作业的运行时间。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM](../core/managing-bam.md)