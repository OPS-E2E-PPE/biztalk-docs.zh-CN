---
title: 规划 BAM 门户 |Microsoft 文档
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
ms.openlocfilehash: 85f7291d56d662a8e3a9d46308d6b16ca2a1cafc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008726"
---
# <a name="planning-for-the-bam-portal"></a><span data-ttu-id="74ed9-102">规划 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="74ed9-102">Planning for the BAM Portal</span></span>
<span data-ttu-id="74ed9-103">本主题介绍规划业务活动监视 (BAM) 门户部署时应考虑的事项。</span><span class="sxs-lookup"><span data-stu-id="74ed9-103">This topic describes items that you should consider when planning your Business Activity Monitoring (BAM) portal deployment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="74ed9-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="74ed9-104">Prerequisites</span></span>  
 <span data-ttu-id="74ed9-105">**系统要求**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-105">**System requirements**.</span></span> <span data-ttu-id="74ed9-106">除了 BizTalk Server 的系统要求，你必须安装以下软件才能安装 BAM 门户：</span><span class="sxs-lookup"><span data-stu-id="74ed9-106">In addition to the system requirements for BizTalk Server, you must install the following software in order to install the BAM portal:</span></span>  
  
-   <span data-ttu-id="74ed9-107">Internet 信息服务 (IIS)</span><span class="sxs-lookup"><span data-stu-id="74ed9-107">Internet Information Services (IIS)</span></span>  
  
-   <span data-ttu-id="74ed9-108">Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="74ed9-108">Microsoft Office Excel</span></span>  
  
-   <span data-ttu-id="74ed9-109">Microsoft Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="74ed9-109">Microsoft Internet Explorer</span></span>  
  
-   <span data-ttu-id="74ed9-110">Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="74ed9-110">Microsoft .NET Framework</span></span>  
  
-   <span data-ttu-id="74ed9-111">Microsoft XML Core Services (MSXML) 6.0</span><span class="sxs-lookup"><span data-stu-id="74ed9-111">Microsoft XML Core Services (MSXML) 6.0</span></span>  
  
-   <span data-ttu-id="74ed9-112">Microsoft Data Access Components (MDAC) 2.7</span><span class="sxs-lookup"><span data-stu-id="74ed9-112">Microsoft Data Access Components (MDAC) 2.7</span></span>  
  
## <a name="configuration-planning"></a><span data-ttu-id="74ed9-113">配置规划</span><span class="sxs-lookup"><span data-stu-id="74ed9-113">Configuration planning</span></span>  
 <span data-ttu-id="74ed9-114">**从以前版本的 BizTalk Server 中迁移**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-114">**Migrating from previous versions of BizTalk Server**.</span></span> <span data-ttu-id="74ed9-115">从早期版本的 BizTalk Server 迁移完成后，BAM 门户中安装的现有页可能将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="74ed9-115">After migrating from previous versions of BizTalk Server, your installations of the existing pages in the BAM portal might no longer be functional.</span></span> <span data-ttu-id="74ed9-116">若要使 BAM 门户成功运行，请参阅 BizTalk Server 升级指南中提供的 BAM 相关注意事项和指南。</span><span class="sxs-lookup"><span data-stu-id="74ed9-116">For the BAM portal to successfully function, refer to the considerations and guidelines for BAM provided in the BizTalk Server Upgrade Guide.</span></span>  
  
 <span data-ttu-id="74ed9-117">**数据库**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-117">**Databases**.</span></span> <span data-ttu-id="74ed9-118">规划数据库时，请考虑以下问题：</span><span class="sxs-lookup"><span data-stu-id="74ed9-118">Consider the following information when planning for databases:</span></span>  
  
