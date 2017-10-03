---
title: "规划 BAM 门户 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM portal, security
- BAM portal, prerequisites
- BAM portal, deploying
- developing, BAM portal
- planning, BAM portal
- BAM portal, planning
- BAM portal, developing
- deploying, BAM portal
- security, BAM portal
ms.assetid: 8a8bd331-c5a8-4d8b-9e93-96e6cd581a1d
caps.latest.revision: "36"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54cc5bb9bd123f68fbeb0013423c3f3cc07cd50a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-the-bam-portal"></a>规划 BAM 门户
本主题介绍规划业务活动监视 (BAM) 门户部署时应考虑的事项。  
  
## <a name="prerequisites"></a>先决条件  
 **系统要求**。 除了的系统要求[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，你必须安装以下软件才能安装 BAM 门户：  
  
-   Internet 信息服务 (IIS)  
  
-   Microsoft Office Excel  
  
-   Microsoft Internet Explorer  
  
-   Microsoft .NET Framework  
  
-   Microsoft XML Core Services (MSXML) 6.0  
  
-   Microsoft Data Access Components (MDAC) 2.7  
  
## <a name="configuration-planning"></a>配置规划  
 **从以前版本的 BizTalk Server 中迁移**。 从早期版本的 BizTalk Server 迁移完成后，BAM 门户中安装的现有页可能将不再起作用。 若要使 BAM 门户成功运行，请参阅 BizTalk Server 升级指南中提供的 BAM 相关注意事项和指南。  
  
 **数据库**。 规划数据库时，请考虑以下问题：  
  
-   为了提高性能，需要规划数据库的索引。 日期和时间列通常需要进度维度的索引。 对无索引的进度维度的查询将是缓慢的，并且会对 BAM 主导入表的性能造成负面影响。  
  
-   需要考虑是否应设置无警报的 BAM。  
  
 **SQL Server Notification Services**。 SQL Server Notification Services 不支持本地主机或用于标识服务器的服务器名称的 IP 地址。  在以下两种情况下，可能会遇到此问题：  
  
1.  在配置过程中 - 如果你选择了 BAM 并打开了警报，配置过程将要求提供服务器名称。  
  
2.  修改配置 .xml 文件 - 如果你试图修改配置过程中留下的配置 .xml 文件以便重复使用的情况下。  
  
 **IIS 安装**。 BAM 门户仅在 32 位模式下运行。 如果在 64 位计算机上安装 IIS，则必须确保在 32 位模式下启用 ASP.NET 2.0。 若要执行此操作，打开 IIS 管理器中，打开**应用程序池**，选择应用程序池 (BAMAppPool)，然后单击**高级设置**。 在“启用 32 位应用程序”中，选择 **True**。 有关详细信息，请参阅 BizTalk Server 升级指南。  
  
## <a name="deployment-planning"></a>部署规划  
 **多计算机部署**。 你是否要在多计算机环境下部署 BizTalk Server？ 如果配置 BAM 门户的服务器不是警报数据库所在的服务器，则必须在多服务器环境下增大查询服务超时值。 其他配置信息，请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)。  
  
-   **Multiculture 部署**。 你是否要在多区域性环境下部署 BizTalk Server？ 安装 BizTalk Server 时，用户界面 (UI) 使用你所安装的语言版本，而 BAM 门户将采取用户为其配置的区域性设置。 若要修改 BAM 门户的 web.config 文件以反映正确的区域性设置，请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)。  
  
 **群集部署**。 你是否要在网络负载平衡 (NLB) 群集中进行部署？ 请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)有关其他配置信息。  
  
 **SSL**。 你是否要在使用 SSL 的 IIS 安装上部署 BAM 门户？ 请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)有关其他配置信息的主题。  
  
 创建视图的用户必须安装了用于 Excel 的 BAM 外接程序。  
  
