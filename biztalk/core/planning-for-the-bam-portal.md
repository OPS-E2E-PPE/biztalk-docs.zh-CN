---
title: 规划 BAM 门户 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a45873711255d6bde4fb6ef5727a2acaea37d1f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395648"
---
# <a name="planning-for-the-bam-portal"></a>规划 BAM 门户
本主题介绍规划业务活动监视 (BAM) 门户部署时应考虑的项。  
  
## <a name="prerequisites"></a>先决条件  
 **系统要求**。 除了 BizTalk Server 的系统要求，必须安装以下软件才能安装 BAM 门户：  
  
-   Internet 信息服务 (IIS)  
  
-   Microsoft Office Excel  
  
-   Microsoft Internet Explorer  
  
-   Microsoft .NET Framework  
  
-   Microsoft XML Core Services (MSXML) 6.0  
  
-   Microsoft 数据访问组件 (MDAC) 2.7  
  
## <a name="configuration-planning"></a>配置规划  
 **从以前版本的 BizTalk Server 迁移**。 从以前版本的 BizTalk Server 进行迁移之后, 你安装 BAM 门户中的现有页可能不再起作用。 若要成功运行 BAM 门户，请参阅 BizTalk Server 升级指南中提供的 BAM 的相关注意事项和准则。  
  
 **数据库**。 规划数据库时，请考虑以下信息：  
  
- 您需要规划数据库来增强性能的索引。 日期和时间列通常需要进度维度的索引。 进度维度没有索引的查询速度较慢，并将对 BAM 主导入表的性能产生负面影响。  
  
- 需要考虑是否应设置 BAM 而无需警报。  
  
  **SQL Server Notification Services**。 SQL Server Notification Services 不支持本地主机或 IP 地址的服务器名称以标识服务器。  您可能遇到这在两个位置：  
  
1. 在配置-如果选择了 BAM 并打开了警报，配置过程将要求提供服务器名称。  
  
2. 如果你尝试修改配置.xml 文件，修改配置.xml 文件-从留下的配置过程以便重复使用。  
  
   **IIS 安装**。 BAM 门户仅在 32 位模式下运行。 如果要在 64 位计算机上安装 IIS，则必须确保在 32 位模式下启用 ASP.NET 2.0。 若要执行此操作，请打开 IIS 管理器中，打开**应用程序池**，选择应用程序池 (BAMAppPool)，然后单击**高级设置**。 在中**启用 32 位应用程序**，选择**True**。 有关详细信息，请参阅 BizTalk Server 升级指南。  
  
## <a name="deployment-planning"></a>部署规划  
 **多计算机部署**。 是在多计算机环境的 BizTalk Server 部署？ 如果不在警报数据库的不同服务器上配置 BAM 门户，您必须增加多服务器环境中的查询服务超时值。 有关其他配置信息，请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)。  
  
- **多区域性部署**。 多区域性环境下是 BizTalk Server 的部署？ 安装 BizTalk Server 时的用户界面 (UI) 是在您安装的版本的语言中，BAM 门户将采取用户为其配置的区域性设置。 若要修改 BAM 门户 web.config 文件以反映正确的区域性设置，请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)。  
  
  **群集部署**。 您要部署在网络负载平衡 (NLB) 群集中？ 请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)有关其他配置信息。  
  
  **SSL**。 要部署使用 SSL 的 IIS 安装上的 BAM 门户？ 请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)主题，了解其他配置信息。  
  
  正在创建视图的用户必须安装 Excel 的 BAM 外接程序。  
  