-   <span data-ttu-id="74ed9-119">为了提高性能，需要规划数据库的索引。</span><span class="sxs-lookup"><span data-stu-id="74ed9-119">You will need to plan for indexes of your databases to enhance performance.</span></span> <span data-ttu-id="74ed9-120">日期和时间列通常需要进度维度的索引。</span><span class="sxs-lookup"><span data-stu-id="74ed9-120">Date and time columns generally require an index on the progress dimension.</span></span> <span data-ttu-id="74ed9-121">对无索引的进度维度的查询将是缓慢的，并且会对 BAM 主导入表的性能造成负面影响。</span><span class="sxs-lookup"><span data-stu-id="74ed9-121">Queries on progress dimensions with no indexes are slow and will negatively impact performance on the BAM Primary Import table.</span></span>  
  
-   <span data-ttu-id="74ed9-122">需要考虑是否应设置无警报的 BAM。</span><span class="sxs-lookup"><span data-stu-id="74ed9-122">You will need to consider whether you should set up BAM without alerts.</span></span>  
  
 <span data-ttu-id="74ed9-123">**SQL Server Notification Services**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-123">**SQL Server Notification Services**.</span></span> <span data-ttu-id="74ed9-124">SQL Server Notification Services 不支持本地主机或用于标识服务器的服务器名称的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="74ed9-124">SQL Server Notification Services does not support local host or IP addresses for server names to identify servers.</span></span>  <span data-ttu-id="74ed9-125">在以下两种情况下，可能会遇到此问题：</span><span class="sxs-lookup"><span data-stu-id="74ed9-125">You may encounter this in two locations:</span></span>  
  
1.  <span data-ttu-id="74ed9-126">在配置过程中 - 如果你选择了 BAM 并打开了警报，配置过程将要求提供服务器名称。</span><span class="sxs-lookup"><span data-stu-id="74ed9-126">During configuration - If you selected BAM and turned on alerts, the configuration process will ask for a server name.</span></span>  
  
2.  <span data-ttu-id="74ed9-127">修改配置 .xml 文件 - 如果你试图修改配置过程中留下的配置 .xml 文件以便重复使用的情况下。</span><span class="sxs-lookup"><span data-stu-id="74ed9-127">Modifying the configuration .xml file - If you attempt to modify the configuration .xml file left over from the configuration process in order to reuse it.</span></span>  
  
 <span data-ttu-id="74ed9-128">**IIS 安装**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-128">**IIS installation**.</span></span> <span data-ttu-id="74ed9-129">BAM 门户仅在 32 位模式下运行。</span><span class="sxs-lookup"><span data-stu-id="74ed9-129">BAM Portal only runs on a 32-bit mode.</span></span> <span data-ttu-id="74ed9-130">如果在 64 位计算机上安装 IIS，则必须确保在 32 位模式下启用 ASP.NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="74ed9-130">If you are installing IIS on a 64-bit machine then you must ensure that ASP.NET 2.0 is enabled on 32-bit mode.</span></span> <span data-ttu-id="74ed9-131">若要执行此操作，打开 IIS 管理器中，打开**应用程序池**，选择应用程序池 (BAMAppPool)，然后单击**高级设置**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-131">To do this, open IIS Manager, open **Application Pool**, select the application pool (BAMAppPool), and then click **Advanced Settings**.</span></span> <span data-ttu-id="74ed9-132">在“启用 32 位应用程序”中，选择 **True**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-132">In **Enable 32-bit applications**, select **True**.</span></span> <span data-ttu-id="74ed9-133">有关详细信息，请参阅 BizTalk Server 升级指南。</span><span class="sxs-lookup"><span data-stu-id="74ed9-133">For more information, see BizTalk Server Upgrade Guide.</span></span>  
  
## <a name="deployment-planning"></a><span data-ttu-id="74ed9-134">部署规划</span><span class="sxs-lookup"><span data-stu-id="74ed9-134">Deployment planning</span></span>  
 <span data-ttu-id="74ed9-135">**多计算机部署**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-135">**Multicomputer deployment**.</span></span> <span data-ttu-id="74ed9-136">你是否要在多计算机环境下部署 BizTalk Server？</span><span class="sxs-lookup"><span data-stu-id="74ed9-136">Is your deployment of BizTalk Server across a multicomputer environment?</span></span> <span data-ttu-id="74ed9-137">如果配置 BAM 门户的服务器不是警报数据库所在的服务器，则必须在多服务器环境下增大查询服务超时值。</span><span class="sxs-lookup"><span data-stu-id="74ed9-137">If your BAM portal is configured on a different server than your alerts database, you must increase the query service timeout value in a multiserver environment.</span></span> <span data-ttu-id="74ed9-138">其他配置信息，请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="74ed9-138">For additional configuration information, see [Customizing the BAM Portal Configuration](../core/customizing-the-bam-portal-configuration.md).</span></span>  
  