## <a name="permissions"></a>Permissions  
 **BAM Manager**。 BAM 管理器 (bm.exe) 的 add-account 命令不会自动将数据库权限授予添加的用户。 这是因为运行 BAM 管理器只需 dbo 权限。 因此，从 BAM 门户访问实时聚合 (RTA) 将导致 SQL Server 失败，除非你属于 SQL Server 内特定的组，见下述。  
  
 **SQL Server 角色**。 若要授予用户对数据库的访问权限，你必须是 securityadmin 或 sysadmin 组的成员。  
  
 securityadmin 或 sysadmin 组的成员可以通过运行 sp_grantdbaccess 和 sp_grantlogin 进行授权。  
  
 有关 SQL Server 中的角色的详细信息，请参阅"角色中 SQL Server 体系结构"在[http://go.microsoft.com/fwlink/?LinkId=56205](http://go.microsoft.com/fwlink/?LinkId=56205)。  
  
## <a name="development-planning"></a>开发规划  
 **数据透视表的连接字符串**。 在部署期间，BAM 管理器实用程序不总能更改实时聚合 (RTA) 透视数据表定义的连接字符串。 当 RTA 数据透视表具有预先存在的 OLAP 连接字符串（该字符串已经过手动编辑）并且值项的大小写不正确时，就会发生这种情况。 例如，在 BAM 定义 XML 文件中有以下行，其中值项为 RTARef，而不是想要的 RtaRef：  
  
 **\<PivotTableView CubeRef ="POCube"RTARef ="POAmountByLocation">**  
  
 这将导致通过 OLAP 多维数据集，而不是通过 RTA 数据透视表来生成数据透视表。  
  
 **字段名称**。 建议你在开发监视解决方案时，为字段名选择不同的命名约定。 BAM 不需要在 BAM 定义的视图部分和聚合的 OLAP 多维数据集之间使用不同的名称。  因此，“活动搜索”查询生成器中的列选择器和字段选择下拉列表可以包含同名的两个字段。 这会导致在尝试选择要包含在结果中的正确字段时出现错误。  
  
 对于使用直通管道的 BizTalk Server 端口，不可能跟踪来自消息负载的数据。 直通管道不会将消息类型转换为架构名称，因此所有消息的架构都为空。  
  
-   由于跟踪配置文件映射到端口和架构对，因此尝试跟踪直通管道的消息负载数据将跟踪不到任何数据。  
  
 **数据透视表的名称**： 在 Excel 中创建的数据透视表的友好名称的计划和开发用户体验时在聚合任务的 BAM 门户中，你都应创建用户。  你可以自定义该名称，方法是右键单击数据透视表，然后从上下文菜单中选择“表”选项。  
  
 **日期范围**。 创建查询和实例警报使用活动搜索页记住时，如果 @@DateFirst SQL 查询中的值不匹配的 CultureInfo.CurrentCulture.DateTimeFormat.FirstDayOfWeek 值，则日期范围上显示搜索页将与用于生成聚合的一周边界不匹配。  
  
 例如，如果 SQL Server 中的每周起始日设置为星期日，则 2005 年第二周的日期范围为 2005 年 1 月 2 日至 2005 年 1 月 8 日，SQL Server 和 OLAP 中显示的第二周的聚合将基于此日期范围。 但是，如果 BAM 门户指定每周的起始日为星期六，则对 2005 年第二周执行深入探查的用户在搜索页上看到的日期范围将从 2005 年 1 月 8 日至 2005 年 1 月 14 日。 因此，搜索查询返回的值会与数据透视表中显示的聚合值不匹配。  
  
 若要获得所需的结果，请调整查询中的时间范围，以检索所需的日期范围。  
  
 **分布式导航**。 用户使用 BAM 门户的分布式导航功能可以跨远程边界查看活动关系。 开发活动时，请考虑以下情况：  
  
-   有时可能要将来自各个 BAM 主导入数据库中的相关活动置于同一视图中。 存在于不同的服务器上的活动可能会有相同的名称，如两个不同的部门各有一个“采购订单”活动。 BAM 门户用户在门户的“我的视图”窗格中选择“视图”时，将看到每个任务下都列出这两个活动。  
  
-   如果用户在不同的服务器上使用 BAM 门户查看部署的视图，则需要对称地启用引用，以使两个门户体验（每一个都针对它本地的 BAM 主导入数据库运行）相同。  
  
## <a name="see-also"></a>另请参阅  
 [自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)