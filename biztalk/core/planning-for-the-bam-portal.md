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
# <a name="planning-for-the-bam-portal"></a><span data-ttu-id="d99c8-102">规划 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="d99c8-102">Planning for the BAM Portal</span></span>
<span data-ttu-id="d99c8-103">本主题介绍规划业务活动监视 (BAM) 门户部署时应考虑的项。</span><span class="sxs-lookup"><span data-stu-id="d99c8-103">This topic describes items that you should consider when planning your Business Activity Monitoring (BAM) portal deployment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d99c8-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="d99c8-104">Prerequisites</span></span>  
 <span data-ttu-id="d99c8-105">**系统要求**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-105">**System requirements**.</span></span> <span data-ttu-id="d99c8-106">除了 BizTalk Server 的系统要求，必须安装以下软件才能安装 BAM 门户：</span><span class="sxs-lookup"><span data-stu-id="d99c8-106">In addition to the system requirements for BizTalk Server, you must install the following software in order to install the BAM portal:</span></span>  
  
-   <span data-ttu-id="d99c8-107">Internet 信息服务 (IIS)</span><span class="sxs-lookup"><span data-stu-id="d99c8-107">Internet Information Services (IIS)</span></span>  
  
-   <span data-ttu-id="d99c8-108">Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="d99c8-108">Microsoft Office Excel</span></span>  
  
-   <span data-ttu-id="d99c8-109">Microsoft Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="d99c8-109">Microsoft Internet Explorer</span></span>  
  
-   <span data-ttu-id="d99c8-110">Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d99c8-110">Microsoft .NET Framework</span></span>  
  
-   <span data-ttu-id="d99c8-111">Microsoft XML Core Services (MSXML) 6.0</span><span class="sxs-lookup"><span data-stu-id="d99c8-111">Microsoft XML Core Services (MSXML) 6.0</span></span>  
  
-   <span data-ttu-id="d99c8-112">Microsoft 数据访问组件 (MDAC) 2.7</span><span class="sxs-lookup"><span data-stu-id="d99c8-112">Microsoft Data Access Components (MDAC) 2.7</span></span>  
  
## <a name="configuration-planning"></a><span data-ttu-id="d99c8-113">配置规划</span><span class="sxs-lookup"><span data-stu-id="d99c8-113">Configuration planning</span></span>  
 <span data-ttu-id="d99c8-114">**从以前版本的 BizTalk Server 迁移**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-114">**Migrating from previous versions of BizTalk Server**.</span></span> <span data-ttu-id="d99c8-115">从以前版本的 BizTalk Server 进行迁移之后, 你安装 BAM 门户中的现有页可能不再起作用。</span><span class="sxs-lookup"><span data-stu-id="d99c8-115">After migrating from previous versions of BizTalk Server, your installations of the existing pages in the BAM portal might no longer be functional.</span></span> <span data-ttu-id="d99c8-116">若要成功运行 BAM 门户，请参阅 BizTalk Server 升级指南中提供的 BAM 的相关注意事项和准则。</span><span class="sxs-lookup"><span data-stu-id="d99c8-116">For the BAM portal to successfully function, refer to the considerations and guidelines for BAM provided in the BizTalk Server Upgrade Guide.</span></span>  
  
 <span data-ttu-id="d99c8-117">**数据库**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-117">**Databases**.</span></span> <span data-ttu-id="d99c8-118">规划数据库时，请考虑以下信息：</span><span class="sxs-lookup"><span data-stu-id="d99c8-118">Consider the following information when planning for databases:</span></span>  
  
- <span data-ttu-id="d99c8-119">您需要规划数据库来增强性能的索引。</span><span class="sxs-lookup"><span data-stu-id="d99c8-119">You will need to plan for indexes of your databases to enhance performance.</span></span> <span data-ttu-id="d99c8-120">日期和时间列通常需要进度维度的索引。</span><span class="sxs-lookup"><span data-stu-id="d99c8-120">Date and time columns generally require an index on the progress dimension.</span></span> <span data-ttu-id="d99c8-121">进度维度没有索引的查询速度较慢，并将对 BAM 主导入表的性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="d99c8-121">Queries on progress dimensions with no indexes are slow and will negatively impact performance on the BAM Primary Import table.</span></span>  
  
