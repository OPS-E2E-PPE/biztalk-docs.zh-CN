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
ms.openlocfilehash: 2a7a6ba4459cbe5b9c92c20859b414ec6e694c59
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530541"
---
# <a name="bam-tasks-for-administrators"></a>管理员的 BAM 任务
本主题描述 BAM 管理员在管理 BAM 基础结构时需要执行的典型任务。  
  
## <a name="configuring-bam"></a>配置 BAM  
 进行 BAM 的初始配置使用 BizTalk Server 配置向导。 使用配置向导，管理员可以：  
  
- 启用业务活动监视工具  
  
- 启用 SQL Server Analysis Services 为 BAM 聚合  
  
- 指定的服务器名称和数据库用于 BAM 工具  
  
- 启用 BAM 警报的 SQL Server Notification Services  
  
- 指定用于运行 BAM 通知服务的帐户  
  
- 指定用于发送 BAM 警报的 SMTP 服务器  
  
- 指定用于存储 BAM 警报文件位置  
  
- 指定所在的 SQL server 的 BAM 警报数据库名称  
  
- 指定警报数据库名称的前缀  
  
- 启用 BAM 门户的计算机上  
  
- 指定用于运行 BAM 门户的 Web 服务帐户  
  
- 指定可以访问 BAM 门户的 Windows 组  
  
- 指定 BAM 门户网站上的位置  
  
  有关使用配置向导的详细信息请参阅以下主题：  
  
- [配置 BAM 警报](../install-and-config-guides/configure-biztalk-server.md)  
  
- [配置 BAM 工具](../install-and-config-guides/configure-biztalk-server.md)  
  
- [配置 BAM 门户](../install-and-config-guides/configure-biztalk-server.md)  
  
### <a name="distributed-notification-services---sql-server-2008-r2-only"></a>分布式的 Notification Services-仅限 SQL Server 2008 R2
处理警报和通知时，配置 BAM 以在分布式环境中运行具有性能优势。 时执行此操作时，通知服务的提供程序、 生成器和分发服务器角色上不同的计算机，并且必须在多计算机环境中安装 Notification Services。  

> [!NOTE]
> 从 SQL Server 2012 开始，BizTalk Server 使用 SQL Database Mail。 因此，如果要使用 SQL Server 2012 或更高版本，这不适用于您。 请参阅[BAM 警报](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts)有关的指南。
  
##### <a name="to-configure-distributed-notification-services"></a>若要配置分布式的 Notification Services  
  
1. 安装 SQL Server Notification Services。 
  
   > [!NOTE]
   >  SQL Server 中不包括通知服务。 通过选择安装 BizTalk Server 时安装 SQL Server Notification Services**用于 SQL Notification Services 的 BAM 警报提供程序**下**其他软件**上**组件安装**安装向导页。  
  
2. 若要创建 BAM 通知服务运行 C:\Program Files\Microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol 在分布式环境中的每台计算机上注册的名称 bamalerts-server\<服务器名称\>-服务-serviceusername\<警报用户帐户\>-servicepassword \<passwd\>从命令提示符。  
  
3. 编辑 BAM 基础结构配置文件配置为分布式通知提供服务的每台计算机上。 若要获取配置文件，请使用**bm.exe 获取配置-FileName:\<输出文件\>** 命令。  
  
4. 编辑配置文件以引用分布式 Notification services 环境中的服务器：  
  
   ```  
   <Property Name="GeneratorServerName">PFIDWYUK</Property>  
   <Property Name="ProviderServerName">PFIDWYUK</Property>  
   <Property Name="DistributorServerName">PFIDWYUK</Property>  
   ```  
  
5. 使用 bm.exe 更新-config-FileName:\<配置文件\>更新 BAM 配置。  
  