## <a name="permissions"></a>权限  
 **BAM 管理器**。 Add-account 命令的 BAM 管理器 (bm.exe) 不会向添加的用户自动授予数据库权限。 这是由于运行 BAM 管理器，只需 dbo 权限。 因此，从 BAM 门户访问实时聚合 (Rta) 会导致 SQL Server 失败，除非你属于 SQL Server 内特定的组按下文所述。  
  
 **SQL Server 角色**。 若要授予用户访问数据库，必须是 securityadmin 或 sysadmin 组的成员。  
  
 Securityadmin 或 sysadmin 组的成员可以通过运行 sp_grantdbaccess 和 sp_grantlogin 进行授权授予权限。  
  
 有关 SQL Server 中的角色的详细信息，请参阅"角色中 SQL Server 体系结构"网址[ http://go.microsoft.com/fwlink/?LinkId=56205 ](http://go.microsoft.com/fwlink/?LinkId=56205)。  
  
## <a name="development-planning"></a>开发规划  
 **数据透视表的连接字符串**。 BAM 管理器实用程序不会始终更改实时聚合 (RTA) 透视数据表定义的连接字符串在部署过程。 当 RTA 数据透视表具有预先存在的已经过手动编辑 OLAP 连接字符串和值项的大小写不正确时，将发生这种情况。 例如，在 BAM 定义 XML 文件中有以下行中的关键是 RTARef，而不是预期的 RtaRef:  
  
 **\<PivotTableView CubeRef="POCube" RTARef="POAmountByLocation"\>**  
  
 这将导致通过 OLAP 多维数据集而不是通过 RTA 数据透视表生成数据透视表。  
  
 **字段名称**。 我们建议在开发监视解决方案时选择不同的字段名称的命名约定。 BAM 不需要 BAM 定义的视图部分和聚合的 OLAP 多维数据集之间的唯一名称。  因此，列选择器和活动搜索查询生成器中的字段选择下拉列表可以包含具有相同名称的两个字段。 尝试选择要在结果中包括的正确字段时，这会导致错误。  
  
 对于使用直通管道的 BizTalk Server 端口，它不能从消息有效负载跟踪数据。 直通管道不会评估消息类型转换为架构名称，这会导致所有架构都为空的消息。  
  
- 由于跟踪配置文件映射到端口和架构对，尝试跟踪直通管道结果之外的任何其他所跟踪的消息有效负载数据。  
  
  **数据透视表的名称**:规划和开发用户体验时聚合任务的 BAM 门户中，应在 Excel 中创建的数据透视表的友好名称创建用户。  通过右键单击数据透视表并从上下文菜单中选择表选项，可以自定义名称。  
  
  **日期范围**。 当创建查询和实例警报使用活动搜索页请记住，如果 @@DateFirst SQL 查询中的值与 CultureInfo.CurrentCulture.DateTimeFormat.FirstDayOfWeek 值不匹配，然后在显示的日期范围搜索页将与用于生成聚合的一周边界不匹配。  
  
  例如，如果一周的开始日期在 SQL Server 中设置为星期日，则在日期范围的第二个每周 2005年是从 1/2/2005 通过 2005 年 1 月 8 日，并在 SQL Server 和 OLAP 周 2 所示的聚合基于此日期范围。 但是，如果 BAM 门户指定每周的起始日为星期六，则第二周执行深入探查用户，2005年将在搜索页上看到一个从 1/8/2005 通过 2005 年 1 月 14 日的日期范围。 因此，搜索查询返回的值可能不匹配该数据透视表中显示的聚合值。  
  
  若要获取所需的结果，请调整查询以检索所需的日期范围中的时间范围。  
  
  **分布式导航**。 BAM 门户分布式的导航功能允许用户跨远程边界查看活动关系。 当开发活动，请考虑以下：  
  
- 可能情况下，您将在其中放置到同一视图从单独的 BAM 主导入数据库的相关的活动。 有可能活动可以具有相同名称但位于不同的服务器，例如两个不同的部门都有一个采购订单活动。 BAM 门户用户在门户上我的视图窗格中选择视图时，他们将看到下列出每个任务这两个活动。  
  
- 如果用户在不同的服务器上使用 BAM 门户查看已部署的视图，则需要将对称地启用两个门户体验，每个针对其本地 BAM 主导入数据库中，运行相同引用。  
  
## <a name="see-also"></a>请参阅  
 [自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)