- <span data-ttu-id="d99c8-122">需要考虑是否应设置 BAM 而无需警报。</span><span class="sxs-lookup"><span data-stu-id="d99c8-122">You will need to consider whether you should set up BAM without alerts.</span></span>  
  
  <span data-ttu-id="d99c8-123">**SQL Server Notification Services**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-123">**SQL Server Notification Services**.</span></span> <span data-ttu-id="d99c8-124">SQL Server Notification Services 不支持本地主机或 IP 地址的服务器名称以标识服务器。</span><span class="sxs-lookup"><span data-stu-id="d99c8-124">SQL Server Notification Services does not support local host or IP addresses for server names to identify servers.</span></span>  <span data-ttu-id="d99c8-125">您可能遇到这在两个位置：</span><span class="sxs-lookup"><span data-stu-id="d99c8-125">You may encounter this in two locations:</span></span>  
  
1. <span data-ttu-id="d99c8-126">在配置-如果选择了 BAM 并打开了警报，配置过程将要求提供服务器名称。</span><span class="sxs-lookup"><span data-stu-id="d99c8-126">During configuration - If you selected BAM and turned on alerts, the configuration process will ask for a server name.</span></span>  
  
2. <span data-ttu-id="d99c8-127">如果你尝试修改配置.xml 文件，修改配置.xml 文件-从留下的配置过程以便重复使用。</span><span class="sxs-lookup"><span data-stu-id="d99c8-127">Modifying the configuration .xml file - If you attempt to modify the configuration .xml file left over from the configuration process in order to reuse it.</span></span>  
  
   <span data-ttu-id="d99c8-128">**IIS 安装**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-128">**IIS installation**.</span></span> <span data-ttu-id="d99c8-129">BAM 门户仅在 32 位模式下运行。</span><span class="sxs-lookup"><span data-stu-id="d99c8-129">BAM Portal only runs on a 32-bit mode.</span></span> <span data-ttu-id="d99c8-130">如果要在 64 位计算机上安装 IIS，则必须确保在 32 位模式下启用 ASP.NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="d99c8-130">If you are installing IIS on a 64-bit machine then you must ensure that ASP.NET 2.0 is enabled on 32-bit mode.</span></span> <span data-ttu-id="d99c8-131">若要执行此操作，请打开 IIS 管理器中，打开**应用程序池**，选择应用程序池 (BAMAppPool)，然后单击**高级设置**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-131">To do this, open IIS Manager, open **Application Pool**, select the application pool (BAMAppPool), and then click **Advanced Settings**.</span></span> <span data-ttu-id="d99c8-132">在中**启用 32 位应用程序**，选择**True**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-132">In **Enable 32-bit applications**, select **True**.</span></span> <span data-ttu-id="d99c8-133">有关详细信息，请参阅 BizTalk Server 升级指南。</span><span class="sxs-lookup"><span data-stu-id="d99c8-133">For more information, see BizTalk Server Upgrade Guide.</span></span>  
  
## <a name="deployment-planning"></a><span data-ttu-id="d99c8-134">部署规划</span><span class="sxs-lookup"><span data-stu-id="d99c8-134">Deployment planning</span></span>  
 <span data-ttu-id="d99c8-135">**多计算机部署**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-135">**Multicomputer deployment**.</span></span> <span data-ttu-id="d99c8-136">是在多计算机环境的 BizTalk Server 部署？</span><span class="sxs-lookup"><span data-stu-id="d99c8-136">Is your deployment of BizTalk Server across a multicomputer environment?</span></span> <span data-ttu-id="d99c8-137">如果不在警报数据库的不同服务器上配置 BAM 门户，您必须增加多服务器环境中的查询服务超时值。</span><span class="sxs-lookup"><span data-stu-id="d99c8-137">If your BAM portal is configured on a different server than your alerts database, you must increase the query service timeout value in a multiserver environment.</span></span> <span data-ttu-id="d99c8-138">有关其他配置信息，请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="d99c8-138">For additional configuration information, see [Customizing the BAM Portal Configuration](../core/customizing-the-bam-portal-configuration.md).</span></span>  
  