6. 在分布式环境中重新启动的所有计算机上的 Notification Services。  
  
   在多计算机环境中安装 BAM 的详细信息，请参阅[安装并配置 BAM （业务活动监视） 在多计算机环境中](http://go.microsoft.com/fwlink/p/?LinkID=208597)。  
  
### <a name="moving-the-bam-primary-import-database"></a>移动 BAM 主导入数据库  
 在某些时候，它可能需要移动 BAM 主导入数据库，例如升级硬件或扩展操作。 若要将数据库移动您执行备份和还原操作。 有关此过程的详细信息，请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。  
  
### <a name="working-with-bam-definitions"></a>处理 BAM 定义  
 管理员需要经常处理 BAM 定义。 用于处理 BAM 定义的主要工具是 BAM 管理实用程序。 可以使用此实用程序来执行以下任务：  
  
- 更改活动。 可以使用**部署全部**，**更新全部**，**删除活动**，**和集 actvitywindow** BAM 管理实用程序的命令若要更改已部署的活动。  
  
- 将索引应用于活动表以提高性能。 您使用**创建索引**并**删除索引**命令来修改活动上的索引。  
  
- 在视图上设置安全性。 可以使用**添加帐户**并**删除帐户**命令，授予用户访问视图的权限。  
  
- 配置分布式的活动导航。 您使用**启用引用**并**禁用引用**命令以配置分布式的活动导航。 有关分布式活动导航的详细信息，请参阅[管理分布式导航的远程活动](../core/managing-distributed-navigation-of-remote-activities.md)。  
  
- 审核更改。 可以列出对 BAM 动态基础结构使用的更改**get 更改**命令。  
  
  可通过 BAM 管理实用程序的所有命令的说明，请参阅[BAM 管理实用程序](../core/bam-management-utility.md)。 有关使用 BAM 管理实用程序来处理 BAM 定义的示例，请参阅[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)。  
  
## <a name="configuring-multiple-biztalk-groups-to-reference-a-single-bam-database"></a>配置多个 BizTalk 组，以引用单个 BAM 数据库  
 在配置 BAM 以使用新的或现有的 BizTalk Server 组，可以配置要使用已在由另一个 BizTalk Server 组使用的 BAM 数据库的组。  若要以这种方式配置 BAM，必须执行以下任务：  
  
-   从使用 BizTalk Server 配置向导在现有 BAM 主导入数据库中获取的配置信息。 这包括服务器和数据库名称。 请注意复选框的状态。 请确保获取 BAM 工具和 BAM 警报页的配置信息。  
  
-   BAM 配置为新组，并输入已配置为目标 PIT 的准确信息。 输入新组的配置信息时将使用从现有组收集的所有信息来配置新的组，除了 BAM 警报用户，必须将保留为空。  
  
## <a name="backing-up-and-restoring-bam"></a>Backing Up and Restoring BAM  
 管理员应规划灾难恢复情况。 您应备份 BAM 分析、 跟踪分析、 BAM 星型架构、 BAM 存档和 BAM 主导入数据库以便为在其中你必须将它们还原的情况下提供。  有关备份和还原 BAM 数据库的信息，请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。  
  
## <a name="working-with-renamed-servers"></a>处理重命名服务器  
 当您重命名服务器或服务器之间移动 BAM 基础结构时，必须通过更新该工作簿中的 BAM 定义来更新 Excel 工作簿。  
  
 需要更新工作簿的方案包括：  
  
- 过渡的方案，为新的数据库移动 BAM 基础结构。 若要确保 Excel 工作簿仍正常工作，必须重新部署或迁移，然后重新更新工作簿。  
  
- 重命名运行 BizTalk Server 的计算机方案。 这需要更新 DTS 包和 OLAP 数据源，除了更新工作簿。  
  
  有两种方法可用于更新 Excel 工作簿：  
  
- 从新的服务器上运行以下 BAM 管理器命令：  
  
   **bm.exe 更新 livedataworkbook-名称：\<update.xls 到实时数据工作簿\>**  
  
  > [!NOTE]
  >  您还可以指定新的服务器名称和/或 BAM 主导入数据库名称： **bm.exe 更新 livedataworkbook-名称：\<update.xls 到实时数据工作簿\>[-Server:\<server\>] [-数据库：\<数据库\>]**  
  
- 或者，你可以更新 Excel 工作簿从 Excel 内：  
  
  1.  打开你想要更新工作的簿。  
  
  2.  从 BAM 菜单中，单击**BAM 数据库连接**。  
  
  3.  输入新的服务器名称和 BAM 主导入数据库名称。  
  
## <a name="managing-alerts"></a>管理警报  
 管理员可以管理警报以几种方式：  
  
 可以使用 BAM 管理实用程序来部署和删除警报。 此外可以使用该实用程序来添加和删除订阅，以及启用和禁用警报。 有关使用 BAM 管理实用程序的详细信息，请参阅[BAM 管理实用程序](../core/bam-management-utility.md)，[管理 BAM 安全性](../core/managing-bam-security.md)，并[管理 BAM 定义](../core/managing-bam-definitions.md)。  
  
 您还可以创建和删除通过 BAM 门户的警报。  有关创建使用 BAM 门户的警报的信息，请参阅[BAM 门户中的活动搜索](../core/activity-searches-in-the-bam-portal.md)。  
  
### <a name="cleaning-up-the-alerts-chronicle-table"></a>清理 Alerts Chronicle 表  
 如果配置 BAM 警报，是为创建每个活动视图创建一个 SQL 作业。 该作业将使用以下模板命名为：  
  
 bam_\<视图名称\>_\<活动视图\>_DelAlertHistJob  
  
 此作业清理审核数据为指定的实例警报\<活动视图\>为 Bam_Metadata_AlertChronicle 表中。 如果在特定的活动视图上定义了实例警报，新行将添加到此表每次触发警报。  
  
 可以运行此作业手动清除的表，或者计划运行根据应用程序或环境的需求。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM](../core/managing-bam.md)