-   <span data-ttu-id="74ed9-139">**Multiculture 部署**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-139">**Multiculture deployment**.</span></span> <span data-ttu-id="74ed9-140">你是否要在多区域性环境下部署 BizTalk Server？</span><span class="sxs-lookup"><span data-stu-id="74ed9-140">Is your deployment of BizTalk Server across a multiculture environment?</span></span> <span data-ttu-id="74ed9-141">安装 BizTalk Server 时，用户界面 (UI) 使用你所安装的语言版本，而 BAM 门户将采取用户为其配置的区域性设置。</span><span class="sxs-lookup"><span data-stu-id="74ed9-141">When you install BizTalk Server the user interface (UI) is in the language of the version that you installed and the BAM portal acquires the culture settings of the user who configures it.</span></span> <span data-ttu-id="74ed9-142">若要修改 BAM 门户的 web.config 文件以反映正确的区域性设置，请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="74ed9-142">To modify the BAM portal web.config file to reflect the proper culture setting, see [Customizing the BAM Portal Configuration](../core/customizing-the-bam-portal-configuration.md).</span></span>  
  
 <span data-ttu-id="74ed9-143">**群集部署**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-143">**Cluster deployment**.</span></span> <span data-ttu-id="74ed9-144">你是否要在网络负载平衡 (NLB) 群集中进行部署？</span><span class="sxs-lookup"><span data-stu-id="74ed9-144">Are you deploying in a network load balancing (NLB) cluster?</span></span> <span data-ttu-id="74ed9-145">请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)有关其他配置信息。</span><span class="sxs-lookup"><span data-stu-id="74ed9-145">See [Customizing the BAM Portal Configuration](../core/customizing-the-bam-portal-configuration.md) for additional configuration information.</span></span>  
  
 <span data-ttu-id="74ed9-146">**SSL**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-146">**SSL**.</span></span> <span data-ttu-id="74ed9-147">你是否要在使用 SSL 的 IIS 安装上部署 BAM 门户？</span><span class="sxs-lookup"><span data-stu-id="74ed9-147">Are you deploying the BAM portal on an IIS installation using SSL?</span></span> <span data-ttu-id="74ed9-148">请参阅[自定义 BAM 门户配置](../core/customizing-the-bam-portal-configuration.md)有关其他配置信息的主题。</span><span class="sxs-lookup"><span data-stu-id="74ed9-148">See the [Customizing the BAM Portal Configuration](../core/customizing-the-bam-portal-configuration.md) topic for additional configuration information.</span></span>  
  
 <span data-ttu-id="74ed9-149">创建视图的用户必须安装了用于 Excel 的 BAM 外接程序。</span><span class="sxs-lookup"><span data-stu-id="74ed9-149">Users who are creating views must have the BAM Add-In for Excel installed.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="74ed9-150">Permissions</span><span class="sxs-lookup"><span data-stu-id="74ed9-150">Permissions</span></span>  
 <span data-ttu-id="74ed9-151">**BAM Manager**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-151">**BAM Manager**.</span></span> <span data-ttu-id="74ed9-152">BAM 管理器 (bm.exe) 的 add-account 命令不会自动将数据库权限授予添加的用户。</span><span class="sxs-lookup"><span data-stu-id="74ed9-152">The add-account command of the BAM Manager (bm.exe) does not automatically grant database permissions to the user added.</span></span> <span data-ttu-id="74ed9-153">这是因为运行 BAM 管理器只需 dbo 权限。</span><span class="sxs-lookup"><span data-stu-id="74ed9-153">This is due to the fact that to run the BAM Manager you only need dbo permissions.</span></span> <span data-ttu-id="74ed9-154">因此，从 BAM 门户访问实时聚合 (RTA) 将导致 SQL Server 失败，除非你属于 SQL Server 内特定的组，见下述。</span><span class="sxs-lookup"><span data-stu-id="74ed9-154">As a result, accessing real-time aggregations (RTAs) from the BAM portal causes SQL Server to fail unless you belong to certain groups within SQL Server, as described next.</span></span>  
  
 <span data-ttu-id="74ed9-155">**SQL Server 角色**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-155">**SQL Server roles**.</span></span> <span data-ttu-id="74ed9-156">若要授予用户对数据库的访问权限，你必须是 securityadmin 或 sysadmin 组的成员。</span><span class="sxs-lookup"><span data-stu-id="74ed9-156">To grant a user access to a database, you must be a member of the securityadmin or sysadmin group.</span></span>  
  
 <span data-ttu-id="74ed9-157">securityadmin 或 sysadmin 组的成员可以通过运行 sp_grantdbaccess 和 sp_grantlogin 进行授权。</span><span class="sxs-lookup"><span data-stu-id="74ed9-157">A member of the securityadmin or sysadmin group can grant permissions by running sp_grantdbaccess and sp_grantlogin.</span></span>  
  
 <span data-ttu-id="74ed9-158">有关 SQL Server 中的角色的详细信息，请参阅"角色中 SQL Server 体系结构"在[http://go.microsoft.com/fwlink/?LinkId=56205](http://go.microsoft.com/fwlink/?LinkId=56205)。</span><span class="sxs-lookup"><span data-stu-id="74ed9-158">For more information about roles in SQL Server, see "Roles in the SQL Server Architecture" at [http://go.microsoft.com/fwlink/?LinkId=56205](http://go.microsoft.com/fwlink/?LinkId=56205).</span></span>  
  
## <a name="development-planning"></a><span data-ttu-id="74ed9-159">开发规划</span><span class="sxs-lookup"><span data-stu-id="74ed9-159">Development planning</span></span>  
 <span data-ttu-id="74ed9-160">**数据透视表的连接字符串**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-160">**Connection strings for PivotTables**.</span></span> <span data-ttu-id="74ed9-161">在部署期间，BAM 管理器实用程序不总能更改实时聚合 (RTA) 透视数据表定义的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="74ed9-161">The BAM Manager utility does not always change the connection strings for real-time aggregation (RTA) PivotTable definitions during deployment.</span></span> <span data-ttu-id="74ed9-162">当 RTA 数据透视表具有预先存在的 OLAP 连接字符串（该字符串已经过手动编辑）并且值项的大小写不正确时，就会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="74ed9-162">This occurs when the RTA PivotTable has preexisting OLAP connection strings that have been manually edited and the casing of the value key is incorrect.</span></span> <span data-ttu-id="74ed9-163">例如，在 BAM 定义 XML 文件中有以下行，其中值项为 RTARef，而不是想要的 RtaRef：</span><span class="sxs-lookup"><span data-stu-id="74ed9-163">For example, in this line from the BAM definition XML file the key is RTARef rather than the expected RtaRef:</span></span>  
  
 <span data-ttu-id="74ed9-164">**\<PivotTableView CubeRef ="POCube"RTARef ="POAmountByLocation"\>**</span><span class="sxs-lookup"><span data-stu-id="74ed9-164">**\<PivotTableView CubeRef="POCube" RTARef="POAmountByLocation"\>**</span></span>  
  
 <span data-ttu-id="74ed9-165">这将导致通过 OLAP 多维数据集，而不是通过 RTA 数据透视表来生成数据透视表。</span><span class="sxs-lookup"><span data-stu-id="74ed9-165">This causes the PivotTable to be generated through the OLAP cube rather than through the RTA PivotTable.</span></span>  
  
 <span data-ttu-id="74ed9-166">**字段名称**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-166">**Field names**.</span></span> <span data-ttu-id="74ed9-167">建议你在开发监视解决方案时，为字段名选择不同的命名约定。</span><span class="sxs-lookup"><span data-stu-id="74ed9-167">We recommend that you choose distinct naming conventions for field names when developing a monitoring solution.</span></span> <span data-ttu-id="74ed9-168">BAM 不需要在 BAM 定义的视图部分和聚合的 OLAP 多维数据集之间使用不同的名称。</span><span class="sxs-lookup"><span data-stu-id="74ed9-168">BAM does not require unique names between the view section of the BAM definition and the OLAP cube of the aggregation.</span></span>  <span data-ttu-id="74ed9-169">因此，“活动搜索”查询生成器中的列选择器和字段选择下拉列表可以包含同名的两个字段。</span><span class="sxs-lookup"><span data-stu-id="74ed9-169">As a result, the column chooser and the field selection drop-down list in the Activity Search query builder can contain two fields with the same names.</span></span> <span data-ttu-id="74ed9-170">这会导致在尝试选择要包含在结果中的正确字段时出现错误。</span><span class="sxs-lookup"><span data-stu-id="74ed9-170">This can cause errors when trying to select the correct fields to include in the results.</span></span>  
  
 <span data-ttu-id="74ed9-171">对于使用直通管道的 BizTalk Server 端口，不可能跟踪来自消息负载的数据。</span><span class="sxs-lookup"><span data-stu-id="74ed9-171">For BizTalk Server ports that use pass-through pipelines, it is not possible to track data from the message payload.</span></span> <span data-ttu-id="74ed9-172">直通管道不会将消息类型转换为架构名称，因此所有消息的架构都为空。</span><span class="sxs-lookup"><span data-stu-id="74ed9-172">Pass-through pipelines do not evaluate the message types into the schema names, which results in all the messages having null schemas.</span></span>  
  
-   <span data-ttu-id="74ed9-173">由于跟踪配置文件映射到端口和架构对，因此尝试跟踪直通管道的消息负载数据将跟踪不到任何数据。</span><span class="sxs-lookup"><span data-stu-id="74ed9-173">Since the tracking profile is mapped to a port and schema pair, attempting to track message payload data for a pass-through pipeline results in nothing being tracked.</span></span>  
  
 <span data-ttu-id="74ed9-174">**数据透视表的名称**： 在 Excel 中创建的数据透视表的友好名称的计划和开发用户体验时在聚合任务的 BAM 门户中，你都应创建用户。</span><span class="sxs-lookup"><span data-stu-id="74ed9-174">**Names for PivotTables**: When planning for and developing the user experience in the aggregations task of the BAM portal, you should create user friendly names for the PivotTables that you create in Excel.</span></span>  <span data-ttu-id="74ed9-175">你可以自定义该名称，方法是右键单击数据透视表，然后从上下文菜单中选择“表”选项。</span><span class="sxs-lookup"><span data-stu-id="74ed9-175">You can customize the name by right-clicking on a PivotTable and selecting Table options from the context menu.</span></span>  
  
 <span data-ttu-id="74ed9-176">**日期范围**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-176">**Date ranges**.</span></span> <span data-ttu-id="74ed9-177">创建查询和实例警报使用活动搜索页记住时，如果 @@DateFirst SQL 查询中的值不匹配的 CultureInfo.CurrentCulture.DateTimeFormat.FirstDayOfWeek 值，则日期范围上显示搜索页将与用于生成聚合的一周边界不匹配。</span><span class="sxs-lookup"><span data-stu-id="74ed9-177">When creating queries and instance alerts using the Activity Search page keep in mind that if the @@DateFirst value in your SQL queries does not match the CultureInfo.CurrentCulture.DateTimeFormat.FirstDayOfWeek value, then the date ranges shown on the search page will not match the week boundaries used to generate the aggregations.</span></span>  
  
 <span data-ttu-id="74ed9-178">例如，如果 SQL Server 中的每周起始日设置为星期日，则 2005 年第二周的日期范围为 2005 年 1 月 2 日至 2005 年 1 月 8 日，SQL Server 和 OLAP 中显示的第二周的聚合将基于此日期范围。</span><span class="sxs-lookup"><span data-stu-id="74ed9-178">For example, if the week start day in SQL Server is set to Sunday, then the date range for the second week of 2005 is from 1/2/2005 through 1/8/2005 and aggregations in SQL Server and OLAP shown for week 2 are based on this date range.</span></span> <span data-ttu-id="74ed9-179">但是，如果 BAM 门户指定每周的起始日为星期六，则对 2005 年第二周执行深入探查的用户在搜索页上看到的日期范围将从 2005 年 1 月 8 日至 2005 年 1 月 14 日。</span><span class="sxs-lookup"><span data-stu-id="74ed9-179">However, if the BAM portal specifies a week start date of Saturday, then a user performing drill down on week 2, 2005 will see a date range of from 1/8/2005 through 1/14/2005 on the search page.</span></span> <span data-ttu-id="74ed9-180">因此，搜索查询返回的值会与数据透视表中显示的聚合值不匹配。</span><span class="sxs-lookup"><span data-stu-id="74ed9-180">As a result, the value returned by the search query may not match the aggregate value shown in the PivotTable.</span></span>  
  
 <span data-ttu-id="74ed9-181">若要获得所需的结果，请调整查询中的时间范围，以检索所需的日期范围。</span><span class="sxs-lookup"><span data-stu-id="74ed9-181">To obtain the desired result adjust the time range in the query to retrieve the desired date range.</span></span>  
  
 <span data-ttu-id="74ed9-182">**分布式导航**。</span><span class="sxs-lookup"><span data-stu-id="74ed9-182">**Distributed navigation**.</span></span> <span data-ttu-id="74ed9-183">用户使用 BAM 门户的分布式导航功能可以跨远程边界查看活动关系。</span><span class="sxs-lookup"><span data-stu-id="74ed9-183">The BAM portal distributed navigation feature allows users to see activity relationships across remote boundaries.</span></span> <span data-ttu-id="74ed9-184">开发活动时，请考虑以下情况：</span><span class="sxs-lookup"><span data-stu-id="74ed9-184">When developing activities consider the following:</span></span>  
  
-   <span data-ttu-id="74ed9-185">有时可能要将来自各个 BAM 主导入数据库中的相关活动置于同一视图中。</span><span class="sxs-lookup"><span data-stu-id="74ed9-185">There may be situations in which you will place related activities from separate BAM Primary Import databases into the same view.</span></span> <span data-ttu-id="74ed9-186">存在于不同的服务器上的活动可能会有相同的名称，如两个不同的部门各有一个“采购订单”活动。</span><span class="sxs-lookup"><span data-stu-id="74ed9-186">It is possible that the activities could have the same names but exist on separate servers, such as two different departments, that both have a Purchase Order activity.</span></span> <span data-ttu-id="74ed9-187">BAM 门户用户在门户的“我的视图”窗格中选择“视图”时，将看到每个任务下都列出这两个活动。</span><span class="sxs-lookup"><span data-stu-id="74ed9-187">When the BAM portal user selects View in the My View pane on the portal they will see both activities listed under each task.</span></span>  
  
-   <span data-ttu-id="74ed9-188">如果用户在不同的服务器上使用 BAM 门户查看部署的视图，则需要对称地启用引用，以使两个门户体验（每一个都针对它本地的 BAM 主导入数据库运行）相同。</span><span class="sxs-lookup"><span data-stu-id="74ed9-188">If users are using BAM portals on different servers to view the deployed views, references need to be enabled symmetrically in order for two portal experiences, each running against its local BAM Primary Import database, to be the same.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74ed9-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74ed9-189">See Also</span></span>  
 [<span data-ttu-id="74ed9-190">自定义 BAM 门户配置</span><span class="sxs-lookup"><span data-stu-id="74ed9-190">Customizing the BAM Portal Configuration</span></span>](../core/customizing-the-bam-portal-configuration.md)