- <span data-ttu-id="d99c8-139">**多区域性部署**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-139">**Multiculture deployment**.</span></span> <span data-ttu-id="d99c8-140">多区域性环境下是 BizTalk Server 的部署？</span><span class="sxs-lookup"><span data-stu-id="d99c8-140">Is your deployment of BizTalk Server across a multiculture environment?</span></span> <span data-ttu-id="d99c8-141">安装 BizTalk Server 时的用户界面 (UI) 是在您安装的版本的语言中，BAM 门户将采取用户为其配置的区域性设置。</span><span class="sxs-lookup"><span data-stu-id="d99c8-141">When you install BizTalk Server the user interface (UI) is in the language of the version that you installed and the BAM portal acquires the culture settings of the user who configures it.</span></span> <span data-ttu-id="d99c8-142">若要修改 BAM 门户 web.config 文件以反映正确的区域性设置，请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="d99c8-142">To modify the BAM portal web.config file to reflect the proper culture setting, see [Customizing the BAM Portal Configuration](../core/customizing-the-bam-portal-configuration.md).</span></span>  
  
  <span data-ttu-id="d99c8-143">**群集部署**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-143">**Cluster deployment**.</span></span> <span data-ttu-id="d99c8-144">您要部署在网络负载平衡 (NLB) 群集中？</span><span class="sxs-lookup"><span data-stu-id="d99c8-144">Are you deploying in a network load balancing (NLB) cluster?</span></span> <span data-ttu-id="d99c8-145">请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)有关其他配置信息。</span><span class="sxs-lookup"><span data-stu-id="d99c8-145">See [Customizing the BAM Portal Configuration](../core/customizing-the-bam-portal-configuration.md) for additional configuration information.</span></span>  
  
  <span data-ttu-id="d99c8-146">**SSL**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-146">**SSL**.</span></span> <span data-ttu-id="d99c8-147">要部署使用 SSL 的 IIS 安装上的 BAM 门户？</span><span class="sxs-lookup"><span data-stu-id="d99c8-147">Are you deploying the BAM portal on an IIS installation using SSL?</span></span> <span data-ttu-id="d99c8-148">请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)主题，了解其他配置信息。</span><span class="sxs-lookup"><span data-stu-id="d99c8-148">See the [Customizing the BAM Portal Configuration](../core/customizing-the-bam-portal-configuration.md) topic for additional configuration information.</span></span>  
  
  <span data-ttu-id="d99c8-149">正在创建视图的用户必须安装 Excel 的 BAM 外接程序。</span><span class="sxs-lookup"><span data-stu-id="d99c8-149">Users who are creating views must have the BAM Add-In for Excel installed.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="d99c8-150">权限</span><span class="sxs-lookup"><span data-stu-id="d99c8-150">Permissions</span></span>  
 <span data-ttu-id="d99c8-151">**BAM 管理器**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-151">**BAM Manager**.</span></span> <span data-ttu-id="d99c8-152">Add-account 命令的 BAM 管理器 (bm.exe) 不会向添加的用户自动授予数据库权限。</span><span class="sxs-lookup"><span data-stu-id="d99c8-152">The add-account command of the BAM Manager (bm.exe) does not automatically grant database permissions to the user added.</span></span> <span data-ttu-id="d99c8-153">这是由于运行 BAM 管理器，只需 dbo 权限。</span><span class="sxs-lookup"><span data-stu-id="d99c8-153">This is due to the fact that to run the BAM Manager you only need dbo permissions.</span></span> <span data-ttu-id="d99c8-154">因此，从 BAM 门户访问实时聚合 (Rta) 会导致 SQL Server 失败，除非你属于 SQL Server 内特定的组按下文所述。</span><span class="sxs-lookup"><span data-stu-id="d99c8-154">As a result, accessing real-time aggregations (RTAs) from the BAM portal causes SQL Server to fail unless you belong to certain groups within SQL Server, as described next.</span></span>  
  
 <span data-ttu-id="d99c8-155">**SQL Server 角色**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-155">**SQL Server roles**.</span></span> <span data-ttu-id="d99c8-156">若要授予用户访问数据库，必须是 securityadmin 或 sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="d99c8-156">To grant a user access to a database, you must be a member of the securityadmin or sysadmin group.</span></span>  
  
 <span data-ttu-id="d99c8-157">Securityadmin 或 sysadmin 组的成员可以通过运行 sp_grantdbaccess 和 sp_grantlogin 进行授权授予权限。</span><span class="sxs-lookup"><span data-stu-id="d99c8-157">A member of the securityadmin or sysadmin group can grant permissions by running sp_grantdbaccess and sp_grantlogin.</span></span>  
  
 <span data-ttu-id="d99c8-158">有关 SQL Server 中的角色的详细信息，请参阅"角色中 SQL Server 体系结构"网址[ http://go.microsoft.com/fwlink/?LinkId=56205 ](http://go.microsoft.com/fwlink/?LinkId=56205)。</span><span class="sxs-lookup"><span data-stu-id="d99c8-158">For more information about roles in SQL Server, see "Roles in the SQL Server Architecture" at [http://go.microsoft.com/fwlink/?LinkId=56205](http://go.microsoft.com/fwlink/?LinkId=56205).</span></span>  
  
## <a name="development-planning"></a><span data-ttu-id="d99c8-159">开发规划</span><span class="sxs-lookup"><span data-stu-id="d99c8-159">Development planning</span></span>  
 <span data-ttu-id="d99c8-160">**数据透视表的连接字符串**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-160">**Connection strings for PivotTables**.</span></span> <span data-ttu-id="d99c8-161">BAM 管理器实用程序不会始终更改实时聚合 (RTA) 透视数据表定义的连接字符串在部署过程。</span><span class="sxs-lookup"><span data-stu-id="d99c8-161">The BAM Manager utility does not always change the connection strings for real-time aggregation (RTA) PivotTable definitions during deployment.</span></span> <span data-ttu-id="d99c8-162">当 RTA 数据透视表具有预先存在的已经过手动编辑 OLAP 连接字符串和值项的大小写不正确时，将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="d99c8-162">This occurs when the RTA PivotTable has preexisting OLAP connection strings that have been manually edited and the casing of the value key is incorrect.</span></span> <span data-ttu-id="d99c8-163">例如，在 BAM 定义 XML 文件中有以下行中的关键是 RTARef，而不是预期的 RtaRef:</span><span class="sxs-lookup"><span data-stu-id="d99c8-163">For example, in this line from the BAM definition XML file the key is RTARef rather than the expected RtaRef:</span></span>  
  
 <span data-ttu-id="d99c8-164">**\<PivotTableView CubeRef="POCube" RTARef="POAmountByLocation"\>**</span><span class="sxs-lookup"><span data-stu-id="d99c8-164">**\<PivotTableView CubeRef="POCube" RTARef="POAmountByLocation"\>**</span></span>  
  
 <span data-ttu-id="d99c8-165">这将导致通过 OLAP 多维数据集而不是通过 RTA 数据透视表生成数据透视表。</span><span class="sxs-lookup"><span data-stu-id="d99c8-165">This causes the PivotTable to be generated through the OLAP cube rather than through the RTA PivotTable.</span></span>  
  
 <span data-ttu-id="d99c8-166">**字段名称**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-166">**Field names**.</span></span> <span data-ttu-id="d99c8-167">我们建议在开发监视解决方案时选择不同的字段名称的命名约定。</span><span class="sxs-lookup"><span data-stu-id="d99c8-167">We recommend that you choose distinct naming conventions for field names when developing a monitoring solution.</span></span> <span data-ttu-id="d99c8-168">BAM 不需要 BAM 定义的视图部分和聚合的 OLAP 多维数据集之间的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="d99c8-168">BAM does not require unique names between the view section of the BAM definition and the OLAP cube of the aggregation.</span></span>  <span data-ttu-id="d99c8-169">因此，列选择器和活动搜索查询生成器中的字段选择下拉列表可以包含具有相同名称的两个字段。</span><span class="sxs-lookup"><span data-stu-id="d99c8-169">As a result, the column chooser and the field selection drop-down list in the Activity Search query builder can contain two fields with the same names.</span></span> <span data-ttu-id="d99c8-170">尝试选择要在结果中包括的正确字段时，这会导致错误。</span><span class="sxs-lookup"><span data-stu-id="d99c8-170">This can cause errors when trying to select the correct fields to include in the results.</span></span>  
  
 <span data-ttu-id="d99c8-171">对于使用直通管道的 BizTalk Server 端口，它不能从消息有效负载跟踪数据。</span><span class="sxs-lookup"><span data-stu-id="d99c8-171">For BizTalk Server ports that use pass-through pipelines, it is not possible to track data from the message payload.</span></span> <span data-ttu-id="d99c8-172">直通管道不会评估消息类型转换为架构名称，这会导致所有架构都为空的消息。</span><span class="sxs-lookup"><span data-stu-id="d99c8-172">Pass-through pipelines do not evaluate the message types into the schema names, which results in all the messages having null schemas.</span></span>  
  
- <span data-ttu-id="d99c8-173">由于跟踪配置文件映射到端口和架构对，尝试跟踪直通管道结果之外的任何其他所跟踪的消息有效负载数据。</span><span class="sxs-lookup"><span data-stu-id="d99c8-173">Since the tracking profile is mapped to a port and schema pair, attempting to track message payload data for a pass-through pipeline results in nothing being tracked.</span></span>  
  
  <span data-ttu-id="d99c8-174">**数据透视表的名称**:规划和开发用户体验时聚合任务的 BAM 门户中，应在 Excel 中创建的数据透视表的友好名称创建用户。</span><span class="sxs-lookup"><span data-stu-id="d99c8-174">**Names for PivotTables**: When planning for and developing the user experience in the aggregations task of the BAM portal, you should create user friendly names for the PivotTables that you create in Excel.</span></span>  <span data-ttu-id="d99c8-175">通过右键单击数据透视表并从上下文菜单中选择表选项，可以自定义名称。</span><span class="sxs-lookup"><span data-stu-id="d99c8-175">You can customize the name by right-clicking on a PivotTable and selecting Table options from the context menu.</span></span>  
  
  <span data-ttu-id="d99c8-176">**日期范围**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-176">**Date ranges**.</span></span> <span data-ttu-id="d99c8-177">当创建查询和实例警报使用活动搜索页请记住，如果 @@DateFirst SQL 查询中的值与 CultureInfo.CurrentCulture.DateTimeFormat.FirstDayOfWeek 值不匹配，然后在显示的日期范围搜索页将与用于生成聚合的一周边界不匹配。</span><span class="sxs-lookup"><span data-stu-id="d99c8-177">When creating queries and instance alerts using the Activity Search page keep in mind that if the @@DateFirst value in your SQL queries does not match the CultureInfo.CurrentCulture.DateTimeFormat.FirstDayOfWeek value, then the date ranges shown on the search page will not match the week boundaries used to generate the aggregations.</span></span>  
  
  <span data-ttu-id="d99c8-178">例如，如果一周的开始日期在 SQL Server 中设置为星期日，则在日期范围的第二个每周 2005年是从 1/2/2005 通过 2005 年 1 月 8 日，并在 SQL Server 和 OLAP 周 2 所示的聚合基于此日期范围。</span><span class="sxs-lookup"><span data-stu-id="d99c8-178">For example, if the week start day in SQL Server is set to Sunday, then the date range for the second week of 2005 is from 1/2/2005 through 1/8/2005 and aggregations in SQL Server and OLAP shown for week 2 are based on this date range.</span></span> <span data-ttu-id="d99c8-179">但是，如果 BAM 门户指定每周的起始日为星期六，则第二周执行深入探查用户，2005年将在搜索页上看到一个从 1/8/2005 通过 2005 年 1 月 14 日的日期范围。</span><span class="sxs-lookup"><span data-stu-id="d99c8-179">However, if the BAM portal specifies a week start date of Saturday, then a user performing drill down on week 2, 2005 will see a date range of from 1/8/2005 through 1/14/2005 on the search page.</span></span> <span data-ttu-id="d99c8-180">因此，搜索查询返回的值可能不匹配该数据透视表中显示的聚合值。</span><span class="sxs-lookup"><span data-stu-id="d99c8-180">As a result, the value returned by the search query may not match the aggregate value shown in the PivotTable.</span></span>  
  
  <span data-ttu-id="d99c8-181">若要获取所需的结果，请调整查询以检索所需的日期范围中的时间范围。</span><span class="sxs-lookup"><span data-stu-id="d99c8-181">To obtain the desired result adjust the time range in the query to retrieve the desired date range.</span></span>  
  
  <span data-ttu-id="d99c8-182">**分布式导航**。</span><span class="sxs-lookup"><span data-stu-id="d99c8-182">**Distributed navigation**.</span></span> <span data-ttu-id="d99c8-183">BAM 门户分布式的导航功能允许用户跨远程边界查看活动关系。</span><span class="sxs-lookup"><span data-stu-id="d99c8-183">The BAM portal distributed navigation feature allows users to see activity relationships across remote boundaries.</span></span> <span data-ttu-id="d99c8-184">当开发活动，请考虑以下：</span><span class="sxs-lookup"><span data-stu-id="d99c8-184">When developing activities consider the following:</span></span>  
  
- <span data-ttu-id="d99c8-185">可能情况下，您将在其中放置到同一视图从单独的 BAM 主导入数据库的相关的活动。</span><span class="sxs-lookup"><span data-stu-id="d99c8-185">There may be situations in which you will place related activities from separate BAM Primary Import databases into the same view.</span></span> <span data-ttu-id="d99c8-186">有可能活动可以具有相同名称但位于不同的服务器，例如两个不同的部门都有一个采购订单活动。</span><span class="sxs-lookup"><span data-stu-id="d99c8-186">It is possible that the activities could have the same names but exist on separate servers, such as two different departments, that both have a Purchase Order activity.</span></span> <span data-ttu-id="d99c8-187">BAM 门户用户在门户上我的视图窗格中选择视图时，他们将看到下列出每个任务这两个活动。</span><span class="sxs-lookup"><span data-stu-id="d99c8-187">When the BAM portal user selects View in the My View pane on the portal they will see both activities listed under each task.</span></span>  
  
- <span data-ttu-id="d99c8-188">如果用户在不同的服务器上使用 BAM 门户查看已部署的视图，则需要将对称地启用两个门户体验，每个针对其本地 BAM 主导入数据库中，运行相同引用。</span><span class="sxs-lookup"><span data-stu-id="d99c8-188">If users are using BAM portals on different servers to view the deployed views, references need to be enabled symmetrically in order for two portal experiences, each running against its local BAM Primary Import database, to be the same.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d99c8-189">请参阅</span><span class="sxs-lookup"><span data-stu-id="d99c8-189">See Also</span></span>  
 [<span data-ttu-id="d99c8-190">自定义 BAM 门户配置</span><span class="sxs-lookup"><span data-stu-id="d99c8-190">Customizing the BAM Portal Configuration</span></span>](../core/customizing-the-bam-portal-configuration.md)